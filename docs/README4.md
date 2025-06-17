# 🧩 Omnixys – The Fabric of Modular Innovation

![CI](https://github.com/omnixys/omnixys-ui/actions/workflows/ci.yml/badge.svg)
![CD](https://github.com/omnixys/omnixys-ui/actions/workflows/cd.yml/badge.svg)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](./LICENSE.md)
[![Security Policy](https://img.shields.io/badge/security-policy-blue)](./SECURITY.md)
[![Made with ❤ by Omnixys](https://img.shields.io/badge/made%20with-%E2%9D%A4-ff69b4)](https://omnixys.com)

> Omnixys ist eine Open-Source-Plattform für modulare Microservices – API-first, sicher, skalierbar. Entwickelt für moderne Unternehmen, die digitale Services effizient entwickeln, integrieren und überwachen möchten – powered by GraphQL, Keycloak und Observability-Standards.

---

## ℹ️ Über Omnixys

Omnixys ist eine offene, modulare Plattform zur Entwicklung von Microservices für moderne Unternehmen. Unser Fokus liegt auf:

* **Flexibler Architektur:** Services in NestJS, FastAPI oder Spring Boot
* **GraphQL-only Kommunikation:** Einheitlich, typsicher und frontend-orientiert
* **Observability by Design:** Tracing, Metriken und Logging eingebaut
* **Security First:** Keycloak für Authentifizierung und Autorisierung
* **Open-Source-Kultur:** MITdenken, Mitmachen, Mitverändern

Unsere Plattform unterstützt Commerce-, Finanz- und Analyseprozesse mit hoher Service-Isolation und horizontaler Skalierbarkeit.

---

## 🧬 Mission

> **Modular Thinking. Infinite Possibilities.**

Unser Ziel ist es, hochgradig skalierbare und technologieunabhängige Services bereitzustellen, die über ein einheitliches GraphQL-Gateway integriert und über moderne Observability-Werkzeuge überwacht werden können.

---

## 🏗️ Struktur der Organisation

Alle Services sind in dedizierten Repositories organisiert, basierend auf Domain und Technologie:

| Kategorie            | Repository                     | Technologie  | Port |
| -------------------- | ------------------------------ | ------------ | ---- |
| Plattform            | `omnixys-os`                   | -            | -    |
| Service Grid         | `omnixys-grid-service`         | -            | -    |
| Cloud Deployment     | `omnixys-cloud-deployer`       | -            | -    |
| UI / Frontend        | `omnixys-ui`                   | Next.js (TS) | 3000 |
| API Gateway          | `omnixys-gateway`              | NestJS       | 8000 |
| Product Service      | `omnixys-product-service`      | NestJS       | 7301 |
| Inventory Service    | `omnixys-inventory-service`    | NestJS       | 7302 |
| Notification Service | `omnixys-notification-service` | FastAPI      | 7402 |
| LogCollector Service | `omnixys-logstream-service`    | FastAPI      | 7401 |
| Analytics Service    | `omnixys-analytics-service`    | FastAPI      | 7303 |
| Person Service       | `omnixys-person-service`       | Spring Boot  | 7001 |
| Account Service      | `omnixys-account-service`      | Spring Boot  | 7002 |
| ShoppingCart Service | `omnixys-shoppingcart-service` | NestJS       | 7101 |

---

## ⚙️ Technologien

**Frontend**

* Next.js (App Router)
* TypeScript
* MUI

**Backend**

* NestJS (TypeScript)
* Spring Boot (Java)
* FastAPI (Python)

**Plattformfunktionen**

* GraphQL (schema-first & code-first)
* Authentifizierung via Keycloak
* CI/CD mit GitHub Actions & Docker
* Observability mit Tempo, Loki, Prometheus & Grafana

---

## 🚀 Einstieg

### Lokal starten

```bash
git clone https://github.com/omnixys/<service-repo>.git
cd <service-repo>
docker-compose up
```

### Oder individuell starten:

```bash
# NodeJS
npm install && npm run start

# Python
pip install -r requirements.txt && uvicorn fastapi_app:app

# Java
./gradlew bootRun
```

---

## 🛡️ Sicherheit & Logs

* Sicherheitsrichtlinien: [SECURITY.md](./SECURITY.md)
* Logging-Konventionen: [logging-guidelines.md](./logging-guidelines.md)
* Sicherheitskontakt: [security@omnixys.com](mailto:security@omnixys.com)
* Logging Framework: [LoggerPlus](https://github.com/omnixys/omnixys-logger)

---

## 🤝 Mitwirken

Wir freuen uns über Beiträge jeder Art – ob Bugfix, Feature oder Dokumentation.

* Lies die [CONTRIBUTING.md](./CONTRIBUTING.md)
* Forke das Repository, arbeite im Branch, öffne Pull Requests
* Nutze `draft PRs` für frühes Feedback
* Bitte teste neue Features gründlich (Testabdeckung > 80 %)

---

## 📜 Lizenz

Dieses Projekt ist lizenziert unter der [GNU General Public License v3.0](./LICENSE.md) – © 2025 Omnixys.

> Bereitgestellt zu Forschungs-, Lehr- und Community-Zwecken.

---

## 🎨 Branding & Domains

Mehr Infos findest du im [Omnixys Branding-Kit](./OMNIXYS-BRANDING.md)

* Primärfarbe: Elegant Lila `#6A4BBC`
* Slogan: *"The Fabric of Modular Innovation"*
* Domains: `omnixys.com`, `omnixys.io`, `omnixys.tech`
* Fonts: **Poppins**, **Inter**
* Statusfarben: Aktiv `#A3E635`, Inaktiv `#F87171`

---

## 🛣️ Roadmap

* ✅ 2025 Q1: Umstellung auf 100 % GraphQL, Einführung von Keycloak und Kafka
* ✅ 2025 Q2: Einführung zentraler Logging- und Tracing-Standards (LoggerPlus, Tempo)
* 🔄 2025 Q3: Rollout von Observability-Dashboards mit Prometheus & Grafana
* 🛠️ 2025 Q4: Admin-UI mit dynamischer Service-Verwaltung (OmnixysOne)
* 📦 2026 Q1: Open Plugin Architecture für Drittanbieter-Integration

---

## 🧭 Architekturübersicht

```mermaid
graph TD
  subgraph Frontend
    UI[Omnixys UI (Next.js)]
  end

  subgraph Gateway
    API[GraphQL Gateway]
  end

  subgraph Services
    Product
    Inventory
    Notification
    LogCollector
    Analytics
    Person
    Account
    ShoppingCart
  end

  UI --> API
  API --> Product
  API --> Inventory
  API --> Notification
  API --> LogCollector
  API --> Analytics
  API --> Person
  API --> Account
  API --> ShoppingCart

  subgraph Infrastructure
    Keycloak
    Kafka
    Grafana
    Prometheus
    Tempo
  end

  Services --> Kafka
  API --> Keycloak
  LogCollector --> Tempo
  Tempo --> Grafana
  Prometheus --> Grafana
```

---

## 🔗 Weitere Ressourcen

* [Projektübersicht (README)](./README.md)
* [Port-Konventionen](./port-konvention.md)
* [Logger-Dokumentation](./logging-guidelines.md)
* [Beispiel-Deployments](https://github.com/omnixys/omnixys-cloud-deployer)
* [Landingpage & UI-Demo](https://omnixys.com)

