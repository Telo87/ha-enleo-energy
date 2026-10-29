# Changelog

## 0.40.1

- **Ersparnis mit Heizstab:** War an einem Tag der Akku auf sich gestellt schon am besten, zog die Nachrechnung den Heizstab mit Überschuss-Regelung bei der Rechnung „optimal“ doppelt ab. Dadurch erschien ein kleiner Betrag „im Nachhinein möglich“, der nicht möglich war, und „optimal“ wich von „ohne ENLEO-Energy“ ab – behoben
- **Warum nicht mehr gespart?** Die Begründung richtet sich danach, was die Prognose damals versprach: Zeigte sie den größten Teil des Möglichen nicht, liegt es an der Prognose, sonst an Mindestnutzen oder Unsicherheit. Ein Eingriff, der Geld gekostet hat, heißt jetzt so
- **Fahrplan:** Statt der gelben Fläche zeigt ein gelber Strich den Verlauf der PV-Prognose
- **Übersicht:** Die Farbe der Empfehlung (grün, bei „Akku halten“ gelb, beim Laden blau) läuft weich in die Karte aus

## 0.40.0

- **Eigenverbrauch des Speichers:** ENLEO-Energy lernt aus den Tagen ohne Eingriff, wie viel der Speicher selbst braucht, ohne dass der Hauszähler es sieht (Elektronik, Bereitschaft, Selbstentladung). Verwendet wird der Wert nur, wenn er an den jüngsten Tagen nachweislich besser zum Netzzähler passt als keiner. Plan, Reichweite und Nachrechnung rechnen dann damit, die Systemprüfung zeigt den gelernten Wert
- **Warum nicht mehr gespart?** Das Tagesdetail der Ersparnis erklärt, woher der Abstand zum Möglichen kommt: aus der Prognose (etwa weniger PV als vorhergesagt) oder aus den Regeln des Plans – ein Eingriff hätte weniger als den Mindestnutzen gebracht oder wäre bei der üblichen Prognoseabweichung nicht sicher genug gewesen. Dazu, was im Nachhinein am besten gewesen wäre. Auf dem Handy zeigt das Tagesdetail nur die wichtigsten Spalten
- **PV-Prognose an trüben Tagen:** Trübe Stunden bekommen eine eigene Gewichtung der Wettermodelle und ein eigenes Niveau – nur bei Anlagen, bei denen das die trüben Stunden der letzten Woche genauer getroffen hat. Zu sehen unter Prognosegüte › „So rechnet die eigene Prognose“
- **Probezeit:** Die Steuerung lässt sich, sobald sie angeboten wird, einmal je Installation kostenlos testen (Einstellungen › System)
- **Neue Speicher-Anleitungen und Vorlagen:** Sungrow SH (Modbus-Vorlage von mkaiser), SENEC.Home V2/V3 (lokale Verbindung) und E3/DC. Die Steuerung kann jetzt Skripte von Home Assistant ausführen – damit lassen sich auch Speicher steuern, deren Integration nur Dienste anbietet. Bei Huawei geht so auch das Laden aus dem Netz
- **Akku folgt nicht:** ENLEO-Energy schaltet die Betriebsart zuerst einmal neu. Folgt der Akku dann immer noch nicht, läuft er bis zum nächsten Abschnitt des Plans im Normalbetrieb, und es kommt eine Meldung
- **Support-Export:** Der Diagnose-Export lässt sich anonymisiert herunterladen – Standort auf etwa 10 km gerundet, Namen von Anlagen, Sensoren und Benachrichtigungszielen ersetzt, ohne Seriennummer
- **Kleinigkeiten:** Die Reichweite auf der Seite Planung wiederholt die Überschrift nicht mehr; das Dateifeld beim Import ist auf dem Handy groß genug zum Antippen

## 0.39.0

- **Geldbeträge einheitlich:** Stromkosten sind überall Bezug minus Einspeisung – positiv heißt bezahlt. „Was wäre wenn“ zeigt Stromkosten statt einer Bilanz mit umgekehrtem Vorzeichen und sagt beim Vergleich „günstiger“ oder „teurer“. Die Ersparnis gegenüber dem Vergleichstarif steht in der Monatstabelle so wie in der Kachel. Überall dasselbe Minuszeichen
- **Wirtschaftlichkeit:** „Nutzen der Anlage“ statt „Wert der Anlage“; Beträge ab 100 € ohne Cent
- **Ersparnis:** Die Kachel „Stromkosten gemessen“ erklärt, dass Messung und Rechnung auch an Tagen ohne Eingriff auseinanderliegen – der Unterschied kommt aus der Rechnung, nicht von ENLEO-Energy. Die Tagestabelle zeigt zuerst Empfehlung, Akkuladung, Möglich und Gespart, die einzelnen Rechnungen über „Alle Spalten“
- **Plan gegen Messung:** Ohne vollständige Stunde ein Hinweis statt fünf leerer Kacheln
- **Prognosegüte:** Die Entwicklung über die Zeit hat eine Achse, auf der die Unterschiede zu sehen sind. Reihenfolge nach den Fragen: Rangliste, Entwicklung, Wetterlage, Tageserträge, zuletzt die Gewichte der eigenen Prognose
- **Systemprüfung:** Probleme und Hinweise stehen offen, was in Ordnung ist, ist je Bereich eingeklappt; die Bereiche schließen ohne Lücken aneinander an
- **Steuerung:** Meldungen erscheinen über der Leiste mit ungespeicherten Änderungen, die Aktion einer Zeile ist nicht mehr abgeschnitten
- **Übersicht:** Mit Lizenz zeigt die Kurzinfo, was ENLEO-Energy in diesem Monat gespart hat und welcher Anteil des Möglichen das ist

