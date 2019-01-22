- Java 9+ Talk (Releasezyklus, LTS, Modulsystem, missioncontrol usw open sourced, G1 collector, ZGC, WebStart discontinued...)
- Wie spielen Maven und Module zusammen?
- Unterschiede in module-exports: requires, opens, provides, ...
- NTTData -> Ikigai (jap. learning framework)
- Web Components anschauen, genau wie Angular Elements (Angular => Web Components)
- DPL in NG ist extremer Lockin auf Angular, weil alles davon abhängen wird. Evtl besser WebComponents (Angular Elements?)
- asciidoc -> revealjs (frank hat hier ahnung)
- Microfrontend-Poc anschauen
- cypress.io e2e tests


- MaFit-Vorträge filmen und intern archivieren
- Weiterbildungskalender
- Es muss klar sein wer wo hin darf und für alles was nicht offen ist (Arch-Kata) einen gleichwertigen Ersatz geben
- Teilnehmerlisten wirklich notwendig?
- "Könner" hervorheben, aber taktvoll. Wie?
- Mal CodeWars und CodinGame verwenden
- Webmontage in NBG?
- "KloKlug", Klowledge Manager: Infos auf Toilette
- Warum keine Scheuklappen: Resilient gegenüber den (sicher irgendwann kommenden) Änderungen sein => wertvoller für Firma und sicherer
    - Außerdem: Ermöglicht paradoxerweise erst Fokus, weil man vieles einfach kennt


- func programming talk ideas
    - effects gemanaged ausführen, functional core imperative shell
    - weil typsystem statisch weiß, dass etwas keinen effekt hat, kann gecached werden (pure function, quasi lookuptable)
    - Functions als Objekte in Java zeigen, Lambda-syntax demystified => kein first-class-citizen
    - Currying von Haskell E. Curry (vs "schönfinkeling"): bind bindet argument und gibt neue "gecurryte" funktion zurück, in der der wert statisch der gebindete wert ist
    - funktionen, monaden (optional, try, completablefuture, ...), evtl. railway-oriented programming idee kurz skizzieren, map/reduce pattern
    - joo-lambda bzw. javaslang/vavr zeigen (geht da currying bzw. auch pattern matching?)
    - was ist neu in java 9+?
    - werte als typconstraint (bspw in idris => dependent types)
    - algebraic datatypes (case classes in scala) und pattern matching (auch java zukunft erwähnen, v.a. auch vs visitor oder instanceof-kaskaden)
    - clojure ref und co, software transactional memory, kann alles quasi mutable machen

- JetBrains MPS:
    - Language workbench, graphisch und textuell gemischt
    - DMN: Decision Model and Notation, tabellarische Entscheidungsmatrix