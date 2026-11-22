# Zeitplaner

Eine kleine Webapp für Termine: Aus der gewünschten Ankunftszeit rechnet sie aus, **wann man sich fertig machen** und **wann man losgehen bzw. losfahren** muss – zu Fuß, mit dem Rad, Auto oder Bus – auch mit Zwischenstopps und weiteren Stationen unterwegs. Dazu erzeugt sie einen Text, den man in die Notizen des Kalendertermins kopiert. Ein Link in diesem Text öffnet später genau diesen Zeitplan wieder in der App.

Die App läuft komplett im Browser auf Handy, Tablet und Computer – ohne Server, ohne Konto, ohne Installation.

## Funktionen

**Anzeige**
- Kopfzeile mit „Fertig machen um“ und „Los um“, jeweils mit Countdown („noch 1 Std. 5 Min.“)
- Nach Stationen mit Aufenthalt oder Puffer fügt die App automatisch „Weiter“ bzw. „Weiter spätestens“ mit Uhrzeit ein – im Ablauf in derselben Zeile wie die Station („bis 17:20“), im Notiztext als eigene Zeile
- Ablauf aller Schritte mit **senkrechtem Fortschrittsbalken**, der sich mit der Zeit füllt; ein Punkt zeigt, wo man gerade steht
- Bei jedem Schritt steht, wie lange es noch dauert („in 25 Min.“) bzw. wie lange er her ist; der nächste Schritt ist hervorgehoben
- **Aufteilungsbalken** ganz unten im Ablauf: farbig in zeitlicher Reihenfolge Vorbereitung, Weg, Zeit vor Ort (z. B. durch „zuvor ankommen“ oder Puffer) und Aufenthalt, darunter die Summen und die Gesamtzeit
- Warnung, wenn man zu spät ankommen würde oder ein Zwischenstopp zu knapp ist

**Teilen und Kalender**
- **In den Kalender:** erstellt eine Kalenderdatei (.ics) mit Titel, Datum und dem Notiztext. Der Termin beginnt mit „Los“ und endet mit der letzten Station; Erinnerungen gibt es zum Fertigmachen, bei „Los“ und bei jedem „Weiter“. Auf dem Handy die Datei öffnen und „Hinzufügen“ wählen
- **Teilen:** öffnet das Teilen-Menü des Handys (WhatsApp, Mail, Notizen …) mit dem Notiztext
- **Nur Link teilen:** teilt nur den Link zum Zeitplan (wo kein Teilen-Menü da ist, wird er kopiert). Bei einer lokal geöffneten Datei gibt es keinen Link
- **Text kopieren** für die Notizen eines vorhandenen Termins
- **Drucken** (Drucker-Symbol oben rechts neben den Einstellungen): druckt Kopf mit Zeiten, den Ablauf mit senkrechtem Balken und Symbolen sowie den Aufteilungsbalken – ohne Notiztext und Countdown

