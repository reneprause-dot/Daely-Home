# Daely Home 2.0 – lokaler Familienkalender

Eine eigenständige, Daely-inspirierte Familienzentrale als statische Progressive Web App (PWA). Für private Nutzung, optimiert für Tablet-Bildschirme und ohne Serverkonto.

## Funktionen
- Tages-, Wochen- und Monatskalender
- Termine mit Kategorie, Ort, Beschreibung, wöchentlicher Wiederholung und Zuordnung zu mehreren Familienprofilen
- Profile mit Name, Farbe, Emoji und Beschreibung
- Aufgaben mit Fälligkeit und Priorität
- Gemeinsame Familiennotizen sowie persönliche Notizen pro Profil, optional wichtig und mit Ablaufdatum
- Notizübersicht auf dem Dashboard und Kiosk-/Vollbildmodus
- JSON-Backup und Wiederherstellung für Kategorien, Termine, Aufgaben, Profile und Notizen
- Basis-Import aus ICS/iCal
- Optionales Wetter nur nach expliziter Aktion (benötigt Internet und Standortfreigabe)
- IndexedDB lokale Datenhaltung, Service Worker und lokale Schrift-/CSS-Abhängigkeiten

## Datenschutz und wichtige Grenzen
- Termine, Profile, Aufgaben und Notizen werden in IndexedDB des Browsers auf diesem Gerät gespeichert.
- GitHub Pages hostet nur den App-Code. Es synchronisiert private Daten nicht zwischen Geräten.
- Browserdaten können durch Löschen der Website-Daten verloren gehen. Bitte regelmäßig ein JSON-Backup exportieren und an einem sicheren Ort aufbewahren.
- „Persönliche“ Notizen sind in dieser lokalen Einzelgeräte-App eine organisatorische Trennung nach Profil, keine Zugangssperre. Wer das Tablet entsperrt nutzt, kann grundsätzlich alle Notizen öffnen.
- Wetter benötigt eine Internetverbindung. Der Rest der App ist auf lokale Nutzung ausgelegt, sobald die App einmal über HTTPS geladen und vom Service Worker gecacht wurde.
- Wiederkehrende Termine und ICS-Import sind bewusst einfach gehalten; komplexe RRULEs, Ausnahmen und Zeitzonen werden nicht vollständig verarbeitet.

## Veröffentlichung über GitHub Pages
1. Alle Dateien und Ordner dieses Projekts ins Repository hochladen; `index.html` muss im Repository-Hauptverzeichnis liegen.
2. GitHub → Repository → Settings → Pages.
3. Unter Build and deployment „Deploy from a branch“ auswählen, Branch `main`, Ordner `/(root)`, speichern.
4. Die angezeigte Pages-URL auf dem Xiaomi-Tablet in Chrome öffnen und „Zum Startbildschirm hinzufügen“ oder „App installieren“ wählen.

## Ordnerstruktur
```text
 daely-home/
 ├── index.html
 ├── app.js
 ├── styles.css
 ├── manifest.json
 ├── sw.js
 ├── README.md
 ├── .nojekyll
 └── icons/
     ├── icon.svg
     ├── icon-192.png
     └── icon-512.png
```