## 0.38.1

- **Strompreis auf schmalen Bildschirmen:** Die Zeile zum Berechnen des Aufschlags (Tag, Uhrzeit, Preis) passt mit den größeren Eingabefeldern wieder auf schmale Handys – auch mit breiteren Systemschriften

## 0.38.0

- **Startbildschirm:** Die volle Animation läuft beim ersten Öffnen des Tages und nach einem Update. Bei jedem weiteren Öffnen gibt es eine Kurzfassung – die Übersicht ist nach knapp einer Sekunde da statt nach dreieinhalb. Die Sonne landet sanfter, das Logo fliegt schneller an seinen Platz
- **Auf Handy und Tablet:** Kein grauer Blitz mehr beim Antippen, dafür eine eigene Rückmeldung beim Drücken. Hervorhebungen beim Überfahren gibt es nur noch mit Maus – sie bleiben nach dem Antippen nicht mehr stehen. Kennzahlen heben sich nicht mehr an. Eingabefelder sind auf Touch-Geräten groß genug, dass iPhone und iPad beim Antippen nicht mehr in die Seite zoomen

## 0.37.0

- **Die ersten Tage:** Solange es noch keine eigene Prognose und keine Rangliste gibt, erklärt die Übersicht, was schon läuft und was mit der Zeit dazukommt. Der Hinweis verschwindet mit „Verstanden“
- **Kennzahlen ruhiger:** Statt eines farbigen Quadrats steht ein kleines Symbol in der Farbe der Messgröße vor der Bezeichnung, die Zahl ist größer
- **Verständliche Fehlermeldungen:** Statt eines Fehlercodes steht da, was passiert ist und was hilft – etwa wenn das Add-on gerade neu startet. Seiten, die nicht laden, bieten „Erneut versuchen“
- **„Jetzt abrufen“** zeigt, dass gerade abgerufen wird, bis die neuen Daten da sind, und bestätigt danach
- **Zeitpunkte um Mitternacht:** Wann der Akku leer oder voll ist, steht als „morgen Mitternacht“ statt „Fr 00:00“
- **Barrierefreiheit:** Diagramme haben eine Beschreibung für Screenreader (was gezeigt wird, Zeitraum, kleinster und größter Wert). Suchfelder zeigen den Tastaturfokus, das Datumsfeld im Tagesverlauf hat eine Beschriftung
- **Einheitlich „Akku“** auch im Einrichtungsassistenten

## 0.36.0

- **Übersicht aufgeräumt:** Die Rangliste der Prognosequellen steht auf der Seite Auswertung. Unter dem PV-Diagramm bleibt eine Zeile mit der genauesten Quelle und dem Zustand der Datenquellen, bei Problemen klappt sie von selbst auf. Beim ersten Öffnen zeigt das Diagramm die genaueste Quelle, weitere über „Quellen vergleichen“. Die Zeile „Haus“ erscheint nur noch, wenn E-Auto oder Heizstab erfasst sind. Auf dem Handy folgen die Kennzahlen direkt auf die Empfehlung
- **Preisdiagramme zeigen den Plan:** Die Balken sind nach dem jeweiligen Tag eingefärbt – günstigstes Drittel grün, teuerstes rot. Zeiten, in denen der Plan den Akku hält oder aus dem Netz lädt, sind hinterlegt. Eine Legende unter dem Diagramm erklärt beides, der Tooltip nennt es je Zeitschritt
- **Tagesverlauf:** Plätze in der Rangliste gibt es erst, wenn mindestens zwei Stunden mit Erzeugung gemessen sind; gleich große Abweichungen teilen sich einen Platz. Das Preisdiagramm steht unter dem PV-Diagramm
- **Schrift und Bezeichnungen:** Klarere Größenstufen, keine Schrift unter 11 px, Gruppen- und Tabellenüberschriften in normaler Schreibweise. Lange Namen werden umbrochen statt abgeschnitten, Sensoren der PV-Anlagen erscheinen mit ihrem Namen aus Home Assistant. Durchgängig „Akku“ statt „Batterie“; die Steuerung steht in den Einstellungen bei der Anlage
- **Feinschliff:** Erklärungen zur Berechnung sind unter „Wie wird gerechnet?“ aufklappbar. Das Kapazitätsdiagramm des Akkus hat eine Legende. Symbole bewegen sich ruhiger. Die Anmeldeseite ist im dunklen Design besser lesbar

## 0.35.2

- **Systemprüfung:** Ein Flat-Tarif mit Freistrom und ohne monatliche Gebühr gilt jetzt als vollständig – solche Tarife gibt es, etwa wenn der Freistrom zum Speicher gehört. „Vergleichstarif unvollständig“ erscheint nur noch, wenn der Preis je kWh fehlt

## 0.35.1

- **„Akku reicht bis“ folgt dem Plan:** Die Reichweite nutzt jetzt den Ladeverlauf des Plans selbst, in dessen Zeitschritten. Bisher wurde sie stündlich getrennt gerechnet und konnte einen kurzen Moment am Mindest-Ladestand übersehen – dann nannte sie einen späteren Zeitpunkt als der Plan. Haltephasen des Plans sind jetzt mit eingerechnet
- **Systemprüfung:** Ein Vergleichstarif ohne monatliche Gebühr gilt als vollständig. Hinweise gibt es nur noch, wenn der Preis je kWh fehlt oder ein Flat-Tarif Freistrom ohne Gebühr enthält
- **Planung:** Lohnt sich kein Eingriff, steht bei der Ersparnis „Kein Eingriff nötig – Normalbetrieb ist am günstigsten“ statt eines Kostenvergleichs mit zweimal demselben Betrag
- **Übersicht:** Die Zeile „Haus“ neben dem Energiefluss zeigt, was E-Auto und Heizstab gerade beziehen, statt die Verbrauchsprognose aus der Kachel darunter zu wiederholen
- **Strompreise:** Veralteten Hinweistext ersetzt

