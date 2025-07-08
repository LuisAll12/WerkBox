# 🗃️ WerkBox – Datenbank-Dokumentation (SQLite)

## Ziel
Modular aufgebaute SQLite-Datenbank zur Abbildung von Projekten, Mitarbeitern, Material, Zeiterfassung, Rapports, Authentifizierung und Konfiguration.

---

## 📁 Tabelle: `users`

| Feldname     | Feldtyp     | SQLite-Typ | Kommentar                        | Beispiel                |
|--------------|-------------|------------|----------------------------------|-------------------------|
| id           | UUID/Text   | TEXT       | Eindeutiger Benutzer-Identifier  | "a2d9f9...e9f1"         |
| name         | Name        | TEXT       | Vollständiger Name               | "Max Mustermann"        |
| email        | Text        | TEXT       | E-Mail-Adresse (unique)         | "max@werkbox.ch"        |
| role         | Text        | TEXT       | Rolle im System (admin, worker) | "worker"                |
| passwordHash | Text        | TEXT       | Gehashter Passwortwert          | "$2a$10$..."            |
| created_at   | Timestamp   | TEXT       | Zeitstempel der Erstellung       | "2025-07-08T08:42:00Z"  |

---

## 📁 Tabelle: `projects`

| Feldname      | Feldtyp   | SQLite-Typ | Kommentar                              | Beispiel                |
|---------------|-----------|------------|----------------------------------------|-------------------------|
| id            | UUID      | TEXT       | Projekt-ID                             | "prj_abc123"            |
| title         | Text      | TEXT       | Titel/Auftragsname                     | "Umbau EFH Zürich"      |
| description   | Text      | TEXT       | Detailbeschreibung                     | "Sanierung Küche + Bad" |
| customer_id   | UUID      | TEXT       | Verweis auf `customers.id`             | "cus_001"               |
| status        | Text      | TEXT       | Status (geplant, laufend, fertig)      | "laufend"               |
| start_date    | Datum     | TEXT       | Geplanter Start                        | "2025-08-01"            |
| end_date      | Datum     | TEXT       | Voraussichtliches Ende                 | "2025-08-21"            |
| created_at    | Timestamp | TEXT       | Erstellungszeit                        | "2025-07-08T08:42:00Z"  |

---

## 📁 Tabelle: `customers`

| Feldname    | Feldtyp | SQLite-Typ | Kommentar                      | Beispiel                  |
|-------------|---------|------------|--------------------------------|---------------------------|
| id          | UUID    | TEXT       | Kunden-ID                      | "cus_001"                 |
| name        | Name    | TEXT       | Name des Kunden                | "Familie Meier"           |
| email       | Text    | TEXT       | E-Mail des Kunden              | "meier@bluewin.ch"        |
| phone       | Text    | TEXT       | Telefonnummer                  | "+41 79 123 45 67"        |
| address     | Text    | TEXT       | Adresse (optional formatiert) | "Bahnhofstr. 10, Zürich"  |

---

## 📁 Tabelle: `tasks`

| Feldname    | Feldtyp | SQLite-Typ | Kommentar                                  | Beispiel                  |
|-------------|---------|------------|--------------------------------------------|---------------------------|
| id          | UUID    | TEXT       | Aufgaben-ID                                | "tsk_98765"               |
| project_id  | UUID    | TEXT       | Verweis auf `projects.id`                  | "prj_abc123"              |
| user_id     | UUID    | TEXT       | Zuweisung an Mitarbeiter (`users.id`)      | "a2d9f9...e9f1"           |
| title       | Text    | TEXT       | Kurztitel der Aufgabe                      | "Wände spachteln"         |
| description | Text    | TEXT       | Beschreibung der Aufgabe                   | "Alle Innenwände EG"      |
| date        | Datum   | TEXT       | Geplanter Ausführungstag                   | "2025-08-02"              |
| status      | Text    | TEXT       | Status (offen, in_arbeit, erledigt)        | "in_arbeit"               |

---

## 📁 Tabelle: `time_entries`

