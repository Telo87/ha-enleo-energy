# Changelog

## 0.25.0

**Tabellen**
- Sortieren per Klick auf einen Spaltenkopf (auch mit der Tastatur): auf, ab, zurück zur ursprünglichen Reihenfolge – im Plan, bei Ersparnis und Kosten und im Protokoll der Schaltungen
- Suchfeld für den Plan, die Tage der Ersparnis und das Protokoll, z. B. „Laden“ oder „18:00“
- Lange Tabellen in Seiten (Plan 24 Zeilen, Tage 14 bzw. 16, Protokoll 10)
- Zeilen, deren Werte sich beim Neuberechnen geändert haben, leuchten kurz auf

**Oberfläche**
- Beim Laden einer Seite stehen Platzhalter in der Form dieser Seite (Kennzahlen, Diagramm, Tabelle) – der Inhalt blendet dort ein, wo sein Platzhalter war
- Mit der Maus: Knöpfe wachsen beim Überfahren leicht, Listeneinträge und anklickbare Zeilen reagieren auf den Zeiger

## 0.24.1

- Ersparnis: neue Spalte **Akkuladung** – was die Energie, die um Mitternacht noch im Akku steckt, danach an Netzbezug spart. Damit geht jede Zeile auf: gespart = ohne − mit + Akkuladung. An Ladetagen ist die Tagesrechnung „mit ENLEO“ höher als „ohne“, die Ersparnis kommt am nächsten Morgen
- Die Tabellen der Seiten Ersparnis, Kosten und Planung passen auch am Desktop und mit breiteren Systemschriften (z. B. Roboto auf Android): weniger Abstand zwischen den Spalten, Spaltenköpfe dürfen zweizeilig werden, kürzere Bezeichnungen

## 0.24.0

**Am Handy besser lesbar**
- Die Erklärungen unter den Kennzahlen enden nicht mehr mit „…“: bis zu drei Zeilen, lange Texte gekürzt
- Seite Ersparnis: die Tage am Handy als Karten statt einer Tabelle zum Seitwärtsschieben
- Seite Kosten: die Tabellen Tage und Monate passen aufs Handy (Ø-Preis und Einspeisung stehen in den Kennzahlen darüber)
- Planung: der Plan je Stunde bzw. Viertelstunde passt aufs Handy – kurze Namen der Betriebsarten, nur die Uhrzeit mit einer Zeile je Tag; PV und Grundverbrauch stehen im Diagramm darüber

**Bedienung**
- Die Abschnitte der Leiste der nächsten Stunden lassen sich auch mit der Tastatur wählen (Tab, Enter, Escape) und werden von Vorlesefunktionen angesagt
- Ein einheitlicher, sichtbarer Rahmen zeigt überall, welches Element die Tastatur gerade gewählt hat

**Sparsamer**
- Die wandernden Punkte im Energiefluss der Übersicht bewegen sich jetzt mit wenig Rechenaufwand – die Übersicht braucht im Leerlauf etwa ein Fünftel der bisherigen Rechenzeit (schont den Akku von Handy und Tablet)

**Steuerung**
- Protokoll der Schaltungen: die erste Schaltung nach dem Start des Add-ons (z. B. nach einem Update) ist als „Start des Add-ons“ gekennzeichnet

## 0.23.4

- Übersicht: Die Uhrzeiten unter der Leiste der nächsten Stunden überlappen am Handy nicht mehr – der Abstand richtet sich nach der tatsächlichen Breite von Leiste und Uhrzeit (manche Handys vergrößern kleine Schrift)
- Am Anfang der Leiste kein eigener dicker Strich mehr – dort beginnt die Leiste selbst, die Uhrzeit darunter genügt
- Abstand zwischen der Leiste und den Knöpfen darunter, wenn sich nichts ändert

## 0.23.3

- Übersicht: Ein Abschnitt der Leiste der nächsten Stunden zeigt beim Überfahren mit der Maus bzw. beim Antippen seine Details – Zeitraum, Betriebsart, Durchschnittspreis und Akku-Ladestand am Ende. Nochmal antippen schließt sie
- Ein kleiner Pfeil über der Leiste markiert die aktuelle Uhrzeit; die Leiste beginnt dort, wo die aktuelle Betriebsart angefangen hat (höchstens 3 Stunden zurück), und der laufende Abschnitt füllt sich mit der verstrichenen Zeit
- Darüber steht rechts, wie lange die aktuelle Betriebsart laut Plan noch dauert (z. B. „Akku halten noch 1 h 25 min“)
- Beginn und Ende jeder Betriebsart sind mit einem kräftigen Strich und der Uhrzeit (fett) markiert; die Uhrzeiten alle 3 Stunden treten zurück, wo es sonst zu eng wird

