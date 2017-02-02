# DDD und REST
*Referent: Oliver Gierke, Pivotal*

- olivergierke.de
- Domain-Driven Design Quickly, infoQ
- Value Objects, alles Strings => Typsystem hilft nicht
- "Stringly typed code"
- Typen explizit machen, z.B. EmailAddress
- Validierung bei Erzeugung, sichere Annahmen möglich (ist immer valide
  Email-Addresse)
- Make implicit concepts explicit
- Domäne gruppieren in Aggregate => allein über JPA-Entities nicht ausdrückbar
- Zugriff über Aggregate Root erzwingt Geschäftsregeln
- Domain-thinking instead of Datastore-thinking
- Aggregates = Scopes of consistency => Transaktionsboundary
- Bounded Context => Unterschiedliche Sichtweisen of Domäne
- Versand und Rechnungsabteilung interessieren z.B. völlig andere Eigenschaften
  einer Bestellung
- Allgegenwärtige Sprache, Ubiquous(TODO: spelling) Language
- Domänenkonzept normalerweise in mehreren Bounded Contexts
- Customer => User Registration, Accounting, Shipping
- Aber Customer-Aggregat global eindeutig identifizierbar
- Daten werden teilweise dupliziert, Herausforderung Synchronisierung (wenn
  überhaupt notwendig, da unterschiedliche Sichten)
- Anemisches Domain Model, Verletzung von Law of Demeter => Domänenobjekt selbst
  kann Regeln nicht enforcen
- If you're calling two setters in a row, you're missing a concept
- Direkte Abhängigkeiten zwischen Bounded Contexts => enge Kopplung =>
  Änderbarkeit
- Feature Creep, Einführung neuer Bounded Contexts wirkt sich auf alte aus
- Sync REST-Calls => komplexes verteiltes Fehlerszenario, verteilte Transaktion
  notwendig, Performanceprobleme => konzeptuelles Problem gegen das auch keine
  Technologie wie Hystrix wirklich hilft
- Domain events to the rescue
- Spring Data -> AbstractAggregateRoot
- Event Sourcing anstatt destruktiver Datenbankänderungen die Transaktionen
  voraussetzen
- Domainevents z.B. über Atom Feeds exponieren
- REST != CRUD via HTTP
- Generisches Interface erhöht Client-Server-Kopplung, da Logik dupliziert
  werden muss
- Representation design > URL-Aufbau
- Wie sieht JSON-Struktur aus?
- Aggregate und REST-Ressourcen haben gleiche Anforderungen (Identifiable,
  Referable, Scope of consistency)
- Hypermedia / HATEOAS -> Evolvability
- Hypermedia: Data and navigation information
- HATEOAS: Links optional, zeigt Client was erlaubt ist
- Bsp RESTBucks
- Links im JSON => Erlaubte Transitions in "State machine"
- Client trifft Entscheidungen anhand Vorhandensein von Links
- Non-hypermedia: Viel Domänenwissen im Client notwendig, wenig Protokollwissen
  notwendig, Hohe Kopplung zu Server
- Hypermedia: Exakt das Gegenteil
- Protokollwissen vs Kopplung
- JSON, Links stabile Konzepte
- Ermöglicht non-breaking changes ohne Versionierung
- API evolvability is key in a system of systems
- Blogpost: Evolving Distributed Systems
- CDC zu spät, früher Fokus auf evolvierbares Protokoll wichtig
- Optimistic Locking -> ETags, Caching-HTTP-Header
- Keine DB-Ids exponieren, URIs!
- Spring RESTBucks-Implementierung als Beispiel => Oliver Gierke GitHub, Blog
