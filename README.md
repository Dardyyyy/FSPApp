# FSP 54260 Ventilstellungsplan

Isolator-App für Maschine 54260 (Bausch+Ströbel SFM5101), Roche Kaiseraugst.

## ⚠️ Wichtig: Vercel statt GitHub Pages

Diese Version hat einen **KI-Chatbot-Tab**. Der Chatbot braucht einen Server im
Hintergrund (`api/chat.js`), der den Anthropic-API-Key sicher verwaltet.
**GitHub Pages kann das nicht** (nur statische Dateien, kein Server-Code).

Deshalb: über **Vercel** deployen (kostenlos, kein Kreditkarte nötig).

## Deployment in 5 Schritten

1. **GitHub-Repo erstellen** (wie gehabt):
   - github.com → New repository → Name z.B. `fsp-54260` → Public → Create
   - "Add file" → "Upload files" → alle 3 Dateien hochladen:
     - `index.html`
     - `ri.webp`
     - `api/chat.js` (den Unterordner `api` beim Upload mit angeben, GitHub erstellt ihn automatisch)
   - Commit changes

2. **Vercel-Account erstellen**
   - vercel.com → Sign Up → "Continue with GitHub" (loggt dich mit deinem GitHub-Account ein)

3. **Projekt importieren**
   - Vercel-Dashboard → "Add New" → "Project"
   - Dein `fsp-54260`-Repo auswählen → "Import"
   - Bei den Einstellungen nichts ändern (Framework: "Other" ist korrekt)

4. **API-Key hinterlegen** (bevor du auf Deploy klickst)
   - Im Import-Screen: "Environment Variables" aufklappen
   - Name: `ANTHROPIC_API_KEY`
   - Value: dein Anthropic-API-Key (von console.anthropic.com/settings/keys)
   - "Add" klicken

5. **Deploy**
   - "Deploy" klicken, ca. 1 Minute warten
   - Du bekommst eine URL wie `https://fsp-54260.vercel.app`
   - Diese URL auf dem Handy öffnen (Chrome) — fertig, voll funktionsfähig inkl. KI-Chat

## Ohne eigenen API-Key?

Falls du keinen Anthropic-API-Key hast: alles außer dem KI-Tab funktioniert
auch ohne Schritt 4 — dann einfach ganz normal über GitHub Pages hosten
(Settings → Pages → Branch main → Save). Der KI-Tab zeigt dann nur einen
Verbindungsfehler, alles andere (Programme, Schritte, Analyse, Übergabe,
Statistik, Schema, Handbuch) läuft normal.

## Enthaltene Features

- **Programme/Schritte**: alle CIP/SIP-Programme mit Fortschrittsverfolgung
- **Weiterschaltbedingungen**: jeder Schritt zeigt genau die Sollwerte
  (Druck/Temp/Zeit), die erfüllt sein müssen bevor die Steuerung weiterschaltet
- **Analyse**: Ventilsuche, Schrittvergleich
- **Schema**: R&I-Fließschema mit Zoom
- **Handbuch**: Sicherheit, Wartung, Betriebsarten, durchsuchbare Fehlersuche
  (22 Alarm-Gruppen)
- **KI-Agent**: Chat mit Claude, kennt Ventile/Schritte/Sollwerte/Alarme,
  bezieht sich automatisch auf den gerade geöffneten Schritt
- Alles lokal gespeichert (localStorage), kein Cloud-Sync, kein Firebase
