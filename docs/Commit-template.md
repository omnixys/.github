## ✅ Commit Template für Omnixys-Projekte

### 📝 Commit Summary (max. 72 Zeichen)

```
<type>(<scope>): <kurze, prägnante Beschreibung im Imperativ>
```

**Beispiele:**

```
feat(payment): implementiere KafkaPublisherService mit Tracing
fix(security): behebe NullPointer bei Keycloak-Token-Verarbeitung
refactor(core): entferne veraltete DTO-Klassen
test(order): füge Tests für Kafka-Consumer hinzu
docs(readme): ergänze Hinweise zur lokalen Installation
chore(ci): füge Postgres-Umgebungsvariablen in cd-ci.yml hinzu
```

---

### 🧾 Commit Description (empfohlen)

```markdown
# Was wurde geändert?
Kurze, verständliche Beschreibung der Änderung.

# Warum ist das relevant?
Begründung der Änderung, z. B. Bugfix, neue Anforderungen, Refactoring etc.

# Wie wurde getestet?
(Optional) Hinweise zu manuellen Tests, Unit Tests, CI etc.

# Hinweise
(Optional) z. B. Breaking Changes, Migration nötig, Review-Empfehlungen
```

---

### ✅ Commit-Typen (`<type>`) für Konventionen

| Typ      | Bedeutung                                         |
| -------- | ------------------------------------------------- |
| feat     | Neue Funktionalität                               |
| fix      | Fehlerbehebung                                    |
| refactor | Code-Umstrukturierung ohne Funktionsänderung      |
| test     | Neue oder geänderte Tests                         |
| chore    | Wartung, Buildsystem, Tooling, keine Codeänderung |
| docs     | Dokumentationsänderungen                          |
| perf     | Performance-Verbesserungen                        |
| ci       | Änderungen an CI/CD                               |
| style    | Codeformatierung, Kommentare, keine Logikänderung |

---

### 💡 Beispiel-Kompletter Commit

**Commit Summary:**

```
chore(ci): füge Postgres-Umgebungsvariablen in cd-ci.yml hinzu
```

**Commit Description:**

```markdown
# Was wurde geändert?
In der Datei `cd-ci.yml` wurden die folgenden Umgebungsvariablen hinzugefügt:
- POSTGRES_SQL_HOST
- POSTGRES_SQL_PORT
- POSTGRES_SQL_DB
- POSTGRES_SQL_USERNAME
- POSTGRES_SQL_PASSWORD
- POSTGRES_SQL_TEST_DB

# Warum ist das relevant?
Ermöglicht konfigurierbare und sichere PostgreSQL-Anbindung in CI/CD-Umgebungen.

# Wie wurde getestet?
CI-Pipeline wurde erfolgreich mit den neuen Secrets ausgeführt.

# Hinweise
Secrets müssen in GitHub Actions korrekt gesetzt sein.
```
