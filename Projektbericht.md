# Publikation eines kontrollierten Vokabulars mit SkoHub Pages

### Projektbericht MALIS25, 2. Semester, IT 2 - Dozent: Adrian Pohl, Dozentin: Petra Maier

**Arbeitsgruppe:**

Inga Frieman (Matrikelnummer: 11076717)

Anne Marx (Matrikelnummer: )

Ida Schneider (Matrikelnummer: 11472577)

Maren Zychla (Matrikelnummer:  )

<a name="1"></a>
## **1. Auswahl des Vokabulars und kontextuelle Einordnung**
Bei dem ausgewählen Vokabular handelt es sich um eine Aufstellungs- und Signaturklassifikation des Instituts für Deutsche Sprache und Literatur I (IDSL I) der Universität zu Köln. URL: https://idsl1.phil-fak.uni-koeln.de/bibliothek/benutzung-und-ausleihe/systematik. Das Einverständnis des IDSL I wurde schriftlich per Email eingeholt. Die Bibliothekarin Frau Knopp-Sullivan bittet um einen Hinweis, wenn das Vokabular auf SKOS veröffentlicht ist.

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
Für das kleine Projekt treffen sie die Mitglieder via Zoom, da dies ortsunabhängige Treffen ermöglicht. In Moodle ist für die Studiengruppe MALIS25 ein Zoom-Raum angelegt, der genutzt wird.

<a name="2.2"></a>
### 2.2 Arbeiten mit einem Kanban Board
Unter "Projects" wird ein Projekt Namens "@amarmalis's IT2" angelegt. Aufgeteilt ist das Kanban in "To do", "In Progress", "Done" und "Offene Fragen". Stand und Entwicklung der Gruppenaufgabe ist somit für alle Mitglieder einsehbar. Die offenen Fragen sind unter anderem die Diskussionsgrundlage für die Treffen.

<a name="2.3"></a>
### 2.3 Aufteilung der Aufgaben für das selbstständige Arbeiten
In der zweiten Sitzung haben sich die Teilnehmerinnen soweit in die SKOS-Materie und das die ausgesuchte Systematik eingearbeitet, dass für das dritte Zoom-Meeting Aufgaben verteilt werden können. Die Aufteilung wird in Kanban dokumentiert. Auf Sciebo wird ein Ordner angelegt, auf den das Projektteam Zugriffsrechte hat. Die Excel-Datei der Systematik ist hier hochgeladen und zudem ein Word-Dokument, in dem die Texte für den Projektbericht vorgeschrieben und kommentiert werden können.
Die Aufgaben werden aufgeteilt in:
- Beschreibung der Systematik
- Wie sieht das Schema aus?
- Welche Properties sind sinnvoll?
- Umgang mit Fehlern und Inkonsistenzen
- Korrektur von Inkonsistenzen und Dokumentation
- SKOS-Veröffentlichung und persistente Identifier (URI)
- Vorteile der SKOS-Darstellung
<a name="3"></a>
## 3. Umsetzungsphase
Da das Vokabular auf einer Website vorliegt und sich nicht in einer strukturierten Datei herunterladen lässt, ist eine automatisierte Transformation nach SKOS nicht möglich. Die Systematik wird daher manuell anhand der öffentlich zugänglichen Webdarstellung in eine strukturierte Form rekonstruiert.

<a name="3.1"></a>
### 3.1 Vorbereitung der Kodierung
#### Vorbereitung der Daten
Kopieren der Systematik von der Seite https://idsl1.phil-fak.uni-koeln.de/bibliothek/benutzung-und-ausleihe/systematik in einen Texteditor
- Manuelle Bearbeitung
   - Zuordnung des Systematiktitels zur jeweiligen Systematiknotation in einer Zeile, getrennt durch ": "
   - Zuordnung der ggf. vorhandenen Beschreibungstexte zur jeweiligen Systemstelle in der folgenden Zeile ohne Leerzeile
   - Trennung aller Systemstellen durch Leerzeile
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
Bei der Datenmodellierung haben wir uns für eine originalgetreue Übernahme entschieden. Für diese Vorgehensweise spricht, die Integrität der Systematik zu wahren, da sie aktiv als Arbeitsinstrument genutzt wird. Änderungen und Anpassungen müssen deshalb begründet und nachvollziehbar sein sowie im Projektbericht dokumentiert werden. In Einzelfällen waren Korrekturen notwendig, wie bei Tipp- oder Rechtschreibfehlern (Hs „Rechswissenschaft“) und der Disambiguierung gleichnamiger prefLabels. Die einzige inhaltliche Korrektur erfolgte bei der Behebung von Fehlern in der Hierarchie unter dem TopConcept „Sp“. 

### Auflösung der kombinierten Notation "Sp 1 + Sp 2"
Die ursprüngliche Systematik verwendet die kombinierte Notation „Sp 1 + Sp 2“ für "Allgemeine und vergleichende Sprachwissenschaft; Angewandte und empirische Linguistik", welche in Sp 1 und Sp 2 jeweils fünf Unterkategorien enthalten.  

