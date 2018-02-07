# Resilient SW Design

- Verfügbarkeit: MTTF/(MTTF+MTTR)
- Traditionell: MTTF erhöhen
- "Resilient Ansatz": MTTR verringern
- "Things will crash. Deal with it"
- Wie?
    - Redundanz
    - Isolation
    - Lose Kopplung
    - Fallback

- Isolation durch Bulkheads:
    - Im Kleinen: Randfälle prüfen, Überläufe, ...
    - Datenmengen beschränken
    - Mit Fehlern rechnen
    - Im Großen: Unabhängig deploybare Einheiten (isoliert)

- "Starbucks does not use two-phase commit"
    - => strict vs eventual (letztendlich) consistency 

- Topic (publish/subscribe, nachrichten können verloren gehen wenn kein empfänger vorhanden)
- Queue (genau ein empfänger bekommt garantiert nachricht)

- AMQP alternativ zu JMS für Systeme mit Nicht-Java Bestandteilen
- MQTT: Bytestream aus IoT-Umfeld, QoS-Level für At moste once, At least once bzw. excactly once

- Synchron: Verzeichnisdienst wie DNS nutzen
- Eureka, Zookeeper, Consul, ...

- Clientseitiges Loadbalancing (Netflix Ribbon)
    - round robin, zone aware round robin, weighted response time

- zentraler session store wie redis (einfach über spring boot konfigurierbar)
- API Gateway bspw. Netflix Zuul

- Circuit Breaker wie Hystrix
- Liefert Fallback wenn aufgerufener Service nicht verfügbar oder langsam (inkl. Retry)
- Fehlerfälle begrenzen, bspw. read-only modus wenn schreiben nicht geht

