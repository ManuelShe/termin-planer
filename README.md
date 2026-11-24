# Zeitplaner

Eine kleine Webapp für Termine: Aus der gewünschten Ankunftszeit rechnet sie aus, **wann man mit der Vorbereitung anfangen** und **wann man losgehen bzw. losfahren** muss – zu Fuß, mit dem Rad, Auto oder Bus – auch mit Zwischenstopps und weiteren Stationen unterwegs. Dazu erzeugt sie einen Text, den man in die Notizen des Kalendertermins kopiert. Ein Link in diesem Text öffnet später genau diesen Zeitplan wieder in der App.

Die App läuft komplett im Browser auf Handy, Tablet und Computer – ohne Server, ohne Konto, ohne Installation.

## Funktionen

**Anzeige**
- Kopfzeile mit „Vorbereiten um“ und „Los um“, jeweils mit Countdown („noch 1 Std. 5 Min.“)
- Oben rechts eine gemeinsame Taste mit **Einstellungen**, **Ortsmarke** (Unterwegs-Modus, siehe unten) und **Kleiderbügel** – der Bügel blendet alle Vorbereitungen aus bzw. ein (wird im Link gespeichert). Sind alle Vorbereitungen vorbei, blendet der Ablauf sie automatisch aus („Vorbereitung erledigt ✓“); ein Tipp auf den Bügel zeigt sie kurz wieder
- Nach Stationen mit Aufenthalt oder Puffer fügt die App automatisch „Weiter“ bzw. „Weiter spätestens“ mit Uhrzeit ein – im Ablauf in derselben Zeile wie die Station („bis 17:20“), im Notiztext als eigene Zeile
- Ablauf aller Schritte mit **senkrechtem Fortschrittsbalken**, der sich mit der Zeit füllt; ein Punkt zeigt, wo man gerade steht
- Bei jedem Schritt steht, wie lange es noch dauert („in 25 Min.“) bzw. wie lange er her ist; der nächste Schritt ist hervorgehoben
- **Aufteilungsbalken** ganz unten im Ablauf: farbig in zeitlicher Reihenfolge Vorbereitung, Weg, Zeit vor Ort (z. B. durch „zuvor ankommen“ oder Puffer) und Aufenthalt, darunter die Summen und die Gesamtzeit
- Warnung, wenn man zu spät ankommen würde oder ein Zwischenstopp zu knapp ist

**Teilen und Kalender**
- **In den Kalender:** erstellt eine Kalenderdatei (.ics) mit Titel, Datum und dem Notiztext. Der Termin beginnt mit „Los“ und endet mit der letzten Station; Erinnerungen gibt es zur Vorbereitung, bei „Los“ und bei jedem „Weiter“. Auf dem Handy die Datei öffnen und „Hinzufügen“ wählen
- **Teilen:** öffnet das Teilen-Menü des Handys (WhatsApp, Mail, Notizen …) mit einer Kurzinfo zum Termin und dem Link (siehe „Link teilen mit Kurzinfo“)
- **Nur Link teilen:** teilt wirklich nur den Link zum Zeitplan, ohne Text (wo kein Teilen-Menü da ist, wird er kopiert). Bei einer lokal geöffneten Datei gibt es keinen Link
- **Text kopieren** für die Notizen eines vorhandenen Termins
- **Drucken** (Drucker-Symbol beim Ablauf, neben Glocke und „Display anlassen“): druckt Kopf mit Zeiten, den Ablauf mit senkrechtem Balken und Symbolen sowie den Aufteilungsbalken – ohne Notiztext und Countdown