## 0.35.0

- **Grundverbrauch heute:** Die Kachel zeigt wie die anderen groß den bisher gemessenen Wert und klein die Prognose für heute und morgen
- **Eigener Sensor für den PV-Kreis:** Unter Einstellungen › Sensoren & Standort › PV-Anzeige lässt sich optional ein schneller meldender Sensor der gesamten PV-Leistung wählen. Er gilt nur für den PV-Kreis im Energiefluss der Übersicht. Die Zeilen je Anlage daneben, Tagesertrag, Prognosen und Planung nutzen weiter die Sensoren der Anlagen. Ohne gültigen Wert zeigt der Kreis wieder deren Summe

## 0.34.1

- **Zurück auf den Stand von 0.32.3:** Die Änderungen aus 0.33.0 und 0.34.0 sind zurückgenommen. Übersicht, Einstellungen und Auswertungen entsprechen wieder 0.32.3. Ein in 0.33.0 gewählter PV-Leistungssensor für die Übersicht wird nicht mehr verwendet
- **Energiebilanz bei Zeitumstellung:** Bleibt aus 0.33.0 erhalten – ausgewertet werden vollständige Kalendertage mit 23, 24 oder 25 Stunden, Tage mit fehlenden Messstunden werden ausgeschlossen

## 0.34.0

- **Übersicht:** „Jetzt“ zeigt aktuelle Energieflüsse, Strompreis und Steuerungsstatus. „Heute“ enthält bisherige Tageswerte und Prognosen für heute. Morgen, Reichweite und geplanter Akku-Betrieb stehen unter „Ausblick“, Diagramme und Quellen unter „Verlauf und Daten“. Der Akku zeigt Leistung und Ladestand zusammen. Bei durchgehendem Normalbetrieb sind Zeitleiste und Wetter aufklappbar
- **Planung und Auswertungen:** Reichweite mit erwarteter PV und Dauer bei gleichbleibender Entladung sind getrennt bezeichnet. Geplante, nachgerechnete und gemessene Werte sind gekennzeichnet. Zusammenhängende Betriebsarten erscheinen als ruhige Flächen
- **Zeiträume und Reihenfolge:** Nachgerechnete Empfehlungen und gemessene Stromkosten stehen getrennt. Langfristige Prognoseentwicklung und Amortisation benennen ihren eigenen Zeitraum. Simulationen verwenden „Ausgangslage“ und zeigen die tatsächlich ausgewerteten Stunden. Grundlegende Sensoren stehen vor optionalen Angaben
- **Diagramme und Vergleiche:** Eigene Prognosen sind stärker hervorgehoben, Unsicherheitsbereiche erläutert, Monatsbalken auch auf dem Handy mit Legende versehen. Kapazitätsmessung und Speicherangabe stehen direkt nebeneinander. Die Rekorde nutzen ein ausgewogenes Raster
- **Tagesverlauf:** Ohne aussagekräftige Vergleichsstunden werden keine Rangplätze vergeben; gleich gute Quellen teilen sich einen Platz
- **Bedienung:** Filter bleiben mit ihrer Beschriftung zusammen. Quellenranglisten zeigen zunächst drei Quellen, weitere Quellen und Lerndetails sind aufklappbar. Günstige Preisfenster stehen vor dem Preisdiagramm
- **Einstellungen und Meldungen:** Gewählte Benachrichtigungsziele stehen zuerst, weitere Ziele lassen sich suchen. Wiederholte Meldungen sind gruppiert. Eingerichtete Sensorgruppen sind aufklappbar, Einstellungsbereiche klar benannt. Die Systemprüfung unterscheidet Probleme, Warnungen und optionale Optimierungen
- **Lesbarkeit und Tastatur:** Erläuterungen in Kennzahlen werden vollständig angezeigt, Diagrammachsen sind besser lesbar. Dialoge führen den Tastaturfokus und geben ihn beim Schließen zurück

## 0.33.0

- **Eigener PV-Leistungssensor für die Übersicht:** Unter Einstellungen › Sensoren & Standort lässt sich optional ein Gesamtleistungssensor auswählen, etwa ein schneller meldender Erzeugungszähler. Er liefert ausschließlich die aktuelle PV-Leistung im Energiefluss der Übersicht. Tagesertrag, Prognosen und Batterieplanung verwenden weiterhin die Anlagensensoren. Bei fehlenden oder ungültigen Werten wird wieder deren Summe angezeigt
- **Grundverbrauch heute:** Die Kachel zeigt den bisher gemessenen Verbrauch groß und die Prognosen für heute und morgen darunter
- **Energiebilanz bei Zeitumstellung:** Der Auswertungszeitraum umfasst vollständige Kalendertage mit 23, 24 oder 25 Stunden. Tage mit fehlenden Messstunden werden ausgeschlossen

## 0.32.3

- **Probebetrieb ausschalten wirkt sofort:** Die Betriebsart von jetzt wird gleich echt geschaltet, und Übersicht und Seite Steuerung zeigen sofort „automatisch“ bzw. „aktiv“. Bisher blieb „Probebetrieb“ stehen, solange der Plan im Normalbetrieb blieb – geschaltet wurde dann erst beim nächsten Halten oder Laden, dann aber echt

