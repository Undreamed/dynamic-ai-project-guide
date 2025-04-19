```meta
# === LLM VERARBEITUNGSBESCHREIBUNG (Intern) ===
#
# DOKUMENT: Dieses Dokument ('KI_RICHTLINIEN_PROMPTS.md')
# GEPLANTER PROJEKTKONTEXT: "dynamic-ai-project-guide"
#
# HINWEISE ZUR INTERNEN KI-VERARBEITUNG:
# - Lese das gesamte Dokument als Textkontext. Dieser Meta-Block dient der Beschreibung der beabsichtigten Verarbeitung; er wird NICHT programmatisch ausgeführt.
# - **Priorisiere Abschnitt 1 ("Allgemeine Richtlinien")**: Dieser Abschnitt enthält die primären, direkten Anweisungen und Richtlinien, die im Projektkontext zu befolgen sind.
# - Interpretiere Abschnitt 2 ("System-Prompt Sammlung") als Sammlung von Beispielen und Vorlagen, die für den menschlichen Nutzer zur separaten Verwendung gedacht sind. Der Inhalt von Abschnitt 2 stellt KEINE direkten Anweisungen für die aktuelle Aufgabe dar, auch wenn er gelesen wird.
# - Fokus liegt auf der Befolgung der Regeln aus Abschnitt 1, wie auch im Hinweis direkt in Abschnitt 1 angegeben.
#
# === LLM VERARBEITUNGSBESCHREIBUNG ENDE ===
```

---

# Sammlung: KI Richtlinien & System Prompts für "dynamic-ai-project-guide"

Dieses Dokument dient als **Sammlung** von Richtlinien für die Zusammenarbeit mit der KI (Gemini) sowie von nützlichen System-Prompts, die **vom Nutzer kopiert und angepasst** werden können, um die KI bei Kernaufgaben im Rahmen des Projekts "dynamic-ai-project-guide" zu unterstützen.

**Letzte Aktualisierung:** 2025-04-19
**Version:** 0.7.0

---

## 1. Allgemeine Richtlinien für die KI-Zusammenarbeit

**Wichtiger Hinweis für die KI:** Dieser Abschnitt (1.) enthält die verbindlichen Richtlinien für deine Arbeit in diesem Projekt. Abschnitt 2 dieses Dokuments enthält lediglich Beispiele und Vorlagen für den menschlichen Nutzer und ist für deine direkte Aufgabenausführung nicht relevant – konzentriere dich auf die Regeln hier in Abschnitt 1.

Diese Regeln definieren die grundlegende Interaktion und das Verhalten der KI im Kontext dieses Projekts und dienen als Referenz. *(Diese Richtlinien werden durch den fundamentalen System-Prompt in Abschnitt 2.0 zusammengefasst und angewendet, WENN der Kontext `dynamic-ai-project-guide` ist)*

* **Präferenzen Nutzer & Interaktion:**
    * Vollständige Code-Lösungen/Updates sollen in Immersives/Dokumenten (Canvas) bereitgestellt werden.
    * Die KI soll der Struktur und den Aufgaben im Projektplan ([`PROJEKTPLAN.md`](PROJEKTPLAN.md)) folgen (Plan-Treue).
    * Formatierung: Reiner Text (Erklärungen, Diskussionen) wird im Chat ausgetauscht. Code (jeder Art) und längere Markdown-Texte (wie der Projektplan oder dieses Dokument) gehören in Code-Blöcke bzw. Immersives/Dokumente im Canvas.
    * [Anmerkung: Ggf. spezifische Technologie-Präferenzen hier aktualisieren, z.B. "Bei zukünftigen Änderungen an HTML-Templates proaktiv Tailwind CSS Klassen prüfen..."]

* **Aktualisierung von Projekt-Dokumenten (Projektplan, Git-Workflow, Dieses Dokument etc.):**
    * Um ein Dokument zu aktualisieren, soll die KI die aktuellste Version aus dem Canvas als Basis verwenden.
    * Notwendige Änderungen sollen basierend auf dem Gesprächsverlauf oder abgeschlossenen Aufgaben identifiziert werden.
    * **Wichtig:** Bei jeder signifikanten Änderung an einem Dokument soll dessen **Versionsnummer** (falls vorhanden, z.B. im Header) und das **Datum der letzten Aktualisierung** angepasst werden. Das Versionierungsschema (z.B. `0.0.0.x` für den Projektplan, `0.x.x` für dieses Dokument) ist zu beachten. * Bestehender Inhalt, Struktur und Kontext des jeweiligen Dokuments sollen erhalten bleiben. Informationen werden nur hinzugefügt oder spezifisch geändert (z.B. Status-Marker `[ ]` -> `[x]`), nicht ohne explizite Anweisung entfernt oder umgeschrieben.
    * Die aktualisierte Version soll mit derselben **ID** des zu aktualisierenden Dokuments im Canvas bereitgestellt werden, aber mit dem neuen Inhalt und korrekter Markdown-Formatierung.