**Einstellungen** (öffnen sich über das Symbol oben rechts als kompaktes Seitenpanel)
- Oben im Panel stehen immer die voraussichtlichen Zeiten (Vorbereiten, Los, letzte Station), jede Station zeigt ihre berechnete Uhrzeit – so sieht man beim Planen sofort, was sich ändert
- **Neu** legt einen frischen Zeitplan an – mit einer Vorbereitung (15 Min.) und einem Termin (mit „Rückgängig“)
- **Vorlagen:** den aktuellen Plan unter einem Namen speichern (z. B. „Schule“) und später mit einem Tipp wieder laden – mit Stationen, Vorbereitung, Puffer, Route und Wiederholung, aber ohne Datum. Gleicher Name überschreibt die Vorlage, ✕ löscht sie. Vorlagen liegen nur im Browser des jeweiligen Geräts Das Disketten-Symbol neben einer Vorlage überschreibt sie mit den aktuellen Einstellungen (mit „Rückgängig“).
- **Titel des Termins** (optional), z. B. „Zahnarzt“
- **Datum** (optional) über einen Kalender. Ohne Datum gilt der Plan für heute – oder für morgen, wenn er heute schon vorbei ist
- **Wiederholung** (optional): täglich, werktags (Mo–Fr), wöchentlich an ausgewählten Tagen, monatlich oder jährlich – ab dem gewählten Datum bzw. ab heute. Die App zeigt dann immer den nächsten Termin, im Kalender entsteht ein Serientermin
- **Stationen** (bis zu 12), alle vom gleichen Typ. Für jede Station stellt man ein:
  - **Bezeichnung** – jede Kategorie hat ihr eigenes Symbol im Fortschrittsbalken:

    | Kategorie | Wofür | Symbol |
    |---|---|---|
    | Vorbereitung | zu Hause fertig werden, z. B. anziehen, Tasche packen – nur „benötigte Zeit“, mit Vorschlägen für die Beschreibung. Die Beschreibung ersetzt „Vorbereiten“; Uhrzeit klein und grau | kleiner Punkt |
    | Los | Hier geht es los, z. B. „von zu Hause“, „vom Büro“ – optional mit fester Uhrzeit, ohne Aufenthalt | Pfeil |
    | Zwischenstopp | kurz etwas erledigen | kleiner Punkt |
    | Termin | Ziel mit Uhrzeit und Dauer | Zielflagge – steht davor eine Zeile „Ankommen“ (durch „zuvor ankommen“ oder nach Bus/Bahn), Kalender und die Flagge bei „Ankommen“ |
    | Beginn | Beginn einer Veranstaltung | immer Play-Zeichen (die Flagge steht bei „Ankommen“) |
    | Treffen | mit jemandem verabredet | zwei Personen |
    | Abholen | jemanden abholen | Person |
    | Bringen | jemanden irgendwo hinbringen | Person mit Pfeil |
    | Haltestelle | Bus oder Bahn – die feste Uhrzeit ist die Abfahrt; optional „Ankunft um“. Dann zeigt die Station in den Einstellungen Fahrzeit, Ankunft, Weg zum nächsten Punkt und den Puffer bis zur nächsten festen Uhrzeit (Puffer = was über das eingestellte „vorher da sein“ hinaus übrig bleibt). Schnellwahl „Verspätung: Abfahrt“ direkt an der Station (auch zugeklappt) | Bus |
    | Abflug | Flug – die feste Uhrzeit ist der Abflug, vorbelegt mit 2 Std. vorher da sein (Einchecken, Sicherheitskontrolle). Schnellwahl „Verspätung“ für den Abflug | Flugzeug |
    | Ankunft | Ankunft von Bus, Bahn oder Flug zu fester Uhrzeit. Direkt nach „Haltestelle“ oder „Abflug“ ergibt sich die Fahr- bzw. Flugzeit automatisch aus beiden Uhrzeiten. Eine spätere Ankunft stellst du mit der Verspätung zwischen Abflug/Haltestelle und Ankunft ein | Pfeil nach unten |
    | Pause | Rast auf langen Wegen (im Balken eigene Farbe) | Tasse |
    | Rückweg | Heimweg als letzte Station – eine Beschreibung (z. B. „Oma“) ersetzt „Zu Hause“ | Haus |
    | Individuell | alles andere, Name über die Beschreibung | Punkt |

  - **Beschreibung** (optional), z. B. „Bäcker“ – bei „Individuell“ ist das der Name der Station
  - **Details** (optional), z. B. Adresse, Raum oder Ansprechpartner – stehen im Ablauf, im Ausdruck und im Notiztext unter der Station
  - **Fest um:** eine feste Uhrzeit (mindestens eine Station braucht eine)
  - **Zeit bis hierhin:** Wegzeit (zu Fuß, mit Rad, Auto, Bus …) bzw. Abstand zur Station davor (bei der ersten: ab Los), beim Rückweg „Zeit für den Rückweg“
  - **Puffer für den Weg** (außer bei Vorbereitungen): +5 bis +30 Min. oder +10 bis +50 % auf die Wegzeit zu dieser Station, z. B. für Stau, Parkplatzsuche oder Umsteigen. Prozent-Puffer werden auf volle 5 Min. aufgerundet
  - **zuvor ankommen:** so viele Minuten vor der Uhrzeit der Station dort sein, z. B. 15 Min. vor Beginn. Im Ablauf erscheint dann automatisch eine Zeile „Ankommen“
  - **Gründe fürs Früher-da-sein** (erscheinen, sobald „zuvor ankommen“ eingestellt ist, mehrere wählbar): z. B. Parkplatzsuche, Fußweg vom Parkplatz, Puffer, Treffpunkt, Anmeldung, Einlass, Einchecken, Sicherheitskontrolle, Ticket holen, Garderobe, Umziehen, Aufwärmen, Platz suchen oder Material aufbauen – dazu ein eigener Grund als Freitext. Sie stehen dann bei „Ankommen“ im Ablauf und im Notiztext
  - **Aufenthalt**
  - **ca.** bei „Zeit bis hierhin“ und „Aufenthalt“: die Dauer ist nur geschätzt. Alle Zeiten, die sich daraus ergeben, stehen dann mit „ca.“ da – bis zur nächsten Station mit fester Uhrzeit
