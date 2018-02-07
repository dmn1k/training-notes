# Eventsourcing

- Egal ob Microservices, Packages oder sonstige Modularisierung oder auch ein "wohlstrukturierter Monolith": Schnitt/Struktur ist entscheidend
- Kommunikation zwischen Bounded Contexts (aka Microservices) über Events
- Nachteil an Event: Properties fuer alle Anwendungsfälle müssen mitkommen und koppeln so doch => kaum noch änderbar
- DDD: Published Language => DAS eine Modell => Im Gegensatz zu spezialisierten Modellen aka Bounded Contexts

- Spezialisierte Events: Unabhängige Weiterentwicklung, einfach verständlich, Erweiterungen benötigen neue Events (kann viel werden)
- DDD: Customer/Supplier

- Universelle Events nur mit ID und spezialisierte API zum Abholen der Informationen => Trade-off

- => Implizite Replikation, potentiell Inkonsistenzen
- => Eventual Consistency (sichergestellt über Middleware die Events irgendwann zustellt)
- Wichtige Frage: Was passiert wenn es 0.1s/1s/1min, ... dauert bis die Daten verfügbar sind

- Reihenfolge der Events wichtig, kann unter Umständen durch Middleware garantiert werden
- Event Sourcing: Alle Events in Event Store, Event Handler kann Snapshots speichern
- Beim Replay dürfen bereits durchgeführte Effekte (bspw. Rechnung verschicken) nicht nochmal ausgeführt werden
- Alte Events können veraltetes Schema haben
- Weitere Vorteile: Replay möglich, Auditing, Time-based queries, Einfache Schemamigration für Snapshots, Debugging

- Kafka speichert alte Events, könnte also als Event Store dienen
- Das ist dann ein globaler Event Store, der Published Language benötigt (groß, unübersichtlich, schwer änderbar)
- => Event Sourcing is pattern for state management (entscheidung lokal pro microservice)

- CQRS: Command Queue (Create Invoice!) => Command Handler => Database
- Query handler liest aus DB
- Command Store analog zu Event Store
- Lesen bspw über Replica
- Gemeinsame DB => gemeinsames Schema => nur zusammen änderbar
- => Command führt zu Event => Event Store

oop2018@ewolff.com