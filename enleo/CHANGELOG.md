# Changelog

## 0.17.3

- Seite Ersparnis lädt schneller: Abgeschlossene Tage werden nur noch einmal am Tag nachgerechnet, nicht bei jedem Aufruf
- Planung: Die aktuelle Stunde im Fahrplan pulsiert jetzt wirklich – die Animation war seit 0.17.0 ohne Wirkung
- Fünf Kennzahl-Kacheln stehen auf mittelbreiten Bildschirmen als drei und zwei statt vier und einer einzelnen; am Handy füllt eine einzelne letzte Kachel die Zeile
- Planung: negative Stromkosten mit richtigem Minuszeichen

## 0.17.2

**Ersparnis**
- Was um Mitternacht noch im Akku steckt, wird nicht mehr mit einem Schätzpreis bewertet: Die Nachrechnung läuft bis zum nächsten Mittag weiter und zählt, was dieser Rest dort tatsächlich an Netzbezug erspart hat
- „Optimal“ ist nie schlechter als „ohne“ oder „mit ENLEO-Energy“

**Batterie**
- Regelung des Speichers: ENLEO-Energy lernt jetzt getrennt für Entladen und Laden, wie viel Netzbezug und Einspeisung der Speicher übrig lässt, und wie das mit dem Verbrauch wächst – bisher ein fester Wert nur fürs Entladen. Die nachgerechnete Stromrechnung liegt damit näher an der gemessenen
- ENLEO-Energy misst die nutzbare Kapazität des Speichers: wie viel Energie für 100 % Ladestand hineingeht und wieder herauskommt. Der Wert steht unter Einstellungen › Batterie neben dem Feld und lässt sich mit einem Klick eintragen; die Systemprüfung meldet eine Abweichung ab 7 %

**Sonstiges**
- Versionsprüfung: genau eine Anfrage pro Tag und eine nach einem Update – bisher verschob sich der Zeitpunkt täglich um eine Stunde
- „Normalbetrieb“ statt „Eigenverbrauch“ auch auf der Seite Ersparnis, in „Warum dieser Plan?“ und in der Systemprüfung

## 0.17.1

**Ersparnis**
- Der laufende Tag steht als Zwischenstand mit dem Hinweis „läuft noch“ in der Tabelle und zählt erst nach Mitternacht zu Summe und Diagramm – bisher erschien er als Verlust, solange das Geladene oder Aufgehobene noch nicht verbraucht war
- Was am Ende im Akku steckt, wird mit den Preisen des ganzen Tages bewertet, nicht mehr nur mit denen der schon ausgewerteten Stunden

**Messwerte**
- Wechselrichter starten erst bei genug Licht: Eine Stunde ohne PV-Wert direkt nach Sonnenaufgang oder vor Sonnenuntergang zählt als 0, statt als Lücke den Tag zu teilen – in Ersparnis, Plan gegen Messung und Tagesverlauf. Eine Lücke am hellen Tag bleibt unbekannt

## 0.17.0

Die Oberfläche ist aufgeräumt, und mehrere Seiten und Einstellungen heißen jetzt so, dass der Name sagt, was gemeint ist.

**Neue Namen**
- Betriebsart **Normalbetrieb** statt „Eigenverbrauch“ – „Eigenverbrauch“ bleibt die Kennzahl auf der Kostenseite
- Seiten: **Prognosegüte** (bisher Prognose-Check), **Plan gegen Messung** (Plan-Check), **Ersparnis** (Protokoll), **Systemprüfung** (Einrichtung)
- Prognose **vom Vortag** / **kurz vorher** statt „Vortag“ / „Kurzfristig“; Plan **zu jeder Stunde** / **vom Tagesbeginn** / **vom Vortag**
- **Grundverbrauch** überall dort, wo der Verbrauch ohne E-Auto und Heizstab gemeint ist
- Batterie: **Mindest-Ladestand** statt „Reserve“, **Aus dem Netz laden bis** statt „Netzladen bis“, **Vorsicht beim PV-Ertrag** mit den Stufen Aus / Mittel / Hoch
- Rangliste: Spalte **Schätzt** („9 % zu hoch“) statt „Tendenz“

**Aufgeräumt**
- Erklärtexte sind auf allen Geräten eingeklappt und über die Zeile mit dem Info-Symbol erreichbar – bisher standen sie am Desktop als große Kästen zwischen den Zahlen
- Übersicht: die drei genauesten Prognosen statt der ganzen Rangliste; der Zustand aller Datenquellen in einer Zeile, aufgeklappt nur bei einem Problem
- Planung: Kennzahlen stehen oben; Preisdiagramm und Stundentabelle liegen eingeklappt unter „Strompreise und Stundenwerte“; „Reichweite“ und „Akku leer“ sind eine Kachel **Akku reicht**
- Übersicht: Der Satz unter der Empfehlung wiederholt die Betriebsart nicht mehr
- Kennzahl-Kacheln zeigen zwei Zeilen Erläuterung; ein Klick auf die Kachel zeigt den Rest
- Prognosegüte: die Rangliste zeigt Genauigkeit, Tagesabweichung, Schätzt und Tage; drei weitere Fehlermaße über „Alle Spalten“

**Auswertungen an einem Ort**
- Prognosegüte, Plan gegen Messung, Ersparnis und Kosten sind ein Menüpunkt **Auswertung** mit vier Reitern unter der Kopfzeile. Das Menü hat damit sieben statt zehn Einträge; der zuletzt geöffnete Reiter wird gemerkt. Die bisherigen Adressen der vier Seiten gelten weiter

