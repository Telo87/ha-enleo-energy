# ENLEO-Energy – Dokumentation

> 🧪 **Testphase:** ENLEO-Energy prognostiziert, plant und empfiehlt – es **steuert den Speicher noch nicht**.
> Die automatische Steuerung folgt, sobald die Auswertungen über einen längeren Zeitraum zeigen, dass Prognose
> und Planung verlässlich sind. Bis dahin ändert das Add-on nichts an deiner Anlage.

ENLEO-Energy sammelt PV-Prognosen mehrerer Wetterdienste, vergleicht sie mit der tatsächlichen Erzeugung deiner
Anlagen und lernt daraus eine eigene Prognose. Zusammen mit der Verbrauchsprognose und den dynamischen
Strompreisen entsteht ein Fahrplan für den Heimspeicher; jede Empfehlung wird festgehalten und mit den Messwerten
nachgerechnet.

## Erste Schritte

1. Add-on starten und **Web-UI öffnen**.
2. Unter **Einstellungen › PV-Anlagen** für jeden Messsensor, meist einen Wechselrichter, eine Anlage anlegen:
   - **Messsensor:** Sensor des Wechselrichters, z. B. die AC-Leistung (W) oder der Energiezähler (kWh).
   - **Teilflächen:** eine Zeile pro Ausrichtung mit Leistung (kWp), Neigung (0° = flach, 90° = senkrecht) und Ausrichtung (Ost, Süd, West … oder genau in Grad, 90° = Ost, 180° = Süd, 270° = West).
3. Unter **Strompreis** die festen Preisbestandteile deines Tarifs eintragen (siehe unten).
4. Optional unter **Sensoren & Standort** Hausverbrauch, Netzleistung und Batterie auswählen.

Nach dem Speichern lädt ENLEO-Energy im Hintergrund:

- die **Messwerte der letzten 90 Tage** aus der Langzeitstatistik von Home Assistant,
- das **Prognose-Archiv** der Wettermodelle für denselben Zeitraum.

Die Seite **Prognosegüte** zeigt damit schon nach wenigen Minuten, welche Quelle bei dir am
genauesten ist. Er muss nicht erst wochenlang Daten sammeln.

## Systemprüfung

Die Seite **Systemprüfung** (unter Verwaltung) prüft, ob alles vorhanden und plausibel ist, und verlinkt zur
passenden Einstellung. Geprüft werden unter anderem:

- ob die gewählten Sensoren existieren, die richtige Einheit und eine Langzeitstatistik haben und aktuelle Werte liefern,
- ob die gemessene Höchstleistung jeder PV-Anlage zur eingetragenen kWp-Leistung passt,
- ob die **Vorzeichen** stimmen: bei großem PV-Überschuss muss die Netzleistung Einspeisung zeigen und die Batterie laden,
- ob Aufschlag, Mehrwertsteuer, Einspeisevergütung und Batteriedaten in einem üblichen Bereich liegen,
- ob die **Energiebilanz** der letzten 14 Tage aufgeht: PV + Netzbezug − Einspeisung − Hausverbrauch muss
  ungefähr dem entsprechen, was in den Akku ging, plus dessen Verluste – im Mittel also leicht positiv.
  Geht sie nicht auf, misst ein Sensor zu viel oder zu wenig oder hat Lücken.

Gibt es Probleme, zeigt das Menü deren Anzahl und die Übersicht einen Hinweis.

**Diagnose-Export** (oben auf der Seite Systemprüfung) lädt eine ZIP-Datei herunter: die Datenbank des
Add-ons (alle Prognosen, Messwerte, Preise und die festgehaltenen Empfehlungen), die Einstellungen ohne Solcast-Schlüssel und
den aktuellen Zustand (Plan mit Erklärung, Live-Werte, gelernte Gewichte, Status der Datenquellen). Damit lässt
sich alles außerhalb von Home Assistant nachrechnen, etwa für eine ausführliche Fehlersuche. Die Datei enthält
den Standort und stündliche Verbrauchs- und Erzeugungswerte – nur weitergeben, wem du das anvertraust.

## Messsensor

