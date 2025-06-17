# 📘 Namenskonventionen für Omnixys Cloud

## 📦 Helm-Charts

- Verzeichnis: `charts/omnixys-<service>/`
- Chart-Name (`Chart.yaml > name`): `omnixys-<service>`
- Namespace: `omnixys`

Beispiel:

```yaml
name: omnixys-person
```  → `charts/omnixys-person/`

---

## 🐳 Docker Images (GHCR)

- Registry: `ghcr.io/omnixys/<service>:<tag>`
- Keine `-service` Endung im Image-Namen

Beispiel:
```yaml
image: ghcr.io/omnixys/person:latest
```

---

## 🏷️ GitHub Labels

- `type:<task|feature|bug>` → Aufgabenart
- `service:<name>` → betroffener Service
- `kubernetes`, `helm`, `ci`, `docker`, ... → technische Kategorie
- `priority:<low|medium|high>` → Dringlichkeit

Beispiel:

```yaml
labels: ["type:task", "service:person", "kubernetes", "helm", "priority:high"]
```

---

## ⚙️ CI/CD Workflows

- Datei: `.github/workflows/deploy-<service>.yml`
- Trigger: Änderungen im Chart-Pfad (`charts/omnixys-<service>/**`)
- Image-Tag-Ziel: `ghcr.io/omnixys/<service>:latest`

Beispiel:

```yaml
on:
  push:
    paths:
      - charts/omnixys-person/**
```

---

Diese Konventionen sichern Konsistenz über alle Services im Omnixys-Projekt. Änderungen daran sollten im Team abgestimmt dokumentiert werden.
