# Zeitplan

Eine kleine Webapp für Termine: Aus der gewünschten Ankunftszeit rechnet sie aus, **wann man sich fertig machen** und **wann man losfahren** muss – auch mit Zwischenstopps und weiteren Stationen unterwegs. Dazu erzeugt sie einen Text, den man in die Notizen des Kalendertermins kopiert. Ein Link in diesem Text öffnet später genau diesen Zeitplan wieder in der App.

Die App läuft komplett im Browser auf Handy, Tablet und Computer – ohne Server, ohne Konto, ohne Installation.

## Funktionen

**Anzeige**
- Kopfzeile mit „Fertig machen um“ und „Los um“, jeweils mit Countdown („noch 1 Std. 5 Min.“)
- Nach Stationen mit Aufenthalt oder Puffer fügt die App automatisch „Weiter“ bzw. „Weiter spätestens“ mit Uhrzeit ein – im Ablauf in derselben Zeile wie die Station („bis 17:20“), im Notiztext als eigene Zeile
- Ablauf aller Schritte mit **senkrechtem Fortschrittsbalken**, der sich mit der Zeit füllt; ein Punkt zeigt, wo man gerade steht
- Bei jedem Schritt steht, wie lange es noch dauert („in 25 Min.“) bzw. wie lange er her ist; der nächste Schritt ist hervorgehoben
- Warnung, wenn man zu spät ankommen würde oder ein Zwischenstopp zu knapp ist

**Einstellungen** (öffnen sich über das Symbol oben rechts als kompaktes Seitenpanel)
- Oben im Panel stehen immer die voraussichtlichen Zeiten (Fertig machen, Los, letzte Station), jede Station zeigt ihre berechnete Uhrzeit – so sieht man beim Planen sofort, was sich ändert
- **Neu** legt einen leeren Zeitplan an (mit „Rückgängig“)
- **Titel des Termins** (optional), z. B. „Zahnarzt“
- **Datum** (optional) über einen Kalender. Ohne Datum gilt der Plan für heute – oder für morgen, wenn er heute schon vorbei ist
- **Vorbereitungszeit:** Normal (15 Min.), Lang (30 Min.) oder individuell in 5‑Minuten-Schritten
- **Stationen** (bis zu 12), alle vom gleichen Typ. Für jede Station stellt man ein:
  - **Bezeichnung:** Ziel, Ankommen, Beginn, Zwischenstopp oder Individuell
  - **Beschreibung** (optional), z. B. „Bäcker“ – bei „Individuell“ ist das der Name der Station
  - **Fest um:** eine feste Uhrzeit (mindestens eine Station braucht eine)
  - **nach vorheriger:** Fahrzeit bzw. Abstand zur Station davor (bei der ersten: ab Los)
  - **vor nächster:** Abstand zur Station danach, z. B. „Ankommen 10 Min. vor Beginn“
  - **Aufenthalt**
- Stationen lassen sich mit ↑ und ↓ umsortieren und mit ✕ entfernen
- **Link zur Route** (optional), z. B. aus Google Maps oder Apple Karten über „Teilen“ kopiert. In der App erscheint dann der Button „Route öffnen“
- Notiztext mit oder ohne Symbole, mit oder ohne Link

Die App rechnet von den Stationen mit fester Uhrzeit aus rückwärts bzw. vorwärts. Liegen zwei feste Uhrzeiten hintereinander, zeigt sie den Puffer – oder warnt, wenn es zu knapp wird. Die letzten Einstellungen merkt sich der Browser.

### Beispiel für den Notiztext

```
Termin: Elternabend 7b
Datum: Donnerstag, 03.12.2026

Fertig machen: 14:15 Uhr
Los: 14:30 Uhr (Fahrzeit 15 Min.)
Zwischenstopp Bäcker: 14:45 Uhr (Aufenthalt 10 Min.)
Weiter: 14:55 Uhr (Fahrzeit 25 Min.)
Ankommen: 15:20 Uhr
Beginn: 15:30 Uhr

Route: https://maps.app.goo.gl/AbC123xyz

Zeitplan öffnen: https://<benutzername>.github.io/termin-planer/#ztp15b3n15y10b1n25q10b2u1530d20261203r1.Elternabend%207b.https%3A%2F%2Fmaps%2Eapp%2Egoo%2Egl%2FAbC123xyz.B%C3%A4cker
```

Tippt man im Kalender auf den Link, öffnet sich die App mit dem kompletten Zeitplan – inklusive Titel, Datum, Stationen und Route. Falls ein Kalender den Link nicht öffnet, kann man in den Einstellungen unter „Plan aus einem Link laden“ den Link oder den ganzen Notiztext einfügen. Links aus älteren Versionen der App funktionieren weiterhin.

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

Hinter dem `#` stehen alle Einstellungen. Zuerst ein Block aus Buchstaben und Zahlen, der mit `zt` beginnt, danach – durch Punkte getrennt – der Titel, ggf. der Route-Link und die Beschreibungen der Stationen.

| Kürzel | Bedeutung | Beispiel |
|---|---|---|
| `p` | Vorbereitung Normal/Lang (15 oder 30 Min.) | `p15` |
| `c` | Vorbereitung individuell in Minuten | `c45` |
| `b` | neue Station: 0 Ziel, 1 Ankommen, 2 Beginn, 3 Zwischenstopp, 4 Individuell | `b1` |
| `u` | feste Uhrzeit der Station (hhmm) | `u1400` |
| `n` | Minuten nach der vorherigen Station (Fahrzeit) | `n30` |
| `q` | Minuten vor der nächsten Station | `q10` |
| `y` | Aufenthalt in Minuten | `y10` |
| `d` | Datum (jjjjmmtt) | `d20261203` |
| `i` | Symbole im Notiztext an | `i1` |
| `r` | Route-Link vorhanden (steht hinter dem Titel) | `r1` |

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

Die App sendet keine Daten an einen Server und lädt nichts von fremden Diensten – auch die Schriften (Red Hat Display und Red Hat Text, SIL Open Font License) liegen mit im Repository. Die letzten Einstellungen werden nur im Browser des jeweiligen Geräts gespeichert (`localStorage`). Was im Link steht (Titel, Zeiten, Route, Beschreibungen der Stationen), landet in der Termin-Notiz und – beim Öffnen – im Browserverlauf.