## 0.23.2

- Übersicht: Die Leiste der nächsten Stunden hat eine Stundeneinteilung – jede volle Stunde ein feiner Strich durch den Balken, jede dritte kräftiger und mit Uhrzeit darunter; über dem laufenden Schritt steht „jetzt“, darunter seine Uhrzeit

## 0.23.1

- Übersicht: Die Leiste der nächsten Stunden steht auf einer Zeitachse – die Uhrzeiten sitzen genau unter ihrer Stunde und laufen am Handy nicht mehr über den Rand; gleiche Betriebsarten hintereinander bilden einen durchgehenden Abschnitt
- Der aktuelle Planschritt pulsiert
- „Nächste Schaltung“ bricht am Handy als normaler Text um; bei eingeschalteter Automatik entfällt der doppelte Hinweis „unverändert in den nächsten Stunden“

## 0.23.0

**Planen im Preisraster des Tarifs**
- Neue Einstellung **Preisraster deines Tarifs** (Einstellungen › Strompreis): stündlich, halbstündlich oder viertelstündlich. Voreingestellt ist stündlich wie bisher; die Seite zeigt, in welchem Raster die Preisquelle liefert
- Bei viertelstündlichen Preisen plant ENLEO-Energy in Viertelstunden: Laden nur in den günstigsten Viertelstunden, Halten z. B. 45 Minuten statt der ganzen Stunde
- Die automatische Steuerung schaltet in denselben Schritten; die Betriebsart steht jeweils bis zum Ende des Schritts fest
- Planung: Fahrplan, Zeitleiste, Preisdiagramm und Tabelle in den Schritten des Tarifs; „Warum dieser Plan?“ nennt Zeiten auf die Viertelstunde
- Ersparnis und „Plan gegen Messung“ bleiben stündlich (die Messwerte werden stündlich gespeichert)

**Steuerung**
- Die Betriebsart steht für den ganzen Planschritt fest: Rechnet der Plan zwischendurch neu, wird erst zum nächsten Schritt umgeschaltet (vorher konnte der Speicher innerhalb weniger Minuten zwischen Laden und Normalbetrieb wechseln)
- Neue Einstellung **Mindestnutzen eines Eingriffs** (Einstellungen › Batterie, voreingestellt 5 ct): Halten oder Laden wird nur geplant, wenn es über den ganzen Zeitraum mindestens so viel spart – bisher 1 ct, was Eingriffe mit kaum messbarem Nutzen zuließ
- Übersicht: bei eingeschalteter Automatik steht unter der aktuellen Betriebsart die nächste geplante Schaltung

**Oberfläche**
- Einstellungen in Gruppen (Anlage, Prognose & Preis, Steuerung, App & System); auf breiten Bildschirmen als Menü an der Seite
- Diagnose-Export enthält den Zustand der Steuerung und den Lizenzstatus (siehe 0.22.1)
- Demo: auch Netz- und Akkuwerte, damit die Seite Kosten und der Wirkungsgrad gefüllt sind

## 0.22.1

- Diagnose-Export: enthält jetzt auch den Zustand der Steuerung mit den letzten Schaltungen und den Lizenzstatus (ohne Schlüssel) gut lesbar in state.json; das vollständige Protokoll der Schaltungen steht wie bisher in der Datenbank

## 0.22.0

**Seite Steuerung übersichtlicher**
- Oben der Zustand der Automatik auf einen Blick: was gerade geschaltet ist (oder im Probebetrieb geschaltet würde), seit wann und warum, dazu die Schalter „Nach Plan schalten“ und „Probebetrieb“
- Die drei Betriebsarten als Reiter statt drei langer Karten untereinander; jeder Reiter zeigt die Zahl seiner Aktionen, rot bei einer nicht erreichbaren Entität
- Aktionen nummeriert, „Jetzt ausführen“ direkt unter den Aktionen
- Die Erklärung der Automatik und das Protokoll der Schaltungen eingeklappt
- Neuer Knopf **Anleitung für Speicher**: Speicher in einer Auswahlliste wählen (sonnenBatterie, Fronius, SolarEdge, SolaX, Huawei, GoodWe, Tesla Powerwall, Victron, SMA, Deye, BYD) und die Aktionen je Betriebsart samt Voraussetzungen direkt auf der Seite lesen
- Am Handy kurze Reiternamen; ein Wechsel des Reiters zählt nicht mehr als ungespeicherte Änderung

## 0.21.0

