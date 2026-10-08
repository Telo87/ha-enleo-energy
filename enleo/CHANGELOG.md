# Changelog

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
