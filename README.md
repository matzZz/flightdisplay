# ✈️ FlightDisplay: Wer fliegt da über mir?

Zeigt Flugzeuge über deinem Zuhause inkl. Route und Herkunftsland auf deiner [AWTRIX](https://blueforcer.github.io/awtrix-ng/) an.

Erkennt über die kostenlose ADS-B API ([adsb.lol](https://api.adsb.lol)) alle Flugzeuge, die innerhalb eines einstellbaren Radius über deinem Standort fliegen. Zum Callsign wird automatisch die Flugroute (Start- und Zielort) über [adsbdb.com](https://api.adsbdb.com) abgefragt und zusammen mit einer kleinen Länder-Flagge des Zielorts als Notification an deine AWTRIX gesendet.

![FlightDisplay Logo](flightdisplay_logo.png)

## Funktionen

- Konfigurierbar über einen einzigen Change-Node (Koordinaten, Radius, Anzeigedauer, Sound, Nachtruhe, Cooldown pro Flugzeug)
- Verhindert Doppel-Meldungen durch Cooldown pro Flugzeug (Standard: 10 Minuten)
- Optionaler Sound, der in einer einstellbaren Nachtruhe automatisch stumm bleibt
- Einfache Pixel-Flaggen für ca. 20 Länder (DE, FR, GB, US, TR, ...)
- Robustes Fehlerhandling: automatischer Backoff bei Rate-Limits (429), kein Absturz bei kaputten API-Antworten
- Live-Status direkt am Node (Anzahl gefundener Flugzeuge / Fehlercode)

## Einrichtung

1. `flows.json` in Node-RED importieren (Menü → Import)
2. Den Node **⚙️ Konfiguration (hier anpassen!)** öffnen und eigene Koordinaten, MQTT-Topic deiner AWTRIX usw. eintragen
3. Den Node **„Hausposition & Radius"** öffnen und beim `User-Agent`-Header eine echte Kontaktmöglichkeit eintragen (adsb.lol verlangt das, siehe Kommentar im Code)
4. Beim **„An AWTRIX senden"**-Node den eigenen MQTT-Broker eintragen
5. Deployen — fertig

Beide verwendeten APIs (adsb.lol, adsbdb.com) sind kostenlos und benötigen keinen API-Key.

Siehe [CHANGELOG.md](CHANGELOG.md) für die Versionshistorie.

---

## ✈️ FlightDisplay: Who's flying over me? (English)

Shows aircraft flying over your home, including route and country of origin, on your AWTRIX.

Uses the free ADS-B API ([adsb.lol](https://api.adsb.lol)) to detect all aircraft flying within an adjustable radius of your location. The flight route (origin and destination) is automatically looked up for the callsign via [adsbdb.com](https://api.adsbdb.com) and sent to your AWTRIX as a notification, together with a small flag icon for the destination country.

### Features

- Configurable via a single Change node (coordinates, radius, display duration, sound, quiet hours, per-aircraft cooldown)
- Prevents duplicate notifications with a per-aircraft cooldown (default: 10 minutes)
- Optional sound that automatically stays muted during an adjustable quiet-hours window
- Simple pixel flags for about 20 countries (DE, FR, GB, US, TR, ...)
- Robust error handling: automatic backoff on rate limits (429), no crash on broken API responses
- Live status shown directly on the node (aircraft count / error code)

### Setup

1. Import `flows.json` into Node-RED (menu → Import)
2. Open the **⚙️ Konfiguration (hier anpassen!)** node and enter your own coordinates, your AWTRIX's MQTT topic, etc.
3. Open the **"Hausposition & Radius"** node and set a real contact in the `User-Agent` header (adsb.lol requires this, see code comment)
4. In the **"An AWTRIX senden"** node, enter your own MQTT broker
5. Deploy — done

Both APIs used (adsb.lol, adsbdb.com) are free and require no API key.

See [CHANGELOG.md](CHANGELOG.md) for version history.

## Lizenz / License

MIT
