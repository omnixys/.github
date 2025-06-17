# 🌐 Omnixys Organisation `.github`

Omnixys ist eine Open-Source-Plattform für modulare Microservices – API-first, sicher, skalierbar. Entwickelt für moderne Unternehmen, die digitale Services effizient entwickeln, integrieren und überwachen möchten – powered by GraphQL, Keycloak und Observability-Standards.

Dieses Repository stellt zentrale Standards und Konfigurationen für alle Repositories der Organisation **Omnixys** bereit. Es sorgt für einheitliche Prozesse, Vorlagen und Workflows über alle Projekte hinweg.

---

## 📂 Struktur

```plaintext
.github/
├── workflows/
│   ├── reusable-ci.yml
│   ├── reusable-test.yml
│   └── reusable-docker.yml
├── ISSUE_TEMPLATE/
│   ├── bug_report.md
│   ├── feature_request.md
│   └── config.yml
├── PULL_REQUEST_TEMPLATE.md
├── CONTRIBUTING.md
├── SECURITY.md
├── CODE_OF_CONDUCT.md
├── SUPPORT.md
branding/
├── omnixys-logo.png
├── omnixys-symbol.png
└── OMNIXYS-BRANDING.md
docs/
├── port-konvention.md
├── logging-guidelines.md
└── architecture.md
LICENSE.md
README.md
```

---

## 🏡 Zweck

| Kategorie           | Beschreibung                                                                 |
|---------------------|------------------------------------------------------------------------------|
| CONTRIBUTING.md     | Globale Richtlinien für Beiträge, Branch-Konventionen, Commit-Stil usw.         |
| SECURITY.md         | Anleitung zur verantwortungsvollen Meldung von Sicherheitslücken               |
| ISSUE_TEMPLATE/     | Einheitliche Templates für Bugreports und Feature-Requests                     |
| PULL_REQUEST_TEMPLATE.md | Checkliste und Beschreibungsvorlage für PRs                                  |
| SUPPORT.md                | Hinweise, wie und wo Nutzer bei Problemen Hilfe finden können                        |
| workflows/          | Wiederverwendbare GitHub Actions Workflows (CI, Tests, Docker)               |
| branding/           | Logos, Farbwerte, Fonts, Slogans etc.                                         |
| docs/               | Architektur, Logging-Standards, Portkonventionen                             |
| LICENSE.md          | Lizenz für die gemeinsamen Inhalte                                              |

---

## 🚀 Verwendung von Actions in anderen Repos

```yaml
jobs:
  build:
    uses: omnixys/.github/.github/workflows/reusable-ci.yml@main
```

---

## © 2025 Omnixys

> The Fabric of Modular Innovation
