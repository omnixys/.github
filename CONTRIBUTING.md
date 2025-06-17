# 🤝 Contributing to OmnixysSphere

Vielen Dank, dass du zur Weiterentwicklung von **OmnixysSphere** beitragen möchtest! Dieses Dokument beschreibt den einheitlichen und technologiespezifischen Contributing-Workflow für alle Microservices der Plattform.

---

## 🔧 Projektsetup (lokal)

### 1. Repository klonen

```bash
git clone https://github.com/omnixys/<repository-name>.git
cd <repository-name>
```

### 2. Abhängigkeiten installieren

* **Node/NestJS**

  ```bash
  npm install
  ```
* **Python/FastAPI**

  ```bash
  pip install -r requirements.txt
  ```
* **Java/Spring Boot**

  ```bash
  ./gradlew build   # oder
  mvn clean install
  ```

### 3. Anwendung starten

* Lokaler Start oder via Docker Compose:

```bash
docker-compose up
```

---

## 🪛 Beitragstypen

* 🐛 Bug Fixes
* ✨ Neue Features
* 📝 Doku-Verbesserungen
* 🧪 Tests hinzufügen/verbessern
* 🔧 Refactoring / Code Cleanup

---

## 🧠 Feature Requests & Bug Reports

Bitte nutze die GitHub-Issues des jeweiligen Repositories:

* Formuliere klar das **Problem** oder den **Vorschlag**
* Verwende Screenshots, Logs oder Use-Cases zur Beschreibung
* Weise Issues optional einem Label wie `bug`, `enhancement`, `question` zu

---

## 🔀 Branch-Konvention

| Zweck       | Namensschema                 |
| ----------- | ---------------------------- |
| Feature     | `feature/<kurzbeschreibung>` |
| Bugfix      | `fix/<bug-id>`               |
| Hotfix      | `hotfix/<bereich>`           |
| Refactoring | `refactor/<thema>`           |

> Beispiel: `feature/payment-encryption`

---

## ✅ Pull Request Workflow

1. Forke das Repository (falls nötig)
2. Arbeite im eigenen Branch
3. Schreibe **aussagekräftige Commits** (`git commit -m "feat: add jwt auth to cart"`)
4. PR öffnen mit Beschreibung, Screenshot (wenn UI), Testhinweis
5. Mindestens 1 Review durch Teammitglied notwendig

> Nutze `draft PRs`, um früh Feedback einzuholen.

---

## 🧪 Tests & Qualitätssicherung

| Sprache     | Tools/Standards                        |
| ----------- | -------------------------------------- |
| NestJS      | Jest, ESLint, Prettier, SonarCloud     |
| Spring Boot | JUnit, Mockito, JaCoCo, SonarQube      |
| FastAPI     | Pytest, Ruff, MyPy, Coverage, Pydantic |

Bitte sorge für mindestens **80 % Testabdeckung** bei neuen Modulen.

---

## 🗂 Projektstruktur pro Sprache

### NestJS (TypeScript)

```
src/
├── modules/
├── resolvers/
├── dto/
├── services/
├── kafka/
├── main.ts
```

### Spring Boot (Java)

```
src/main/java/com/omnixys/<modulename>/
├── controller/
├── service/
├── model/
├── repository/
```

### FastAPI (Python)

```
src/
├── api/
├── services/
├── kafka/
├── models/
├── graphql/
├── fastapi_app.py
```

---

## ❤️ Danke!

Dein Beitrag macht OmnixysSphere besser, robuster und vielseitiger. 💜

> Bei Fragen oder Problemen wende dich bitte an das Core-Team unter `team@omnixys.com` (oder öffne ein Issue).

---

© 2025 Omnixys – Modular Thinking. Infinite Possibilities.
