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

Es handelt sich um ein einsprachiges deutschsprachiges Vokabular, weshalb auf die Sprachkennzeichnung (@de) verzichtet wird. 

Notation, Hierarchie und Gliederung
- Hierarchisch-enumerativ: Die Hauptgruppen sind alphabetisch mit 1-2 Buchstaben  kodiert, die Untergruppen sind alphabetische oder nummerische Zusätze am Hauptgruppenpräfix (AK 1, Ha). Gruppen der 3. Hierarchieebene sind in der Regel als numerische Ergänzung nach Punkt gekennzeichnet (Ausnahme ist die Notation AT 3.1, die zur zweiten Hierarchieebene gehört). 
- Die Notation der Systemstelle ist Signaturbestandteil aller Medien dieses Bereiches 
- Gliederung folgt teilw. formalen Kriterien (z.B. A - Anthologien, D - Dissertationen, Z - Zeitschriften)
- Teilw. werden Gruppen nach Sachgebiet gebildet (AT - Ältere Texte, Sp - Sprachwissenschaft)
- Binnengliederung einzelner Sachgruppen erfolgt unter unterschiedlichen Aspekten:
  - Form / Materialart
  - Erscheinungsjahr der Literatur
  - Geburtsjahre der Autor\*innen
- Notationsregeln werden durch  Aufstellanweisungen ergänzt, die selbst nicht in der Notation codiert sind. (Bsp. Aufstellanweisung innerhalb der Gruppen von NT: Zuordnung zu den Untergruppen anhand der Geburtsjahre der Autor\*innen von Primärliteratur. Innerhalb der Signaturgruppen ohne explizite Notation: Name der Autor\*in (alphabetisch). I. Primärliteratur: a) Gesamtausgaben, b) Teilsammlungen, c) Briefe, Tagebücher u.ä., d) Einzelausgaben (alphabetisch sortiert), e) selbständige Bibliographien; II. Sekundärliteratur: im Alphabet der Autor\*innen, Jahrbücher, Mitteilungen der Dichtergesellschaften, Wörterbücher

<a name="2"></a>
## **2. Arbeitsorganisation**


<a name="2.1"></a>
### 2.1 Treffen via Zoom
Für das kleine Projekt treffen sie die Mitglieder via Zoom, da dies für ortsunabhängige Treffen ermöglicht. In Moodle ist für die Studiengruppe MALIS25 ein Zoom-Raum angelegt, der genutzt wird.

<a name="2.2"></a>
### 2.2 Arbeiten mit einem Kanban Board
Unter "Projects" wird ein Projekt Namens "@amarmalis's IT2" angelegt. Aufgeteilt ist das Kanban in "To do", "In Progress", "Done" und "Offene Fragen". Stand und Entwicklung der Gruppenaufgabe ist somit für alle Mitglieder einsehbar.

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
### 3.2 Datenmodellierung

### Analyse von und Umgang mit Inkonsistenzen
Bei der Datenmodellierung haben wir uns für eine originalgetreue Übernahme entschieden. Für diese Vorgehensweise spricht, die Integrität der Systematik zu wahren, da sie aktiv als Arbeitsinstrument genutzt wird. Änderungen und Anpassungen müssen deshalb begründet und nachvollziehbar sein sowie im Projektbericht dokumentiert werden. In Einzelfällen waren Korrekturen notwendig, bei Tipp- oder Rechtschreibfehlern (Hs „Rechswissenschaft“) und einheitlicher Klammersetzung in prefLabels bzw. altLabels. Die einzige inhaltliche Korrektur erfolgte bei der Behebung von Fehlern in der Hierarchie unter dem TopConcept „Sp“. 

### Auflösung der kombinierten Notation "Sp 1 + Sp 2"
Die ursprüngliche Systematik verwendet die kombinierte Notation „Sp 1 + Sp 2“ für "Allgemeine und vergleichende Sprachwissenschaft; Angewandte und empirische Linguistik", welche in Sp 1 und Sp 2 jeweils fünf Unterkategorien enthalten.  

Anstatt der Mehrfachnotation innerhalb eines Konzepts, wurde „Sp 1 + Sp 2“ in zwei separate Konzepte aufgelöst, wobei beide gleichberechtigt unter Sp als narrower concepts stehen:
- Sp 1: Allgemeine und vergleichende Sprachwissenschaft
- Sp 2: Angewandte und empirische Linguistik

Im Zuge der Auflösung erhalten die Konzepte Sp 1.0 bis Sp 2.5 korrigierte broader-Verweise, wodurch die hierarchische Struktur konsistent wird. 

Diese Anpassung ermöglicht eine valide SKOS-Struktur und sorgt für semantische Stringenz, da die beiden Bereiche mit ihren unterschiedlichen Schwerpunkten (theoretisch/anwendungsorientiert) separiert werden. Dennoch bleibt die originale inhaltliche Zuordnung der Unterkategorien erhalten. 

Es wird deutlich, dass die Überführung in strukturierte Formate inhaltliche Interpretationen erfordern kann. Da die Entscheidungen dokumentiert und nachvollziehbar sind, können sie stets aktualisiert oder revidiert werden. 

<a name="3.3"></a>
### 3.3 SKOS-Kodierung des Vokabulars

<a name="3.4"></a>
### 3.4 Veröffentlichung mit SKOHub Pages und langfristige Verfügbarkeit via URI

<a name="4"></a>
## 4. Lern- und Kompetenzentwicklung RDF und SKOS

"SKOS Play!" ist sehr hilfreich um das Ergebnis in verschiedenen Visualisierungen zu checken.

<a name="5"></a>
## 5. Ausblick

<a name="4.1"></a>
### 5.1 Mehrwert des SKOS-Vokabulars

- Skos-Version ermöglicht Einbindung an verschiedenen Stellen der Webseite oder des Katalogs
- Einfache Datenpflege und Ergänzung
- Steuerung der anzuzeigenden und der durchsuchbaren Informationen
- Bearbeitungshinweise für die Editorinnen sind über die Nutzung bestimmter Skos-Properties möglich
- Im Bedarfsfall könnten eigene Properties definiert und genutzt werden.
- Veröffentlichung und Nachnutzbarkeit durch andere Einrichtungen ist in diesem Fall weniger wichtig. Vokabular ist jedoch gut geeignet, um die Datenmodellierung zu testen.

<a name="4.2"></a>
### 5.2 Anwendungsfälle
