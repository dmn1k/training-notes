# Agila Tag 2

 * Diagramme einfach, Diskussions/Kommunikationsgrundlage, Laufzeit nicht
   unbedingt gleich Sequenzdiagramm
 * Kontextdiagramm: Alles in der Aussenwelt um das System, auch Personen
 * "George Miller: Magical Seven": 7+-2 Dinge unterscheidbar
 * Story->Anforderungen->Tasks evtl besseres Modell als Story->Tasks, da
   Anforderungen evtl für mehrere Stories relevant

## Architektur im agilen Umfeld

 * Architekturanforderungen basieren immer auf fachlichen Anforderungen
 * Risikogetriebene Architekturarbeit (ATAM)
 * Evtl Iteration 0 für architektonische Grundlagen
 * Businessanforderungen auch technisch
 * Technische und fachliche Anforderungen sind orthogonal zueinander
 * Unbewusstes Wissen (Awareness test) berücksichtigen, was man ständig macht
   ist einem nicht mehr bewusst
 * Microserviceansatz als Basis für Architektur, unter Umständen Einfügen von
   Abhängigkeiten als Antwort auf Risiken
 * Iteration 0: Architekturvision (kurz, klar, akzeptiert)
 * Iteration 0 quasi als Grooming vor Projektstart
 * Kanban macht Prozessmängel sichtbar (Einzelne Produktionsstellen haben
   Kapazität)
 * Kanban dezentralisiert PO-Rolle, Priorisierung nicht Teil der Entwicklung
 * PO ist nicht Start des Prozesses, sondern nur eine Station => sollte auch WIP
   haben
 * Dokumentzentrisch vs Workshopzentrisch
 * Besser: Workshop->(Anforderungen, Akzeptanzkriterien)->Dokumente->Entwicklung/Test
 * Kanban: Pull statt Push auf Prozessebene

## Rolle des Architekten in agilen Projekten

 * Klassisch, unterstützend, Architekturagent (Entwickler mit Spezialwissen zu
   einzelnen Architekturthemen), kein ausgewiesener Architekt
 * Auswahl hängt ab von Wissensverteilung, nicht von Teamgröße
 * Mehrere Teams: Klassisch oder unterstützend oder gemischt
 * *Essence and accidents of software engineering* (brooks)
 * Rolle: Architecture Owner (teamübergreifend, Ansprechpartner) komplementär zu
   Product Owner (Frage: Wer macht PO auf Architekturrelevanz aufmerksam? Wie
   ist AO eingebunden?)
 * Conways Law: Eigene Verantwortlichkeit für Wissensgebiet Architektur(Wissen
   weitertragen, weiterentwickeln)
 * Architektur macht Businessanforderungen möglich, befreit von Risiken
 * Wichtigkeit von Architektur deutlich machen: In Sprache der Stakeholder,
   Kosten offenlegen (Cost of Delay)
 * *ISO 42010 Conceptual Model* (früher IEEE 1471): Beschreibung von Systemen
 * Nicht alles sofort digitalisieren
 * Viele Beispiele mit fachlichem Vokabular
 * Szenarien

## Architekturtreiber

 * Zielgruppengerecht: Glossar, Qualitätsszenarien (=Anforderungen)
 * Qualitätsszenarien wie Stories unscharf, für Vollständigkeit, Präzision durch
   Anforderungen
 * Qualität definiert durch Anforderungen welche Teil eines
   Qualitätsmerkmals/attributs sein können (eine Strukturierungsmethode), ISO 9126 als Basis aber individuell
   zu ändern
 * Anforderungsmanagement auch für nicht fachliche Anforderungen notwendig
 * Architekt erkennt Risiken und erzeugt dadurch eigene Anforderungen
 * Übergreifende Architekturaspekte evtl in DoD aufnehmen
 * Teil einer anderen Story, eigene Story oder übergreifend
 * Entwicklung von innen (fachl. Kern) nach außen (UI, Datenbank usw.) vs Top
   down (UI->Datenbank mit Prototypen)
 * Technische Schulden werden zu Architekturanforderungen
 * Tech. Schulden auf Architektur und Designebene möglich
 * Tech. Schulden -> Cost of Delay -> Vergleichbarkeit mit fachl. Anforderungen
 * Quadruple Constraint: Qualitäts-, Kosten-, Termin- und Funktionalitätsrisiko
 * Risikomaßnahmen: z.B. Squid
 * Unterschiedliche Priorisierungsmethoden z.B. AHP, CV, LST
 * Der letzte Vernünftige Moment <-> Real Options Theorie (wenn zu lange
   gewartet wird ist evtl Option weg)

## Architekturen im Team

 * Kooperativ: Mehr Ideen und Prüfungskapazität
 * Entscheidung entgültig
 * Risiko: Produktivität sinkt weil sich manche als Verlierer sehen
 * Gesichtsverlust vermeiden
 * Konsens, Quantifizierung, möglichst objektive Enscheidung
 * Entscheidungsmatrix
 * Konsens vs Kompromiss, evtl durch Thumb-Voting
 * Wenigste Negativstimmen gewinnen um Vorschlag mit wenigster Ablehnung
   umzusetzen
 * Moderation entscheidend, verschiedene Methoden
 * Prozess zum Umgang mit Widersprüchen/Einwänden etablieren, damit sich niemand
   übergangen fühlt
 * Kommunikation entscheidend
 * Regelmäßig reflektieren
 * Vertrauenskultur etablieren
 * Widerstände ernst nehmen
 * Förderung lokaler Entscheidungen: Kommunikation über Schnittstellen,
   Information Hiding
