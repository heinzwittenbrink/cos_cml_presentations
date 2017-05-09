% XML and Content Management — DITA
% Heinz Wittenbrink
% 9. Mai 2017

## Zielsetzung

- Grundwissen über DITA
- Sammlung von Fragen
- Überlegungen zu einem Beispielprojekt


# DITA-Basics

## Warum DITA?

- Wiederverwendbarkeit von Inhalten

- Wiederverwendbarkeit von Modellen

- Trennung von Modell und Präsentation

- Orientierung an digitaler Ausgabe statt an papier-basierten Formaten

## Typische Vorteile

- supporting the publication of a range of information products for a variety of user types and across a number of product releases.

- to introduce new collections of content that would add new types of content (e.g., hardware documentation, business procedures, and so on)

([dita-demo-content-collection/README.md at dita-1.3 · dita-community/dita-demo-content-collection](https://github.com/dita-community/dita-demo-content-collection/blob/dita-1.3/README.md "dita-demo-content-collection/README.md at dita-1.3 · dita-community/dita-demo-content-collection"))

## Design-Prinzipien

- Minimalismus

- Vererbung/Objektorientierung

## DITA-Basics in Code-Beispielen

(Quelle: [Darwin Information Typing Architecture - Wikipedia](https://en.wikipedia.org/wiki/Darwin_Information_Typing_Architecture "Darwin Information Typing Architecture - Wikipedia")

### Ditamap file (table of contents) sample 
```
<source lang="xml">
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "map.dtd">
<map id="map" xml:lang="en">
  <topicref format="dita" href="sample.dita" navtitle="Sample" type="topic"/>
</map>
</source>
```

### Hello World (topic DTD)
```
<source lang="xml">
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE topic PUBLIC "-//OASIS//DTD DITA Topic//EN" "topic.dtd">
<topic xml:lang="en" id="sample">
  <title>Sample</title>
  <body>
  <p audience="foo">Hello World!</p>
  </body>
</topic>
</source>
```

### .ditaval file sample (for conditionalizing text) 
```
<source lang="xml">
<?xml version="1.0" encoding="UTF-8"?>
<val>
  <prop att="audience" val="foo" action="include" />
  <prop att="audience" val="bar" action="exclude" />
</val>
</source>
```
*Example of conditionalized text:*
```
<source lang="xml">
<?xml version="1.0" encoding="UTF-8"?> 
<p audience="foo">
This is an information useful for the foo audience! 
</p>
<p audience="bar">
This is an information useful for the bar audience. 
</p>
</source>
```
## Topics

> A topic is a unit of information with a title and content, short enough to be specific to a single subject or answer a single question, but long enough to make sense on its own and be authored as a unit.

> Topics are the basis for high-quality information. They should be short enough to be easily readable, but long enough to make sense on their own.

> Information typing is the practice of identifying types of topics that contain distinct kinds information, such as concepts, tasks, and reference information. Topics that answer different kinds of questions can be categorized as different information types. The base topic types provided by DITA ( a generic topic, plus concept, task, and reference ) provide a usable starter set that can be adopted for immediate authoring.

Quelle: [DITA topics](https://docs.oasis-open.org/dita/v1.0/archspec/topicover.html "DITA topics")

## Grundlegende Topic-Typen

- *Concepts*: DITA concept topics answer "What is..." questions. They include a body-level element with a basic topic structure, including sections and examples.
- *Tasks*: Task topics answer "How do I?" questions, and have a well-defined structure that describes how to complete a procedure to accomplish a specific goal.
- *Reference*: Reference topics describe regular features of a subject or product, such as commands in a programming language.

Quelle: [DITA topics](https://docs.oasis-open.org/dita/v1.0/archspec/topicover.html "DITA topics")

## Struktur, Content, Module

- [Topic structure](https://docs.oasis-open.org/dita/v1.0/archspec/dita_spec_22_topics_structure.html "Topic structure")

- [Topic content](https://docs.oasis-open.org/dita/v1.0/archspec/topiccontent.html "Topic content")

- [Topic modules](https://docs.oasis-open.org/dita/v1.0/archspec/topicmodules.html "Topic modules")

## Maps

[DITA map files are used for defining the topics of a publication, specifying the topic sequence, and controlling linking between topics.](https://www.oxygenxml.com/dita/styleguide/webhelp-feedback/Artefact/Maps/c_Working_with_Map_Files.html "Purpose of ditamap files")

- Defining the topics
- Specifying the sequence
- Controlling linking

Teile
- Topic Manifest definiert die Topics in einer Publikation
-  Hierarchy Definition Reihenfolge, Bedeutung, Navigationswege
-  Link-Beziehungen 

Siehe zu den Maps: [Purpose of ditamap files](https://www.oxygenxml.com/dita/styleguide/webhelp-feedback/Artefact/Maps/c_Working_with_Map_Files.html "Purpose of ditamap files")

Die Maps bestehen vor allem aus topicref-elementen. Diese gehören zur hierarchy und gegebenenfalls tz relationship tables.

## Beispiel topic map

```
<map>
  <title>DITA for the Impatient</title>

  <topicmeta>
    <author>Hussein Shafie</author>
    <publisher>Pixware</publisher>
    <critdates>
      <created date="October 7, 2009"/>
    </critdates>
  </topicmeta>

  <topicref href="introduction.dita"/>
  <topicref href="topics_and_maps.dita"/>
  <topicref href="topic.dita">
    <topicref href="topic_structure.dita">
      <topicref href="samples/sample_topic.dita" toc="no"/>
    </topicref>
    <topicref href="block_elements.dita"/>
    <topicref href="inline_elements.dita"/>
    <topicref href="link_elements.dita"/>
  </topicref>
  .
  .
  .
  <topichead navtitle="Topic maps">
    <topicref href="map.dita"/>
    <topicref href="bookmap.dita"/>
  </topichead>
  <topicref href="conclusion.dita"/>
</map>
```
Quelle: [DITA for the Impatient](http://www.xmlmind.com/tutorials/DITA/ "DITA for the Impatient")

## Publications and Collections


References:  [Publication and collection defined](https://www.oxygenxml.com/dita/styleguide/webhelp-feedback/Artefact/Maps/c_Publication_Defined.html "Publication and collection defined")

## Zentralisiertes Management von Variablen 

**Beispiel:**

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE reference PUBLIC "-//OASIS//DTD DITA 1.3 Reference//EN" "reference.dtd">
<reference id="product_warehouse_STA">
  <title>Product Name Variables</title>
  <shortdesc>Reused variable definitions.</shortdesc>
  <refbody>
        <section>
            <p>
                <table frame="none" id="table_47ae399c-8ad1-4f3e-9595-e7225da6becb">
                    <title>Variable names</title>
                    <tgroup cols="2">
                        <colspec colname="c1" colnum="1" colwidth="1.0*"/>
                        <colspec colname="c2" colnum="2" colwidth="1.0*"/>
                        <thead>
                            <row>
                                <entry>
                                    <p><ph>Used as...</ph></p>
                                </entry>
                                <entry>
                                    <p><ph>Name to use</ph></p>
                                </entry>
                            </row>
                        </thead>
                        <tbody>
                            <row>
                                <entry>
                                    <p><ph>Primary product name</ph></p>
                                </entry>
                                <entry>
                                    <p><term
                    id="ph_prodname">STA</term></p>
                                    <draft-comment>Change value here when primary
                                        product name changes. </draft-comment>
                                </entry>
                            </row>
                            <row>
                                <entry>
                                    <p><ph>Company name</ph></p>
                                </entry>
                                <entry>
                                    <p><term id="ph_companyname">Thunderbird</term></p>
                                    <draft-comment>Change value here when the
                                        company name changes. </draft-comment>
                                </entry>
                            </row>
                            <row>
                                <entry>
                                    <p><ph>Reporting system</ph></p>
                                </entry>
                                <entry>
                                    <p><term id="ph_clusterview">ClusterView</term></p>
                                </entry>
                            </row>
                            <row>
                                <entry>
                                    <p><ph>Controller system</ph></p>
                                </entry>
                                <entry>
                                    <p><term id="ph_clustercontrol">ClusterControl</term></p>
                                </entry>
                            </row>
                            <row>
                                <entry>
                                    <p><ph>End User</ph></p>
                                </entry>
                                <entry>
                                    <p><term id="ph_enduser">MobileView</term></p>
                                </entry>
                            </row>
                            <row>
                                <entry><p><ph>Data Syncrhonization System</ph></p></entry>
                                <entry><p><term id="ph_balance">ClusterBalance</term></p></entry>
                            </row>
                            <row>
                                <entry><p><ph>Analytics Server</ph></p></entry>
                                <entry><p><term id="ph_analytics">ClusterAnalyzer</term></p></entry>
                            </row>
                            <row>
                                <entry><p><ph>Data Persistence</ph></p></entry>
                                <entry><p><term id="ph_persistence">ClusterStore</term></p></entry>
                            </row>                            
                        </tbody>
                    </tgroup>
                </table>
            </p>
        </section>
    </refbody>
</reference>
```

## Anpassung/Spezialisierung


## Geschichte

März 2001: IBM stellt Kern-DTD und XML-Schema fertig

Mai 2002: Zur Topic-Spezialisierung kommt die Domain-Spezialisierung

2004 OASIS Technical Commitee

Februar 2005: IBM übergibt das DITA Open Toolkit an Sourceforge

Juni 2005: DITA 1.0

August 2007: DITA 1.1 (neue Bookmap-Spezialisierung)

2010: DITA 1.2 (Lernobjekte)

Material: [History of DITA](http://dita.xml.org/book/export/html/1047 "History of DITA")

17.12.2015: DITA 1.3 (Troubleshooting-Topic, Scoped Keys, MathML und Equation-Domains, Relax NG für normative Schemas
)

## Beispiele

- DITA-Dokumente: [dita-community/dita-demo-content-collection: DITA Demonstration Content Collection](https://github.com/dita-community/dita-demo-content-collection "dita-community/dita-demo-content-collection: DITA Demonstration Content Collection")°°°°°

- DITA-basierte Website: [The Content Era is here](http://www.thecontentera.com/live/php/viewpage.php?topic=home.dita "The Content Era is here")

- DITA-basiertes CMS: [DITAToo DITA CCMS](http://intuillion.com/products/ditatoo/ "DITA Content Management | DITAToo DITA CCMS: Your Easy Entry to DITA")

# Anwendungsmöglichkeiten

## Integrierte Content-Strategie

# Nächste Schritte


# Material

## Websites:

> DITA XML.org is the official community gathering place and information resource for the DITA OASIS Standard, an XML architecture for designing, writing, managing, and publishing information. We encourage you to contribute content to this site.

[DITA XML.org | Online community for the Darwin Information Typing Architecture OASIS Standard](http://dita.xml.org/ "DITA XML.org | Online community for the Darwin Information Typing Architecture OASIS Standard")

## Editoren:


- Oxygen
- [Xeditor, a CMS editor for XML content | I'd Rather Be Writing](http://idratherbewriting.com/2016/03/30/xeditor-xml-editor-for-your-cms-or-ccms/ "Xeditor, a CMS editor for XML content | I'd Rather Be Writing")

## Texte

[10 reasons for moving away from DITA | I'd Rather Be Writing](http://idratherbewriting.com/2015/01/28/10-reasons-for-moving-away-from-dita/ "10 reasons for moving away from DITA | I'd Rather Be Writing")



/Applications/Aquamacs.app/Contents/Resources/etc/schema/xhtml.rnc

[Step by step process to create new DITA project - Oxygen XML Forum](https://www.oxygenxml.com/forum/topic6637.html "Step by step process to create new DITA project - Oxygen XML Forum")

[DITA Maps Manager - Oxygen XML Editor](https://www.oxygenxml.com/xml_editor/dita_maps_manager.html "DITA Maps Manager - Oxygen XML Editor")


[Reusing DITA Content](https://www.oxygenxml.com/doc/versions/19.0/ug-editor/topics/eppo-pathfinder-reuse.html "Reusing DITA Content")

## Tools

- [XMLmind DITA Converter](http://www.xmlmind.com/ditac/what_is_ditac.html "XMLmind DITA Converter: XMLmind DITA Converter")

- [DITA Open Toolkit](http://www.dita-ot.org/ "DITA Open Toolkit")

## Meine DITA Links

[Pinboard: bookmarks for heinzwittenbrink tagged 'dita'](https://www.pinboard.in/u:heinzwittenbrink/t:DITA/ "Pinboard: bookmarks for heinzwittenbrink tagged 'dita'")