**Bewegung**
- Die Markierung der aktiven Seite gleitet in Menü, Reitern und der Leiste am Handy zum neuen Eintrag
- Beim Laden einer Seite erscheinen Platzhalter in der Form der Kacheln und Diagramme
- Der Akku-Ring füllt sich beim Öffnen der Übersicht bis zum Ladestand und folgt Änderungen weich
- Eine Kachel, deren Zahl sich ändert, leuchtet kurz auf; eingeklappte Bereiche öffnen sich weich; die aktuelle Stunde im Fahrplan pulsiert leicht
- Wer am Gerät „Bewegung reduzieren“ eingestellt hat, sieht wie bisher keine Animationen

**Einstellungen und Handy**
- Handy: Die Einstellungen sind eine Liste der acht Bereiche mit kurzer Beschreibung – bisher waren von der Reiterleiste nur knapp drei Reiter sichtbar, und der aktive rutschte aus dem Bild
- Speichern ist einheitlich: Die Leiste mit „Speichern“ erscheint, sobald etwas geändert wurde – auch bei Batterie, Strompreis und Prognosequellen
- Versionsprüfung und Datensicherung stehen zusammen im Bereich **System**
- Handy: „Mehr“ zeigt nur noch die Seiten, die nicht in der Leiste unten stehen; die Leiste nennt die Seiten wie das Menü
- Handy: Kontrollkästchen und kleine Schaltflächen sind groß genug für den Finger

## 0.16.2

- **Behoben: „Ausrichtung prüfen“ brach mit „Interner Fehler: must be real number, not NoneType“ ab.** Im ausgelieferten, übersetzten Programm wurden Zahlen an Stellen erzwungen, an denen ein Wert fehlen darf – etwa für Stunden ohne Messwert. Dadurch lief auch die wöchentliche automatische Prüfung nicht mehr. Der Build entfernt die Ursache jetzt grundsätzlich, sodass das übersetzte Programm überall so rechnet wie der Quelltext
- **Neue Prognosequellen übernehmen den Plan nicht mehr vorschnell:** Eine Quelle mit nur wenigen Tagen wurde an anderen Tagen gemessen als die übrigen – nach fünf schönen Tagen stand sie auf Platz 1 der Rangliste, und der Plan rechnete mit ihr statt mit der lernenden Prognose. Einen Platz bekommt eine Quelle jetzt erst, wenn sie mindestens 60 % der Tage der am besten abgedeckten Quelle hat; bis dahin steht sie ohne Platz unter den übrigen, und der Plan wählt nur unter den platzierten
- **Sicherheitsabschlag bei der Sonne aus ganzen Tagen gelernt:** Bisher zog der Plan je Stunde einen Anteil der Stundenspanne ab. Über einen Tag gleichen sich Stundenfehler aber weitgehend aus – die Summe der unteren Stundengrenzen lag bei der Hälfte der Prognose, ein Tag, den es praktisch nie gibt. Jetzt lernt ENLEO-Energy aus den letzten 60 Tagen, wie weit der Tagesertrag in einem schlechten Fall (ein Tag von zehn) unter der Prognose liegt, getrennt für heute und morgen. „Vorsichtig“ zieht diesen Anteil ab, „Mittel“ die Hälfte. Der Plan rechnet dadurch mit etwas mehr Sonne als bisher; unter „Warum dieser Plan?“ steht der aktuelle Abschlag in Prozent. Bis 14 vergleichbare Tage vorliegen, gilt die bisherige Rechnung
- Handy: Das Logo steht in der Kopfzeile neben dem Seitentitel
- **Ausrichtungsprüfung ehrlicher:** Bei manchen Belegungen – vor allem flach und zu gleichen Teilen nach Ost und West – ändert eine Drehung die Tageskurve kaum. Die Prüfung meldete dort bisher „Ausrichtung passt“ und nannte im Dialog eine beliebige andere Ausrichtung als „passt am besten“, obwohl sie rechnerisch gleichauf lag. Jetzt steht dort, dass sich die Ausrichtung aus den Messwerten nicht bestimmen lässt. Ohne klaren Vorschlag zeigt der Dialog nur noch die eingetragene Ausrichtung. Alle Anlagen werden nach dem Update einmal neu geprüft
- Einrichtung: Datumsangaben wie „zuletzt am 04.10.“ wurden mit Komma geschrieben („04,10.“)
- Positive Meldungen im Dialog „Ausrichtung prüfen“ sind grün statt orange hinterlegt
- Plan-Check: Erklärtexte verweisen nicht mehr auf Versionsnummern

## 0.16.1

- **Neues Logo „Energiewelle“:** eine blaue Welle mit grünem Punkt – im Add-on-Store, in der Seitenleiste, auf der Anmeldeseite und als Symbol der Handy-App. Wer ENLEO-Energy bereits auf dem Home-Bildschirm hat, sieht das neue Symbol erst nach erneutem Hinzufügen

## 0.16.0

- **Neuer Name: ENLEO-Energy** – der Energie- und Lade-Optimierer. Das Add-on führt die bisherige Entwicklung unter neuem Namen und in einem eigenen Repository fort
- **Umzug einer bestehenden Installation:** Unter Einstellungen › Datensicherung lässt sich eine Datensicherung aus der Vorgängerversion importieren. Messwerte, Prognosen, Lernstand und alle Einstellungen sind danach wie zuvor
- Funktionsumfang wie die letzte Vorgängerversion: PV-Prognose aus mehreren Quellen mit lernendem Modell, Verbrauchsprognose, Fahrplan für den Akku mit dynamischem Strompreis, Plan-Check, Protokoll, Kostenübersicht, Direktzugriff als Handy-App, Datensicherung, Versionsprüfung mit Hinweisen
