# Code as a crime scene - Adam Tornhill

- Codescene analysiert Source-Code-Repositories und findet u.a. Hotspots, d.h.
  Code der häufig geändert wird und relativ komplex ist bzw. stark an
Komplexität zunimmt

- Patterns: Wenn Komplexität stark sinkt wurde wohl refactored, wenn
  Komplexitätslevel gleich bleibt werden nur kleine Fixes durchgeführt (da
wahrscheinlich niemand den Code anfassen will)

- Hotspot-Analysen könnten in Retrospektiven verwendet werden, in denen die
  technische Dimension oft fehlt - allerdings geht es hier um Trends und nicht
um absolute Zahlen (Heuristik, keine automatisierten harten Entscheidungen)

- Normalization of deviance: Wenn immer wieder von der Norm abgewichen wird
  ("wir machen das mal schnell so") wird damit eine neue (niedrigere) Norm
geschaffen (Buchempfehlung "The Challenger launch decision")

- Wie wird Komplexität gemessen: Cyclomatische Komplexität ist nicht gut
  definiert (gibt viele Edge Cases und Tools implementieren sie
unterschiedlich), einfachere Metrik: Indentation base, d.h. Messung des
"Negativraums"

- Formen der Kopplung: Physisch (es gibt direkte Abhängigkeiten im Code) und
  zeitliche Kopplung (zwei oder mehrere Source-Dateien werden immer oder
meistens zusammen geändert)

- Temporal coupling ist nur problematisch wenn es unerwartet ist (Heuristik!)

- Duplizierung wird erst dann ein Problem, wenn sich die Kopien in die gleiche
  Richtung entwickeln. Wenn sie auseinanderdriften wäre eine Eliminierung der
Duplizierung wahrscheinlich die falsche Abstraktion

- Proximity ist wichtig für Verständnis: Dinge die zusammengehören sollten
  physisch nah beieinander sein

- Es gibt tatsächlich keinen Unterschied zwischen Produktions- und Testcode.
  Beides muss gleichermaßen gewartet werden.

- Diffusion of responsibility: Wenn zu viele Leute involviert sind, fühlt sich
  keiner mehr verantwortlich

- Codescene erlaubt auch soziale Analysen: Wer sind die Wissensträger für
  einzelne Codeteile, wie hoch ist der Schaden wenn eine bestimmte Person das
Team verlässt, Wie sind die Kommunikationsstrukturen (Conways law)