- Stationen stehen zugeklappt und kompakt untereinander (Uhrzeit, Name, Kurzinfo); ein Tipp klappt eine Station zum Bearbeiten auf. Zwischen den Stationen stehen Abfahrts-, Ankunfts- und Wegzeiten, die sich beim Ändern sofort anpassen
- **Aufenthalt:** steht standardmäßig auf 0 – nur bei Zwischenstopp (10 Min.), Abholen (5 Min.) und Pause (20 Min.) gibt es einen Startwert. Beim Wechsel der Kategorie wird ein solcher Startwert nicht mitgenommen
- **Aufenthalt „Ende fest“:** Danach geht es wirklich weiter – wie bei der Haltestelle rücken alle flexiblen Zeiten danach nach vorne (z. B. „Ankommen“ bei der nächsten Station), feste Uhrzeiten bleiben.
- **Name statt „Los um“:** Ist die erste Station ohne Weg dorthin erreichbar (Zeit bis hierhin „–“), steht oben ihr Name (z. B. „Treffen Hbf“) statt „Los um“
- **„Los“ übernimmt:** Liegt zwischen dem automatischen „Los“ und der ersten Station keine Zeit (Zeit bis hierhin „–“), entfällt die automatische Zeile „Los“ und diese Station ist der Startpunkt (Countdown, Kalender-Beginn). Eine Station der Kategorie „Los“ bekommt den Pfeil, andere behalten ihr Symbol
- Mit **+** zwischen zwei Stationen lässt sich dort eine neue einfügen (ganz oben eine Vorbereitung)
- **Verspätungen – drei Schnellwahlen:** (1) **zwischen zwei Stationen** (⏱ im Zwischenraum, in den Einstellungen): „so viele Minuten später unterwegs“ – Stau, später losgekommen, Bus/Bahn kommt später an. Ab da rücken flexible Zeiten nach hinten, feste Uhrzeiten bleiben (dort wird der Puffer kleiner, reicht er nicht, warnt die App). (2) **später losgekommen** – im Zwischenraum nach dem automatischen „Los“ gibt es zwei Knöpfe: ⏱ **Los** (später losgekommen) und ⏱ **an** (unterwegs aufgehalten, später angekommen); überall sonst genügt ein Knopf: Die Los-Zeit oben und im Ablauf wird ersetzt, alles danach rückt nach hinten. (3) **an Haltestelle/Abflug** („Verspätung: Abfahrt/Abflug“, auch zugeklappt): Bus, Bahn oder Flug fährt später ab. „Los“ und alles davor bleiben wie geplant. Im Ablauf werden die betroffenen Uhrzeiten durchgestrichen und durch die neuen in **Rot** ersetzt, dazu „+10 Min.“ neben dem Namen
- **Drucken auf iPhone/iPad als Web-App:** Apple erlaubt in Home-Bildschirm-Web-Apps kein Drucken (der Druck-Dialog öffnet sich dort nicht). Die App zeigt stattdessen einen Hinweis: „Teilen“ schickt den Ablauf als Bild (A4) ins Teilen-Menü, dort „Drucken“ wählen; alternativ Link kopieren und in Safari öffnen
- **Ohne feste Uhrzeit:** Hat keine Station eine feste Uhrzeit, rechnet die App von der letzten Station rückwärts. Statt Uhrzeiten steht dann überall, wie viel vorher (z. B. „0:45“ mit „vorher“ darunter = 45 Min. vor der letzten Station; im Notiztext „0:45 vorher“). Die letzte Station steht ohne Zeit direkt an der Linie. Countdown und Kalenderdatei gibt es dann nicht
- **Symbol wählbar:** Bei „Individuell“ lässt sich das Symbol im Fortschrittsbalken aussuchen (Punkt, Zielflagge, Pfeil, Kalender, Bus, Tasse, Haus, Stern, Einkaufen, Sport, Buch, Herz, Ort …), bei „Ankunft“ zwischen Pfeil auf Strich und Zielflagge (Link-Kürzel `x`, ab 16: Nummer des Symbols)
- **„ca.“ bei fester Uhrzeit:** Neben „Fest um“ lässt sich „ca.“ anhaken (z. B. Ende eines Spiels). Die Uhrzeit und die Zeiten, die davon abhängen, erscheinen dann mit „ca.“ (Link-Kürzel `x`, Bit 8)
- **Erwartete Ankunft:** Passt eine feste Uhrzeit nicht mehr (Verspätung oder zu knapp geplant), steht unter der gelben Uhrzeit in Rot „erwartet 18:10“ und beim Namen ein rotes Kästchen „10 Min. zu spät“, ebenso im Hinweis oben. Ohne feste Uhrzeit verschiebt eine Verspätung die letzte Station; dort steht „Verspätung erwartet: voraussichtlich … später da“
- **Verspätungen im Notiztext:** eine eigene Zeile „Verspätung: …“ nennt, wo sie entsteht (z. B. „20 Min. später los“, „unterwegs zu Bäcker +10 Min.“, „Abfahrt Bus +5 Min.“) und was daraus folgt („Termin 9 Min. zu spät (erwartete Ankunft 18:09 Uhr)“); verschobene Zeilen nennen zusätzlich die geplante Zeit
- **Aufteilungsbalken:** Ist die Vorbereitung ausgeblendet (per Knopf oder automatisch, weil sie vorbei ist), fehlt sie auch im Balken und in der Gesamtzeit
- **Früher dran (Minuszeiten):** Die Verspätungs-Knöpfe zwischen den Stationen (und „Los“ nach den Vorbereitungen) bieten auch Minuszeiten (−1 bis −60 Min.). Flexible Zeiten rücken dann nach vorne und werden **grün** angezeigt (alte Zeit durchgestrichen, grünes Kästchen „−10 Min.“); vor festen Uhrzeiten wächst der Puffer. Im Notiztext steht „Früher dran: 10 Min. früher los …“. Auch „Bin da“ trägt Früher-da-sein so ein (Link: `v1010` = 10 Min. früher)
- **Unterwegs-Modus** (Ortsmarke oben): Im Ablauf erscheinen Knöpfe „Bin los“ bzw. „Bin da“, bei der Haltestelle „Abgefahren“ und „Angekommen“ (in einem gemeinsamen Rahmen; auf schmalen Handys untereinander). Antippen vergleicht die aktuelle Uhrzeit mit der geplanten und trägt die Abweichung automatisch als Verspätung ein („später los“ bzw. Verspätung auf dem Weg zu dieser Station) – mit „Rückgängig“. Früher da verringert eine eingetragene Verspätung. Nur mit fester Uhrzeit und am Tag des Termins
- **Erinnerungen** (Glocke beim Ablauf): Benachrichtigung zum Vorbereiten, 5 Min. vor „Los“ und zu „Los“. Funktioniert, solange die App geöffnet ist (am besten zusammen mit „Display anlassen“); auf iPhone/iPad nur als Web-App vom Home-Bildschirm (ab iOS 16.4). Zuverlässige Erinnerungen auch bei geschlossener App gibt es über „In den Kalender“
- **Station gelöscht?** Unten erscheint kurz „Rückgängig“
- **„Display anlassen“** (neben „Ablauf“): Das Display geht nicht aus, solange der Zeitplan offen ist; nochmal tippen schaltet es wieder ab. Der Knopf erscheint nur, wenn der Browser das kann (z. B. Chrome, Edge, Safari ab iOS 16.4)
- **Link teilen mit Kurzinfo** (Knopf „Teilen“): Vor dem Link steht automatisch, worum es geht – Titel, Termin mit Datum und Uhrzeit, „Los um …“ (ggf. „vorbereiten ab …“) und die Stationen unterwegs. WhatsApp zeigt diesen Text über der Link-Vorschau. Die Vorschau-Karte selbst (Titel, Beschreibung, Bild aus den `og:`-Angaben in `index.html`) ist für alle Links gleich, weil WhatsApp die Seite ohne den #-Teil und ohne JavaScript abruft. Tipp: Bei `og:image` die volle Adresse eintragen, z. B. `https://<benutzername>.github.io/termin-planer/icon-512.png` – manche Apps zeigen das Bild sonst nicht
- **Farben der Uhrzeiten:** feste Uhrzeiten in einem gelben, abgerundeten Kasten, verschobene (verspätete) Uhrzeiten rot, berechnete schwarz
- Stationen lassen sich mit ↑ und ↓ umsortieren und mit ✕ entfernen
- **Link zur Route** (optional), z. B. aus Google Maps oder Apple Karten über „Teilen“ kopiert. In der App erscheint dann der Button „Route öffnen“
- Notiztext mit oder ohne Symbole, mit oder ohne Link