**Automatisch steuern (nur mit Lizenz)**
- Einstellungen › Steuerung: „Akku automatisch nach Plan schalten“. Zu Beginn jeder Planstunde wird die Betriebsart des Plans ausgeführt; Halten und Laden werden alle 5 Minuten wiederholt, falls der Speicher Vorgaben zurücksetzt
- Ist der Zielladestand erreicht, wird bis zum Ende der Stunde gehalten; Halten hält den Ladestand vom Beginn des Haltens
- Probebetrieb (voreingestellt): nur aufschreiben, was geschaltet würde – mit Protokoll der Schaltungen
- Rückkehr in den Normalbetrieb beim Ausschalten, ohne gültige Lizenz, bei abgeschalteter Steuerung durch den Hersteller, ohne aktuellen Plan und beim Beenden des Add-ons
- Übersicht: „Geschaltet jetzt“ bzw. „Probebetrieb“ statt „Empfehlung jetzt“

**Einrichten**
- Aktionen lassen sich mit Pfeilen verschieben
- Entitäten, die Home Assistant als „unavailable“ meldet, sind rot markiert und werden nicht geschaltet – bisher meldete Home Assistant dabei keinen Fehler, und es passierte nichts
- Bei Halten und Laden sendet ENLEO-Energy alle 5 Minuten nur das erneut, was der Speicher zurückgestellt hat (Knöpfe nicht) – Einstellungen, die manche Speicher dauerhaft speichern, werden so nicht ständig neu geschrieben
- Bis zu 16 Aktionen je Betriebsart (Deye braucht 12)
- Anleitung in der Dokumentation: welche Entitäten in welche Betriebsart, mit Beispielen für sonnenBatterie, Fronius, SolarEdge, SolaX, Huawei, GoodWe, Tesla Powerwall, Victron, SMA, Deye und BYD

## 0.20.0

**Steuerung einrichten (nur mit Lizenz)**
- Neuer Bereich Einstellungen › Steuerung: Für Normalbetrieb, Akku halten und Aus dem Netz laden wird festgelegt, was in Home Assistant geschaltet wird – Option wählen, Wert setzen (fest, aktueller Ladestand oder Ladeleistung), Knopf drücken, ein- oder ausschalten
- Jede Betriebsart lässt sich mit „Jetzt ausführen“ von Hand testen; das Ergebnis jeder Aktion wird angezeigt
- Ohne gültige Lizenz ist der Bereich nicht sichtbar, und das Add-on nimmt weder Einstellungen noch Schaltbefehle dafür an
- Automatisch nach Plan geschaltet wird noch nicht – das ist der nächste Schritt

## 0.19.1

**Lizenz für die Steuerung (vorbereitet)**
- Unter Einstellungen › System gibt es ein Feld für den Lizenzschlüssel. Mit einer Lizenz (Abo) wird die automatische Steuerung des Akkus freigeschaltet, sobald es sie gibt – an Prognose, Planung und Empfehlungen ändert sich ohne Lizenz nichts
- Die Freigabe ist digital unterschrieben und wird von ENLEO-Energy selbst geprüft; sie wird einmal am Tag erneuert und hält ohne Internet bis zu 35 Tage
- Gesendet werden dabei nur der Schlüssel, eine zufällige Kennung der Installation und die Versionsnummer – und nur, wenn eine Lizenz eingetragen ist
- Der Diagnose-Export enthält den Lizenzschlüssel nicht

## 0.18.0

**Schatten nach Sonnenstand**
- Die eigene PV-Prognose lernt Verschattung jetzt nach Sonnenstand: aus welcher Richtung und unter welcher Höhe die Sonne verdeckt ist, etwa von einem Nachbarhaus oder Baum. Was die Sonne bei 30° verdeckt, verdeckt sie auch bei 20° – im Herbst wird der Schatten deshalb schon erwartet, während die Sonne sinkt. Bisher lernte die Korrektur nur je Uhrzeit aus den letzten 30 Tagen und hinkte dem wachsenden Schatten hinterher
- Genutzt wird der gelernte Schatten nur, wenn er die letzte Woche besser vorhergesagt hätte als die Prognose ohne ihn – eine Anlage ohne Schatten bleibt unverändert
- Zu sehen unter Prognosegüte › „So rechnet die eigene Prognose“: Richtung und Höhe des Schattens je Anlage
- Lernen schneller: Die gelernten Modelle vergangener Tage werden in der Datenbank gespeichert und übernommen, solange sich ihre Daten nicht ändern – auch über einen Neustart hinweg. Nur der erste Lauf nach diesem Update rechnet alle Tage einmal neu

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
