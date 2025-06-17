# Best Practices für Kubernetes Helm Charts (Omnixys – Stand 2025)

Dieses Dokument beschreibt empfohlene Best Practices für die Konfiguration von Kubernetes-Deployments mittels Helm Charts, speziell für produktionsreife Services wie den `omnixys-person-service`.

---

## 🔐 1. Trennung von Konfiguration & Secrets

| Typ            | Ort                          | Empfehlung                              |
|----------------|------------------------------|------------------------------------------|
| Konfiguration  | `ConfigMap`, `values.yaml`   | Für nicht-sensitive Parameter wie `ACTIVE_PROFILE`, `SERVER_PORT` |
| Secrets        | `Secret`, Helm Values via Sealed Secrets oder External Secrets | Niemals in Klartext im `values.yaml` speichern |

---

## ⚙️ 2. Ressourcen-Requests & Limits

```yaml
resources:
  requests:
    cpu: "200m"
    memory: "256Mi"
  limits:
    cpu: "500m"
    memory: "512Mi"
```

→ Definiert in `deployment.yaml` unter `resources:`. Wichtig für Scheduling & Stabilität.

---

## 🌡 3. Liveness & Readiness Probes

```yaml
livenessProbe:
  httpGet:
    path: /actuator/health/liveness
    port: 7001
  initialDelaySeconds: 15
  periodSeconds: 20

readinessProbe:
  httpGet:
    path: /actuator/health/readiness
    port: 7001
  initialDelaySeconds: 5
  periodSeconds: 10
```

→ Nutze Spring Boot Actuator oder explizite Endpoints für Monitoring.

---

## 🐳 4. Image-Tagging & Pull-Policy

- Verwende **niemals `latest`**
- Beispiel: `omnixys/person:2025.6.1`
- `imagePullPolicy: IfNotPresent` (Dev), `Always` (CI/CD)

---

## 🌐 5. Ingress-Konfiguration

- Verwende `ingressClassName: nginx`
- TLS aktivieren via cert-manager:

```yaml
annotations:
  cert-manager.io/cluster-issuer: letsencrypt-prod
tls:
  - hosts:
      - person.omnixys.dev
    secretName: omnixys-person-tls
```

---

## 📦 6. Namenskonventionen & Labels

```yaml
metadata:
  labels:
    app.kubernetes.io/name: {{ include "omnixys-person.name" . }}
    app.kubernetes.io/instance: {{ .Release.Name }}
```

→ Einheitliche Labels für Monitoring, Logging & Tracing.

---

## 📂 7. Struktur für Helm Chart

```bash
omnixys-person/
├── Chart.yaml
├── values.yaml
├── templates/
│   ├── deployment.yaml
│   ├── service.yaml
│   ├── configmap.yaml
│   ├── secret.yaml
│   ├── ingress.yaml
│   ├── _helpers.tpl
│   └── NOTES.txt
```

---

## 📊 8. Observability (2025-Stack)

- **Logging**: Loki (via Fluent Bit)
- **Metrics**: Prometheus
- **Tracing**: OpenTelemetry → Tempo

→ In alle Deployments integrieren via Sidecar oder Instrumentation Libs.

---

## ✅ 9. Helm Release Management

- Deployment pro Namespace (`dev`, `test`, `prod`)
- CI/CD Integration mit `helm lint`, `helm upgrade --install`
- Beispiel:

```bash
helm upgrade --install person ./omnixys-person   --namespace omnixys-prod   --set image.tag=2025.6.1
```

---

## 📉 10. Deployment Policies

```yaml
strategy:
  type: RollingUpdate
  rollingUpdate:
    maxSurge: 1
    maxUnavailable: 0
```

- `terminationGracePeriodSeconds: 30`
- `revisionHistoryLimit: 2`

---

## 🧪 11. Lokales Testen

```bash
helm template . --debug
helm lint
kubectl create namespace omnixys-dev
helm install person . -n omnixys-dev
```

---

## 🧼 12. Secrets in CI/CD

- Nutze GitHub Secrets (`DOCKER_PASSWORD`, `KC_CLIENT_SECRET` etc.)
- Niemals Secrets in Git speichern – stattdessen verschlüsseln (z. B. `sealed-secrets`)

---

3. README-Hinweis für Entwickler

Dokumentiere die Secret-Erzeugung (Base64):

# Beispiel zur Erzeugung
echo -n "dein-wert" | base64
und die Dekodierung:

# Beispiel zur Prüfung
echo "YmFzZTY0LWVuY29kZWQ=" | base64 -d


Stand: **2025-06-02** · Maintainer: `Omnixys Platform Team`