Die App rechnet von den Stationen mit fester Uhrzeit aus rückwärts bzw. vorwärts. Liegen zwei feste Uhrzeiten hintereinander, zeigt sie den Puffer – oder warnt, wenn es zu knapp wird. Die letzten Einstellungen merkt sich der Browser.

### Beispiel für den Notiztext

```
Termin: Elternabend 7b
Datum: Donnerstag, 03.12.2026

Vorbereiten: 14:15 Uhr (15 Min.)
Los: 14:30 Uhr (Weg 15 Min.)
Zwischenstopp Bäcker: 14:45 Uhr (Aufenthalt 10 Min.)
Weiter: 14:55 Uhr (Weg 25 Min.)
Termin: 15:20 Uhr
Beginn: 15:30 Uhr

Route: https://maps.app.goo.gl/AbC123xyz

Zeitplan öffnen: https://<benutzername>.github.io/termin-planer/#ztb14y15b3n15y10b6n25b2u1530n10d20261203r1.Elternabend%207b.https%3A%2F%2Fmaps%2Eapp%2Egoo%2Egl%2FAbC123xyz..B%C3%A4cker
```

Tippt man im Kalender auf den Link, öffnet sich die App mit dem kompletten Zeitplan – inklusive Titel, Datum, Stationen und Route. Links aus älteren Versionen der App funktionieren weiterhin.

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
| `m` | `m0` = Vorbereitungen ausgeblendet | `m0` |
| `p` / `c` | nur in älteren Links: Vorbereitungszeit – wird beim Öffnen zur Station „Vorbereitung“ | `p15` |
| `b` | neue Station: 2 Beginn, 3 Zwischenstopp, 4 Individuell, 5 Rückweg, 6 Termin, 7 Abholen, 8 Haltestelle, 9 Pause, 10 Bringen, 11 Treffen, 12 Abflug, 13 Ankunft, 14 Vorbereitung, 15 Los (0 und 1 aus älteren Links werden zu Termin) | `b6` |
| `u` | feste Uhrzeit der Station (hhmm) | `u1400` |
| `n` | Minuten nach der vorherigen Station (Wegzeit) | `n30` |
| `y` | Aufenthalt in Minuten | `y10` |
| `e` | zuvor ankommen (Minuten vor der Uhrzeit der Station) | `e15` |
| `o` | Gründe fürs Früher-da-sein als Summe: 1 Parkplatzsuche · 2 Fußweg vom Parkplatz · 3 Puffer · 4 Treffpunkt · 5 Anmeldung · 6 Einlass · 7 Einchecken · 8 Sicherheitskontrolle · 9 Ticket holen · 10 Garderobe · 11 Umziehen · 12 Aufwärmen · 13 Platz suchen · 14 Material aufbauen – jeder Grund n zählt 2^(n−1), z. B. Parkplatzsuche + Fußweg = 1 + 2 = 3 | `o3` |
| `z` | Haltestelle: Ankunft nach der Fahrt (hhmm) | `z0805` |
| `a` | Haltestelle/Abflug: Verspätung der Abfahrt in Minuten | `a10` |
| `v` | Verspätung auf dem Weg zu dieser Station in Minuten (nach Haltestelle/Abflug: spätere Ankunft); vor der ersten Station: so viele Minuten später losgekommen. Ab 1000: so viel früher (`v1005` = 5 Min. früher) | `v10` |
| `x` | Bits (addiert): 1 = Zeit bis hierhin ca., 2 = Aufenthalt ca., 4 = Aufenthalt „Ende fest“, 8 = feste Uhrzeit ca.; dazu 16 × Nummer des gewählten Symbols | `x4` |
| `l` | Details vorhanden – sie stehen hinter den Beschreibungen (und ggf. den eigenen Gründen) | `l1` |
| `t` | eigene Gründe vorhanden – sie stehen dann hinter den Beschreibungen der Stationen | `t1` |
| `d` | Datum (jjjjmmtt) | `d20261203` |
| `w` | Wiederholung: 1 täglich, 2 werktags, 3 wöchentlich, 4 monatlich, 5 jährlich | `w3` |
| `k` | Wochentage bei wöchentlich (Mo = 1, Di = 2, Mi = 4 … So = 64, addiert) | `k6` |
| `i` | Symbole im Notiztext an | `i1` |
| `r` | Route-Link vorhanden (steht hinter dem Titel) | `r1` |
| `f` / `s` | Puffer für den Weg zur Station in Minuten / in Prozent | `f10`, `s20` |
| `g` / `h` | nur in älteren Links: Puffer für alle Wege – wird beim Öffnen auf die Stationen verteilt | `g10` |

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

## Versionen

Ganz unten in der App steht die Versionsnummer; antippen zeigt die Änderungen der letzten Versionen. Format **Hauptversion.Unterversion** (z. B. 3.9): Bei einer größeren Änderung (neue Funktion, neues Konzept) steigt die erste Zahl und die zweite beginnt bei 0 (3.9 → 4.0), bei einer kleinen Änderung (Korrektur, Feinschliff) steigt die zweite Zahl (3.9 → 3.10). Bei jeder neuen Version `APP_VERSION` und die Liste `CHANGES` in `index.html` sowie `CACHE` in `sw.js` (gleiche Nummer) anpassen.