Der Sensor braucht eine **Langzeitstatistik**, also ein Attribut `state_class`. Die
Die meisten Wechselrichter-Integrationen setzen das automatisch. Im Auswahlfeld sind Sensoren
ohne Statistik markiert. Unterstützt werden:

- Leistung in W oder kW (ENLEO-Energy nutzt den Stundenmittelwert),
- Energie in Wh oder kWh (Zählerstand, ENLEO-Energy nutzt die Änderung pro Stunde).

### Ost-West-Anlagen und mehrere Ausrichtungen an einem Wechselrichter

Zeigt ein String nach Osten und einer nach Westen, der Wechselrichter meldet aber nur einen
Gesamtwert, legst du **eine** Anlage mit diesem Sensor an und trägst **zwei Teilflächen** ein
(Ost und West, jeweils mit ihrer kWp-Leistung). ENLEO-Energy rechnet jede Teilfläche einzeln und
vergleicht die Summe mit dem Sensor. Die Wechselrichter-Grenze (Erweitert) gilt dabei für die Summe.

Liefert der Wechselrichter die Strings einzeln (z. B. Spannung und Strom je MPPT-Eingang), kannst du
in Home Assistant je String einen Leistungssensor anlegen und daraus zwei getrennte Anlagen machen.
Dann zeigt die Prognosegüte sogar, welches Modell Osten und Westen jeweils besser trifft.

## Prognosequellen

| Quelle | Kosten | Zeitraum | Archiv |
|---|---|---|---|
| Open-Meteo: DWD ICON-D2, ICON-EU, ECMWF, GFS, Météo-France, KNMI Harmonie, DMI Harmonie, UK Met Office, „Auto“ | kostenlos | bis 3 Tage | ja |
| Forecast.Solar | kostenlos (12 Abrufe/Stunde, ein Abruf je Teilfläche) | heute + morgen | nein |
| Solcast (Hobby-Zugang) | kostenlos mit Anmeldung (10 Abrufe/Tag) | 3 Tage | nein |

Bei den Open-Meteo-Modellen berechnet ENLEO-Energy die PV-Leistung selbst. Die Global- und
Diffusstrahlung wird auf die Modulebene umgerechnet (Hay-Davies-Modell, Sonnenstand in
10-Minuten-Schritten), danach werden Temperaturverluste und der Systemwirkungsgrad abgezogen. Wenn du
die Teilflächen einer Anlage änderst, berechnet ENLEO-Energy alle gespeicherten Prognosen
sofort neu.

Standardmäßig sind alle Modelle außer UK Met Office aktiv – dessen Feinmodell deckt nur Großbritannien ab.
KNMI Harmonie und DMI Harmonie rechnen wie ICON-D2 mit 2 km Auflösung und decken Mitteleuropa bzw.
Nordwesteuropa ab. Welches Modell an deinem Standort am besten trifft, zeigt die Prognosegüte; schwache
Modelle kannst du abschalten, das Lernmodell gewichtet sie ohnehin nach ihrem bisherigen Fehler.

**Solcast einrichten:** Unter Einstellungen › Prognosequellen führt der Knopf „Anleitung“ durch die
Anmeldung (Hobby-Zugang, kostenlos, bis 2 Dachflächen) und zeigt für jede Anlage die Werte, die du bei
Solcast einträgst – mit dem Azimut schon in der Zählweise von Solcast (Norden 0°, Osten −90°, Westen 90°,
Süden 180°). Danach die Resource-ID bei der PV-Anlage und den API-Schlüssel bei den Prognosequellen eintragen.

### Prognose-Horizonte

Jede Prognose wird für jede Stunde in zwei Varianten gespeichert:

- **Vortag:** die letzte Prognose, die vor Mitternacht vorlag. Auf ihr beruht die Planung für den nächsten Tag, z. B. ob die Batterie nachts günstig aus dem Netz geladen wird.
- **Kurz vorher:** die letzte Prognose, bevor die Stunde begann.

## Eigene Prognose „ENLEO-Energy (lernend)“

ENLEO-Energy baut aus allen Quellen eine eigene Prognose je Anlage:

