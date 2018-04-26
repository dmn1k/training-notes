# Docs-as-Code
Ralf Müller, Falk Sippach - @docToolchain

- Warum? Dokumentation notwendig zur Kommunikation, Bewertbarkeit, Frage nach Warum, Neue MA, Entwurfsunterstützung
- Nervt: Falsche Werkzeuge, Dateiablage, Textwüste, Handarbeit, veraltet leicht, liest eh keiner
- WYSIWYG Tools wie Visio, Word, UML-Tools usw. sehr aufwändig für Doku
- Stattdessen: Plain-Text (Markdown, AsciiDoc)
- Auch Grafiken: plantUml, ditaa oder auch in Tools erstellte und eingebettete Grafiken (bspw. yEd)
- Einbettung in normalwerweise genutzte Tools wünschenswert (IDE, Buildtool, Kommandozeile, Versionsverwaltung) 
- Redundanzen vermeiden: Inhalte generieren bspw. aus Swagger, über Annotationen, DB-Schema, ...
- Continuous Documentation: iterativ, kontinuierlich, automatisiert erstellt
- Sphinx reStructuredText als Tool
- Markdown: Nicht feature-complete im hinsicht auf Dokumentationen, diese features werden durch Dialekte ergänzt (=> Kompatibilitätsprobleme)
- AsciiDoc mit AsciiDoctor als Buildtool
- scaffolding über templates: arc42 für arch, volere, grails guides
- gradle empfohlen weil flexibler
- plantuml braucht graphviz auf dem system oder pragma graphviz_dot jdot (nutzt java emulation)
- plantum speichert metadaten im bild: java -jar plantuml.jar -metadata bild.png
- c4model von Simon Brown guter Start
- Modularer Ansatz für verschieden Stakeholder: Jeweils ein Haupttemplate das entsprechende Kapitel referenziert. Es können auch Teildokumente referenziert werden
- Asciidoc kann den Level einer Überschrift beim Import korrigieren
- pandoc: asciidoc -> docx
- AsciiDoc bildet DocBook-features ab. pandoc kann DocBook->word
- AsciiDoc -> XHTML -> push nach confluence über REST-API via gradle/maven -> confluence-seite erzeugt
- Inline-Kommentare werden bei Republish überschrieben
- Excel - POI -> AsciiDoc
- HTML SanityCheck (gradle plugin): broken cross-references, tag-fehler usw
- hemingwayapp.com, github.com/btford/write-good: linters
- AsciiDoc -> PPT, reveal.js
- AsciiDoc in PPT-Sprechernotizen => Aus einem AsciiDoc Präsentation UND Dokument generieren