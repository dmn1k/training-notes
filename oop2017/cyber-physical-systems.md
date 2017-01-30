# Cyber-Physical Systems - Die etwas anderen Dinge im IoT
*Referent: Frank Buschmann*

- Integration zw computation, networking, physical processes
- Events in sehr kurzer Abfolge, near-realtime verarbeitung notwendig, cloud
  evtl suboptimal wegen latenz
- In sich geschlossene Systeme, müssen funktionieren wenn Abhängigkeiten (Cloud)
  nicht verfügbar
- Zusammenspiel physikalischer prozess <-> cps
- failure modes wichtig, z.b. stehen bleiben auf kreuzung ungünstig, d.h.
  "operational failure mode", graceful degradation
- interoperatibilität zw. herstellern (google mit tesla zb)
- 5C architecture:
  - Smart Connection Level: PnP connectivitiy, ...
  - Data Information Level: Daten unterschiedlicher Sensoren korrelieren, daraus
    Bedeutung extrahieren, Daten->Fakten
  - Cyber Level, Cognition Level, Configuration Level
  => Nicht layered oder tiered arch. sondern mental model
- CPS Netzwerk aus Komponenten inkl Hardware

## Architecture

- OS, evtl real-time
- Wertschöpfung durch digitale Schicht, ändert sich sehr schnell, deutlich
  schneller als bisher => App, Microservice-Konzept
- Basisdienste die geteilt werden wie z.B. Data Mgmt, Security, Networking,
  Resource Mgmt, ...
- Messaging / Eventing
- Containerized services
- Software defined networking, IEEE802 Time Sensitive Networking

## Detailbetrachtung

- Self awareness: digitales Modell eigener Struktur, Zustand, Umwelt
- Digitaler Zwilling / Digital Thread
- Digital Twin Management
- Semantic Information Models bringen Semantik in Rohdaten, Sprache der
  Schnittstellen des Digital Twin, Beschreibung durch Ontologien wie W3C OWL,
  OPC UA
- Semantische Modelle definieren ziemlich aufwendig
- Pub-Sub MoM: DDS (Data Distribution System, geistiger Nachfolger von CORBA),
  OpenFlow für QoS-Garantien
- Half object plus protocol: Statische Daten duplizieren
- Konzept der Micro Databases by ABB
- CLAP-theorem, L fuer Latency, waehrend Nachricht unterwegs ist temporaere
  Inkonsistenz
- Reflective Architecture: Meta-level services greifen auf digital twin zu,
  machen decisioning und greifen auf Basis-Dienste zu um Aktionen durchfuehren
  zu koennen wie Bremsen
- Self-X Functions: Optimierung, Forecast, Estimation
- Constraint-solving, neural networks
- Semantic-matching between CPS components
- Numeric constraint solving fuer beste collaboration parameter
- Ontologie von Faehigkeiten matched mit Ontologie von Aufgabe,
  herstelleruebergreifend, extrem kompliziert solche semantischen Modelle
  aufzubauen
- PnP services bieten Dienste an bzw nutzen Dienste und gleichen Constraints ab
- Objekt muss selbst wissen was sie braucht, kann, Randbedingung => Zero
  Engineering
- Herausforderung security: System ändert sich dauernd
- Security architecture: Sichere Bausteine bilden rekursiv sicheres System
- Security in extremem Frühstadium, PnP-Systeme gibt es aber bereits
- Safety: Clear separation between safety criticial und nicht critical
- Safety: Konservative Abhandlung, "neue Welt" separat (reference arch by NAMUR)
- Safety: Separierung der Hardware z.B. in Automobilbereich
- Resilience extrem wichtig
- Fail-safe: Alles auf stop, sehr teuer, nicht immer praktikabel (z.B. Flugzeug)
- Fail-operational: Graceful degradation, z.B. an Straßenrand fahren
- Fault-Tolerance: MTTR minimal wenn MTBF nicht beeinflusst werden kann
- Robustness
- Sensor-fusion-architecture: Sense->Understand->Act
- Sensoren -> Digital Twin -> Semantic Reasoning -> Warn/Assist/Control
- Deployment: Safety-critical, real-time funktionalität nah an
  hardware/embedded; infotainment z.b. in cloud
- Balance: Automatisierung vs manuellem Design
- IoT-Scale: Nichts ist fertig, konsistent, kontrollierbar. Es ist immer etwas
  kaputt
- Think distributed, async
- Verschiedene Stufen der Kontrollabgabe bis hin zu System ignoriert externe
  Eingaben
- Auch hier agile Softwarepraktiken: Microservices, DevOps, Continuous
  Deployment, Containerization
- Schnell evolvieren: MVP->Feedback/Innovationsschleife auf Basis von harten
  Daten->Continuous Delivery