1. **Gewichtung:** Jede Quelle zählt umso mehr, je kleiner ihr Fehler bei dieser Anlage in den letzten
   30 Tagen war – getrennt nach erwarteter Wetterlage.
2. **Korrektur je Uhrzeit, getrennt für Sonne und Wolken:** Schatten von Bäumen oder Nachbarhäusern
   wirkt nur bei direkter Sonne; systematische Fehler der Wettermodelle zeigen sich auch bei Bewölkung.
3. **Spanne (80 %):** aus der Verteilung der bisherigen Fehler in derselben Wetterlage – so eingestellt, dass
   die Erzeugung in 8 von 10 Stunden innerhalb des grauen Bandes liegt (an echten Daten nachgeprüft).

Gelernt wird **jede Stunde neu** und rückwirkend Tag für Tag nur aus den Tagen davor. In der Prognosegüte
tritt sie daher fair gegen die Wetterdienste an.

### Live-Korrektur

Die gemessene PV-Leistung der letzten Stunde wird mit der Prognose verglichen. Die Abweichung korrigiert
die laufende Stunde (40 %), die nächste (20 %) und die übernächste (10 %). Stärkere Gewichte reagieren an
echten Daten zu sehr auf einzelne Wolken und machen die Prognose schlechter. In der Prognosegüte erscheint
sie unter „kurz vorher“ als „ENLEO-Energy (live korrigiert)“; der Planer rechnet damit.

### Ausrichtung prüfen

Unter Einstellungen › PV-Anlagen berechnet „Ausrichtung prüfen“ aus den klaren Stunden (Sonnenhöhe über
20°), welche Ausrichtung und Neigung am besten zur gemessenen Tageskurve passen – verglichen wird nur die
Form, nicht die Höhe. Eine falsch eingetragene Ausrichtung macht alle Wetterdienst-Prognosen ungenauer;
der Vorschlag lässt sich mit einem Klick übernehmen.

Die Prüfung läuft außerdem **automatisch einmal pro Woche** für jede Anlage mit Messsensor. Das Ergebnis steht in
der Liste unter der Anlage und in der Systemprüfung; ein Hinweis erscheint nur, wenn die Messwerte zu einer anderen
Ausrichtung deutlich besser passen (mindestens 5 % weniger Abweichung). Übernommen wird nichts von selbst.

Nicht jede Anlage lässt sich so prüfen: Bei manchen Belegungen – vor allem flach und zu gleichen Teilen nach Ost und
West – ändert eine Drehung die Tageskurve kaum, die Messwerte passen dann zu vielen Ausrichtungen gleich gut. In
diesem Fall steht dort „Ausrichtung aus den Messwerten nicht bestimmbar“; die eingetragenen Werte bleiben, und der
Systemwirkungsgrad wird trotzdem verglichen.

Dieselbe Prüfung vergleicht den **Systemwirkungsgrad**: wie hoch die gemessene Kurve in klaren Stunden gegenüber
der berechneten liegt. Der Wert fasst alle Verluste zwischen Modul und Zähler zusammen (Wechselrichter, Kabel,
Verschmutzung, Alterung) – und auch Abweichungen der eingetragenen Leistung oder des Wettermodells. Er lässt sich
deshalb nur auf einige Prozentpunkte genau bestimmen; ein Hinweis erscheint ab 5 Punkten Abweichung. Die lernende
Prognose gleicht einen unpassenden Wert ohnehin aus – mit dem passenden liegen aber auch die einzelnen Wettermodelle
näher an der Messung.

## Verbrauchsprognose

Aus Hausverbrauch minus E-Auto minus Heizstab (Einstellungen › Sensoren) ergibt sich der
**Grundverbrauch**. Er wird nach Uhrzeit für Werktage und für Wochenenden/Feiertage gelernt (bundesweite
Feiertage des in Home Assistant eingestellten Landes), jüngere Wochen zählen mehr; hängt der Verbrauch
erkennbar von der Außentemperatur ab, wird das berücksichtigt. Zusätzlich folgt die Prognose zur Hälfte dem
Verbrauchsniveau der letzten drei Tage – etwa wenn Besuch da ist oder ein neues Gerät läuft. E-Auto und
Heizstab sind steuerbar und werden später gezielt eingeplant. Vergleichsmaßstab in der Prognosegüte
(Auswahl „Grundverbrauch“) ist „Wie vor einer Woche“.