**Einstellungen** (öffnen sich über das Symbol oben rechts als kompaktes Seitenpanel)
- Oben im Panel stehen immer die voraussichtlichen Zeiten (Fertig machen, Los, letzte Station), jede Station zeigt ihre berechnete Uhrzeit – so sieht man beim Planen sofort, was sich ändert
- **Neu** legt einen leeren Zeitplan an (mit „Rückgängig“)
- **Vorlagen:** den aktuellen Plan unter einem Namen speichern (z. B. „Schule“) und später mit einem Tipp wieder laden – mit Stationen, Vorbereitung, Puffer, Route und Wiederholung, aber ohne Datum. Gleicher Name überschreibt die Vorlage, ✕ löscht sie. Vorlagen liegen nur im Browser des jeweiligen Geräts
- **Titel des Termins** (optional), z. B. „Zahnarzt“
- **Datum** (optional) über einen Kalender. Ohne Datum gilt der Plan für heute – oder für morgen, wenn er heute schon vorbei ist
- **Wiederholung** (optional): täglich, werktags (Mo–Fr), wöchentlich an ausgewählten Tagen, monatlich oder jährlich – ab dem gewählten Datum bzw. ab heute. Die App zeigt dann immer den nächsten Termin, im Kalender entsteht ein Serientermin
- **Vorbereitungszeit:** Keine, Normal (15 Min.), Lang (30 Min.) oder individuell in 5‑Minuten-Schritten. Ohne Vorbereitungszeit entfällt „Fertig machen“
- **Stationen** (bis zu 12), alle vom gleichen Typ. Für jede Station stellt man ein:
  - **Bezeichnung** – jede Kategorie hat ihr eigenes Symbol im Fortschrittsbalken:

    | Kategorie | Wofür | Symbol |
    |---|---|---|
    | Zwischenstopp | kurz etwas erledigen | kleiner Punkt |
    | Termin | Ziel mit Uhrzeit und Dauer | Zielflagge – mit „zuvor ankommen“ Kalender (die Flagge steht dann bei „Ankommen“) |
    | Beginn | Beginn einer Veranstaltung | Zielflagge – mit „zuvor ankommen“ Play-Zeichen |
    | Treffen | mit jemandem verabredet | zwei Personen |
    | Abholen | jemanden abholen | Person |
    | Bringen | jemanden irgendwo hinbringen | Person mit Pfeil |
    | Haltestelle | Bus oder Bahn – die feste Uhrzeit ist die Abfahrt | Bus |
    | Abflug | Flug – die feste Uhrzeit ist der Abflug, vorbelegt mit 2 Std. vorher da sein (Einchecken, Sicherheitskontrolle) | Flugzeug |
    | Ankunft | Ankunft von Bus, Bahn oder Flug zu fester Uhrzeit. Direkt nach „Haltestelle“ oder „Abflug“ ergibt sich die Fahr- bzw. Flugzeit automatisch aus beiden Uhrzeiten | Pfeil nach unten |
    | Pause | Rast auf langen Wegen (im Balken eigene Farbe) | Tasse |
    | Rückweg | Heimweg als letzte Station | Haus |
    | Individuell | alles andere, Name über die Beschreibung | Punkt |

  - **Beschreibung** (optional), z. B. „Bäcker“ – bei „Individuell“ ist das der Name der Station
  - **Details** (optional), z. B. Adresse, Raum oder Ansprechpartner – stehen im Ablauf, im Ausdruck und im Notiztext unter der Station
  - **Fest um:** eine feste Uhrzeit (mindestens eine Station braucht eine)
  - **Zeit bis hierhin:** Wegzeit (zu Fuß, mit Rad, Auto, Bus …) bzw. Abstand zur Station davor (bei der ersten: ab Los), beim Rückweg „Zeit für den Rückweg“
  - **zuvor ankommen:** so viele Minuten vor der Uhrzeit der Station dort sein, z. B. 15 Min. vor Beginn. Im Ablauf erscheint dann automatisch eine Zeile „Ankommen“
  - **Gründe fürs Früher-da-sein** (erscheinen, sobald „zuvor ankommen“ eingestellt ist, mehrere wählbar): z. B. Parkplatzsuche, Fußweg vom Parkplatz, Puffer, Treffpunkt, Anmeldung, Einlass, Einchecken, Sicherheitskontrolle, Ticket holen, Garderobe, Umziehen, Aufwärmen, Platz suchen oder Material aufbauen – dazu ein eigener Grund als Freitext. Sie stehen dann bei „Ankommen“ im Ablauf und im Notiztext
  - **Aufenthalt**
  - **ca.** bei „Zeit bis hierhin“ und „Aufenthalt“: die Dauer ist nur geschätzt. Alle Zeiten, die sich daraus ergeben, stehen dann mit „ca.“ da – bis zur nächsten Station mit fester Uhrzeit