## 0.32.2

- **Menü:** Die eigene Reihenfolge gilt jetzt gleich beim Öffnen. Bisher erschien sie erst, nachdem man einmal die Einstellungen geöffnet hatte

## 0.32.1

- **Rekorde wechseln sofort:** Die Rekorde jedes Jahres werden einmal ausgewertet und wie Akku und Wirtschaftlichkeit zwischengespeichert und stündlich vorgerechnet. „Insgesamt“ nutzt die schon fertigen Jahre. Bisher brauchte jeder Wechsel bis zu 3 Sekunden

## 0.32.0

- **Status-Sensor des Wechselrichters (optional, je PV-Anlage):** ENLEO-Energy ordnet gängige Zustände vieler Hersteller vorab ein – auch Ein/Aus-Sensoren von Balkonkraftwerken (OpenDTU, AhoyDTU, Anker Solix) – und lernt an der gemessenen Leistung, was jeder Zustand an der eigenen Anlage bedeutet. Meldet ein Wechselrichter eine Störung, zeigen Übersicht und Systemprüfung das; nach 10 Minuten kommt auf Wunsch eine Benachrichtigung (neuer Anlass „Wechselrichter-Störung“). Ein ruhender Wechselrichter gilt nicht mehr als Problem, auch wenn er an trüben Tagen spät startet
- **Vorlagen für Balkonspeicher:** Anker SOLIX Solarbank und Zendure SolarFlow für Normalbetrieb, Halten und Laden – aus den Quelltexten der Integrationen abgeleitet, noch nicht an einer Anlage erprobt

## 0.31.1

- **Menü sortieren:** Unter Einstellungen › Darstellung lässt sich die Reihenfolge der Menüeinträge innerhalb von Heute, Rückblick und Verwaltung ändern – gespeichert für alle Geräte, „Standard“ stellt sie zurück. Die Liste zeigt nur die Seiten, die man öffnen darf
- Läuft die Lizenz ab, während eine Seite mit Lizenz offen ist, wechselt ENLEO-Energy jetzt bei allen diesen Seiten in die Einstellungen – bisher nur bei Benachrichtigungen und Rekorden

## 0.31.0

- **Eingriffe bei unsicherer Prognose:** Jedes geplante Halten oder Laden wird zusätzlich mit weniger und mehr Bedarf durchgerechnet – so weit, wie Verbrauch und PV über ein paar Stunden typisch danebenliegen (an den eigenen Messwerten gelernt). Es bleibt nur, wenn es den Mindestnutzen im Mittel über alle drei Fälle bringt. Ein Halten, das nur aufgeht, wenn der Abend genau wie vorhergesagt kommt, entfällt; eine Ladung mit großem Preisabstand bleibt. Die gelernten Werte zeigt die Systemprüfung, weggelassene Eingriffe stehen unter „Warum?“

## 0.30.1

- **Akku leer:** Ist der Akku schon auf dem Mindest-Ladestand, steht das so in der Übersicht, im Energiefluss und unter „Akku reicht“ der Planung – statt einer Uhrzeit, die schon vorbei ist („reicht bis heute 18:08 Uhr“ um 18:16)
- **Der Tag auf einen Blick:** Die PV, die heute noch kommt, rechnet ENLEO-Energy aus den Prognosestunden ab jetzt. Bisher war es Tagesprognose minus Gemessenes, und weil nur volle Stunden gemessen sind, standen bei Sonnenuntergang noch „~0,7 kWh“ da

## 0.30.0

- **Was wäre wenn:** neue Seite, die die letzten zwölf Monate mit anderem Akku, mehr PV oder einem Festpreis neu durchrechnet – fertige Varianten im Vergleich und eine eigene Variante neben dem heutigen Stand, mit Bilanz, Netzbezug, Einspeisung und Autarkie
- **Der Tag auf einen Blick:** Eine Zeile über der Empfehlung sagt, wie viel PV heute noch kommt, wie lange der Akku reicht und wann der Strom am günstigsten ist
- **Einheitliche Farben:** PV orange, Akku grün, Netz grau, Haus und Verbrauch violett – im Energiefluss, in Plan, Planungs-Zeitleiste, Plan gegen Messung, Wirtschaftlichkeit und Akku. Bisher war das Netz im Live-Fluss blau wie das Haus und die Einspeisung grün wie der Akku
- **Feinschliff:** „Wann starten?“ am Computer in einer Zeile, am Handy brechen die Geräte um statt abgeschnitten zu werden; im Tagesverlauf bleibt das Diagramm neben einer langen Rangliste kompakt und im Blick; die Legende der Planung zeigt die Farben der Balken

## 0.29.5

- **Akku, Wirtschaftlichkeit und Energiefluss (Jahr, Insgesamt) öffnen sofort:** Ist das Ergebnis älter als 15 Minuten, zeigt die Seite es gleich an und rechnet im Hintergrund neu. Die Wirtschaftlichkeit des laufenden Jahres und der Energiefluss des Jahres werden wie der Akku stündlich vorgerechnet
- **Energiefluss heute am Morgen:** Statt „0,0 von 0,0 kWh PV“ steht beim Eigenverbrauch, dass heute noch keine volle Stunde mit PV-Ertrag vorliegt

## 0.29.4

- **Logo oben links:** Statt eines kaum sichtbaren Schimmers schlägt der Punkt alle sechs Sekunden zweimal, jeweils mit einem Ring – wie auf dem Startbildschirm. Mit „Bewegung reduzieren“ im System bleibt das Logo still

