# Entwicklungs- und Veröffentlichungsworkflow

## Branches
- `main`: veröffentlichte Version (GitHub Pages).
- `entwicklung`: neue Funktionen und Änderungen, die zunächst überprüft werden.

## Lokal mit Codex arbeiten
Arbeitsordner: `/Users/macair/Documents/GitHub/Webseite Andreas Schönlein Voice`

Einmalig nach dem Klonen:
```bash
git fetch origin
git switch --track origin/entwicklung
```

Später:
```bash
git switch entwicklung
git pull --ff-only
```

Codex bearbeitet Dateien in diesem lokalen Arbeitsordner. Vor jedem Push Änderungen lokal prüfen.

## Änderungen übertragen
```bash
git status
git add -A
git commit -m "Beschreibung der Änderung"
git push -u origin entwicklung
```

Auf GitHub Pull Request von `entwicklung` nach `main` erstellen, automatisierte Prüfung abwarten und erst nach manueller Freigabe mergen. Merge in `main` löst bei entsprechend eingerichteten GitHub-Pages-Einstellungen die Veröffentlichung aus.

## GitHub Pages kontrollieren
Repository → Settings → Pages → Build and deployment:
- Source: Deploy from a branch
- Branch: `main`
- Folder: `/(root)`

Optional können Vorschau-Deployments für Pull Requests später separat ergänzt werden. Sie sind hier noch **nicht** eingerichtet.

## Sicherheit
Keine Zugangsdaten, API-Schlüssel oder privaten Dokumente committen. Vor Veröffentlichung Impressum, Datenschutz, Bildrechte und Kontaktangaben überprüfen. Veröffentlichen auf GitHub Pages ist öffentlich; `noindex` ist kein Zugriffsschutz.