- Stationen lassen sich mit ↑ und ↓ umsortieren und mit ✕ entfernen
- **Puffer für Wege:** +5 bis +20 Min. oder +10 bis +50 % auf jede Wegzeit, z. B. für Stau, Parkplatzsuche oder Umsteigen
- **Link zur Route** (optional), z. B. aus Google Maps oder Apple Karten über „Teilen“ kopiert. In der App erscheint dann der Button „Route öffnen“
- Notiztext mit oder ohne Symbole, mit oder ohne Link

Die App rechnet von den Stationen mit fester Uhrzeit aus rückwärts bzw. vorwärts. Liegen zwei feste Uhrzeiten hintereinander, zeigt sie den Puffer – oder warnt, wenn es zu knapp wird. Die letzten Einstellungen merkt sich der Browser.

### Beispiel für den Notiztext

```
Termin: Elternabend 7b
Datum: Donnerstag, 03.12.2026

Fertig machen: 14:15 Uhr
Los: 14:30 Uhr (Weg 15 Min.)
Zwischenstopp Bäcker: 14:45 Uhr (Aufenthalt 10 Min.)
Weiter: 14:55 Uhr (Weg 25 Min.)
Ankommen: 15:20 Uhr
Beginn: 15:30 Uhr

Route: https://maps.app.goo.gl/AbC123xyz

Zeitplan öffnen: https://<benutzername>.github.io/termin-planer/#ztp15b3n15y10b1n25b2u1530n10d20261203r1.Elternabend%207b.https%3A%2F%2Fmaps%2Eapp%2Egoo%2Egl%2FAbC123xyz.B%C3%A4cker
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
| `p` | Vorbereitung Keine/Normal/Lang (0, 15 oder 30 Min.) | `p15` |
| `c` | Vorbereitung individuell in Minuten | `c45` |
| `b` | neue Station: 2 Beginn, 3 Zwischenstopp, 4 Individuell, 5 Rückweg, 6 Termin, 7 Abholen, 8 Haltestelle, 9 Pause, 10 Bringen, 11 Treffen, 12 Abflug, 13 Ankunft (0 und 1 aus älteren Links werden zu Termin) | `b6` |
| `u` | feste Uhrzeit der Station (hhmm) | `u1400` |
| `n` | Minuten nach der vorherigen Station (Wegzeit) | `n30` |
| `y` | Aufenthalt in Minuten | `y10` |
| `e` | zuvor ankommen (Minuten vor der Uhrzeit der Station) | `e15` |
| `o` | Gründe fürs Früher-da-sein als Summe: 1 Parkplatzsuche · 2 Fußweg vom Parkplatz · 3 Puffer · 4 Treffpunkt · 5 Anmeldung · 6 Einlass · 7 Einchecken · 8 Sicherheitskontrolle · 9 Ticket holen · 10 Garderobe · 11 Umziehen · 12 Aufwärmen · 13 Platz suchen · 14 Material aufbauen – jeder Grund n zählt 2^(n−1), z. B. Parkplatzsuche + Fußweg = 1 + 2 = 3 | `o3` |
| `x` | ungefähr: 1 = Zeit bis hierhin, 2 = Aufenthalt, 3 = beides | `x2` |
| `l` | Details vorhanden – sie stehen hinter den Beschreibungen (und ggf. den eigenen Gründen) | `l1` |
| `t` | eigene Gründe vorhanden – sie stehen dann hinter den Beschreibungen der Stationen | `t1` |
| `d` | Datum (jjjjmmtt) | `d20261203` |
| `w` | Wiederholung: 1 täglich, 2 werktags, 3 wöchentlich, 4 monatlich, 5 jährlich | `w3` |
| `k` | Wochentage bei wöchentlich (Mo = 1, Di = 2, Mi = 4 … So = 64, addiert) | `k6` |
| `i` | Symbole im Notiztext an | `i1` |
| `r` | Route-Link vorhanden (steht hinter dem Titel) | `r1` |
| `g` / `h` | Puffer je Weg in Minuten / in Prozent | `g10`, `h20` |

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
