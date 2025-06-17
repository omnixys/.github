# Omnixys-Sphere

**Omnixys-Sphere** is a comprehensive suite of modular microservices designed to meet a wide range of business needs in a modern digital environment. It replaces the GentleCorp-Ecosystem and introduces better scalability, observability, and service isolation.

---

## Table of Contents

1. [Overview](#overview)
2. [Microservices and Functionality](#microservices-and-functionality)
3. [Repository Names](#repository-names)
4. [Tech Stack](#tech-stack)
5. [Database Selection](#database-selection)
6. [Repository Structure](#repository-structure)
7. [Getting Started](#getting-started)

   * [Using Docker](#using-docker)
   * [Starting Individually](#starting-individually)
8. [Contributing](#contributing)
9. [License](#license)

---

## Overview

> *Powered by **OmnixysOS** – our internal microservice operating layer.*

**OmnixysSphere** is a multilingual, modular microservices-based platform. It supports diverse domains such as shopping, travel, finance, content delivery, messaging, analytics, and administration – each service implemented in its own technology-appropriate repository.

All services communicate **exclusively via GraphQL**, ensuring type safety, flexibility, and frontend-driven development.

---

## Microservices and Functionality

### TypeScript (NestJS)

| Service              | Funktionalität                                              |
| -------------------- | ----------------------------------------------------------- |
| Note Service         | Erstellung, Speicherung und Verwaltung persönlicher Notizen |
| Auction Service      | Verwaltung von Auktionen und Live-Geboten                   |
| Order Service        | Auftragsmanagement und Statusverfolgung                     |
| Inventory Service    | Lagerbestandsverwaltung und Produktverfügbarkeit            |
| Menu Service         | Verwaltung dynamischer Menüstrukturen                       |
| Payment Service      | Sichere Zahlungsabwicklung inkl. Validierung                |
| Product Service      | Produktkatalog, Varianten, Suche und Filterung              |
| ShoppingCart Service | Temporäre Warenkorbverwaltung pro Benutzer                  |

### Java (Spring Boot)

| Service               | Funktionalität                                                      |
| --------------------- | ------------------------------------------------------------------- |
| Account Service       | Verwaltung von Benutzerkonten, Zugangsdaten und Berechtigungen      |
| Person Service        | Verwaltung von Personen, Kunden- und Mitarbeiterprofilen mit Rollen |
| Invoice Service       | Erstellung und Verarbeitung von Rechnungen und Gutschriften         |
| Transaction Service   | Nachvollziehbare und abgesicherte Finanztransaktionen               |
| Property Service      | Verwaltung von Immobilienangeboten, Miete & Verkauf                 |
| Booking Service       | Buchungssystem für Reisen, Termine oder Events                      |
| Entertainment Service | Bereitstellung multimedialer Inhalte über GraphQL                   |
| TaskPlanner Service     | Planung, Tracking und Status von Aktivitäten                        |
| Todo Service          | Einfache Aufgabenverwaltung mit lokalem Speicher                    |

### Python (FastAPI)

| Service                 | Funktionalität                                                                                                                                                                                                                                                                               |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Notification Service    | Versenden von E-Mails, Benachrichtigungen und Alert-Handling                                                                                                                                                                                                                                 |
| LogCollector Service    | Zentrale Speicherung und Abfrage von Event- und System-Logs                                                                                                                                                                                                                                  |
| Recommendation Service  | KI-gestützte Vorschläge basierend auf Benutzerverhalten                                                                                                                                                                                                                                      |
| Reviews Service         | Verwaltung von Bewertungen, Rezensionen und Ratings                                                                                                                                                                                                                                          |
| Transport Service       | Routen, Fahrpläne und Lieferdaten für Mobilitätsdienste                                                                                                                                                                                                                                      |
| Analytics Service | Zentrale Auswertung geschäftsrelevanter Kennzahlen (KPIs) wie Kundenwachstum, Umsatzentwicklung, Transaktionsvolumen und Gewinnanalyse. Unterstützt monatliche, jährliche und benutzerdefinierte Zeiträume. Ergebnisse sind exportierbar und über ein interaktives Dashboard visualisierbar. |
| Orchestrator Service | Zentrale Steuerung aller Dienste (Start/Stop/Restart/Status) |

---

## Database Selection

| Tech        | Databases Used                            |
| ----------- | ----------------------------------------- |
| NestJS      | SQLite, PostgreSQL                        |
| Spring Boot | PostgreSQL, MySQL, MongoDB, Redis         |
| FastAPI     | PostgreSQL, MySQL, MongoDB, Redis, SQLite |

Each language uses all major DBs at least once.

---

## 🔌 Ports by Language

> 🟢 = done	🟡 = in progress	🔴 = planned

### 🐍 Python Services

| Service         | Port | Status |
| --------------- | ---- | ------ |
| Notification    | 7402 | 🟡     |
| Inventory       | 7302 | 🟡     |
| Product         | 7301 | 🟡     |
| Analytics Service | 7303 | 🟡     |
| LogCollector Service     | 7401 | 🟡     |
| Recommendation  | 7403 | 🔴     |
| Reviews         | 7404 | 🔴     |
| Transport       | 7405 | 🔴     |
| Orchestrator Service | 7090 | 🟡     |


### ☕ Java Services

| Service       | Port | Status |
| ------------- | ---- | ------ |
| Person        | 7001 | 🟡     |
| Payment       | 7201 | 🟡     |
| Invoice       | 7202 | 🟡     |
| Transaction   | 7203 | 🟡     |
| Account       | 7002 | 🟡     |
| Property      | 7204 | 🔴     |
| Booking       | 7205 | 🔴     |
| Entertainment | 7206 | 🔴     |
| Activity      | 7207 | 🔴     |
| Todo          | 7208 | 🔴     |

### 🕆 TypeScript Services

| Service        | Port | Status |
| -------------- | ---- | ------ |
| Gateway        | 8000 | 🟢     |
| Authentication | 7501 | 🟢     |
| ShoppingCart   | 7101 | 🟡     |
| Order          | 7102 | 🟡     |
| Note           | 7103 | 🔴     |
| Auction        | 7104 | 🔴     |
| Menu           | 7105 | 🔴     |

---

## 🔐 Rollen- & Berechtigungskonzept

### 🎫 Access Tiers (für Kunden)

| Tier     | Beschreibung                          | Rollen (Keycloak)     | API-Zugriff | Admin-Zugang | Exporte | Benutzerverwaltung |
|----------|---------------------------------------|------------------------|-------------|---------------|---------|--------------------|
| Supreme  | Premium-Zugriff auf alle Features     | ROLE_SUPREME           | ✅ Ja        | ❌ Nein         | ✅ Ja    | ❌ Nein             |
| Elite    | Fortgeschrittener Zugriff für Power-User | ROLE_ELITE           | ✅ Teilweise | ❌ Nein         | ✅ Ja    | ❌ Nein             |
| Basic    | Standard-Nutzung (z. B. Käufer)        | ROLE_BASIC             | ❌ Nein      | ❌ Nein         | ❌ Nein  | ❌ Nein             |

### 🧑‍💼 Interne Rollen

| Rolle          | Beschreibung                                |
|----------------|---------------------------------------------|
| ROLE_EMPLOYEE  | Interne:r Mitarbeiter:in mit Service-Zugriff |
| ROLE_ADMIN     | Systemadministrator mit globalem Zugriff     |

| Feature / Bereich                         | 🔰 Basic            | ⚡ Elite                       | 👑 Supreme                           |
| ----------------------------------------- | ------------------- | ----------------------------- | ------------------------------------ |
| 🔐 Login & Self-Service                   | ✅                   | ✅                             | ✅                                    |
| 📦 Eigene Bestellungen & Buchungen        | ✅                   | ✅                             | ✅                                    |
| 💾 **Produktreservierung**                | ❌                   | 🔸 Nur 24h / limitierte Menge | ✅ Unbegrenzt + manuelle Verlängerung |
| 📄 Rechnungs- & Transaktionsübersicht     | ✅ (Nur eigene)      | ✅ (Team/Abteilung)            | ✅ (Unternehmensweit)                 |
| 🛒 Warenkorb & Zahlungsabwicklung         | ✅ (direkt zahlen)   | ✅ (auch reserviert möglich)   | ✅ (auch reserviert möglich)          |
| 🔍 Produkt- & Dienstleistungssuche        | ✅                   | ✅ (inkl. erweiterter Filter)  | ✅ (inkl. Volltext + API Access)      |
| 📊 Persönliches Dashboard                 | ✅ (Grundfunktionen) | ✅ (inkl. Verlauf & KPIs)      | ✅ (Vollständige Analytics)           |
| 📨 Systembenachrichtigungen               | ✅ (passiv)          | ✅ (aktiv & archiviert)        | ✅ (voller Verlauf & Steuerung)       |
| 📁 Dateidownload (PDF/CSV/Excel)          | ❌                   | ✅ (eigene Reports)            | ✅ (alle Daten + Pivot/Charts)        |
| 🌐 API-Zugriff                            | ❌                   | 🔸 Lesend mit Limit           | ✅ Vollzugriff + Token-Generierung    |
| 📣 Interne Kommunikation (z. B. Anfragen) | ❌                   | ✅                             | ✅                                    |
| 👥 Benutzer-/Rollenübersicht              | ❌                   | ❌                             | ✅ (Nur eigene Organisation)          |
| 🧩 Multi-Tenant-Ansicht                   | ❌                   | ❌                             | ✅ (bei Unternehmenskonto)            |
| 🧠 KI-gestützte Empfehlungen              | ❌                   | 🔸 Nur Vorschläge             | ✅ + Personalisierung & Feedback      |
| 📆 Termin- oder Servicebuchung            | ✅                   | ✅                             | ✅ (inkl. Delegierung & Teamsicht)    |
| 📤 Export aus Dashboards                  | ❌                   | ✅                             | ✅                                    |
| 🧾 Custom Reports / Business KPIs         | ❌                   | 🔸 Auswahl                    | ✅ (Custom Builder + Download)        |
| 🧭 Navigation / Menüpersonalisierung      | 🔸 Nur Standardmenü | ✅                             | ✅ (inkl. Rechte-basierte Module)     |

---

## Getting Started

### Using Docker

```bash
docker-compose up
```

### Starting Individually

```bash
cd service-name
npm install | mvn clean install | pip install -r requirements.txt
```

---

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md) for workflow, naming, and PR rules.

---

# 📁 Namenskonventionen für Dateien & Ordner – Omnixys UI

Diese Konventionen stellen sicher, dass alle Dateinamen und Ordnerstrukturen im Projektteam konsistent, vorhersagbar und technologieübergreifend korrekt benannt sind. Sie werden über `eslint-plugin-filenames` automatisiert geprüft.

---

## 📦 Ordnerkonventionen

* Verwende durchgängig **kebab-case** (nur Kleinbuchstaben und Bindestriche)
* Keine Umlaute, Leerzeichen oder Großbuchstaben

### ✅ Beispiele für Ordnernamen:

```
components/
person/
person/customer/
graphql/employee/query/
shared-ui/
```

### ❌ Vermeide:

```
Customer/
SharedUI/
GraphQL/
person/Employee/
```

> 📌 Faustregel: Wenn du den Ordnernamen in einer URL, einem Import oder einem Terminalbefehl nutzen könntest, dann **kebab-case**.

---

## 📄 Dateinamenkonventionen

| Typ                         | Format                   | Beispiel                          |
| --------------------------- | ------------------------ | --------------------------------- |
| **React-Komponenten**       | `PascalCase.tsx`         | `CustomerForm.tsx`                |
| **Hilfsfunktionen / Hooks** | `camelCase.ts`           | `formatDate.ts`, `useDebounce.ts` |
| **GraphQL-Dateien**         | `UPPER_SNAKE.ts`         | `GET_EMPLOYEE_BY_ID.ts`           |
| **Typdefinitionen**         | `kebab-case.type.ts`     | `employee-form.type.ts`           |
| **DTOs / Formdaten**        | `kebab-case.dto.ts`      | `person-form.dto.ts`              |
| **Next.js-Seiten**          | `page.tsx`, `layout.tsx` | automatisch (nicht ändern)        |

---

## ✅ Automatische Prüfung mit ESLint

Die Regeln sind über [`eslint-plugin-filenames`](https://github.com/selaux/eslint-plugin-filenames) konfiguriert.

### Installation:

```bash
npm install --save-dev eslint-plugin-filenames
```

### Konfiguration (Ausschnitt):

```js
"filenames/match-regex": [
  "error",
  "^(?:[A-Z][a-z0-9]+)+\\.tsx$",
  { "message": "React-Komponenten müssen in PascalCase sein." }
],
```

### Gültige Beispiele:

```tsx
// ✅ React-Komponente
CustomerForm.tsx

// ✅ GraphQL Query
GET_EMPLOYEE_BY_ID.ts

// ✅ DTO
employee-form.dto.ts

// ✅ Hilfsfunktion
useFormattedDate.ts
```

### Ungültige Beispiele:

```tsx
// ❌ falsches Format für Komponente
customerform.tsx

// ❌ GraphQL Query nicht in UPPER_SNAKE
getEmployeeById.ts

// ❌ Typendatei nicht in kebab-case
EmployeeForm.Type.ts
```

---

## 🧪 Empfehlungen

* Trenne Domains sauber (z. B. `customer/`, `employee/`, `product/`)
* Vermeide `index.ts` außer für Barrel-Exports
* Verwende ausschließlich `.tsx` / `.ts`, niemals `.js` / `.jsx`

---

## 🔒 Verbindlichkeit

Diese Namensregeln gelten verbindlich für alle Entwickler\:innen im **Omnixys UI & Frontend**. Sie unterstützen:

* 🔍 Schnelles Auffinden von Komponenten
* ✅ Konsistente Builds in CI/CD
* 🧠 Einheitliches Onboarding neuer Entwickler


---

## License

This project is licensed under the [GNU General Public License v3.0](./LICENSE) – © 2025 Omnixys.

> This software is provided for educational and research purposes only.
