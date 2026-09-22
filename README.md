# Trainingsplan

Eine reine Client-seitige Web-App (eine einzige `index.html`, kein Backend, keine
Build-Schritte). Daten (Häkchen, Fortschritt, letzter App-Start) werden nur lokal
im Browser via `localStorage`/`sessionStorage` gespeichert.

## 1. Auf GitHub hochladen

```bash
git init
git add .
git commit -m "Trainingsplan initial commit"
git branch -M main
git remote add origin https://github.com/<dein-user>/<dein-repo>.git
git push -u origin main
```

(Oder einfach im GitHub-Web-Interface ein neues Repo anlegen und `index.html`,
`render.yaml` und diese `README.md` per Drag & Drop hochladen.)

## 2. Auf Render deployen

**Option A – automatisch per `render.yaml` (Blueprint):**
1. Auf [render.com](https://render.com) einloggen.
2. **New +** → **Blueprint** auswählen.
3. Das GitHub-Repo verbinden/auswählen.
4. Render erkennt die `render.yaml` und legt automatisch einen **Static Site**
   Service namens `trainingsplan` an. Einfach bestätigen.

**Option B – manuell:**
1. Auf [render.com](https://render.com) einloggen.
2. **New +** → **Static Site**.
3. Das GitHub-Repo auswählen.
4. Einstellungen:
   - **Build Command:** leer lassen
   - **Publish Directory:** `.` (Repo-Root, da `index.html` dort liegt)
5. **Create Static Site** klicken.

Nach ein paar Sekunden ist die App unter der von Render vergebenen URL
(`https://trainingsplan-xxxx.onrender.com`) erreichbar.

## Hinweise

- Es sind keine Umgebungsvariablen oder Server nötig – es handelt sich um eine
  reine statische Seite.
- Da alle Daten nur lokal im Browser gespeichert werden, ist der Fortschritt
  geräte-/browserspezifisch (kein Sync zwischen Geräten).
- Für eine eigene Domain kann in Render unter **Settings → Custom Domains**
  eine Domain hinzugefügt werden.
