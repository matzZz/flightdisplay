# Changelog

## v1.1

**Deutsch**
- Konfiguration über einen zentralen Change-Node statt hartcodierter Werte im Code (Koordinaten, Radius, MQTT-Topic, Anzeigedauer, Sound, Nachtruhe, Cooldown)
- Fix: adsb.lol lehnte Anfragen wegen fehlendem/generischem User-Agent ab -> echter User-Agent-Header mit Kontaktinfo ergänzt
- Fix: HTTP-Antworten werden jetzt robust als Text geparst (try/catch) statt den Flow bei kaputtem/nicht-JSON-Response mit "JSON parse error" abstürzen zu lassen
- Neu: automatischer Backoff bei 429 (Rate-Limit) - Flow pausiert 5 Minuten statt weiter anzufragen
- Neu: Live-Status direkt am Node (Anzahl gefundener Flugzeuge / Fehlercode)
- Poll-Intervall von 20s auf 30s erhöht
- Neu: globaler Error-Catch-Node für Diagnosezwecke (standardmäßig deaktiviert)
- Persönliche MQTT-Broker-Adresse und Test-Inject-Node entfernt
- Umbenannt zu "FlightDisplay", zweisprachige (DE/EN) Kommentare und Node-Beschreibungen ergänzt

**English**
- Configuration now lives in a single Change node instead of hardcoded values in the code (coordinates, radius, MQTT topic, display duration, sound, quiet hours, cooldown)
- Fix: adsb.lol was rejecting requests due to a missing/generic User-Agent -> added a real User-Agent header with contact info
- Fix: HTTP responses are now parsed robustly as text (try/catch) instead of crashing the flow with a "JSON parse error" on a broken/non-JSON response
- New: automatic backoff on 429 (rate limit) - flow pauses for 5 minutes instead of continuing to hammer the API
- New: live status shown directly on the node (aircraft count / error code)
- Poll interval increased from 20s to 30s
- New: global error-catch node for diagnostics (disabled by default)
- Removed personal MQTT broker address and test inject node
- Renamed to "FlightDisplay", added bilingual (DE/EN) comments and node descriptions

## v1.0

- Erste Version: Flugzeuge über dem Haus per adsb.lol erkennen, Route über adsbdb.com nachschlagen, als Notification mit Flaggen-Icon an AWTRIX senden
- Initial version: detect aircraft overhead via adsb.lol, look up route via adsbdb.com, send as a notification with a flag icon to AWTRIX
