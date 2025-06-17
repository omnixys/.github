# ✍️ Commit Message Guidelines (Conventional Commits)

Dieses Projekt verwendet den [Conventional Commits Standard](https://www.conventionalcommits.org/) für strukturierte Commit-Nachrichten.

## ✨ Format

```
<type>(optional scope): kurze beschreibung

optionaler längerer beschreibungsteil

BREAKING CHANGE: beschreibung falls inkompatibel
```

## ✅ Erlaubte Commit-Typen

| Typ        | Bedeutung                                       |
|------------|--------------------------------------------------|
| `feat`     | Neues Feature                                    |
| `fix`      | Bugfix                                           |
| `docs`     | Nur Dokumentationsänderung                       |
| `style`    | Formatierung, keine Codeänderung (z. B. Leerzeichen, Kommas) |
| `refactor` | Code-Umstrukturierung ohne funktionale Änderung  |
| `test`     | Nur Test-bezogene Änderungen                     |
| `chore`    | Build-System, Hilfs-Tools, Metadaten             |
| `ci`       | CI/CD-Konfiguration (GitHub Actions etc.)        |
| `perf`     | Performance-Verbesserung                         |
| `build`    | Änderungen am Buildsystem (Gradle, Docker etc.) |

## 🔍 Beispiele

```
feat: unterstütze Kafka für Events
fix(order): entferne doppelte Validierung
docs: ergänze README zu Keycloak
chore(ci): update GitHub Actions Workflow
refactor: extrahiere Service-Logik aus Controller
```

## 🚨 Breaking Changes

Für inkompatible Änderungen:

```
feat!: ersetze Auth-System komplett

BREAKING CHANGE: Login-Flow und Tokenstruktur wurden überarbeitet
```

## 📦 Tools

Dieses Projekt verwendet:

- `commitlint` zur Commitprüfung
- `husky` zur Ausführung vor dem Commit (`.husky/`)
