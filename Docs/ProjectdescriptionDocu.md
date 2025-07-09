# 🧱 Projektbeschreibung: WerkBox – Micro-SaaS für Handwerksbetriebe

## 📌 Projekttitel
**WerkBox – Planung, Zeiterfassung & Materialmanagement für Handwerksbetriebe**

---

## 🎯 Zielsetzung

**WerkBox** ist eine modulare Micro-SaaS-Plattform für kleine bis mittlere Handwerksbetriebe (z. B. Bau, Elektro, Sanitär, Schreinerei). Ziel ist es, die tägliche Organisation von Projekten, Mitarbeitenden, Zeit und Material effizient, intuitiv und digital abzubilden – mobil, einfach und ohne IT-Vorkenntnisse.

Das System wird als Webapplikation mit optionalem PWA-Zugriff umgesetzt und unterstützt sowohl **Betriebsleiter:innen** als auch **Montage-Mitarbeitende** im Arbeitsalltag.

---

## 💼 Zielgruppen

- **Einzelunternehmer:innen im Handwerk**
- **KMU mit 2–50 Mitarbeitenden**
- Branchen: Bau, Ausbau, Elektro, Sanitär, Heizung, Maler, Schreiner

---

## 🧩 Kernfunktionen (MVP)

### 👷 Projekt- & Mitarbeitereinsatzplanung
- Kunden- & Projektverwaltung
- Tagesbasierte Aufgabenplanung
- Kalenderbasierter Wochenplan
- Projektstatusanzeige (offen, laufend, erledigt)

### 📱 Mobiler Mitarbeitereinsatz
- Tagesplan mobil abrufen
- Fortschrittsstatus setzen
- Fotos vom Baufortschritt hochladen

### ⏱️ Zeiterfassung & Rapporte
- Start-/Stopp-Zeiterfassung
- Rapportformular pro Auftrag & Tag
- PDF-Export und Historie der Einträge

### 🧰 Materialverwaltung
- Zentrales Inventar mit Mindestbeständen
- Materialentnahme je Auftrag
- Verbrauchsberichte zur Nachverrechnung

### 🔐 Plattformfunktionen
- Rollenbasierte Authentifizierung (Admin, Worker, später Kunde)
- REST-API zur Anbindung mobiler Clients
- Firmenkonfiguration: Logo, Arbeitszeiten, Sprache, etc.

---

## 🧑‍💻 Technischer Stack (geplant)

| Bereich       | Technologie                                     |
|---------------|-------------------------------------------------|
| Frontend      | Vue 3 + TailwindCSS                            |
| Backend       | Node.js (Express) oder Laravel (flexibel)      |
| Datenbank     | SQLite (embedded, leichtgewichtig)             |
| Auth          | JWT-basiert (optional: Laravel Sanctum)        |
| API-Doku      | OpenAPI/Swagger                                 |
| Hosting       | Cloud-first, optional Desktop (Electron/PWA)   |
| DevOps        | GitHub + CI/CD Pipeline                        |

---

## 🗂️ Hauptmodule (Domainstruktur)

| Modul              | Beschreibung                                                              |
|--------------------|---------------------------------------------------------------------------|
| `Users`            | Nutzerverwaltung mit Rollen (Admin, Worker, später: Kunde)                |
| `Projects`         | Projekte mit Status, Zeitraum, Kunden, Aufgaben                           |
| `Tasks`            | Aufgaben mit Beschreibung, Datum, Status und Mitarbeiterzuweisung         |
| `TimeEntries`      | Zeiterfassung mit Start/Ende, Notiz, Projektbezug                         |
| `WorkReports`      | Rapporte mit Text, Datum, Bildern, Mitarbeiter                            |
| `Materials`        | Materialinventar mit Lagerort, Einheit, Mindestmenge                      |
| `MaterialLogs`     | Buchungen je Auftrag (entnommen, zurückgegeben)                           |
| `Settings`         | Konfigurierbare Betriebseinstellungen (Logo, Zeit, Sprache)               |

---

## 🖥️ Geplante Views & UX

### Admin (Betriebsleiter)
- Dashboard mit Tagesüberblick, Projektstatus, Materialwarnung
- Projekt- & Kundenverwaltung
- Wochenplan (Kalender)
- Rapportfreigabe und Materialentnahmen

### Mitarbeitende (Mobil)
- Tagesplan mit Aufgaben
- Zeiterfassung (Start/Stopp)
- Arbeitsrapport mit Notiz und Bildern
- Übersicht eigene Einsätze

### Kunden (Phase 2)
- Projektübersicht (Login-basiert)
- Status und letzte Rapporte

---

## 🧭 Sprints (MVP)

| Sprint   | Thema                                  | Inhalte                                                                 |
|----------|----------------------------------------|-------------------------------------------------------------------------|
| Sprint 1 | Basis & Planung                        | Login, Kunden, Projekte, Aufgabenplanung, API-Doku                      |
| Sprint 2 | Mobil & Mitarbeiter                    | Tagesplan mobil, Fortschrittsmeldung, Uploads                          |
| Sprint 3 | Zeit & Rapporte                        | Zeiterfassung, Rapportierung, PDF-Export                               |

---

## ✅ Definition of Done (DoD – global)

- Alle User Stories sind mit Akzeptanzkriterien erfüllt
- Frontend & API vollständig angebunden
- Funktion in Dev/Testumgebung lauffähig
- Designsystem eingehalten (Buttons, Farben, UX)
- Dokumentation (Swagger + DevDocs) gepflegt
- Tests (Unit/API) vorhanden

---

## 🚀 Vision / Erweiterung nach MVP

- Kundenportal mit Zugriff auf Status, Rechnungen, Dokumente
- Digitale Unterschrift auf Rapport
- Rechnungsmodul mit Zeiterfassungsintegration
- Live-Zeiterfassung über QR-Code auf Baustelle
- Integration mit Buchhaltungstools (z. B. sevDesk, bexio)
- Offline-Fähigkeit für schwache Netzabdeckung

---

## 🧠 KI-/ChatGPT-Einsatzmöglichkeiten (optional in Zukunft)

- Automatische Vorschläge für Arbeitszuteilung nach Verfügbarkeit & Qualifikation
- Sprachgesteuertes Rapportieren („Hey WerkBox, trage ein: 5 Stunden Wände gespachtelt…“)
- Chatbasierter Kundensupport (Statusnachfragen, Termine, etc.)
- NLP-gestützte Analyse von Rapports und Materialverbrauch

---

## 📂 Projektdokumentation

- `README.md`: Übersicht & Setup
- `user-stories.md`: Alle Funktionen nach Epics
- `werkbox-schema.sql`: SQLite-Datenbankstruktur
- `sprint-plan.md`: Zeitplan MVP-Entwicklung
- `design-guideline.md`: UI-Konventionen & Komponenten
- `api-docs.yaml`: OpenAPI-Spezifikation

---

*Stand: Juli 2025 – erstellt von Luis für das Projekt „WerkBox“ (agil, modular, praxisnah)*

