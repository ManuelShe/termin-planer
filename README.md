# Wann muss ich los?

Eine kleine Webapp, die aus der gewünschten Ankunftszeit ausrechnet, **wann man sich fertig machen** und **wann man losfahren** muss – und daraus direkt einen Text erzeugt, den man in die Notizen eines Kalendertermins kopieren kann.

Die App besteht aus einer einzigen HTML-Datei, braucht keinen Server, kein Konto und keine Installation. Sie läuft im Browser auf Handy, Tablet und Computer.

## Funktionen

- **Vorbereitungszeit:** Normal (15 Min.), Lang (30 Min.) oder individuell in 5‑Minuten-Schritten
- **Fahrzeit:** in 5‑Minuten-Schritten (5 Min. bis 4 Std.), vorausgewählt 30 Minuten
- **Ankommen:** zu einer festen Uhrzeit oder – wenn ein Beginn eingetragen ist – eine bestimmte Zeit vor Beginn (Schnellauswahl 10 / 15 / 30 / 60 Min.)
- **Beginn der Veranstaltung:** optional
- **Kopfzeile** mit den beiden wichtigsten Zeiten: „Fertig machen um“ und „Losfahren um“
- **Ablauf** mit allen Zeiten und einem Zeitbalken (Vorbereitung, Fahrt, Puffer bis Beginn)
- **Notiztext zum Kopieren**, auf Wunsch mit Symbolen, Einstellungs-Code und Link
- **Einstellungen wiederherstellen** über den Link in der Notiz oder durch Einfügen des Codes bzw. des ganzen Notiztextes
- Warnung, wenn man erst nach Beginn ankommen würde; Zeiten über Mitternacht werden mit „(Vortag)“ markiert
- Die letzten Einstellungen merkt sich der Browser
- Hell- und Dunkelmodus, offline nutzbar, als App zum Home-Bildschirm hinzufügbar

### Beispiel für den Notiztext

```
Fertig machen: 13:15 Uhr
Losfahren: 13:30 Uhr (Fahrzeit 30 Min.)
Ankommen: 14:00 Uhr
Beginn: 14:10 Uhr

Einstellungs-Code: ztp15f30a1400s1410
Zeitplan öffnen: https://<benutzername>.github.io/termin-planer/#ztp15f30a1400s1410
```

## Auf GitHub Pages veröffentlichen

1. Auf GitHub ein neues **öffentliches** Repository anlegen, z. B. `termin-planer`.
2. ZIP-Datei entpacken und alle Dateien hochladen (*Add file → Upload files*, alle Dateien auf einmal auswählen). Es gibt keine Unterordner – alles liegt direkt im Hauptverzeichnis.
3. Im Repository *Settings → Pages* öffnen.
4. Unter *Build and deployment* bei *Source* „Deploy from a branch“ wählen, Branch `main` und Ordner `/ (root)` einstellen und speichern.
5. Nach ein bis zwei Minuten ist die App erreichbar unter
   `https://<benutzername>.github.io/termin-planer/`

Der Link im Notiztext passt sich automatisch an diese Adresse an – es muss nichts eingetragen werden.

### Eigene Adresse fest eintragen (optional)

Soll der Link in der Notiz immer auf eine bestimmte Adresse zeigen (z. B. eine eigene Domain), trägt man sie oben im Skript von `index.html` ein:

```js
const LINK_URL = 'https://meine-domain.de/termin-planer/';
```

## Als App auf dem Home-Bildschirm

- **iPhone / iPad (Safari):** Teilen-Symbol → *Zum Home-Bildschirm*
- **Android (Chrome):** Menü ⋮ → *Zum Startbildschirm hinzufügen* bzw. *App installieren*

Die App öffnet sich dann ohne Browserleiste und funktioniert nach dem ersten Aufruf auch ohne Internetverbindung.

## Einstellungs-Code

Der Code ist ein einziges Wort aus Buchstaben und Ziffern, damit er sich mit einem Doppeltippen komplett markieren lässt. Er beginnt immer mit `zt`, danach folgen Kürzel mit Zahlen:

| Kürzel | Bedeutung | Beispiel |
|---|---|---|
| `p` | Vorbereitung Normal/Lang (15 oder 30 Min.) | `p15` |
| `c` | Vorbereitung individuell in Minuten | `c45` |
| `f` | Fahrzeit in Minuten | `f30` |
| `a` | Ankunft um Uhrzeit (hhmm) | `a1400` |
| `v` | Ankunft Minuten vor Beginn | `v15` |
| `s` | Beginn der Veranstaltung (hhmm, optional) | `s1410` |
| `i` | Symbole im Notiztext an | `i1` |

Beispiel: `ztc45f35v15s0930` = 45 Min. Vorbereitung, 35 Min. Fahrt, 15 Min. vor Beginn ankommen, Beginn 09:30 Uhr.

Ältere Codes mit Bindestrichen (`zt-p15-f30-a1400`) werden weiterhin erkannt.

## Dateien

| Datei | Zweck |
|---|---|
| `index.html` | Die komplette App (HTML, CSS und JavaScript in einer Datei) |
| `manifest.webmanifest` | Name, Farben und Symbole für „Zum Home-Bildschirm“ |
| `sw.js` | Service Worker für die Offline-Nutzung |
| `icon-192.png`, `icon-512.png`, `icon-maskable-512.png`, `apple-touch-icon.png` | App-Symbole |
| `red-hat-*.woff2` | Schriften (lokal, ohne Google Fonts) |
| `OFL-LICENSE.txt` | Lizenz der Schriften (SIL Open Font License) |
| `README.md` | Diese Beschreibung |

`index.html` funktioniert auch allein, z. B. lokal geöffnet. Dann enthält der Notiztext nur den Code, keinen Link, die Offline-Funktion entfällt und ohne die `.woff2`-Dateien daneben wird eine Systemschrift verwendet.

## Datenschutz

Die App sendet keine Daten an einen Server und lädt nichts von fremden Diensten – auch die Schriften (Red Hat Display und Red Hat Text, SIL Open Font License) liegen als `.woff2`-Dateien mit im Repository. Die letzten Einstellungen werden nur im Browser des jeweiligen Geräts gespeichert (`localStorage`).