## Planung

Die Seite **Planung** rechnet alle 5 Minuten den günstigsten Fahrplan für den Heimspeicher bis zum Ende
der bekannten Strompreise (die Preise für morgen erscheinen gegen 13 Uhr). **„Warum dieser Plan?“** erklärt
jede Entscheidung aus dem aktuellen Plan: was ohne Eingriff passieren würde (wann der Akku leer wäre und was
Netzstrom danach kostet), für welche Stunden gehaltene oder gekaufte Energie aufgehoben wird und was das je
kWh bringt – oder, wenn der Akku im Normalbetrieb bleibt, warum sich kein Eingriff lohnt. Im Stundenplan
steht die Begründung beim Überfahren einer Stunde. Für jede Stunde gibt es drei Möglichkeiten:

| Modus | Bedeutung |
|---|---|
| Normalbetrieb | Der Akku arbeitet wie gewohnt: PV-Überschuss laden, Verbrauch decken |
| Akku halten | Der Akku wird nicht entladen – die Energie wird für spätere, teurere Stunden aufgespart |
| Aus dem Netz laden | Günstiger Netzstrom wird eingespeichert, weil er später teureren Netzstrom ersetzt |

Grundlage sind die genaueste PV-Prognose, die Verbrauchsprognose (ohne E-Auto und Heizstab), der
aktuelle Ladezustand, die Akku-Daten (Einstellungen › Batterie) und die Strompreise. Energie, die am
Ende noch im Akku ist, wird mit einem vorsichtigen Preis bewertet, damit der Plan den Akku nicht
künstlich leerfährt. Umgeschaltet wird nur, wenn es über den ganzen Zeitraum mindestens 1 ct spart.

Mit der Einstellung **Vorsicht beim PV-Ertrag** (Einstellungen › Batterie) rechnet der Planer mit weniger Sonne, als die eigene
Prognose sagt. Wie viel, lernt ENLEO-Energy aus ganzen Tagen: „Hoch“ nimmt den Tagesertrag an, der nur an einem
von zehn Tagen unterschritten wird, „Mittel“ die Hälfte dieses Abschlags. Der Abschlag gilt für den ganzen Tag, weil
sich Abweichungen einzelner Stunden über den Tag weitgehend ausgleichen – die Summe der unteren Stundengrenzen wäre
ein Tag, den es praktisch nie gibt. Für heute und morgen wird er getrennt bestimmt (die Prognose für heute ist
genauer). Solange weniger als 14 vergleichbare Tage vorliegen, gilt die untere Grenze der Stundenspanne. So bleibt der
Akku eher für den Abend gefüllt, wenn der Tag trüber wird als erwartet.

Die **Reichweite** zeigt, wie lange der Akku beim aktuellen Hausverbrauch bis zum Mindest-Ladestand reicht, und
wann er laut Prognose (mit PV-Erzeugung) leer bzw. wieder voll ist.

ENLEO-Energy **steuert den Akku noch nicht** – der Plan ist eine Empfehlung, die du in der Oberfläche siehst.
Entitäten in Home Assistant legt ENLEO-Energy nicht an.

## Kosten

Die Seite **Kosten** rechnet aus dem gemessenen Netzbezug jeder Stunde und dem Preis dieser Stunde (Mittel
der Viertelstundenpreise) die tatsächlichen Stromkosten – pro Tag und Monat, plus anteilige Grundgebühr,
abzüglich Einspeisevergütung (Einstellungen › Strompreis). Dazu:

- **Eigene Einspeisevergütung je Anlage** (bei der PV-Anlage, optional): Hängen Anlagen mit unterschiedlicher
  Vergütung an einem Zähler, wird die eingespeiste Energie aufgeteilt – nach Anlagenleistung (kWp, wie es
  Netzbetreiber meist tun) oder nach der gemessenen Erzeugung jeder Anlage in der jeweiligen Stunde
  (Einstellungen › Strompreis › „Einspeisung aufteilen“).