## 0.29.3

- **Systemprüfung an dunklen Tagen:** Ein Wechselrichter ohne Wert gilt auch tagsüber als „aus, weil zu wenig Licht“, wenn die anderen Anlagen zusammen weniger als 2 % ihrer Spitzenleistung liefern – oder, bei nur einer Anlage, der Wetterdienst kaum Einstrahlung meldet. Bisher erschien dann der Hinweis „Messsensor gerade nicht verfügbar“, obwohl ein kleinerer oder ungünstiger ausgerichteter Wechselrichter bei trübem Wetter einfach später startet. Liefern die anderen Anlagen gut, bleibt der Hinweis

## 0.29.2

- **Start wieder in Sekunden:** Seit 0.29.0 die Börsenpreise aller Jahre nachlädt, brauchte das Aufräumen der Preistabelle beim Start auf einem Raspberry Pi mehrere Minuten – das Add-on schien nicht zu starten. Start und Speichern neuer Preise schauen jetzt nur noch auf die benachbarten Einträge; das Nachladen läuft neben den Seiten, ohne sie zu bremsen
- **Bericht für den Hersteller:** Modell, Seriennummer und Inbetriebnahme lassen sich direkt im Bericht eintragen und bleiben für den nächsten gespeichert

## 0.29.1

- **Akku, Angaben des Speichers:** Statt eines Sensors „verbleibende Kapazität“ – bei vielen Speichern der aktuelle Energieinhalt, nicht die Kapazität im Alter – rechnet die Seite die Kapazität von heute aus installierter Kapazität und Akkuzustand
- **Kapazitätssprung:** Als Monat des Sprungs gilt der erste niedrige Monat. Bisher konnte ein späterer Monat genannt werden, wenn sein rechnerischer Abfall knapp größer war

## 0.29.0

- **Akku: Kapazitätssprung erkennen.** Fällt die gemessene nutzbare Kapazität in einem Schritt um 5 % oder mehr und bestätigen das zwei Monate, zeigt die Seite Akku einen Hinweis mit Monat und Kapazität vorher und nachher. Die Systemprüfung nennt ihn auch; auf Wunsch kommt eine Benachrichtigung (neuer Anlass „Akku-Zustand“)
- **Akku: Angaben des Speichers.** Optional lassen sich die Sensoren wählen, mit denen der Speicher selbst Akkuzustand, verbleibende und installierte Kapazität und Ladezyklen meldet. Die Seite Akku stellt sie neben die eigene Messung, dazu die Kapazität je Monat als Verlauf
- **Bericht für den Hersteller:** Die Seite Akku fasst die Messung auf einer Seite zusammen – zum Drucken oder als PDF, die Monate zusätzlich als CSV
- **Wirtschaftlichkeit:** Die Börsenpreise aller Jahre mit Messwerten werden im Hintergrund nachgeladen, damit jede Stunde mit ihrem echten Preis bewertet wird statt mit dem Durchschnitt. Unter „Insgesamt“ stehen die Jahre im Vergleich: Wert, PV-Ertrag und Autarkie
- Energiefluss (Jahr, Insgesamt), Akku und Wirtschaftlichkeit rechnen alle Stunden aller Jahre durch und werden deshalb 15 Minuten zwischengespeichert – die Seiten öffnen schneller

## 0.28.1

- **Energiefluss:** Netzbezug und Einspeisung zählen wie gemessen, auch in Stunden mit beidem (eine Wolke, der Backofen). Bisher wurden sie in solchen Stunden gegeneinander verrechnet – über ein Jahr fehlten so einige Prozent bei „Gekauft“ und „Eingespeist“, und die Autarkie lag etwas zu hoch. Jetzt passen die Summen zu den Rekorden und zur Kostenseite

## 0.28.0

- **Energiefluss:** neue Seite unter Rückblick mit einem Sankey-Diagramm – woher der Strom kam (PV, Netz, Akku) und wohin er ging (Haus, Akku, Netz), für heute, gestern, 7 Tage, Monat, Jahr oder insgesamt. Darunter Autarkie, Eigenverbrauch, Einspeisung und Netzbezug
- **Akku:** neue Seite mit Ladung, Entladung, Vollzyklen, Wirkungsgrad und nutzbarer Kapazität je Monat – so wird sichtbar, ob der Speicher nachlässt
- **Wirtschaftlichkeit:** neue Seite mit dem Wert von PV und Akku je Monat und Jahr (direkt genutzt, durch den Akku, Einspeisung), bewertet mit dem Preis jeder Stunde. Mit eingetragener Anschaffung: wie viel schon zurückgekommen ist und wann sich die Anlage bezahlt hat
- **Wann starten?** Die Übersicht zeigt, wann Waschmaschine, Spülmaschine, Trockner oder ein eigenes Gerät nach dem Plan am günstigsten laufen – und was ein sofortiger Start kosten würde
- **Monatsbericht:** am Monatsersten um 8 Uhr eine Meldung mit PV-Ertrag, Verbrauch, Autarkie, Einspeisung, Ersparnis und bestem Tag des Vormonats; unter Benachrichtigungen abschaltbar
- **Wetter an der Zeitleiste:** unter den Zeiten der Übersicht zeigen Symbole die Bewölkung laut Wetterprognose

## 0.27.11

