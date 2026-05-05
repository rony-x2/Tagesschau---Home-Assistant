# Tagesschau RSS für Home Assistant

Zeigt aktuelle Nachrichten der [Tagesschau](https://www.tagesschau.de) als Liste im Home-Assistant-Dashboard. Jeder Eintrag verlinkt auf den vollständigen Artikel und enthält Uhrzeit, Schlagzeile und gekürzte Beschreibung. Die Anzahl der angezeigten Meldungen ist über einen Slider direkt im Dashboard einstellbar.

## Voraussetzungen

- Home Assistant
- [HACS](https://hacs.xyz)
- Custom Integration: [`feedparser`](https://github.com/custom-components/feedparser)
- Custom Frontend Module: [`card-mod`](https://github.com/thomasloven/lovelace-card-mod)

## Installation

1. **HACS-Module installieren:**
   - HACS → *Integrationen* → `feedparser` suchen und installieren
   - HACS → *Frontend* → `card-mod` suchen und installieren
2. Home Assistant neu starten.
3. Falls in der `configuration.yaml` noch nicht aktiv, Packages-Loader aktivieren:
   ```yaml
   homeassistant:
     packages: !include_dir_named packages
   ```
4. Datei `packages/tagesschau.yaml` in das `packages/`-Verzeichnis deiner HA-Konfiguration kopieren. Sie enthält:
   - den `feedparser`-Sensor
   - den `input_number`-Helper für die Anzahl der Meldungen
5. Konfiguration prüfen (*Entwicklungswerkzeuge → YAML-Konfiguration prüfen*) und HA neu starten.
6. Inhalt aus `lovelace/card.yaml` als neue Karte in dein Dashboard einfügen (vertical-stack mit Slider und Markdown-Karte).

## Konfiguration anpassen

- **Feed-Quelle:** `feed_url` in `packages/tagesschau.yaml` auf einen anderen RSS-Feed umbiegen.
- **Aktualisierungsintervall:** `scan_interval` (Standard: 10 Minuten).
- **Anzahl Meldungen:** direkt im Dashboard per Slider — Bereich konfigurierbar über `min` / `max` beim `input_number`-Helper.
- **Beschreibungslänge:** `truncate(150, false, '…')` in `lovelace/card.yaml` — die `150` ist die maximale Zeichenanzahl.
- **Icon im Header:** URL nach `## ![](...)` in `lovelace/card.yaml` austauschen, oder lokales Icon in `/config/www/` ablegen und als `/local/dateiname.png` referenzieren.

## Lizenz

MIT

---

# Tagesschau RSS for Home Assistant *(English)*

Displays current news items from [Tagesschau](https://www.tagesschau.de) (German public broadcaster) as a list on the Home Assistant dashboard. Each entry links to the full article and shows the publication time, headline and a truncated description. The number of displayed entries is adjustable via a slider directly in the dashboard.

## Requirements

- Home Assistant
- [HACS](https://hacs.xyz)
- Custom integration: [`feedparser`](https://github.com/custom-components/feedparser)
- Custom frontend module: [`card-mod`](https://github.com/thomasloven/lovelace-card-mod)

## Installation

1. **Install HACS modules:**
   - HACS → *Integrations* → search for `feedparser` and install
   - HACS → *Frontend* → search for `card-mod` and install
2. Restart Home Assistant.
3. If not already active in `configuration.yaml`, enable the packages loader:
   ```yaml
   homeassistant:
     packages: !include_dir_named packages
   ```
4. Copy `packages/tagesschau.yaml` into the `packages/` directory of your HA configuration. It contains:
   - the `feedparser` sensor
   - the `input_number` helper for the entry count
5. Check configuration (*Developer Tools → Check Configuration*) and restart HA.
6. Add the contents of `lovelace/card.yaml` as a new card to your dashboard (vertical-stack with slider and markdown card).

## Customization

- **Feed source:** change `feed_url` in `packages/tagesschau.yaml` to any other RSS feed.
- **Update interval:** `scan_interval` (default: 10 minutes).
- **Number of entries:** adjust directly in the dashboard via the slider — range configurable through `min` / `max` of the `input_number` helper.
- **Description length:** `truncate(150, false, '…')` in `lovelace/card.yaml` — `150` is the max character count.
- **Header icon:** swap the URL after `## ![](...)` in `lovelace/card.yaml`, or place a local icon under `/config/www/` and reference it as `/local/filename.png`.

## License

MIT