- **Ø bezahlter Preis** gegenüber dem Durchschnitt aller Viertelstunden: liegt er darunter, wird eher in
  günstigen Stunden gekauft – genau das sollen Akku und Planung bewirken.
- **Vergleich mit einem anderen Tarif**, wahlweise:
  - **Festpreis** mit Arbeits- und Grundpreis, oder
  - **Flat mit Freistrom**: Grundgebühr, Freistrom-Kontingent pro Jahr, Preis über dem Kontingent,
    eigene Einspeisevergütung und Beginn des Abrechnungsjahres. Das Kontingent wird ab Beginn des
    Abrechnungsjahres fortlaufend mit dem gemessenen Netzbezug verbraucht; für Tage ohne Messwerte wird der
    anteilige Freistrom als verbraucht angesetzt. Die Kosten-Seite zeigt, wie viel davon schon verbraucht ist
    und wie lange der Rest voraussichtlich reicht.
- **Autarkie** (Anteil des Hausverbrauchs aus eigener Erzeugung) und **Eigenverbrauch** (Anteil der
  PV-Erzeugung, der nicht eingespeist wird).

Am genauesten wird es mit eigenen Sensoren für **Netzbezug** und **Einspeisung** (Einstellungen ›
Sensoren – viele Speicher und Smartmeter liefern beide Werte getrennt). Mit nur einer Netzleistung mit
Vorzeichen heben sich Bezug und Einspeisung innerhalb einer Stunde gegenseitig auf.

## Wirkungsgrad des Speichers

Der Wirkungsgrad „Laden + Entladen“ sagt, wie viel von einer geladenen kWh wieder herauskommt. Er entscheidet,
ab welchem Preisunterschied sich Laden aus dem Netz lohnt. Datenblätter nennen oft den besten Fall; im Alltag
liegt der Wert meist niedriger, weil der Speicher selbst Strom braucht.

Ist ein Sensor für die Akku-Leistung eingetragen, misst ENLEO-Energy den Wert selbst: geladene gegen entladene
Energie der letzten bis zu 90 Tage, sobald das 15-Fache der Kapazität durch den Akku gegangen ist. Das Ergebnis
steht unter Einstellungen › Batterie neben dem Feld und in der Systemprüfung. Übernommen wird es nicht von selbst.

Genauso misst ENLEO-Energy die **nutzbare Kapazität**: wie viel Energie für 100 % Ladestand hineingeht und wie viel
wieder herauskommt, aus den Stunden, in denen sich der Ladestand deutlich bewegt hat. Der Wert erscheint, sobald der
Akku zusammen etwa dreimal geladen und entladen wurde. Ist die eingetragene Kapazität zu hoch, hält der Akku im Plan
länger als in Wirklichkeit.

## Regelung des Speichers

Kein Speicher folgt dem Haus ohne Verzögerung. Während der Akku das Haus versorgt, bleibt ein kleiner Netzbezug
(oft 20–50 Wh pro Stunde), und ein wenig fließt ins Netz – umso mehr, je höher und unruhiger der Verbrauch ist.
Während er aus dem PV-Überschuss lädt, geht ein kleiner Teil an ihm vorbei ins Netz.

ENLEO-Energy lernt das selbst aus den Messwerten der letzten zwei Wochen, getrennt für beide Fälle: aus den Stunden
ohne PV, in denen der Akku für die ganze Stunde reichte, und aus den Stunden, in denen der Überschuss den noch nicht
vollen Akku geladen hat. Für jeden Fall entsteht ein Grundwert und ein Anteil, der mit der Energie wächst, die der
Akku gerade liefert oder aufnimmt. Stunden, in denen das E-Auto lädt, bleiben außen vor.

Das Gelernte steht im Plan (Netzbezug in den Stunden, in denen der Akku arbeitet) und in der Nachrechnung auf der
Seite Ersparnis. An den Empfehlungen ändert es nichts, weil es mit und ohne Plan gleich anfällt. Zeigt die Anlage
weniger als 5 Wh pro Stunde oder gibt es weniger als zwölf passende Stunden, nimmt ENLEO-Energy nichts an –
einstellen muss man dafür nichts.

