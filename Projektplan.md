# Projektplan: [Projektname]

**Version:** [0.0.0.1]
**Letzte Aktualisierung:** [Datum]
**Ziel:** [Kurze, klare Beschreibung des Projektziels]
**Status:** [Kurzer Überblick über den aktuellen Stand, z.B. "Planung", "In Entwicklung", "Abgeschlossen"]

---

## A. Projekt-Richtlinien & Grundsätze

* **Projektkontext:** [Kurze Beschreibung des Projekts und seines Zwecks, z.B. entwicklung eines Kochbuchs (Python, ...)]
* **Referenzen:** [Links zu relevanten Dokumenten, Code-Basis, dieser Projektplan, [Git Workflow Richtlinien](GIT_WORKFLOW.md) etc.]
* **Kernziele:**
    * [Messbares Ziel 1]
    * [Messbares Ziel 2]
    * [...]
* **Technologie-Stack (Geplant):**
    * [Sprache/Framework 1, z.B. Flask]
    * [Datenbank, z.B. SQLAlchemy]
    * [Frontend-Technologie, z.B. Tailwind CSS]
    * [Andere wichtige Tools/Bibliotheken, z.B. Flask-WTF]
* **Leitprinzipien:** [Wichtige Konzepte für dieses Projekt, z.B. Modularität, Sicherheit, Performance, Benutzerfreundlichkeit, Testabdeckung], **Einhaltung des definierten Git-Workflows**
* **Formatierung dieses Dokuments:** Dieses Dokument (der Projektplan) wird als Markdown-Text innerhalb dieses Dokuments/Immersive-Blocks gepflegt, um die Lesbarkeit und Versionskontrolle zu vereinfachen. [Anmerkung: Ggf. an neues Projekt anpassen]
* **Versionskontrolle & Workflow:** Die Versionskontrolle erfolgt mittels Git. Detaillierte Anweisungen zum Branching-Modell, Commit-Prozess, Pull Requests und Releasing sind im separaten Dokument `[Git Workflow Richtlinien](GIT_WORKFLOW.md)` festgelegt und sind verbindlich für dieses Projekt.
* **Wichtige Entscheidungen:** [Raum für festgehaltene Architekturentscheidungen etc.]

* **Spezifische Richtlinien für die KI-Zusammenarbeit:**
    * **Präferenzen Nutzer & Interaktion:** Vollständige Code-Lösungen/Updates in Immersives/Dokumenten bereitstellen. Plan-Treue beachten. Formatierung: Text als Chat/Fließtext, nur Code in Code-Blöcke/Immersives. [Anmerkung: Ggf. spezifische Technologie-Präferenzen hier aktualisieren, z.B. "Bei zukünftigen Änderungen an HTML-Templates proaktiv prüfen..."]
    * **Aktualisierung dieses Projektplans:** Um diesen Projektplan zu aktualisieren, verwende die aktuellste Version als Basis. Identifiziere die notwendigen Änderungen basierend auf dem Gesprächsverlauf oder abgeschlossenen Aufgaben. **Bei jeder signifikanten Änderung wird die Versionsnummer im Header (beginnend mit `0.0.0.1` und dann fortlaufend erhöht, z.B. `0.0.0.2`, `0.0.0.3`...) und das Datum der letzten Aktualisierung aktualisiert.** Typischerweise werden auch der Status-Abschnitt, die Checklisten in Abschnitt B, die Wiederaufnahme-Notizen in Abschnitt E und/oder die Debugging-Zusammenfassung in Abschnitt F angepasst. Wichtig: Bestehender Inhalt, Struktur und Kontext des Projektplans sollen dabei erhalten bleiben. Informationen werden nur hinzugefügt oder spezifisch geändert (z.B. Status-Marker [ ] -> [x]), nicht ohne explizite Anweisung entfernt oder umgeschrieben. Die aktualisierte Version wird mit derselben ID (`projektplan_v3`), aber mit dem neuen Inhalt und korrekter Markdown-Formatierung bereitgestellt.
    * **Wissensintegration:** Infos aus Diskussion/Code sind hier zu berücksichtigen. Wichtige Probleme und Lösungen sind in Abschnitt F zu dokumentieren.
    * **Interne AI-Prüfung:** Die KI prüft ihre Antworten vor dem Senden auf die hier definierten Formatierungsregeln und Richtlinien.

---

## B. Projektphasen & Aufgaben

