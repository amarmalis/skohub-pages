# Publikation eines kontrollierten Vokabulars mit SkoHub Pages

### Projektbericht MALIS25, 2. Semester, IT 2 - Dozent: Adrian Pohl, Dozentin: Petra Maier

**Arbeitsgruppe:**

Inga Frieman (Matrikelnummer: 11076717)

Anne Marx (Matrikelnummer: )

Ida Schneider (Matrikelnummer: )

Maren Zychla (Matrikelnummer:  )

<a name="1"></a>
## **1. Auswahl des Vokabulars und kontextuelle Einordnung**
Bei dem ausgewählen Vokabular handelt es sich um eine Aufstellungs- und Signaturklassifikation des Instituts für Deutsche Sprache und Literatur I (IDSL I) der Universität zu Köln. URL: https://idsl1.phil-fak.uni-koeln.de/bibliothek/benutzung-und-ausleihe/systematik

<a name="1.1"></a>
### 1.1 Aufbau des Vokabulars

<a name="2"></a>
## **2. Arbeitsorganisation**

<a name="2.1"></a>
### 2.1 Treffen via Zoom

<a name="2.2"></a>
### 2.2 Arbeiten mit einem Kanban Board
Im geforkten Repo fehlen uns die Rechte ein neues Projekt anzulegen. Um in Kanban arbeiten zu können, wird ein neues Repo angelegt, das mit einem Projekt versehen ist. Das Projekt wird mit den Mitgliedern geteilt, die die Rolle "Admin" erhalten. Der Link lautet: https://github.com/users/miringa83/projects/2.

<a name="2.3"></a>
### 2.3 Aufteilung der Aufgaben für das selbstständige Arbeiten

<a name="3"></a>
## 3. Umsetzungsphase
Da das Vokabular auf einer Website vorliegt und sich nicht in einer strukturierten Datei herunterladen lässt, ist eine automatisierte Transformation nach SKOS nicht möglich. Die Systematik wird daher manuell anhand der öffentlich zugänglichen Webdarstellung in strukturierte Form rekonstruiert.

<a name="3.1"></a>
### 3.1 Vorbereitung der Kodierung
#### Vorbereitung der Daten
Kopieren der Systematik von der Seite https://idsl1.phil-fak.uni-koeln.de/bibliothek/benutzung-und-ausleihe/systematik in einen Texteditor
- Manuelle Bearbeitung
   - Zuordnung des Systematiktitels zur jeweiligen Systematiknotation in einer Zeile, getrennt durch ": "
   - Zuordnung der ggf. vorhandenen Beschreibungstexte zur jeweiligen Systemstelle in der folgenden Zeile ohne Leerzeile
   - Trennung aller Systemstellen durch Leezeile
   - Ausweisung der TopLevel-Einträge durch "**...**"
- Weitere Bearbeitung im Jupyter Notebook
#### Bearbeitung im Jupyter Notebook
- Einlesen der Rohdaten
- Parsing des Fließtexts
- Erstellung einer strukturierten Tabelle
- Bearbeitung der Hierarchieebenen
- Einfügen der skos:narrower und skos:broader-Verweise (Im Moment noch fehlerhaft für die Zeilen Sp1+Sp2, Sp1.0, Sp1.1, Sp1.2, Sp1.3, Sp1.4, Sp1.5, Sp2.1, Sp2.2, Sp2.3, Sp2.4, Sp2.5.)
- Export der Excel-Datei


<a name="3.2"></a>
### 3.2 SKOS-Kodierung des Vokabulars

<a name="3.3"></a>
### 3.3 Veröffentlichung mit SKOHub Pages und langfristige Verfügbarkeit via URI

<a name="4"></a>
## 4. Lern- und Kompetenzentwicklung RDF und SKOS

"SKOS Play!" ist sehr hilfreich um das Ergebnis in verschiedenen Visualisierungen zu checken.

<a name="5"></a>
## 5. Ausblick

<a name="4.1"></a>
### 5.1 Mehrwert des SKOS-Vokabulars

<a name="4.2"></a>
### 5.2 Anwendungsfälle
