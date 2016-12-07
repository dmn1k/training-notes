# Agila Tag 3 - Daniel Ried

## Architekturen im Team entwerfen

 * Architekturprinzipien als Leitplanken für Teamentscheidungen
 * Prinzipien: Konstruktiv, Testbar, Nachvollziehbar, Signifikant
 * Lokale Entscheidungen im Team fördern z.B. durch Microservices oder CQRS
 * Tradeoff globale / lokale Optimierung, z.B. Kompromisse bei
   Technologieentscheidungen um nicht zu heterogen zu werden
 * Unabhängigkeit sorgt für Redundanz, Verlust konzeptioneller Integrität und
   Inkonsistenzen
 * Entscheidungen so spät wie möglich für maximalen Wissensaufbau (Letzter
   vernünftiger Moment)
 * *Set-based Design* bei hoher Dringlichkeit und hohem Risiko
 * SBD: Jede Alternative in Set möglicher Lösungen (parallel) ausprobieren und testen /
   Feedback sammeln
 * Zu späte Entscheidung => Tech. Debt
 * LVM verschieben durch Abstraktionen, Standards, flexible Lösungen
 * Derartige Entscheidungen als Backlog-Item anlegen (Teil einer fachlichen
   Story, eigene Story oder allgemeiner Merker)
 * Architektur kommunizieren: Architekturwand, Daily Standups, Workshops usw
 * Architekturwand: Überblick, analog, von allen jederzeit einsehbar, evtl.
   Webcam

## Reflexion und Feedback

 * Regelmäßig zusammensetzen, möglichst leichtgewichtig
 * Metriken
 * Auch teamfremde Entwickler und Stakeholder einbeziehen
 * In Releaseplanung aufnehmen
 * Möglichst viel automatisieren (Testdurchführung und -auswertung)
 * CI
 * Root Cause Analysis z.B. Ursachen-Wirkungs-Diagramm
 * Zyklen auflösen: Irgendwo mit möglichst wenig Kosten oder beteiligten Root
   Cause und davon abhängige Probleme lösen
 * Infrastructure as code, Container (Docker) usw. in CI
 * Goal-Question-Metric Methode: Fragen bezogen auf ein Ziel und Metriken die
   Zielerfüllung zu messen
 * Microservices hauptsächlich organisatorisches Problem / Team- und
   Unternehmensstruktur

## Case Study OTTO

 * Matrix- und Linienorganisation und orthogonal dazu CoPs
 * Mehrere Teams bilden eine Delivery Unit
 * Ein Team betreut einen Bereich komplett (Vertikale)
 * APOLLO: "Featureteams", d.h. mehrere Teams auf einer kompletten Codebasis

## Case Study Spotify

 * High Alignment, High Autonomy
 * Internal open source
 * Release trains, feature toggles
 * Cross-pollination > standardization
 * Fail fast
 * continuous improvement
 * decoupled arch -> limited blast radius
 * squad health check model: karten, abstimmen, ampel, regelmäßiger workshop
 * Canary releases, A/B tests