## Heizstab mit Überschuss-Regelung

Ein Heizstab mit eigener Regelung, der nur PV-Überschuss nutzt (Einstellungen › Sensoren & Standort), nimmt nie
Strom aus Akku oder Netz – an den Empfehlungen für den Akku ändert er nichts. Er verringert aber die Einspeisung.
ENLEO-Energy lernt aus den Messwerten der letzten zwei Wochen, welchen Anteil des Überschusses er zu welcher Tageszeit
aufnimmt (bis zur eingetragenen maximalen Leistung), und zieht diesen Anteil im Plan von der Einspeisung ab. Wann
der Pufferspeicher voll ist, steckt damit in den Messwerten; ein Temperaturfühler ist nicht nötig.

## Plan gegen Messung

*Zu finden unter **Auswertung** – die vier Reiter Prognosegüte, Plan gegen Messung, Ersparnis und Kosten stehen dort unter der Kopfzeile.*

Vergleicht für einen Tag den Plan mit der Wirklichkeit: Was ENLEO-Energy zu Beginn jeder Stunde erwartet hat
(Prognose für PV und Grundverbrauch und was daraus für Akku und Netz folgt) gegen das, was in der Stunde gemessen
wurde. Für PV-Erzeugung, Grundverbrauch, Netzbezug, Einspeisung und Akku-Ladestand gibt es je ein Diagramm
(Balken = gemessen, Linie = Plan) und oben die Tagessummen mit Abweichung. Verglichen werden nur vollständige
Stunden. Stunden, in denen der Plan den Akku pausiert („Akku halten“) oder aus dem Netz lädt, sind in den
Diagrammen farbig hinterlegt.

Mit **„Plan vom“** wählst du, wie weit im Voraus der Plan gemacht wurde: zu Beginn jeder Stunde, kurz nach
Mitternacht für den ganzen Tag („vom Tagesbeginn“) oder am Vortag, sobald der Plan den Tag zum ersten Mal enthielt
(meist gegen 13 Uhr, wenn die Preise für morgen kommen). Je weiter im Voraus, desto größer die Abweichung – das
zeigt, wie verlässlich die Planung über Nacht und für den nächsten Tag ist. „vom Tagesbeginn“ und „vom Vortag“ gibt es
ab dem ersten Tag nach der Einrichtung.

Der Plan kennt den Grundverbrauch und den üblichen Anteil eines Überschuss-Heizstabs; das E-Auto ist nicht planbar.
Lädt das Auto oder läuft der Heizstab anders als üblich, weichen Netzbezug, Einspeisung und Akku vom Plan ab; die gemessenen Mengen stehen in der
Erklärung auf der Seite. Solange ENLEO-Energy den Akku nicht steuert, zeigt der Plan bei „Akku halten“ und „Aus dem
Netz laden“, was passiert wäre, wenn die Empfehlung befolgt worden wäre.

## Ersparnis

*Zu finden unter **Auswertung** – die vier Reiter Prognosegüte, Plan gegen Messung, Ersparnis und Kosten stehen dort unter der Kopfzeile.*

Jede Stunde hält ENLEO-Energy fest, was es zu Beginn der Stunde empfohlen hat – mit Preis, PV- und
Verbrauchsprognose sowie geplantem und gemessenem Ladezustand. Sobald die Messwerte der Stunde da sind,
rechnet es für jeden Tag drei Stromrechnungen aus den **echten** Werten:

| Rechnung | Bedeutung |
|---|---|
| ohne ENLEO-Energy | Akku im Normalbetrieb – so, wie er tatsächlich lief |
| mit ENLEO-Energy | die Empfehlungen, die aus den Prognosen entstanden, wären befolgt worden |
| optimal | im Nachhinein bestmöglicher Fahrplan mit perfektem Wissen |

