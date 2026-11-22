# Zeitplan

Eine kleine Webapp für Termine: Aus der gewünschten Ankunftszeit rechnet sie aus, **wann man sich fertig machen** und **wann man losfahren** muss – auch mit Zwischenstopps unterwegs. Dazu erzeugt sie einen Text, den man in die Notizen des Kalendertermins kopiert. Ein Link in diesem Text öffnet später genau diesen Zeitplan wieder in der App.

Die App läuft komplett im Browser auf Handy, Tablet und Computer – ohne Server, ohne Konto, ohne Installation.

## Funktionen

**Anzeige**
- Kopfzeile mit „Fertig machen um“ und „Losfahren um“, jeweils mit Countdown („noch 1 Std. 5 Min.“)
- Ablauf aller Schritte mit **senkrechtem Fortschrittsbalken**, der sich mit der Zeit füllt; ein Punkt zeigt, wo man gerade steht
- Bei jedem Schritt steht, wie lange es noch dauert („in 25 Min.“) bzw. wie lange er her ist; der nächste Schritt ist hervorgehoben
- Warnung, wenn man zu spät ankommen würde oder ein Zwischenstopp zu knapp ist

**Einstellungen** (öffnen sich über den Button „Einstellungen“ als Seitenpanel)
- **Titel des Termins** (optional), z. B. „Zahnarzt“
- **Datum** (optional) über einen Kalender. Ohne Datum gilt der Plan für heute – oder für morgen, wenn die Ankunftszeit heute schon vorbei ist
- **Vorbereitungszeit:** Normal (15 Min.), Lang (30 Min.) oder individuell in 5‑Minuten-Schritten
- **Zwischenstopps** (bis zu 8), jeweils mit Name, Fahrzeit bis dorthin und Aufenthalt – entweder als **Dauer** oder zu einer **festen Uhrzeit** (z. B. „Kind abholen um 15:20“)
- **Fahrzeit** bis zum Ziel in 5‑Minuten-Schritten, vorausgewählt 30 Minuten
- **Ankommen:** zu einer festen Uhrzeit oder – wenn ein Beginn eingetragen ist – eine bestimmte Zeit vor Beginn (Schnellauswahl 10 / 15 / 30 / 60 Min.)
- **Beginn der Veranstaltung** (optional)
- Notiztext mit oder ohne Symbole, mit oder ohne Link

Die letzten Einstellungen merkt sich der Browser.

### Beispiel für den Notiztext

```
Termin: Elternabend 7b
Datum: Donnerstag, 03.12.2026

Fertig machen: 14:15 Uhr
Losfahren: 14:30 Uhr (Fahrzeit 15 Min.)
Zwischenstopp Bäcker: 14:45 Uhr (Weiterfahrt 14:55 Uhr, Fahrzeit 25 Min.)
Zwischenstopp Kind abholen: 15:20 Uhr (Weiterfahrt 15:40 Uhr, Fahrzeit 20 Min.)
Ankommen: 16:00 Uhr
Beginn: 16:10 Uhr

Zeitplan öffnen: https://<benutzername>.github.io/termin-planer/#ztp15f20a1600s1610x15y10x25y5z1520d20261203.Elternabend%207b.B%C3%A4cker.Kind%20abholen
```

Tippt man im Kalender auf den Link, öffnet sich die App mit dem kompletten Zeitplan – inklusive Titel, Datum und Zwischenstopps. Falls ein Kalender den Link nicht öffnet, kann man in den Einstellungen unter „Plan aus einem Link laden“ den Link oder den ganzen Notiztext einfügen.

## Auf GitHub Pages veröffentlichen

1. Auf GitHub ein neues **öffentliches** Repository anlegen, z. B. `termin-planer`.
2. ZIP-Datei entpacken und alle Dateien hochladen (*Add file → Upload files*, alle Dateien auf einmal auswählen, dann *Commit changes*). Es gibt keine Unterordner – alles liegt direkt im Hauptverzeichnis.
3. Im Repository *Settings → Pages* öffnen.
4. Unter *Build and deployment* bei *Source* „Deploy from a branch“ wählen, Branch `main` und Ordner `/ (root)` einstellen und speichern.
5. Nach ein bis zwei Minuten ist die App erreichbar unter
   `https://<benutzername>.github.io/termin-planer/`

Der Link im Notiztext passt sich automatisch an diese Adresse an – es muss nichts eingetragen werden.

### Update einspielen

Neue Version einfach wieder über *Add file → Upload files* hochladen und die alten Dateien überschreiben. Wer die App auf dem Home-Bildschirm hat, bekommt die neue Version beim nächsten Öffnen mit Internetverbindung.

### Eigene Adresse fest eintragen (optional)

Soll der Link immer auf eine bestimmte Adresse zeigen (z. B. eine eigene Domain), trägt man sie oben im Skript von `index.html` ein:

```js
const LINK_URL = 'https://meine-domain.de/termin-planer/';
```

## Als App auf dem Home-Bildschirm

- **iPhone / iPad (Safari):** Teilen-Symbol → *Zum Home-Bildschirm*
- **Android (Chrome):** Menü ⋮ → *Zum Startbildschirm hinzufügen* bzw. *App installieren*

Die App öffnet sich dann ohne Browserleiste und funktioniert nach dem ersten Aufruf auch ohne Internetverbindung.

## Aufbau des Links

Hinter dem `#` stehen alle Einstellungen. Zuerst ein Block aus Buchstaben und Zahlen, der mit `zt` beginnt, danach – durch Punkte getrennt – der Titel und die Namen der Zwischenstopps.

| Kürzel | Bedeutung | Beispiel |
|---|---|---|
| `p` | Vorbereitung Normal/Lang (15 oder 30 Min.) | `p15` |
| `c` | Vorbereitung individuell in Minuten | `c45` |
| `f` | Fahrzeit zum Ziel (bzw. vom letzten Zwischenstopp) | `f30` |
| `a` | Ankunft um Uhrzeit (hhmm) | `a1400` |
| `v` | Ankunft Minuten vor Beginn | `v15` |
| `s` | Beginn der Veranstaltung (hhmm) | `s1410` |
| `x` | neuer Zwischenstopp: Fahrzeit bis dorthin | `x15` |
| `y` | Aufenthalt am Zwischenstopp in Minuten | `y10` |
| `z` | feste Uhrzeit am Zwischenstopp (hhmm) | `z1520` |
| `d` | Datum (jjjjmmtt) | `d20261203` |
| `i` | Symbole im Notiztext an | `i1` |

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

`index.html` funktioniert auch allein, z. B. lokal geöffnet. Dann enthält der Notiztext keinen Link, die Offline-Funktion entfällt und ohne die `.woff2`-Dateien daneben wird eine Systemschrift verwendet.

## Datenschutz

Die App sendet keine Daten an einen Server und lädt nichts von fremden Diensten – auch die Schriften (Red Hat Display und Red Hat Text, SIL Open Font License) liegen mit im Repository. Die letzten Einstellungen werden nur im Browser des jeweiligen Geräts gespeichert (`localStorage`). Was im Link steht (Titel, Zeiten, Namen der Zwischenstopps), landet in der Termin-Notiz und – beim Öffnen – im Browserverlauf.
