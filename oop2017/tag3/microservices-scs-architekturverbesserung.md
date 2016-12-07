# Architekturverbesserung mit Microservices und SCS
*Referenten: Alexander Heusingfeld, Michael Vitz*

- Monolith enthält normalerweise viele Fachdomänen
- Außerdem Strukturierungskonzepte wie Module und Frameworks usw
- Ziele: Verständlichkeit und niedrige Cost of Change, Realität oft genau
  andersrum
- Oft schnell gewachsene Systeme, Komplexität und Teamgröße steigt, Fluktuation
- Solche Systeme sind in der Regel erfolgreich, sonst gäbe es sie nicht mehr!
- Entwickler erkennen Probleme zuerst, da sie damit leben müssen (WTFs per
  minute)
- Entwickler fordern Improvements => Refactoring-Sprint
- Kernprobleme lösen in kurzer Zeit nicht möglich, es wird nur an Oberfläche
  gekratzt
- Hohe Kopplung heißt kleine Änderungen können riesige Auswirkungen haben
- Häufig Fokus auf Technologie statt auf Business Value
- Improvement is more than refactoring
- aim42 - Architecture Improvement Method
- Open Source/Collaboration auf GitHub
- In der Praxis bewährte Methoden, nicht nur Theorie
- Iterativ: Analyze->Evaluate->Improve
- Analyze: Architekturdokumentation, Code sichten; Laufzeitumgebung betrachten;
  Organisation betrachten
- Probleme und Lösungsvorschläge sammeln
- Evaluate: "Wert" der Probleme/Risiken/Lösungsvorschläge ermitteln um damit mit Management diskutieren zu
  können (price-tag)
- Improve: Strategie definieren, Refactorings, Architektur ändern, Organisation
  anpassen
- Annahmen explizit machen
- Diverse Practices, nicht nur Refactoring
- System aufteilen, breaking the monolith => diverse Praktiken wie Split, Branch
  by abstraction, strangulate, ...
- Sammlung von sinnvollen Praktiken ähnlich wie Working Effectively With Legacy
  Code
- Module sollen explizite Grenzen haben
- Direktes Aufrufen von Klassen/Interfaces vs z.B. REST-Schnittstelle => Kosten
  werden bewusst
- Komponentenschnitt entscheidend => möglichst autarke services / keine sync
  calls in andere module notwendig
- Microservices kein Allheilmittel
- Architektur ist kein Selbstzweck
- Microservices-Definitionen nicht eindeutig, viel Spielraum offen,
  Bullshit-Bingo
- Big Bang Umstellung risikoreich, besser Frontend-Switch (Reverse Proxy, leitet
  Teil der Anfragen an neues System weiter, erlaubt step-by-step umstellung)
- Security, Logging nun anders als wenn man nur Monolithen hat
- Change on Copy(Aufteilung schwierig da Monolith sehr komplex, unbekannt): Sourcecode-Repo kopieren pro neu identifiziertem Service,
  Inhalte aus anderen Services entfernen, sehr langwierig
- => Erzeugt Request-Kaskaden, Performanceprobleme
- Release It Resilience-Patterns: isolate failure, apply graceful degradation, responsive
  in case of failure
- Netflix Hystrix
- Change via Extraction(ich weiß bereits welche services entstehen sollen):
- Schnitt fachlich! Services können im besten Fall Use-Case end-to-end abbilden
  (bounded context)
- Request Cascades lower availability!
- Service Discovery: Reicht DNS oder ist Registry wie Consul, etcd notwendig?
  Heartbeat?
- Performance in Discovery z.B. ein Kriterium für sophisticated registry
- Consul: Datacenter übergreifende Discovery möglich? TODO
- Strangulate bad parts: Frontend switch, kill bad parts over time
- Langsam anfangen Services aufzubauen um Betrieb nicht zu überfordern
- Domain, Macro, Micro Architecture => Lokale Entscheidungen fördern
- Abstimmungen zwischen Teams in Macro-Architektur notwendig, Micro-Architektur
  kann jedes Team gestalten
- Einzelne Services können so Technologien/Prozesse wählen die perfekt auf ihre
  fachlichen Anforderungen passen
- SCS: Komplette Vertikale von UI bis DB in einer fachlichen Domäne / Bounded
  Context
- Optional: API, Business Logik in weitere Services aufteilen
- Wichtig: Eigene Datenhaltung, möglichst wenige Abhängigkeiten zu anderen SCS
- Autonomie: Ein SCS pro Team, evtl auch mehrere SCS pro Team aber keinesfalls
  ein SCS und mehrere Teams
- Optimal: Oberflächenintegration über Links (ROCA)
- http://scs-architecture.org
- aim42: Structure for software modernization
