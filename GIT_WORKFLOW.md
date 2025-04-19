# Git Workflow Richtlinien

Dieses Dokument beschreibt den empfohlenen Git-Workflow, um eine konsistente und nachvollziehbare Entwicklung sicherzustellen.

## Projekt-Richtlinien (Ergänzung)

* **Formatierung dieses Dokuments:** Dieses Dokument (die Git Workflow Richtlinien) wird als Markdown-Text innerhalb eines Immersive-Blocks gepflegt.
* **Commit Messages:** Commits folgen dem Conventional Commits Standard.
    * **Empfehlung bei Nutzung von VS Codium & Gemini Coder:** Um Konsistenz sicherzustellen, wird empfohlen, den Gemini Coder mit folgendem spezifischen Prompt zur Generierung der Commit Message zu verwenden:
      > Generate a Git commit message for the staged changes using the Conventional Commits specification.  Format: <type>(scope): description  [optional body]  [optional footer]  Allowed types: feat, fix, chore, docs, style, refactor, test, perf. Rules: Use imperative, present tense for the description (e.g., 'add', not 'added'). No period at the end of the description. Keep it concise.
* **Branch-Namen:** Feature-, Bugfix- und Hotfix-Namen sollten kurz, deskriptiv und idealerweise auf eine Aufgabe oder ein Ticket (z.B. aus dem Projektplan oder Issue Tracker) bezogen sein. Verwende Kleinbuchstaben und Bindestriche.

## Branching-Modell (Gitflow - Erweitert)

Wir verwenden eine an Gitflow angelehnte Version mit den folgenden Hauptbranches:

* **`main`**: Enthält den produktiven Code. Nur stabiler, getesteter und freigegebener Code wird hierhin gemerged. Direkte Commits sind nicht erlaubt. Jeder Merge nach `main` stellt eine neue Release-Version dar und **muss getaggt werden**.
* **`dev`**: Der Hauptentwicklungsbranch. Hier werden alle abgeschlossenen Features und Bugfixes integriert, bevor sie für ein Release vorbereitet werden. Dient als Basis für nächtliche Builds oder Staging-Deployments.
* **Feature-Branches (`feature/<feature-name>`)**: Für jede neue Funktion oder Aufgabe wird ein eigener Branch von `dev` erstellt. Beispiel: `feature/user-authentication`. Werden nach Abschluss via PR/MR in `dev` gemerged.
* **Bugfix-Branches (`bugfix/<issue-description>`)**: Für Korrekturen an `dev` (nicht-dringende Fehler). Werden von `dev` erstellt und via PR/MR wieder in `dev` gemerged.
* **Release-Branches (`release/<version-number>`)**: *(Optional, aber empfohlen für größere Releases)* Werden von `dev` erstellt, wenn ein Release vorbereitet wird (z.B. `release/v1.1.0`). Dienen der Stabilisierung (nur Bugfixes, keine neuen Features). Werden nach Abschluss in `main` gemerged (und getaggt) und die Änderungen auch zurück in `dev` gemerged.
* **Hotfix-Branches (`hotfix/<issue-description>`)**: Für dringende Korrekturen am `main`-Branch. Werden von `main` (vom letzten Tag) erstellt und nach Abschluss sowohl in `main` (und getaggt) als auch in `dev` gemerged.

## Pull Requests / Merge Requests (PR/MR)

* **Zwingend erforderlich:** Alle Merges in die Branches `dev` und `main` (einschließlich Bugfixes, Hotfixes, Release-Branches) **müssen** über einen Pull Request (GitHub/GitLab/etc.) erfolgen. Direkte Pushes/Merges in diese Branches sind gesperrt/nicht erlaubt (außer ggf. durch Maintainer nach Hotfix-Prozess).
* **Code Review:** Jeder PR/MR sollte mindestens von einer anderen Person überprüft werden (Code-Qualität, Funktionalität, Einhaltung von Richtlinien).
* **CI/CD:** Idealerweise löst ein PR/MR automatische Checks aus (Linting, Tests, Build). Der Merge sollte erst nach erfolgreichen Checks erfolgen.
* **Beschreibung:** PR/MRs sollten eine klare Beschreibung der Änderungen enthalten und ggf. auf zugehörige Issues oder Aufgaben im Projektplan verweisen.

## Workflow-Schritte

1.  **Synchronisieren**: Vor Beginn jeder Arbeit sicherstellen, dass `dev` aktuell ist:
    * `git checkout dev`
    * `git pull origin dev`

2.  **Neue Aufgabe beginnen (Feature)**:
    * `git checkout -b feature/<feature-name>` *(Erstelle Branch von `dev`)*

3.  **Neue Aufgabe beginnen (Bugfix für `dev`)**:
    * `git checkout -b bugfix/<issue-description>` *(Erstelle Branch von `dev`)*

