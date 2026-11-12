# CABLE / LOG – Deine private Fitness-Web-App

## Enthalten

- **Übersicht:** Trainingswoche mit Fußballterminen, nächste Krafteinheit und letzte Einheiten.
- **Training:** Montag, Mittwoch und Freitag; Satz-für-Satz-Logging mit Gewicht, Wiederholungen, RIR und Erledigt-Haken.
- **Deine aktuellen Mittwochswerte:** 63 kg Latzug und Rudern, 27 kg Straight-Arm Pulldown, 45 kg Face Pulls, 22,5 kg Bizepscurls, 13,5 kg Hammer Curls und Woodchops. Als **undatierte Ausgangswerte**, nicht als erfundene historische Trainingseinheit.
- **Plan bearbeiten:** Übungen hinzufügen/ändern, Satz- und Wiederholungsziele festlegen.
- **Ernährung:** Wochenrezepte aus dem bisherigen Plan, Kalorien- und Proteinziel, tatsächliche Tageswerte, Körpergewicht und Bauchumfang.
- **Fortschritt:** Verlaufsgrafiken aus den selbst eingetragenen Daten.
- **Für ChatGPT:** Schaltfläche „Bericht kopieren“ und lokales JSON-Backup.
- **Offline:** Nach dem ersten Öffnen über eine HTTPS-Website kann die App dank Service Worker offline verwendet werden.

## Installation als echte Website (0 €)

1. Lege auf **github.com** ein kostenloses **öffentliches** Repository an, beispielsweise `cable-log`.
2. Entpacke die ZIP-Datei und lade die **Dateien im Ordner `cablecoach/`** direkt in die Wurzel dieses Repositories hoch: `index.html`, `app.js`, `styles.css`, `manifest.webmanifest`, `sw.js`, `icon-192.png` und `icon-512.png`.
3. Öffne in GitHub **Settings → Pages**. Unter **Build and deployment** wähle **Deploy from a branch**, `main` und `/ (root)` und speichere.
4. Deine Webseite wird unter `https://DEIN-NUTZERNAME.github.io/cable-log/` erreichbar sein. Die tatsächliche URL steht in GitHub Pages.
5. Auf dem iPhone: URL in **Safari** öffnen → Teilen-Menü → **Zum Home-Bildschirm**. Jetzt kannst du die Seite wie eine App starten.
6. Öffne die App einmal mit Internet, damit die Dateien im Offline-Cache gespeichert werden.

**Wichtig:** Das Repository ist öffentlich, aber der Quellcode enthält keine persönlichen Trainingsdaten. Die Eingaben bleiben in IndexedDB auf deinem Gerät. Keine Accounts, kein Tracking, kein Fitness-Backend, keine kostenpflichtigen Dienste.

### Lokale Vorschau am Windows-PC

- Am einfachsten die entpackte `index.html` in Microsoft Edge oder Chrome öffnen. Unter `file://` können Browserspeicher und Offline-App-Funktionen eingeschränkt sein.
- Für eine zuverlässige Vorschau vor dem Hochladen den Ordner `cablecoach` lokal mit einem einfachen HTTP-Server ausliefern, beispielsweise `python -m http.server 8080` im Ordner und anschließend `http://localhost:8080` öffnen.
- Ein solcher Server ist **nur für die Vorschau auf dem PC**, nicht für die spätere Nutzung nötig.

## Backup und KI-Auswertung

- In **Einstellungen → Gesamtes Backup als JSON** werden Training, Ernährung, Messwerte und Plan heruntergeladen.
- **Trainingsbericht für ChatGPT kopieren** erzeugt einen lesbaren Text mit deinen letzten dokumentierten Einheiten, Gewichten und Wiederholungen. Füge ihn in deinen Chat ein.
- Um nach einem Gerätewechsel Daten wiederherzustellen, wähle **Backup importieren** und die zuvor gespeicherte JSON-Datei.
- **ChatGPT hat keinen automatischen Zugriff auf den lokalen Speicher** des iPhones. Eine echte Live-Synchronisierung würde einen mit deinem Einverständnis eingerichteten Cloud- oder Connector-Dienst benötigen. Das ist in dieser kostenlosen, lokalen Version bewusst nicht enthalten.

## Technische Details

- Vanilla JavaScript ohne Framework-/CDN-Abhängigkeiten; HTML, CSS; IndexedDB mit lokalem Fallback; Service Worker für Offline-Caching; Web App Manifest.
- Kein externer Datenverkehr durch die App selbst; Hosting lädt nur die statische App-Hülle.
- Für dieselbe Übung ist das Steckgewicht die relevante Vergleichsgröße. Aufgrund der Übersetzung des Cable Crossovers kann der tatsächliche Seilzugwiderstand abweichen.
- Exportiere regelmäßig ein Backup: Browser-Datenlöschung oder Geräteschaden können lokale Einträge entfernen.

Version 1.0 · 12. November 2026
