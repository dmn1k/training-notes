# Microservices sind ganz anders als man denkt
*Referent: Eberhard Wolff, innoQ*

- continuous-delivery-buch.de
- microservices-buch.de
- microservices-book.com/primer.html
- SOA done right?
- Beide nicht eindeutig definiert
- SOA: GUI/Portal -> Orchestration -> atomare Services
- SOA: Service besteht aus Modulen -> jedes Modul entspricht dann einem
  Microservice
- SOA: Layers; Microservices: vertikaler Schnitt (fachlich) => avoid layers
- Gute Architektur => Änderungen beschränken sich auf ein Modul
- SOA auf Unternehmensebene, Microservices lokale Entscheidung
- Microservices kann Teil von SOA-Umgebung sein
- Microservice nicht unbedingt REST-basiert -> Messaging, Data Replication, HTML
- Microservices are individually deployable modules
- blog.acolyer.org
- on the criteria to be used in decomposing systems into modules
- Module: Kleine Schnittstelle, Datenkapselung / Information hiding,
  comprehensible
- Backend for frontend: Spezielles Backend für Frontend (Mobile, web, ...)
- BFF, Layered: Änderungen an Businessprozess erzeugt viele Änderungen im
  System, gut für APIs, Weg den Netflix usw geht
- SCS: Autonome Webanwendungen, data und logic, no shared ui => otto, kaufhof,
  ...
- Möglichst wenige Interaktionen zwischen SCS
- Klassen: Information Hiding; Services: Genauso Datenkapselung
- Ein Service eine Datenbank
- Normalisierte, redundanzfreie, zentrale Datenbank nicht erstrebenswert
- DDD->Bounded Context als Kriterium für Serviceschnitt
- Unterschiedliche Sicht auf Daten je Service
- Geteiltes Schema sorgt auch für Kopplung zw Services, keine unabh.
  Änderbarkeit mehr
- Nicht zu viel Information verteilen, da sie in anderen Modulen verwendet wird
  und so Kopplung entsteht
- DRY trade-off auf serviceebene
- Reuse oft Illusion
- Reuse funktioniert am besten in OSS
- Reuse is hard, OSS demands high quality, high standards
- Code reuse erfordert Nutzung der gleichen Technologie, im Javaumfeld gleiche
  Bibliotheksversionen
- Reuse über service => erzeugt genauso abhängigkeiten
- => Still trade-off!
- Microservices macht derartige trade-offs sichtbar
- Abhängigkeiten zw Services u.U. auch Abhängigkeiten zw. Teams => Coordination
- Reuse vs independent development => Code, auch so Dinge wie Deployment
  Pipeline, ...
- Independent deployment vs integration tests
- Nur Schnittstellen teilen => Unabhängige Teams
- Fördert Service-lokale Entscheidungen(Technologie, Architektur, Deployment,
  Release schedule, Funktionalität)
- Gesamtsystem muss nicht mehr verstanden werden
- Änderungen normalerweise auf Vertikale beschränkt
- SOA und Microservices technisch ähnlich, architekturell unterschiedlich /
  verschiedene Ziele
- Unabhängigkeit, lokale Entscheidungen vs unternehmensweite Architektur
- Grobgranulare Module sind nicht unbedingt Microservices
- Microservices: Deployment harder, dev easier
- Schlechte Idee wenn Deployment und dev getrennt
- Zwischenstufen möglich z.B. klassische Module mit getrennten DB-Schemata aber
  nicht unabhängig deploybar
- oop2017@ewolff.com -> microservice liefert slides usw
