#  WerkBox – Technisches MVP (Sprintplanung)

## 🎯 Ziel
Fokus auf ein schnell lauffähiges, nützliches Basissystem ohne überflüssige Komplexität. Der MVP wird in 3 agilen Sprints realisiert und bildet die Grundlage für weitere Erweiterungen.

---

## 🏁 Sprint 1 – Basisfunktionen & Planung

**Ziel:**  
Grundstruktur des Systems, erste Datenerfassung, Benutzerrollen, erste UI-Komponenten.

**Umfang:**

- [ ] Authentifizierung (Login mit E-Mail & Passwort, Rollen: Admin, Worker)
- [ ] Nutzerverwaltung (nur Admin)
- [ ] Kundenverwaltung (CRUD: Erstellen, Bearbeiten, Löschen, Listen)
- [ ] Projektverwaltung (CRUD: Titel, Beschreibung, Status, Zeitrahmen, Kunde zuordnen)
- [ ] Aufgabenverwaltung (Zuweisung an Mitarbeitende, Tagesübersicht)
- [ ] API-Routenstruktur dokumentieren (OpenAPI/Swagger oder Markdown)

---

## 📱 Sprint 2 – Mobil & Einsatzvorbereitung

**Ziel:**  
Ermöglicht mobile Nutzung durch Mitarbeitende im Feld, Statusmeldungen und Bild-Dokumentation.

**Umfang:**

- [ ] Mobile Aufgabenübersicht (API + responsive Frontend)
- [ ] Fortschrittsmeldung (Status setzen: offen, in Bearbeitung, erledigt)
- [ ] Foto-Upload pro Aufgabe (Bildspeicherung lokal oder Cloud-Speicher)
- [ ] Tagesplanung als Mobile View aufrufbar

---

## ⏱️ Sprint 3 – Zeiterfassung & Rapport

**Ziel:**  
Transparente Zeiterfassung mit Bezug auf Aufgaben und Projekte, tägliche Rapporte und Exportmöglichkeit.

**Umfang:**

- [ ] Start/Stopp-Zeiterfassung mit Bezug auf Projekt
- [ ] Rapport-Funktion: Tagesbeschreibung + optionale Fotos
- [ ] PDF-Export der Rapporte (optional über Puppeteer generiert)
- [ ] Liste eigener Zeiteinträge und Rapporte für Mitarbeitende

---

## 📌 Hinweis zur Umsetzung

Jeder Sprint ist für 1–2 Wochen realistisch umsetzbar, sofern Backend + Frontend parallel entwickelt werden.  

---

*Stand: Juli 2025 – erstellt für das Micro-SaaS Projekt „WerkBox“*
