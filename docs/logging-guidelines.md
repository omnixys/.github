# 📘 Logging Guidelines für GentleCorp Microservices

Diese Richtlinie definiert **Best Practices für Logging** im gesamten GentleCorp-Ecosystem. Ziel ist es, nachvollziehbare, sicherheitskonforme und geschäftsrelevante Logs zu erzeugen, die sowohl für Entwickler als auch für Monitoring-Tools (Grafana, Loki, Prometheus) nützlich sind.

---

## ✅ 1. Strukturierte Logs (JSON)

Alle Logs **müssen JSON-formatiert** sein und mindestens folgende Felder enthalten:

```json
{
  "timestamp": "ISO 8601 oder UNIX",
  "level": "DEBUG | INFO | WARN | ERROR | AUDIT",
  "message": "Klarer, menschlich lesbarer Text",
  "service": "z. B. product-service",
  "context": "z. B. ProductWriteService#create",
  "traceId": "...",
  "user": "optional, wenn relevant"
}
```

---

## ✅ 2. Log-Level

| Level  | Bedeutung                                   | Beispiel                              |
|--------|---------------------------------------------|----------------------------------------|
| DEBUG  | Entwicklungsdetails, nie in Prod aktiv      | „Starte Preisberechnung für SKU=123“ |
| INFO   | Normale Business-Events                     | „Bestellung abgeschlossen: ID=456“    |
| WARN   | Unerwartete, aber tolerierte Probleme       | „Payment langsam, retry...“           |
| ERROR  | Fehler, die Aufmerksamkeit brauchen         | „Email-Versand fehlgeschlagen“        |
| AUDIT  | Nachvollziehbare Benutzeraktionen (DSGVO)   | „User X änderte Profil“               |

---

## ✅ 3. Logging-Beispiele

### 👍 GUT:
```json
{
  "level": "INFO",
  "message": "Neues Produkt erstellt",
  "productId": "abc123",
  "service": "product-service",
  "context": "ProductWriteService#create",
  "traceId": "xyz..."
}
```

### ❌ SCHLECHT:
- Logs ohne TraceID
- Logs mit vollständigen JWTs oder Passwörtern
- Unstrukturierte Texte (z. B. `print("hier läuft was...")`)

---

## 🚫 4. Sicherheitsrelevante No-Gos

- ❌ Keine JWTs oder Tokens loggen
- ❌ Keine E-Mails, Telefonnummern, Adressen
- ❌ Keine personenbezogenen Daten ohne Zweck

---

## 📦 5. Integration

- Verwende zentrale `LoggerPlus` Utility
- Trage Logs in Kafka ein mit `LogEventDTO`
- Konfiguriere Grafana mit Labels: `level`, `service`, `trace_id`, `context`

---

## 📌 Ziel

Einheitliches, sicheres und verlässliches Logging zur:
- schnelleren Fehleranalyse
- besseren Traceability
- automatisierten Alarmierung via Loki/Alertmanager