„Mit ENLEO-Energy gespart“ kann auch negativ sein, wenn Prognosen danebenlagen. Liegt der Wert über einige Tage
nahe an „optimal“ (Anteil „davon erreicht“ hoch), sind Prognosen und Planung verlässlich genug, um
ENLEO-Energy die Steuerung zu überlassen. Gerechnet wird mit dem gesamten gemessenen Hausverbrauch
einschließlich E-Auto. Ein Heizstab, der nur mit PV-Überschuss läuft (Einstellung beim Heizstab-Sensor),
nimmt in der Nachrechnung nur auf, was sonst eingespeist würde. Zur Kontrolle steht daneben die gemessene
Rechnung aus Netzbezug und Einspeisung.

## Prognosegüte

*Zu finden unter **Auswertung** – die vier Reiter Prognosegüte, Plan gegen Messung, Ersparnis und Kosten stehen dort unter der Kopfzeile.*

| Kennzahl | Bedeutung |
|---|---|
| Genauigkeit | 100 % minus mittlerer Stundenfehler relativ zur Erzeugung |
| Tagesabweichung Ø | mittlerer Fehler beim Tagesertrag relativ zum Tagesertrag |
| Tendenz | systematische Abweichung: + = Prognose zu hoch, − = zu niedrig |
| Größter Tagesfehler | der schlechteste Tag im Zeitraum |

**Nach Wetterlage** teilt die Tage anhand der gemessenen Erzeugung im Verhältnis zu einem
wolkenlosen Tag ein: sonnig ≥ 60 %, wechselhaft 30–60 %, trüb < 30 %. So sieht man, welches Modell
bei welchem Wetter am besten liegt.

**Entwicklung über die Zeit** zeigt die Genauigkeit der eigenen Prognose Woche für Woche neben dem besten
Wettermodell (PV) bzw. „Wie vor einer Woche“ (Verbrauch) auf denselben Stunden. Weil das Wetter bestimmt,
wie schwer eine Woche vorherzusagen ist, zählt der **Vorsprung**: Wächst er, lernt ENLEO-Energy dazu, schrumpft
er, wird die eigene Prognose schlechter. Ein Urteil erscheint nur, wenn die Veränderung deutlich größer ist als
die Schwankung von Woche zu Woche. Vergangene Wochen sind mit dem heutigen Verfahren nachgerechnet – jeweils
nur mit den Daten, die damals vorlagen.

Mit **Nur gemeinsame Stunden** werden alle Quellen auf denselben Stunden verglichen. Das ist fair,
wenn Quellen unterschiedlich lange Daten haben, z. B. Forecast.Solar ohne Archiv.

Eine Quelle bekommt erst dann einen Platz in der Rangliste, wenn sie mindestens 60 % der Tage abdeckt, die die am
besten abgedeckte Quelle hat. Bis dahin steht sie mit „–“ unter den übrigen: Sie wurde an anderen Tagen gemessen und
ist noch nicht vergleichbar. Auch der Plan wählt seine PV-Prognose nur unter den platzierten Quellen.

## Strompreis

Dynamische Stromtarife geben den Börsenpreis (EPEX Day-Ahead, seit Oktober
2025 in Viertelstunden) weiter. ENLEO-Energy lädt ihn von Energy-Charts (Fraunhofer ISE) mit
aWATTar als Ersatzquelle und rechnet den Endpreis so:

```
Endpreis = (Börsenpreis + Aufschlag netto) × (1 + MwSt)
```

Der Aufschlag netto ist die Summe aus Netzentgelt, Umlagen, Stromsteuer und dem Aufschlag des
Anbieters, jeweils in ct/kWh ohne Mehrwertsteuer. Die Werte stehen im Vertrag bzw. auf der Rechnung.

Einfacher geht es mit **„Aufschlag aus einem Preis berechnen“**: einen oder mehrere Gesamtpreise aus der
App des Stromanbieters (viertelstündlicher Preis) mit Tag und Uhrzeit eintragen. ENLEO-Energy
rechnet `Preis ÷ (1 + MwSt) − Börsenpreis` für jede Viertelstunde aus und übernimmt den Mittelwert.

## Als App auf dem Handy (Direktzugriff)