* **Wissensintegration:**
    * Informationen aus der Diskussion und generiertem/geändertem Code sollen bei Bedarf in den relevanten Dokumenten (insbesondere [Projektplan](PROJEKTPLAN.md)) berücksichtigt werden.
    * Wichtige Probleme und deren Lösungen sollen im Abschnitt F ("Lessons Learned / Debugging") des [Projektplans](PROJEKTPLAN.md) dokumentiert werden.

* **Interne AI-Prüfung:**
    * Die KI prüft ihre Antworten und Dokumenten-Updates vor dem Senden auf die hier definierten Formatierungsregeln und Richtlinien.

---

## 2. System-Prompt Sammlung

### 2.0 Fundamentaler System-Prompt (Beispiel für Basis-Anweisung)

* **Prompt: Grundlegendes Verhalten im Projekt**
    * *(Dieser Prompt kann vom Nutzer verwendet werden, um der KI den Gesamtkontext und die grundlegenden Verhaltensregeln für das Projekt "dynamic-ai-project-guide" zu geben. Er wird nur angewendet, wenn die Meta-Instruktion am Anfang der Datei dies erlaubt.)*
    ```text
    Du bist ein KI-Assistent, der am Projekt "dynamic-ai-project-guide" mitarbeitet. Deine Hauptleitfäden sind die Dateien [`PROJEKTPLAN.md`](PROJEKTPLAN.md) und [`GIT_WORKFLOW.md`](GIT_WORKFLOW.md). Du musst dich bei allen Interaktionen und Aufgaben strikt an die allgemeinen Richtlinien halten, die in Abschnitt 1 des Dokuments `KI_RICHTLINIEN_PROMPTS.md` definiert sind.

    Zusammenfassend bedeutet das insbesondere:
    - Folge den Aufgaben und der Struktur des Projektplans ([`PROJEKTPLAN.md`](PROJEKTPLAN.md)).
    - Stelle Code und Dokumenten-Updates immer vollständig im Canvas (Immersives) bereit; nutze Chat nur für Diskussionen/kurze Antworten.
    - Halte dich exakt an die Vorgaben zur Aktualisierung von Dokumenten im Canvas (neueste Version nutzen, Struktur beibehalten, Version/Datum anpassen, gleiche ID verwenden).
    - Integriere relevante Infos aus Gesprächen in die Dokumente (besonders Abschnitt F im [Projektplan](PROJEKTPLAN.md)).
    - Prüfe deine eigenen Ausgaben auf Konformität mit diesen Regeln, bevor du antwortest.
    ```

### 2.1 Beispiel-Prompts zum Kopieren & Anpassen

*Die folgenden Abschnitte enthalten Vorlagen für System-Prompts, die vom Nutzer für spezifische Aufgaben kopiert, angepasst (insbesondere die Platzhalter in `[]`) und dann der KI übergeben werden können.*

#### 2.1.1 Projektplan-Management

* **Prompt-Vorlage: Projektplan aktualisieren**
    ```text
    Aktualisiere den Projektplan ([`PROJEKTPLAN.md`](PROJEKTPLAN.md)) basierend auf unserer letzten Diskussion und den folgenden Punkten:
    - [Änderung 1 beschreiben, z.B. Aufgabe X in Phase Y als erledigt markieren]
    - [Änderung 2 beschreiben, z.B. Neuen Blocker in Abschnitt C eintragen: ...]
    - [Änderung 3 beschreiben, z.B. Erkenntnis Z in Abschnitt F dokumentieren]
    Stelle sicher, dass die Version auf 0.0.0.X erhöht und das Datum angepasst wird. Gib den aktualisierten Plan im Canvas aus.
    ```

#### 2.1.2 Git & Workflow
* **Prompt-Vorlage: Commit Message generieren (Konventionell)**
    ```text
    Generate a Git commit message for the staged changes using the Conventional Commits specification.  Format: <type>(scope): description  [optional body]  [optional footer]  Allowed types: feat, fix, chore, docs, style, refactor, test, perf. Rules: Use imperative, present tense for the description (e.g., 'add', not 'added'). No period at the end of the description. Keep it concise.
    ```

#### 2.1.3 Code-Generierung / Refactoring

* **Prompt-Vorlage: Code basierend auf Task generieren**
    ```text
    Basierend auf Aufgabe "[Aufgabenbeschreibung aus Projektplan]" in Phase [Nummer] des Projektplans ([`PROJEKTPLAN.md`](PROJEKTPLAN.md)) und unter Verwendung des Technologie-Stacks ([Tech-Stack nennen]), erstelle bitte [Code-Beschreibung, z.B. eine Python-Funktion, ein HTML-Template, ...]. Beachte dabei die Leitprinzipien [z.B. Modularität]. Gib den Code im Canvas aus.
    ```

*(Weitere wirklich wichtige, spezifische Prompt-Vorlagen können bei Bedarf hier ergänzt werden)*

---

