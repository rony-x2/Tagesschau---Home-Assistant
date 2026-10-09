# Changelog

Alle nennenswerten Änderungen an diesem Projekt. Das Format folgt
[Keep a Changelog](https://keepachangelog.com/de/1.1.0/), die Versionen
[Semantic Versioning](https://semver.org/lang/de/).

## [1.1.0] – 2026-10-09

### Behoben
- Die Dateien liegen jetzt dort, wo das README sie beschreibt:
  `packages/tagesschau.yaml` und `lovelace/card.yaml`.
- Einträge mit unlesbarem Datum lassen die Karte nicht mehr mit einem
  Template-Fehler abbrechen, sie werden übersprungen.

### Geändert
- Uhrzeiten werden in die lokale Zeitzone von Home Assistant umgerechnet.
- README: Installationsschritte für HACS 2 aktualisiert (feedparser ggf. als
  benutzerdefiniertes Repository hinzufügen).

### Hinzugefügt
- `LICENSE`-Datei (MIT), die im README bereits genannt war.

## [1.0.0] – 2026-05-05

- Erste Veröffentlichung.

[1.1.0]: https://github.com/rony-x2/Tagesschau---Home-Assistant/compare/1.0.0...1.1.0
[1.0.0]: https://github.com/rony-x2/Tagesschau---Home-Assistant/releases/tag/1.0.0
