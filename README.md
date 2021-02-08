# FOSSGIS-Projekt WS 2020 / 2021

Autoren: 
- Schindler, Pascal
- Steinheber, Judith
- Weiser, David <br/>

Dozentin: Christina Ludwig <br/>
Wintersemester 2020 / 2021 <br/>


# Risikoanalyse - Wildfeueranalyse in Kalifornien <br/>


Dies ist unsere Github Seite für unsere Wildfeueranalyse in Kalifornien bzw. Santa Cruz.


## Überblick

Zunächst ein grundlegender kurzer Überblick über unsere doch recht einfach aufgebaute Github seite. <br/>

Im Ordner `Dateien` findet ihr alle für die Analyse relevanten Dateien. <br/>

Dieser Ordner ist noch mal weiter unterteit; einerseits in den Ordner für die Risiko-, andererseits in den Ordner für die Vulnerabilitätsdaten.

Im Ordner "Präsentation" könnt ihr unsere Präsentation sowie gesondert unsere Abbildungen in Origianlgröße finden.

## 1. Vorbereitung

Bitte erstellt einen neuen Ordner `Risikoanalyse_Santa_Cruz` oder ähnliches; eine saubere Ordnerstruktur von Beginn an ist sehr wichtig.

Ladet euch zunächst die Dateien der Risikoanalyse runter, dann die der Vulnerabilitätsanalyse. Speichert diese getrennt in eurem `Risikoanalyse_Santa_Cruz` Ordner

Öffnet nun QGIS. Stellt eure Koordinatensystem unten rechts auf das folgende ein: WGS 84 / UTM zone 32 N, EPSG: 32610.

Ladet folgende Dateien in Qgis: <br/>
- Niederschlagslayer
- Bodenfeuchtelayer
- Temperaturlayer
- Vegetationslayer
- Windlayer.

## 2. Klassifizierung innerhalb der Layer

Jeder Layer muss nun mit individuellen Werten klassifiziert werden. Dies geschieht mit dem Tool `Reclassify by Table` , zu finden ebenfalls bei den Verarbeitungswerkzeugen.

Schaut euch mithilfe der Histogramme die verschidenen Wertigkeiten der Rasterlayer an und entscheidet, wo ihr die Klassengrenzen setzt. Für eine sinnvolle Vergleichbarkeit und bessere Übersichtlichkeit soll jeder Layer in fünf Klassen eingeteilt werden.

## 3. Klassifizierung der einzelnen Layer

Sucht bei den Verarbeitungswerkzeugen bzw. in der Processing Toolbox nach dem "Raster calculator". Öffnet diesen.

Es sollen nun alle fünf Layer bezogen auf ihre Beziehung untereinander klassifiziert werden. Ihr könnt verschiedene Klassifizierungen ausprobieren und beobachten, wie sich die Ergebniskarte unterschiedlich verhält.

Unsere Klassifizierung sah folgende Wertigkeiten vor:

- Geringe Wichtigkeit (1) --> Wind
- Mittlere Wichtigkeit (2) --> Bodenfeuchte
- Hohe Wichtigkeit (3) --> Temperatur, Vegetation
- Sehr hohe Wichtigkeit (4) --> Niederschlag


Lässt den Prozess durchlaufen und speichert die neue Rasterdatei dauerhaft ab.

## 3. 