Über Home Assistant bleibt dessen Kopfzeile mit dem Menü immer sichtbar. Wer ENLEO-Energy wie eine eigene
App nutzen möchte, schaltet den Direktzugriff ein (die Anleitung mit dem Stand der einzelnen Schritte steht auch
unter Einstellungen › Handy-App):

1. Add-on › **Konfiguration**: ein **Passwort für den Direktzugriff** eintragen.
2. Auf derselben Seite unter **Netzwerk** in das leere Feld neben „8099/tcp“ eine freie Portnummer eintragen
   (z. B. 8199) und speichern; das Add-on startet neu. Meldet Home Assistant „port … is already in use“, ist die
   Nummer belegt und das Add-on startet nicht – dann eine andere Zahl eintragen und das Add-on wieder starten.
3. Auf dem Handy im Browser `http://<IP-Adresse von Home Assistant>:<Port>` öffnen, z. B.
   `http://192.168.1.20:8199`, und mit dem Passwort anmelden. Die fertige Adresse steht unter Einstellungen ›
   Handy-App. Der Name `homeassistant.local` wird nicht auf jedem Handy und nicht über VPN gefunden.
4. **iPhone (Safari):** Teilen-Symbol › „Zum Home-Bildschirm“. **Android (Chrome):** Menü › „Zum Startbildschirm
   hinzufügen“ bzw. „App installieren“.

Vom Home-Bildschirm startet ENLEO-Energy im Vollbild. Die App fragt das Passwort beim ersten Start noch einmal ab
und merkt es sich dann.

Der Direktzugriff ist unverschlüsselt (http) und nur durch das Passwort geschützt – er ist für das Heimnetz und
für VPN-Verbindungen gedacht. Den Port nicht im Router ins Internet freigeben. Über Home Assistant Cloud ist
er nicht erreichbar; dort bleibt der Weg über die Home-Assistant-App. Ohne Passwort ist der Direktzugriff aus.

## Versionsprüfung

ENLEO-Energy fragt einmal am Tag und nach einem Update, ob es zur installierten Version etwas Wichtiges gibt – etwa einen bekannten
Fehler oder ein dringendes Update. Gibt es einen Hinweis, erscheint er oben in der Übersicht.

Gesendet wird dabei ausschließlich die **Versionsnummer** von ENLEO-Energy. Es gibt keine Kennung der Installation;
Messwerte, Einstellungen, Standort, Namen von Sensoren oder Zugangsdaten werden nicht übertragen. Die IP-Adresse,
die bei jeder Internetverbindung anfällt, wird vom Dienst nicht gespeichert. Gezählt wird nur, wie viele Anfragen
pro Tag und Version eingehen – daraus ergibt sich, wie viele Installationen mit welcher Version laufen.

Abschalten: Einstellungen › System › **Versionsprüfung**. Danach wird nichts mehr gesendet, und es erscheinen
keine Hinweise mehr. Ohne Internetverbindung läuft ENLEO-Energy unverändert weiter.

## Datensicherung und Umzug

Unter Einstellungen › **System** lässt sich der gesamte Bestand einer Installation als eine Datei
exportieren und in einer anderen Installation wieder importieren:

- **Daten exportieren** lädt eine ZIP-Datei herunter. Sie enthält die Datenbank (Messwerte, Prognosen aller Quellen,
  Preise, festgehaltene Empfehlungen und damit alles, woraus gelernt wird) und sämtliche Einstellungen.
- **Daten importieren** ersetzt alle Daten und Einstellungen der Installation durch den Inhalt einer solchen Datei.
  Sie wird vorher geprüft; ist sie beschädigt oder keine Datensicherung, bleibt alles unverändert. Danach startet die
  Berechnung neu.

Die Datei enthält den Standort, stündliche Verbrauchs- und Erzeugungswerte und – falls eingetragen – den
Solcast-Schlüssel. Sie gehört nicht in fremde Hände. Der Diagnose-Export (Seite Systemprüfung) ist etwas anderes: Er
enthält keine Schlüssel und lässt sich nicht importieren.

Eine Datensicherung aus der Vorgängerversion lässt sich ebenfalls importieren – so zieht eine bestehende
Installation mit allen Daten um.