**Phase 0: Vorbereitung & Setup**

* [ ] Projektstruktur definieren
* [ ] Versionskontrolle einrichten (z.B. Git Repository erstellen) *(Details siehe [Git Workflow Richtlinien](GIT_WORKFLOW.md))*
* [ ] Entwicklungsumgebung aufsetzen (z.B. Virtuelle Umgebung, Docker)
* [ ] Initial bekannte Abhängigkeiten festlegen & Management einrichten (z.B. `requirements.txt`/`package.json` anlegen)
* [ ] Konfigurationsmanagement planen (z.B. `.env`-Dateien)
* [ ] Ggf. initiale Design-Mockups/Wireframes erstellen

**Phase 1: Kernstruktur & Basisfunktionen**

* [ ] Datenbankmodelle definieren (falls zutreffend)
* [ ] Datenbank-Setup & Migrationen (falls zutreffend)
* [ ] Grundlegende API-Endpunkte / Anwendungslogik erstellen
* [ ] Authentifizierung & Autorisierung implementieren (falls nötig)
* [ ] Basis-UI/Frontend-Struktur aufsetzen (falls zutreffend)
* [ ] Logging einrichten

**Phase 2: Feature-Entwicklung [Feature A]**

* [ ] Teilaufgabe 1 für Feature A
* [ ] Teilaufgabe 2 für Feature A
* [ ] Tests für Feature A schreiben
* [ ] UI-Anpassungen für Feature A (falls zutreffend)

**Phase 3: Feature-Entwicklung [Feature B]**

* [ ] Teilaufgabe 1 für Feature B
* [ ] Teilaufgabe 2 für Feature B
* [ ] Tests für Feature B schreiben
* [ ] UI-Anpassungen für Feature B (falls zutreffend)

**(Weitere Phasen nach Bedarf hinzufügen)**

**Phase X: Testing & Qualitätssicherung**

* [ ] Unit-Tests vervollständigen/überprüfen
* [ ] Integrationstests durchführen
* [ ] Manuelle Tests / User Acceptance Testing (UAT)
* [ ] Performance-Tests (falls nötig)
* [ ] Sicherheitsüberprüfungen

**Phase Y: Deployment & Abschluss**

* [ ] Deployment-Umgebung vorbereiten
* [ ] Deployment-Prozess definieren/automatisieren *(Beachte Release-Prozess in [Git Workflow Richtlinien](GIT_WORKFLOW.md))*
* [ ] Finale Tests in der Produktivumgebung
* [ ] Projektdokumentation abschließen (z.B. README, Benutzerhandbuch)
* [ ] Projektübergabe / Go-Live

---

## C. Nächste Schritte / To-Do

* **Aktuell:** [Was ist die unmittelbar nächste Aufgabe?]
* **Blocker:** [Gibt es Hindernisse?]
* **Offene Fragen:** [Welche Fragen müssen noch geklärt werden?]

---

## D. Wichtige Befehle & Einstellungen (Referenz)

* **Setup:**
    * `git clone [Repository URL]` *(Initiales Auschecken des Projekts)*
    * `cd [Projektordner]`
    * `[Befehl zum Installieren der Abhängigkeiten, z.B. pip install -r requirements.txt]`
    * `[Befehl zum Starten der Anwendung, z.B. python main.py]`
    * *(Für alle weiteren Git-Operationen wie Branching, Committing, Merging, Tagging etc., siehe die [Git Workflow Richtlinien](GIT_WORKFLOW.md))*
* **Datenbank (Beispiel):**
    * `[Befehl für Migrationen erstellen]`
    * `[Befehl für Migrationen anwenden]`
* **Tests:**
    * `[Befehl zum Ausführen der Tests]`
* **Sonstiges:**
    * [Wichtige Konfigurationspfade]
    * [Links zu wichtigen externen Diensten]

---

## E. Wiederaufnahme-Notizen (Optional)

* **Letzter Stand:** [Wo wurde die Arbeit unterbrochen?]
* **Kontext:** [Wichtige Informationen für die Wiederaufnahme]

---

## F. Lessons Learned / Debugging (Optional)

* **Problem:** [Beschreibung eines aufgetretenen Problems]
    * **Ursache:** [Analyse der Ursache]
    * **Lösung:** [Beschreibung der Lösung]
    * **Erkenntnis:** [Was wurde daraus gelernt?]
* **(Weitere Einträge hinzufügen)**

