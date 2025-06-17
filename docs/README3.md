# 🧩 Omnixys – The Fabric of Modular Innovation

Omnixys ist eine moderne Plattform für modulare Microservices – API-first, sicher, skalierbar und vollständig Open Source. Perfekt für Unternehmen, die digitale Services schnell entwickeln und orchestrieren wollen.

Willkommen bei **Omnixys**, einer modernen, modularen Microservice-Plattform für digitale Services in den Bereichen Commerce, Finanzen, Kommunikation und KI-gestützter Analyse. Diese Organisation bündelt alle Open-Source-Repositories der OmnixysSphere-Architektur.

![CI](https://github.com/omnixys/omnixys-ui/actions/workflows/ci.yml/badge.svg)
![CD](https://github.com/omnixys/omnixys-ui/actions/workflows/cd.yml/badge.svg)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](./LICENSE.md)
[![Security Policy](https://img.shields.io/badge/security-policy-blue)](./SECURITY.md)
[![Made with ❤ by Omnixys](https://img.shields.io/badge/made%20with-%E2%9D%A4-ff69b4)](https://omnixys.com)

---

## 🧬 Mission

> **Modular Thinking. Infinite Possibilities.**

Unser Ziel ist es, hochgradig skalierbare und technologieunabhängige Services bereitzustellen, die über ein einheitliches GraphQL-Gateway integriert und über moderne Observability-Werkzeuge überwacht werden können.

---

## 🏗️ Struktur der Organisation

Jeder Microservice lebt in seinem eigenen Repository:

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

* **Frontend:** Next.js (App Router), TypeScript, MUI
* **Backend:** NestJS (TS), Spring Boot (Java), FastAPI (Python)
* **GraphQL:** Schema- oder Code-First je nach Sprache
* **Security:** Keycloak für AuthN & AuthZ
* **Observability:** Tempo (Tracing), Loki (Logging), Prometheus + Grafana (Metriken)
* **CI/CD:** GitHub Actions + Docker

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

Lies unsere [CONTRIBUTING.md](./CONTRIBUTING.md), um Pull-Requests, Branch-Namen und Teststandards zu verstehen. Wir freuen uns auf deine Beiträge!

> ✨ Du kannst auch einen Draft-PR eröffnen, um frühzeitig Feedback zu erhalten.

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

## 🔗 Weitere Ressourcen

* [Projektübersicht (README)](./README.md)
* [Port-Konventionen](./port-konvention.md)
* [Logger-Dokumentation](./logging-guidelines.md)
* [Beispiel-Deployments](https://github.com/omnixys/omnixys-cloud-deployer)
* [Landingpage & UI-Demo](https://omnixys.com)