- **Ersparnis am Handy kompakter:** je Tag nur Datum, Empfehlungen und „gespart“ – alle Werte und die einzelnen Stunden zeigt ein Tippen auf den Tag. **Tage ohne Eingriff** (nur Normalbetrieb, nichts gespart) lassen sich ausblenden, voreingestellt ausgeblendet. Die Seite ist am Handy nur noch halb so lang
- **Übersicht:** „Genaueste Prognosen“ und „Datenquellen“ sind eine Karte „Prognosen und Quellen“ mit einer Zeile wie „Am genauesten: … 93 % · alle 11 Quellen aktuell“ – am Handy eingeklappt, am Computer mit der Rangliste und eingeklappten Quellen. Bei einem Problem öffnet sie sich von selbst. Der Strompreis steht darunter in voller Breite
- **Benachrichtigungen:** die zuletzt gesendeten Meldungen mit Uhrzeit und Zahl der erreichten Ziele – auch wenn sie auf dem Handy schon weggewischt sind
- **Rekorde öffnen sofort:** die Statistik aller Jahre wird kurz nach dem Start im Hintergrund geholt

## 0.27.10

- **Rekorde, Autarkie:** zählt Netzbezug und Verbrauch nur über dieselben Stunden. Kam der Verbrauchszähler erst im Lauf eines Jahres dazu, wurde bisher der Netzbezug des ganzen Jahres gegen den Verbrauch weniger Wochen gerechnet – die Autarkie war viel zu niedrig. Unter dem Verbrauch steht dann, seit wann er gemessen wird
- **Autarke Tage** statt „Tage ohne Netzbezug“: Tage, an denen höchstens 2 % des Verbrauchs aus dem Netz kamen. Fast jeder Speicher lässt beim Regeln ein wenig Netzbezug übrig – bisher stand dort deshalb meist 0

## 0.27.9

- **Einrichtungsassistent:** führt Schritt für Schritt durch Sensoren und Standort, PV-Anlagen, Strompreis, Batterie und – mit Lizenz – die Steuerung. Jeder Schritt zeigt, was er braucht, erledigte Schritte sind abgehakt, „Weiter“ speichert, was geändert wurde, und zum Schluss stehen offene Punkte und das Ergebnis der Systemprüfung. Bei einer neuen Installation über „Einrichtung starten“ auf der Übersicht, sonst unter Einstellungen › System
- Kleine Knöpfe (z. B. „Ausrichtung prüfen“ bei den PV-Anlagen) sind am Handy mindestens 44 px breit

## 0.27.8

- **Rekorde als eigene Seite** im Menü unter Rückblick: je Jahr auswählbar (2026, 2025, …) oder **insgesamt** über alle Jahre. Oben das Jahr in Zahlen – PV-Ertrag, Verbrauch, Autarkie, Tage ohne Netzbezug –, darunter die Rekorde nach Erzeugung (Spitze je Anlage, beste Stunde, bester Tag, bester Monat), Verbrauch und Netz (höchster und niedrigster Verbrauch, autarkster Tag, meiste Einspeisung, höchster Netzbezug) und Strompreis (günstigster und teuerster Preis, Stunden mit negativem Börsenpreis)
- **Startbildschirm:** Beim Ausblenden wandert die Welle an ihren Platz – in die Seitenleiste, am Handy in die Kopfzeile – und wird dabei zum App-Logo

## 0.27.7

- **Seitenwechsel ohne Neuladen:** ENLEO-Energy wechselt seine Seiten jetzt selbst, statt die Adresse über einen Link ändern zu lassen. Manche Apps auf dem Handy haben dabei die ganze Seite neu geladen – das Menü flackerte und rutschte bei jedem Wechsel kurz nach unten. Die Zurück-Taste funktioniert wie bisher
- Beim ersten Aufbau einer Seite gleitet nichts mehr an seinen Platz (Markierung im Menü, Balken)
- Seite Planung: kürzerer Hinweis unter „Akku reicht“, damit er am Handy nicht abgeschnitten wird

## 0.27.6

- **Startbildschirm nur beim Öffnen:** Manche Apps auf dem Handy laden die ganze Seite neu, wenn in ENLEO-Energy eine andere Seite gewählt wird – dann kam jedes Mal der Startbildschirm, und es ging zurück zur Übersicht. Ein solches Neuladen kurz nach einem Seitenwechsel erkennt ENLEO-Energy jetzt: kein Startbildschirm, die gewählte Seite bleibt. Beim Öffnen gibt es weiter den Startbildschirm und die Übersicht

## 0.27.5

- **Startbildschirm:** „enleo energy“ und „Energie- und Lade-Optimierer“ blenden jetzt gleichzeitig mit der Welle ein, statt erst nach ihr – der Name ist so länger zu lesen
- **Startbildschirm:** Nach dem Landen pulsiert die Sonne zweimal, erst dann geht es zur Übersicht (etwa 3,5 Sekunden)

## 0.27.4

- **Startbildschirm:** Beim Öffnen – in Home Assistant und in der App auf dem Handy – erscheint das Logo von ENLEO-Energy: Die Energiewelle zeichnet sich, die Sonne landet, dann folgen „enleo energy“ und „Energie- und Lade-Optimierer“. Er bleibt, bis die Übersicht geladen ist (mindestens so lange, bis das Logo fertig ist), und blendet dann in sie über. Bei „Bewegung reduzieren“ steht das Logo still und verschwindet, sobald die Seite da ist
- **Jedes Öffnen beginnt mit der Übersicht** – auch wenn zuletzt eine andere Seite offen war, und wenn die App nach mehr als zehn Minuten im Hintergrund wieder nach vorne kommt

## 0.27.3

