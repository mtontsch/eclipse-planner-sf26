# Spanien Eclipse Trip 2026 — Planner PWA

Living Planning Document für die totale Sonnenfinsternis am 12.08.2026.
Läuft als installierbare Web-App auf Android & iOS, speichert Haken/Votes/Notizen
lokal auf dem Gerät (localStorage), funktioniert nach dem ersten Laden offline.

## Deployment (einmalig)

```bash
git init && git add -A && git commit -m "eclipse planner pwa"
git branch -M main
git remote add origin git@github.com:mtontsch/eclipse-planner-sf26.git
git push -u origin main
```

Dann auf GitHub: **Settings → Pages → Source: Deploy from a branch → main / (root) → Save.**
Nach 1–2 Minuten erreichbar unter:

    https://mtontsch.github.io/eclipse-planner-sf26/

(Repo vorher unter https://github.com/new anlegen, Name `eclipse-planner-sf26`, public, OHNE Readme initialisieren.)

## Aufs Handy

- **Android (Chrome):** URL öffnen → Menü ⋮ → „App installieren"
- **iOS (Safari!):** URL öffnen → Teilen-Symbol → „Zum Home-Bildschirm"

Danach vom **Homescreen-Icon** starten (nicht Browser-Tab — die installierte
App hat auf iOS einen eigenen, persistenten Storage-Container).
Einmal mit Netz öffnen (Service Worker cached alles), danach offline-fähig.

## Updates

Neue `index.html` pushen — die App holt sich das Update beim nächsten
Öffnen mit Netzverbindung automatisch (network-first Service Worker).

## Hinweise

- Haken/Notizen sind **pro Gerät** (kein Sync zwischen Geräten).
- Der Wetter-Tab braucht Internet (Open-Meteo API), cached aber den letzten Stand.
- `noindex` ist gesetzt; das Repo enthält trotzdem persönliche Ticketdaten —
  Link nur privat weitergeben.

Eclipse Predictions by Fred Espenak, EclipseWise.com · Basemap: © klokantech/Instituto Geográfico Nacional via click_that_hood · Karten-Rendering: Leaflet (BSD-2) · Fonts: Space Grotesk, IBM Plex Mono (OFL)
