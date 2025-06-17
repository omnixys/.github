# 🧾 Omnixys Branding-Kit

## 🖼️ Logo

* Logo-Datei: `omnixys-logo.png` (Vollversion)
* Logo-Datei: `omnixys-symbol.png` (Icon-only)

---

## 🎨 Farbpalette

| Zweck               | Farbe        | HEX       |
| ------------------- | ------------ | --------- |
| Primärfarbe         | Elegant Lila | `#6A4BBC` |
| Hover / Akzentfarbe | Dunkles Lila | `#4E3792` |
| Hintergrundfarbe    | Hellgrau     | `#F8F8FC` |
| Sekundärtext        | Dunkelblau   | `#312E81` |
| Weißraum / Karten   | Weiß         | `#FFFFFF` |
| Status: Aktiv       | Grün         | `#A3E635` |
| Status: Inaktiv     | Rot          | `#F87171` |

---

## 🌓 Farbmodus (Light / Dark Theme)

### 🌞 Light Mode
- `background.default`: `#F8F8FC`
- `background.paper`: `#FFFFFF`
- `text.primary`: `#312E81`
- `text.secondary`: `#6B7280`
- `primary.main`: `#6A4BBC`
- `secondary.main`: `#4E3792`

### 🌙 Dark Mode
- `background.default`: `#121212`
- `background.paper`: `#1E1E1E`
- `text.primary`: `#EDEDED`
- `text.secondary`: `#BFBFC7`
- `primary.main`: `#6A4BBC`
- `secondary.main`: `#4E3792`

> Alle Komponenten reagieren dynamisch über `theme.palette.mode`

---

## 🔤 Typografie

| Verwendung      | Schriftart         | Stil               |
| --------------- | ------------------ | ------------------ |
| Logo / Headline | **Poppins Bold**   | Modern, Tech       |
| Text (Web)      | **Inter Regular**  | Klar & lesbar      |
| Akzent/Buttons  | **Poppins Medium** | Elegant, auffällig |

---

## ✨ Slogan

> **Omnixys – The Fabric of Modular Innovation**

Alternativen:

* *Modular Thinking. Infinite Possibilities.*
* *Connect Everything. Empower Everyone.*

---

## 🌐 Domains (verfügbar)

* [x] `omnixys.com`
* [x] `omnixys.io`
* [x] `omnixys.tech`

**→ Empfehlung:** .com für Hauptseite, .io für API, .tech für Branding.

---

## 📦 Projekt- / Produktnamen

| Name             | Verwendung                          |
| ---------------- | ----------------------------------- |
| **OmnixysOS**    | Microservice-Plattform              |
| **OmnixysGrid**  | Service-Netzwerk                    |
| **OmnixysFlow**  | Event-Streaming (Kafka, Tracing)    |
| **OmnixysCloud** | Cloud-native Umgebung (Deployments) |
| **OmnixysOne**   | UI-/Admin-Frontend-Plattform        |

---

## 🔤 Namenskonvention

| Schreibweise       | Kontext                                           |
| ------------------ | ------------------------------------------------- |
| **OmnixysSphere**  | Verwendung in Code, Repositories, Dokumentationen |
| **Omnixys-Sphere** | Branding, Marketing, Logos, externe Kommunikation |

**Regel:** Für technische Artefakte und interne Dokumentation wird `OmnixysSphere` (ohne Bindestrich) verwendet. Für Präsentationen, Webseiten und visuelles Design ist `Omnixys-Sphere` (mit Bindestrich) zulässig.

---

## 💻 Web-Technologie (Empfehlung)

* **Frontend:** Next.js mit App Router, TypeScript, MUI
* **Backend:** NestJS / Spring Boot / FastAPI je nach Microservice
* **CI/CD:** GitHub Actions + Docker (pro Service-Repo)
* **Observability:** Tempo, Grafana, Loki, Prometheus
* **Security:** Keycloak (AuthN + AuthZ)

---

## 🗂 Repository-Struktur (Microservices = eigene Repos)

Beispielhafte Repos:

* `omnixys-os`
* `omnixys-grid-service`
* `omnixys-flow-service`
* `omnixys-cloud-deployer`
* `omnixys-ui` (Frontend)
* `omnixys-gateway` (API Gateway)
* `omnixys-logger` (Kafka/LoggerPlus)

---

## 🚀 Nächste Schritte

1. Domain registrieren
2. GitHub-Repositories erstellen (pro Service)
3. CI/CD Setup mit GitHub Actions in jedem Repo
4. Landingpage mit Next.js aufsetzen
5. Microservices iterativ implementieren