- **Rekorde des Jahres** (Seite Tagesverlauf, unten): höchste Leistung je PV-Anlage – auch kurze Spitzen am Wolkenrand, aus der Langzeitstatistik von Home Assistant –, beste PV-Stunde, bester PV-Tag, höchster Tagesverbrauch, günstigster und teuerster Strompreis
- **Wechselrichter-Grenze erkennen:** Stauen sich die höchsten Stundenwerte einer Anlage an derselben Leistung (an vielen Tagen bis auf 1,5 % gleich, mehr als knapp darunter), regelt dort der Wechselrichter oder eine Einspeisebegrenzung ab. Die Systemprüfung schlägt dann den Wert für „Wechselrichter AC“ vor, damit die Prognosen an klaren Tagen mit dieser Grenze rechnen
- **Logo:** zeichnet sich beim Öffnen der App, danach leuchtet die Sonne ab und zu sanft auf (nicht bei „Bewegung reduzieren“)
- **Viertelstunden-Werte von Energiezählern in kWh** (z. B. Heizstab) wurden 1000-fach zu groß gespeichert – Home Assistant liefert sie schon in Wh. Ohne Folgen für Rechnungen (dort zählen nur die Anteile innerhalb einer Stunde); die Werte werden einmal neu abgerufen

## 0.27.2

- **Leiste der nächsten Stunden am Handy:** Kurze Abschnitte (etwa eine Stunde Laden) sind jetzt auch mit dem Finger zu treffen – eine unsichtbare Fläche von 44 px nimmt den Tipp an, die Nachbarn behalten ihre Breite. Ebenso der Hinweis „Probebetrieb“ / „automatisch“ in der Übersicht
- Enthält 0.27.1 (Vorlagen für Speicher mit Namen in der Sprache von Home Assistant)

## 0.27.1

- **Vorlagen für Speicher:** finden die Entitäten jetzt auch, wenn die Integration sie in der Sprache von Home Assistant benennt (z. B. „Betriebsmodus“, „Laden erzwingen (W)“, „Reset Laden/Entladen“ bei der sonnenBatterie) – auch über den Schlüssel in der Entitäts-ID. Bisher blieben dort Aktionen ohne Entität. Hinweise auf mehrere passende Entitäten (z. B. ein Gerät doppelt eingebunden) erscheinen nur noch einmal

## 0.27.0

- **Benachrichtigungen als eigene Seite** (im Menü unter Verwaltung, mit Lizenz): Meldungen gehen jetzt an **mehrere Geräte** gleichzeitig – mehrere Handys mit der Home-Assistant-App, weitere Benachrichtigungsdienste und die Benachrichtigungen von Home Assistant, einzeln an- und abwählbar. Ein Gerät, das nicht erreichbar ist, hält die Meldung an die anderen nicht auf; die Testnachricht sagt, welche Geräte nicht erreicht wurden. Ein gewähltes Gerät, das Home Assistant nicht mehr anbietet, bleibt markiert sichtbar. Die bisherige Auswahl wird übernommen
- **Systemprüfung prüft die Steuerung** (mit Lizenz): ob die Automatik läuft oder im Probebetrieb ist, ob jede benötigte Betriebsart Aktionen hat, ob die Entitäten der Aktionen existieren und erreichbar sind, ob die gewählte Option bzw. der Wert zur Entität passt (Optionen, Mindest- und Höchstwert, Ladeleistung in W statt kW), ob Schaltungen der letzten 24 Stunden fehlgeschlagen sind und ob Fehler an ein Gerät gemeldet werden
- **Prüfung, ob der Akku folgt:** Einige Minuten nach dem Schalten prüft ENLEO-Energy, ob der Akku tut, was geschaltet wurde – entlädt er trotz „Akku halten“ oder lädt er nicht, obwohl „Aus dem Netz laden“ geschaltet ist (gemessen an der Akku-Leistung, ohne diesen Sensor am Ladestand), steht das nach zehn Minuten im Protokoll, auf der Seite Steuerung und in der Systemprüfung und wird gemeldet. Bisher wurde nur geprüft, ob der Befehl angenommen wurde
- **Weitere Anlässe für Benachrichtigungen**, jeder einzeln abschaltbar: Akku folgt nicht, seit einer Stunde kein Plan, um 15 Uhr keine Preise für morgen, Ladestand-Sensor seit 30 Minuten ohne Wert, Lizenz in der Kulanzzeit oder abgelaufen bzw. Steuerung abgeschaltet. Ein anhaltendes Problem wird einmal am Tag wiederholt
- **Vorlagen für gängige Speicher:** In der „Anleitung für Speicher“ übernimmt „Als Vorlage übernehmen“ die Aktionen aller drei Betriebsarten (sonnenBatterie, Fronius, SolarEdge, SolaX, Huawei, GoodWe, Tesla, Victron, SMA, Deye) und sucht die Entitäten über die Namen der Integration. Was nicht gefunden wird, bleibt offen, mit dem Namen, nach dem gesucht wurde. Gespeichert wird erst mit „Speichern“
- **Ersparnis in Viertelstunden:** Bei Tarifen mit Viertel- oder Halbstundenpreisen rechnen die Rechnungen ohne / mit ENLEO-Energy und optimal in Viertelstunden mit dem Preis jeder Viertelstunde – wo Hausverbrauch und PV je Viertelstunde gemessen sind. Dafür holt ENLEO-Energy auch deren 5-Minuten-Werte aus Home Assistant
- **Oberfläche:** auf der Seite Steuerung größere Tippfläche für „Alle Einstellungen“, besserer Kontrast für Lade-Kennzeichnung, Schritt-Nummern und Fehler-Markierungen, und das Protokoll der Schaltungen passt aufs Handy
- **Prognose bei Schnee:** Liegt laut Wetterdienst Schnee und liefert die Anlage in hellen Stunden kaum etwas, wird die PV-Prognose gesenkt, bis die Module wieder liefern oder der Schnee geschmolzen ist. Die Stunden unter Schnee lernen die eigenen Prognosen nicht – sie lagen danach sonst tagelang zu tief
- **Viertelstunden der Wetterprognose:** Bei Viertelstunden-Tarifen verteilen die 15-Minuten-Werte von Open-Meteo die PV-Erzeugung einer Stunde – wenn sie die gemessenen Viertelstunden der Anlage genauer treffen als der Sonnenstand
- **Live-Korrektur lernt dazu:** ob die letzte Viertelstunde oder die letzte Stunde besser vorhersagt und wie stark die nächsten Stunden folgen sollen – je Anlage aus den eigenen Messwerten
- **Verbrauchsprognose:** Profil je Wochentag und die Temperatur jeder Stunde (z. B. Wärmepumpe) werden je Installation ausprobiert und nur genutzt, wenn sie genauer sind; außerdem folgen die nächsten Stunden der Abweichung der letzten drei – so stark, wie es an den vergangenen Tagen geholfen hätte
- **Preise schätzen, solange die von morgen fehlen** (Einstellungen › Strompreis, voreingestellt an): Vor etwa 13 Uhr rechnet der Plan mit geschätzten Preisen bis zum Ende von morgen weiter, statt um Mitternacht zu enden; in der Planung mit „≈“ gekennzeichnet
- **Systemprüfung:** zeigt, welche Verfeinerungen der Prognosen bei dieser Installation genutzt werden, und vermuteten Schnee

