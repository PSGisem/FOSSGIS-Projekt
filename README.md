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

Im Ordner `Dateien` sind alle für die Analyse relevanten Dateien zu finden. <br/>

Dieser Ordner ist noch mal weiter unterteilt; einerseits in den Ordner für die Risiko-, andererseits in den Ordner für die Vulnerabilitätsdaten.

Im Ordner "Präsentation" könnt ihr unsere Präsentation sowie gesondert unsere Abbildungen in Originalgröße finden.

## 1. Vorbereitung

Erstellt einen neuen Ordner namens `Risikoanalyse_Santa_Cruz` (oder ähnlich); eine saubere Ordnerstruktur von Beginn an ist sehr wichtig.

Ladet euch zunächst die Dateien der Risikoanalyse runter, dann die der Vulnerabilitätsanalyse. Speichert diese getrennt in eurem `Risikoanalyse_Santa_Cruz` Ordner

Öffnet nun QGIS. Stellt das Koordinatensystem unten rechts auf `WGS 84 / UTM zone 32 N, EPSG: 32610` ein.

Ladet folgende Dateien in QGis: <br/>
- Niederschlagslayer
- Bodenfeuchtelayer
- Temperaturlayer
- Vegetationslayer
- Windlayer

## 2. Klassifizierung innerhalb der Layer

Jeder Layer muss nun mit individuellen Werten klassifiziert werden. Dies geschieht mit dem Tool `Reclassify by Table` , zu finden ebenfalls bei den Verarbeitungswerkzeugen.

Schaut euch mithilfe der Histogramme die verschiedenen Wertigkeiten der Rasterlayer an und entscheidet, wo ihr die Klassengrenzen setzt. Für eine sinnvolle Vergleichbarkeit und bessere Übersichtlichkeit soll jeder Layer in fünf Klassen eingeteilt werden.

Unsere Klassifizierungen innerhalb der einzelnen Layer sind als PDF mit dem Namen "Klassifizierungen" in unserem Dateienordner zu finden.

## 3. Klassifizierung der einzelnen Layer

Sucht bei den Verarbeitungswerkzeugen bzw. in der Processing Toolbox nach dem "Raster calculator". Öffnet diesen.

Es sollen nun alle fünf Layer bezogen auf ihre Beziehung untereinander klassifiziert werden. Ihr könnt verschiedene Klassifizierungen ausprobieren und beobachten, wie sich die Ergebniskarte unterschiedlich verhält.

Unsere Wertigkeiten der einzelnen Layer sind wie folgt:

- Geringe Wichtigkeit (1) --> Wind
- Mittlere Wichtigkeit (2) --> Bodenfeuchte
- Hohe Wichtigkeit (3) --> Temperatur, Vegetation
- Sehr hohe Wichtigkeit (4) --> Niederschlag


Lässt den Prozess durchlaufen und speichert die neue Rasterdatei dauerhaft ab.

## 4. Herunterladen der OpenSteetMap-Dateien

Die OpenSteetMap Dateien könnt ihr mithilfe der ohsome APi herunterladen.
Insgesamt sollen folgende verschiedene Flächen für den Bereich von Scotts Valley heruntergeladen werden:

- Fläche für kommerzielle Gebäude
- Landwirtschaftlich genutzte Fläche
- Waldfläche
- Industriell genutzte Fläche
- Wiesenfläche
- Wohnfläche
- Einzelhandelsfläche

Herunterladen könnt ihr diese mit dem Befehl `curl -X POST -o DATEINAME.geojson --data-urlencode "bboxes=-122.041703,37.029156,-121.983888,37.08064" --data-urlencode "time=2020-12-05" --data-urlencode "filter=landuse=FLÄCHENTYP and type:node or landuse=FLÄCHENTYP and (geometry:polygon)" "https://api.ohsome.org/v1/elements/geometry"`

Anmerkungen zu dem Befehl:
1. Neuere Dateien als vom 05.12.2020 sind leider nicht vorhanden
2. Die Bounding Box wurde von uns zuvor mit https://boundingbox.klokantech.com/ bestimmt.
3. Für "DATEINAME" bitte den jeweiligen gewünschten Dateiname einfügen, bei FLÄCHENTYP auf Englisch den Name der Fläche. Die Namen der Landuse-Flächen könnt ihr dem OpenStreetMap Wiki entnehmen: 
https://wiki.openstreetmap.org/wiki/Map_features#Landuse (im Feld Value abzulesen).