Anstatt der Mehrfachnotation innerhalb eines Konzepts, wurde „Sp 1 + Sp 2“ in zwei separate Konzepte aufgelöst, wobei beide gleichberechtigt unter Sp als narrower concepts stehen:
- Sp 1: Allgemeine und vergleichende Sprachwissenschaft
- Sp 2: Angewandte und empirische Linguistik

Im Zuge der Auflösung erhalten die Konzepte Sp 1.0 bis Sp 2.5 korrigierte broader-Verweise, wodurch die hierarchische Struktur konsistent wird. 

Diese Anpassung ermöglicht eine valide SKOS-Struktur und sorgt für semantische Stringenz, da die beiden Bereiche mit ihren unterschiedlichen Schwerpunkten (theoretisch/anwendungsorientiert) separiert werden. Dennoch bleibt die originale inhaltliche Zuordnung der Unterkategorien erhalten. 

Es wird deutlich, dass die Überführung in strukturierte Formate inhaltliche Interpretationen erfordern kann. Da die Entscheidungen dokumentiert und nachvollziehbar sind, können sie stets aktualisiert oder revidiert werden. 

###Umgang mit der Doppelvergabe der Oberbegriffe GT
Die Notation GT als Oberbegriff wurde doppelt vergeben. Einmal unter "GT - Graphische Texte" und "GT - Sammelbände, Anthologien". Beschreibend ist noch der Hinweis "Graphic Novels / überwiegend deutschsprachiger Autor*innen" zu erkennen. Diese Doppelvergabe sollte nicht doppelt in SKOS übernommen werden, deswegen wurde die Bibliothekar im IDSL1 befragt. Sie erklärt, dass GT als Überbegriff den Inhalt der Signaturengruppe beschreibt und GT nicht nicht als separate Signatur vergeben wird, sondern nur innerhalb einer Zahl für den Zeitabschnitt, innhalb derer die AutorIinnen geboren sind. Das sind GT 1 und GT 2. Die Gruppenteilnehmerin versichert sich, dass die Gruppe "GT - Graphische Texte" durch "Graphic Novels / überwiegend deutschsprachiger AutorInnen, Sammelbände, Anthologien" beschrieben wird. Dies wird durch die Bibliothekarin bestätigt.

<a name="3.3"></a>
### 3.3 SKOS-Kodierung des Vokabulars

Die Transformation der IDSL-Bibliothekssystematik in SKOS erfolgte in mehreren Schritten.

### Strukturelle Abbildung
Die hierarchische Gliederung der Systematik wurde mittels skos:broader und skos:narrower abgebildet. Hauptklassen wie "Sprachwissenschaft (Sp)" oder "Neuere Texte (NT)" erhielten den Status skos:topConceptOf, während ihre Unterklassen (z.B. Sp1, Sp2) über skos:broader mit der übergeordneten Klasse verknüpft wurden. Dies ermöglicht eine maschinell auswertbare Navigation durch die Systematik.

Die Systematik enthält zeitbasierte Gliederungen (z.B. NT1-NT12 nach Geburtsjahren der Autor*innen) und formatspezifische Kategorien (z.B. GT für Graphic Novels). Die Ausleihinformationen unter "a - Bücher zur Ausleihe" wurden als eigenständiges Top Concept mit ausführlicher skos:note modelliert, da sie organisatorische Relevanz für die Bibliotheksnutzung haben. Inkonsistenzen der Originalvorlage wurden, wie beschrieben, für die SKOS-Version vereinheitlicht.

### Verwendete SKOS-Properties
Neben den grundlegenden SKOS-Properties (hasTopConcept, topConceptOf, inScheme, prefLabel), sollten mindestens drei zusätzliche Properties sinnvoll genutzt werden:
- skos:prefLabel: Bevorzugte Benennung
- skos:altLabel: Alternative Benennung
- skos:notation: Signatur bzw. Systemstellenbezeichnung
- skos:scopeNote: Inhaltliche Erläuterung zum Anwendungsbereich
- skos:note: Administrative Hinweise
- skos:editorialNote: Interne Bearbeitungshinweise
- skos:broader/narrower: Hierarchische Beziehungen
+ concept_id = row["ID"] # z.B. "0001"
+ concept_uri = BASE_URI + concept_id

<a name="3.4"></a>
### 3.4 Veröffentlichung mit SKOHub Pages und langfristige Verfügbarkeit via URI

### Persistente URIs via w3id.org
Für die langfristige Verfügbarkeit und Zitierbarkeit wurde eine w3id.org-URI beantragt. Anders als die example.org-Domain bietet w3id.org einen kostenfreien Redirect-Service, der auch bei Serverumzügen die Erreichbarkeit gewährleistet. Dies ist besonders für bibliothekarische Anwendungsfälle wichtig, wenn Systematiken etwa in Katalogdaten stabil referenzierbar sein müssen.