4.  **Entwickeln**:
    * Mache deine Änderungen und committe sie regelmäßig auf deinem Arbeits-Branch (Feature/Bugfix). Nutze aussagekräftige Commit Messages (Conventional Commits - siehe oben).
    * `git commit -m "feat: add user login functionality"` *(Beispiel)*
    * `git push -u origin feature/<feature-name>` *(Pushe frühzeitig, um Backup zu haben und ggf. frühen PR zu erstellen)*

5.  **Arbeit abschließen (Feature/Bugfix)**:
    * Stelle sicher, dass deine Änderungen lokal funktionieren und getestet sind (Unit-Tests, etc.).
    * Aktualisiere deinen Branch mit dem neuesten Stand von `dev`:
        * `git pull origin dev` *(Hole neuesten Stand von dev)*
        * `git merge dev` *(Integriere Änderungen von dev in deinen Branch. Löse Konflikte sorgfältig!)*
        * *(Alternativ für lineare History: `git rebase dev`, erfordert aber Vorsicht bei gepushten Branches)*
    * Teste erneut gründlich nach dem Merge/Rebase.
    * Pushe die finalen Änderungen deines Branches: `git push`
    * **Erstelle einen Pull Request (PR/MR)** von deinem `feature/*` oder `bugfix/*` Branch nach `dev`.
    * Warte auf Code Review und Freigabe. Ggf. Feedback einarbeiten und erneut pushen.
    * Nach erfolgreichem Merge des PR/MR in `dev`:
        * `git checkout dev`
        * `git pull origin dev` *(Lokalen dev aktualisieren)*
        * `git branch -d feature/<feature-name>` *(Lokalen Branch löschen)*
        * Optional: Lösche den Remote-Branch über die Git-Plattform.

6.  **Hotfix durchführen (Dringende Korrektur auf `main`)**:
    * Finde den letzten Release-Tag auf `main`: `git describe --tags` oder `git tag`
    * `git checkout main`
    * `git pull origin main`
    * `git checkout -b hotfix/<issue-description> <last-tag-name>` *(Branch vom letzten Tag erstellen)*
    * Mache die notwendige Korrektur und committe sie.
    * Teste gründlich.
    * Merge nach `main`:
        * `git checkout main`
        * `git merge --no-ff hotfix/<issue-description>`
        * `git push origin main`
    * **Tagge den Hotfix auf `main`** (z.B. Erhöhung der Patch-Version gemäß SemVer):
        * `git tag -a v1.0.1 -m "Hotfix: Critical login issue"`
        * `git push origin --tags`
    * Merge nach `dev`, um den Fix auch dort zu haben:
        * `git checkout dev`
        * `git pull origin dev`
        * `git merge --no-ff hotfix/<issue-description>`
        * `git push origin dev`
    * Lösche den Hotfix-Branch:
        * `git branch -d hotfix/<issue-description>`
        * Optional: Remote-Branch löschen.

## Releasing & Versionierung (Merging nach `main`)

* **Ziel:** Der `main`-Branch enthält ausschließlich stabile, getestete und freigegebene Versionen der Software. Jede Version auf `main` wird durch einen Git-Tag markiert.
* **Versionsschema:** Es wird **Semantic Versioning (SemVer)** empfohlen (z.B. `vMAJOR.MINOR.PATCH` -> `v1.0.0`, `v1.1.0`, `v1.1.1`).
* **Prozess (mit optionalem Release-Branch):**
    1.  **Entscheidung zum Release:** Wenn der `dev`-Branch stabil ist und die geplanten Features für das nächste Release enthält.
    2.  **(Optional) Release Branch erstellen:**
        * `git checkout dev`
        * `git pull origin dev`
        * `git checkout -b release/<version-number>` (z.B. `release/v1.1.0`)
        * Auf diesem Branch erfolgen nur noch Bugfixes für das Release, keine neuen Features. Commits hierauf werden auch zurück nach `dev` gemerged.
    3.  **Finale Tests & Stabilisierung:** Führe letzte Tests (Regression, QA) auf dem `dev`- oder `release/*`-Branch durch.
    4.  **Merge nach `main`:**
        * Erstelle einen PR/MR vom `dev`- oder `release/*`-Branch nach `main`.
        * Nach erfolgreichem Review und finalen Checks wird der PR/MR gemerged.
        * `git checkout main`
        * `git pull origin main`
    5.  **Tagging:** Erstelle einen **annotierten Tag** auf dem Merge-Commit auf `main`:
        * `git tag -a <version-number> -m "Release Version <version-number>"` (z.B. `git tag -a v1.1.0 -m "Release Version 1.1.0"`)
        * `git push origin --tags` *(Pushe alle Tags)*
    6.  **(Wenn Release-Branch genutzt) Zurück nach `dev` mergen:**
        * `git checkout dev`
        * `git pull origin dev`
        * `git merge --no-ff release/<version-number>`
        * `git push origin dev`
        * `git branch -d release/<version-number>`
        * Optional: Remote-Branch löschen.

---

**Hinweis:** Dieser Workflow ist eine Richtlinie. Je nach Projektgröße und Teamstruktur können Anpassungen sinnvoll sein. Konsistenz ist jedoch der Schlüssel.