| Feldname    | Feldtyp   | SQLite-Typ | Kommentar                                 | Beispiel                 |
|-------------|-----------|------------|-------------------------------------------|--------------------------|
| id          | UUID      | TEXT       | Zeit-Log-ID                                | "time_456xyz"            |
| user_id     | UUID      | TEXT       | Bezug zu `users.id`                        | "a2d9f9...e9f1"          |
| project_id  | UUID      | TEXT       | Auftrag, zu dem die Zeit gehört            | "prj_abc123"             |
| start_time  | Timestamp | TEXT       | Arbeitsbeginn                              | "2025-08-01T08:00:00Z"   |
| end_time    | Timestamp | TEXT       | Arbeitsende                                | "2025-08-01T16:30:00Z"   |
| note        | Text      | TEXT       | Bemerkung / Tätigkeitsbeschreibung         | "Elektroverkabelung EG"  |

---

## 📁 Tabelle: `work_reports`

| Feldname    | Feldtyp   | SQLite-Typ | Kommentar                                 | Beispiel                  |
|-------------|-----------|------------|-------------------------------------------|---------------------------|
| id          | UUID      | TEXT       | Rapport-ID                                | "rep_9981"                |
| user_id     | UUID      | TEXT       | Verweis auf Mitarbeiter                   | "a2d9f9...e9f1"           |
| project_id  | UUID      | TEXT       | Verweis auf Projekt                       | "prj_abc123"              |
| date        | Datum     | TEXT       | Ausführungstag                            | "2025-08-01"              |
| description | Text      | TEXT       | Freitext-Rapport                          | "Wände gespachtelt, EG"   |
| photo_urls  | Text      | TEXT       | Kommagetrennte Bildpfade (lokal/S3/etc.)  | "img/1.jpg,img/2.jpg"     |

---

## 📁 Tabelle: `materials`

| Feldname     | Feldtyp | SQLite-Typ | Kommentar                                | Beispiel                 |
|--------------|---------|------------|------------------------------------------|--------------------------|
| id           | UUID    | TEXT       | Material-ID                              | "mat_123"                |
| name         | Text    | TEXT       | Bezeichnung des Artikels                 | "Gipsplatte 12mm"        |
| unit         | Text    | TEXT       | Einheit (Stück, m², Liter, etc.)         | "Stück"                  |
| quantity     | Zahl    | INTEGER    | Lagerbestand aktuell                     | 240                      |
| min_quantity | Zahl    | INTEGER    | Mindestbestand für Warnung               | 50                       |
| location     | Text    | TEXT       | Lagerort                                 | "Lagerhalle 1 – Regal A" |

---

## 📁 Tabelle: `material_logs`

| Feldname     | Feldtyp   | SQLite-Typ | Kommentar                               | Beispiel                  |
|--------------|-----------|------------|-----------------------------------------|---------------------------|
| id           | UUID      | TEXT       | Log-ID                                  | "log_9921"                |
| material_id  | UUID      | TEXT       | Verweis auf `materials.id`              | "mat_123"                 |
| project_id   | UUID      | TEXT       | Verwendet für Projekt                   | "prj_abc123"              |
| quantity     | Zahl      | INTEGER    | Anzahl entnommen/verbraucht             | 20                        |
| action       | Text      | TEXT       | "entnahme", "rückgabe", "korrektur"     | "entnahme"                |
| date         | Datum     | TEXT       | Zeitpunkt der Bewegung                  | "2025-08-01"              |
| user_id      | UUID      | TEXT       | Wer hat das Material verbucht           | "a2d9f9...e9f1"           |

---

## 📁 Tabelle: `settings`

| Feldname   | Feldtyp | SQLite-Typ | Kommentar                                | Beispiel                  |
|------------|---------|------------|------------------------------------------|---------------------------|
| id         | Text    | TEXT       | Einstellungsschlüssel                    | "company_name"            |
| value      | Text    | TEXT       | Einstellungswert                         | "WerkBox AG"              |
| category   | Text    | TEXT       | Gruppierung                              | "general", "branding"     |

---

## 🔐 Authentifizierung (optional separat via JWT/Session gespeichert)

Sessionmanagement wird in der Anwendungsschicht gelöst. Login erfolgt mit E-Mail + Passwort, gespeichert als Hash. Optional kann `last_login` oder Token-Tabelle ergänzt werden.

---

## 📌 Hinweise zur Umsetzung in SQLite

- UUIDs als TEXT abbilden (SQLite hat keinen UUID-Typ)
- Timestamps und Datum als ISO-8601 Text (`TEXT`) speichern
- Beziehungen über `FOREIGN KEY` deklarieren (wenn benötigt)
- Datensicherung via `.dump` oder Flatfile-Export (z. B. für Cloudsync)

---

*Stand: Juli 2025 – Erstellt für das Micro-SaaS Projekt „WerkBox“ von Luis*