## 0.26.2

Ergebnisse einer Prüfung aller Berechnungen:
- **Kosten je Viertelstunde:** Bei halb- oder viertelstündlichem Tarif wird der Netzbezug wie beim Anbieter je Viertelstunde mit ihrem Preis abgerechnet (bisher mit dem Mittel der Stunde). Dafür holt ENLEO-Energy laufend die 5-Minuten-Werte der Netz-Zähler aus Home Assistant und speichert sie. Gilt auch für die gemessene Rechnung auf der Seite Ersparnis. Die Seite Kosten zeigt, was der Kauf in den günstigen Viertelstunden gespart hat
- **Ladestand zur vollen Stunde:** Wirkungsgrad und nutzbare Kapazität nehmen den Ladestand jetzt genau zur vollen Stunde aus der Statistik von Home Assistant – bisher aus dem Moment, in dem der Plan der Stunde gerechnet wurde (nach einem Neustart bis zu einer Stunde später)
- **Wirkungsgrad des Speichers:** berücksichtigt jetzt, wie voll der Akku zu Beginn und am Ende des Messzeitraums war – endete der Zeitraum mit vollerem Akku, wurde der Wirkungsgrad bisher um einige Prozentpunkte zu niedrig gemessen
- **Autarkie und Eigenverbrauch** (Seite Kosten): Netzbezug und Verbrauch bzw. Einspeisung und Erzeugung werden über dieselben Stunden verglichen – fehlten Werte des Hausverbrauchs oder der PV, war die Autarkie zu niedrig
- **Prognosegüte:** der ausgewertete Zeitraum beginnt auch über die Zeitumstellung hinweg genau um Mitternacht (bisher konnte ein Tag mit einer einzigen Stunde in die Tagesfehler eingehen)
- **Planer:** eine Planstunde, die kurz vor dem Mindest-Ladestand von „Akku halten“ auf „Normalbetrieb“ wechselt, zeigt jetzt auch die Werte des Normalbetriebs
- **Systemprüfung:** Hinweise, wo die Daten nur eine Näherung zulassen – Kosten aus einem einzelnen Sensor für die Netzleistung (Bezug und Einspeisung derselben Stunde heben sich auf), ob die Viertelstunden-Werte schon da sind, unvollständiger Vergleichstarif

## 0.26.1

**Besser lesbar und bedienbar**
- Am Handy und Tablet sind alle Knöpfe, Felder, Spaltenköpfe und Menüeinträge mindestens 44 × 44 Pixel groß; die Abschnitte der Leiste der nächsten Stunden und die Legenden-Knöpfe haben eine größere unsichtbare Tippfläche. Mit der Maus bleibt alles so kompakt wie bisher
- Schrift in Orange, Grün und Blau sowie die grauen Untertitel sind etwas dunkler und erreichen überall den empfohlenen Kontrast (WCAG AA, 4,5 : 1) – auch bei Sonne am Handy; im dunklen Design ist die Schrift auf blauen Knöpfen dunkel statt weiß

## 0.26.0

**Steuerung**
- Neu: **Bei Fehlern benachrichtigen** (Einstellungen › Steuerung) – schlägt ein Befehl an den Speicher fehl oder ist eine Entität nicht erreichbar, kommt eine Nachricht an die Benachrichtigungen von Home Assistant oder aufs Handy (Home-Assistant-App). Derselbe Fehler höchstens einmal pro Stunde, mit Knopf für eine Testnachricht

**Planung**
- Bei halb- und viertelstündlichen Preisen folgt die PV-Erzeugung innerhalb der Stunde dem Sonnenstand statt gleich verteilt zu sein – morgens und abends wird genauer geplant. Das gilt für jede Anlage, es braucht nur den Standort
- Der Planer rechnet etwa 2,7-mal so schnell (gleiches Ergebnis) – wichtig für den Raspberry Pi bei Plänen in Viertelstunden
- Systemprüfung: zeigt, wie lange der Plan auf diesem Gerät rechnet, und rät bei langer Rechenzeit zu einem gröberen Preisraster

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