### SkoHub Pages als Publikationsplattform
SkoHub Pages generiert aus der Turtle-Datei eine HTML-Ansicht des Vokabulars. Dies ermöglicht Nutzer*innen und Kolleg*innen einen niedrigschwelligen Zugang zur Systematik. Die Darstellung enthält eine hierarchische Navigation mit Suchfunktion, wobei es sich um wichtige Funktionen für die bibliothekarische Praxis handelt.

### GitHub als Infrastruktur
Die Versionierung über GitHub ermöglicht nachvollziehbare Änderungen an der Systematik, beispielsweise bei Erweiterungen um neue Fachgebiete. Dass Änderungen dokumentiert udn tranparent sind sowie rückgängig gemacht werden könne, kommt den Anforderungen an Datenpflege entgegen.

### Validierung
Vor der Publikation erfolgte eine Validierung mit "SKOS Play!" / "RDF Playground", um das Vokabular zu testen und syntaktische Fehler auszuschließen. "SKOS Play!" ist außerdem sehr hilfreich, um das Ergebnis in verschiedenen Visualisierungen zu checken. Diese unmittelbare visuelle Rückmeldung hilft, Modellierungsfehler schnell zu erkennen und zu korrigieren.

<a name="4"></a>
## 4. Lern- und Kompetenzentwicklung RDF und SKOS

Zu Beginn des Projekts war unser Verständnis von RDF und SKOS überwiegend theoretisch. Die Konzepte von Tripeln (Subjekt-Prädikat-Objekt) und URIs als Identifikatoren waren bekannt, jedoch fehlte praktische Erfahrung in der Anwendung. Durch die konkrete Arbeit mit der IDSL-Systematik entwickelte sich ein Verständnis für die Modellierungslogik: Jede bibliothekarische Systemstelle wird zum skos:Concept, Hierarchien werden zu broader/narrower-Relationen, und unterschiedliche Informationstypen (Titel, Beschreibung, Hinweise) erhalten passende Properties. Die zunächst abstrakt wirkende RDF-Syntax wurde somit immer besser lesbar. 
Die erworbenen Kompetenzen sind übertragbar auf andere bibliothekarische Aufgaben, wie Normdatenpflege udn Schlagwortmanagement.

<a name="5"></a>
## 5. Ausblick

<a name="4.1"></a>
### 5.1 Mehrwert des SKOS-Vokabulars

- Technische Integration: Die SKOS-Version ermöglicht die Einbindung der Systematik an verschiedenen Stellen der Bibliothekswebseite oder des Katalogs via API-Abfrage. Dort können nun dynamische Systematikbrowser implementiert werden, die Nutzer*innen durch die Bestände führen.
- Effiziente Datenpflege: Änderungen erfolgen zentral in der Turtle-Datei und werden automatisch an allen Verwendungsstellen übernommen. Dies reduziert den Pflegeaufwand erheblich gegenüber dezentralen Excel-Listen oder PDF-Dokumenten. Ergänzungen, beispielsweise neue Unterklassen, können strukturiert eingepflegt werden.
- Informationssteuerrung: Über die SKOS-Properties lässt sich steuern, welche Informationen wo angezeigt werden: skos:prefLabel für die öffentliche Katalogansichte, skos:editorialNote nur für die interne Bearbeitungsoberflächen. Somit ist eine Trennung der Sicht von Nutzer*innen und Verwaltung möglich.
- Bearbeitungshinweise: Im Sinne der Nachvollziehbarkeit und Tranparenz während des kollaborativen Arbeitens können  Hinweise für Kolleg*innen direkt am Konzept in der skos:editorialNote hinterlassen werden. Im Bedarfsfall könnten eigene Properties definiert und genutzt werden.
- Reichweite: Für die IDSL-Bibliothek steht die interne Nutzbarkeit im Vordergrund. Obwohl eine Veröffentlichung und Nachnutzbarkeit durch andere Einrichtungen in diesem Fall nachrangig ist, eignet sich das Vokabular, um die Datenmodellierung zu testen, sodass es als Best Practice für andere Institutsbibliotheken dienen könnte. 

<a name="4.2"></a>
### 5.2 Anwendungsfälle
Die Bibliothekarinnen im IDSL1 habe Interesse daran bekundet, das SKOS Vokabular auf der Institutshomepage zu verlinken.
- Katalogintegration: Anzeige der Systematikstelle beim Titeldatensatz mit Verlinkung zur Systematik-Ansicht
- Bestandübersicht: Generierung von Bestandsübersichten je Systemstelle, z.B. "Wie viele Titel in N12?"
- Digitale Sammlungen: Verschlagwortung von Digitalisaten nach IDSL-Systematik für verbesserte Auffindbarkeit und Vernetzung der Bestände
- Forschungsdatenmanagement: Klassifikation von Forschungsdaten des Instituts nach der Systematik
- Fachinformationsdienste: Bereitstellung der Systematik für germanistische FID-Dienste zur überregionalen Nutzung
- Automatische Klassifikation: Erprobung von Machine-Learning-Modellen zur automatischen Zuordnung von Neuwerbungen zu Systemstellen basierend auf dem SKOS-Vokabular


