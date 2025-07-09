# ✅ WerkBox – Definition of Done (DoD) & Sprint-Zuordnung

## 🔍 Allgemeine Definition of Done (für alle User Stories)

Eine User Story gilt als **erledigt**, wenn:

- [ ] Akzeptanzkriterien vollständig erfüllt sind
- [ ] Alle Pflichtfelder gespeichert und validiert sind
- [ ] API-Request/Response funktionieren wie spezifiziert
- [ ] UI/UX funktioniert auf Desktop **und** Mobile
- [ ] Code wurde reviewed (mind. 1 Person)
- [ ] Funktion in Dev- oder Testumgebung erfolgreich getestet wurde
- [ ] Tests vorhanden (Unit / API / manuell)
- [ ] Dokumentation (Swagger, Kommentare oder Wiki) wurde aktualisiert

---

## 🏁 Sprint 1 – Basisfunktionen & Planung

| Story ID | Titel                                | Definition of Done (Story-spezifisch)                                          |
|----------|--------------------------------------|--------------------------------------------------------------------------------|
| 1        | Aufgabenplanung pro Tag              | Aufgaben können per Datum erstellt, einem Projekt & Mitarbeiter zugewiesen werden |
| 2        | Kunden- und Auftragsanlage           | Kundendaten und Aufträge speicherbar & bearbeitbar im UI                       |
| 3        | Auftragsstatus im Dashboard          | Anzeige von Projektstatus nach Start-/Enddatum & Fortschritt                   |
| 13       | Rollenbasierte Authentifizierung     | Login, JWT/Token-basierte Auth, Rollensteuerung sichtbar im UI                 |
| 14       | REST-API zur Anbindung               | Swagger/OpenAPI-Doku verfügbar, Routen vollständig implementiert               |
| 15       | Firmenkonfiguration                  | Logo, Betriebsname & Arbeitszeiten speicherbar im Admin-Panel                  |

---

## 📱 Sprint 2 – Mobil & Einsatzvorbereitung

| Story ID | Titel                                | Definition of Done (Story-spezifisch)                                          |
|----------|--------------------------------------|--------------------------------------------------------------------------------|
| 5        | Aufgaben mobil einsehen              | Mobile Ansicht zeigt zugewiesene Tasks inkl. Status, Datum, Projekt            |
| 6        | Fortschrittsmeldung                  | Statusänderung möglich (z. B. „in Arbeit“), sichtbar im Backend/Dashboard       |
| 7        | Bilder vom Baufortschritt            | Upload, Anzeige & Verknüpfung mit Task/Projekt, Anzeige im Bericht             |
| 4        | Wochenplan als PDF                   | Generierter PDF-Wochenplan enthält Aufgaben je Mitarbeiter & Tag               |

---

## ⏱️ Sprint 3 – Zeiterfassung & Rapport

| Story ID | Titel                                | Definition of Done (Story-spezifisch)                                          |
|----------|--------------------------------------|--------------------------------------------------------------------------------|
| 8        | Zeiterfassung pro Auftrag            | Start/Stopp-Zeiten mit Projektreferenz erfassbar und abrufbar                  |
| 9        | Arbeitsrapport mit Notiz & Bildern   | Beschreibung + optional Bilder erfassbar, Ausgabe als Übersicht oder PDF       |
| 12       | Materialverbrauch je Auftrag         | Verbrauchsliste pro Auftrag, dynamisch aus Materialbewegungen generiert        |

---

## 📦 Technisch parallel in allen Sprints

| Story ID | Titel                                | Definition of Done (Story-spezifisch)                                          |
|----------|--------------------------------------|--------------------------------------------------------------------------------|
| 10       | Zentrales Materialinventar           | Artikel mit Menge, Einheit, Ort, Mindestbestand verwaltbar                     |
| 11       | Material für Auftrag entnehmen       | Verbrauch dokumentiert, Material wird aus Inventar abgebucht                   |

---

## 🕓 Phase 2 – Erweiterung (nach MVP)

| Story ID | Titel                                | Definition of Done (Story-spezifisch)                                          |
|----------|--------------------------------------|--------------------------------------------------------------------------------|
| 16       | Projektübersicht für Kunden          | Login mit Kundenzugang zeigt Projektstatus & Rapportdaten                      |
| 17       | Automatische Benachrichtigungen      | E-Mail-Trigger bei Terminänderung oder neuem Rapport implementiert             |

---

## 📌 Umsetzungshinweis

- Die **Definition of Done** ist für alle Entwickler verbindlich
- Stories ohne vollständige DoD gelten nicht als abgeschlossen
- Bei Bedarf kann jede Story vor dem Sprint durch ein technisches Task Breakdown (Tasks/Subtasks) aufgeteilt werden

---

*Stand: Juli 2025 – erstellt für das Micro-SaaS Projekt „WerkBox“*
