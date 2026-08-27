# 🎉 JGA Patrick – Scoreboard

Mobile-first Scoreboard-App für den Junggesellenabschied von Patrick.

## Features

- 📊 **Live-Dashboard** mit aktuellem Durchschnitt und Status (Bestanden / Extra-Challenge / Verloren)
- 🎯 **Standard-Challenges** zählen zum Durchschnitt
- ⭐ **Zusatz-Challenges** bringen Bonuspunkte (kein Einfluss auf Durchschnitt)
- ℹ️ **Regelübersicht** als Info-Modal
- 🔐 **Admin-Panel** (versteckt) zum Eintragen von Challenges und Punkten
- 🏁 **Abschlussauswertung** nach dem Ende

## Spielregeln

| Durchschnitt Standard | Ergebnis |
|---|---|
| > 4 Punkte | ✅ Bestanden |
| 3–4 Punkte | ⚡ Extra-Challenge am Schluss |
| < 3 Punkte | ❌ Verloren |

Zusatz-Challenges zählen als Bonuspunkte und beeinflussen den Durchschnitt nicht.

## Admin-Zugang

**Variante 1 – Browser (lokal):**
1. Auf dem Scoreboard unten 7× auf den unsichtbaren Bereich tippen
2. Passwort eingeben (Standard: `jga2025` – in `index.html` anpassbar)
3. Challenges und Punkte eintragen; Daten werden in `localStorage` gespeichert

**Variante 2 – GitHub Actions (Multi-Device-Sync):**
1. GitHub → Repository → Actions → *Update Scores*
2. *Run workflow* → Aktion wählen:
   - `add_challenge` – neue Challenge anlegen
   - `update_score` – Punkte eintragen (Index 0-basiert)
   - `finish` – Challenges beenden → Auswertung
   - `reset` – alles zurücksetzen
3. Nach dem Workflow-Lauf wird `data/scores.json` committet und die GitHub-Pages-Seite automatisch neu deployt.

## Deployment

Die App wird über **GitHub Pages** ausgeliefert.  
Beim Push auf `main` (oder nach einem `Update Scores`-Workflow) wird automatisch deployt.

**Einmalig aktivieren:**  
*Settings → Pages → Source: GitHub Actions*

## Passwort ändern

In `index.html` die Konstante `ADMIN_PASSWORD` anpassen:

```js
const ADMIN_PASSWORD = 'jga2025';   // ← hier ändern
```
