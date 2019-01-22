# Microservices und Transaktionen

- Benötige ich fachlich wirklich Transatktionen?
  (enterpriseintegrationpatterns.com/ramblings/18\_starbucks.html)
- Strategie 1: Lazy Evaluation -> Eventual Consistency
  - Vorher schauen, wie viele Items aktuell verfügbar sind um Wahrscheinlichkeit
    zu erhöhen, dass alles gut gehen wird
  - Ansonsten Kompensation
- Chris Richardson (Buch "Microservices Pattern" oder Blog)
- Geänderte Servicegrenzen => Verteilter Monolith
- XA / 2PC => Langsam, Ressourcen müssen es unterstützen
- Saga Pattern: Aus Paper von 1987 (SAGAS, Hetor Garcia-Molina)
  - Abbildung über mehrere lokale Transaktionen (technisch)
  - Abfolge ist wohldefiniert => Datenkonsistenz
  - Service kommuniziert erfolgreiche TXN an nächsten Service
  - Lokale Transaktion legt Daten mit Status "Pending" an => Neuer fachlicher
    Status notwendig
  - Bei Fehler: Kompensation aller bereits erfolgten Teilschritte
  - Kompensationsschritte können auch schiefgehen und brauchen damit ihrerseits
    Kompensation (am Ende evtl. einfach manuelle Korrektur)
  - Steuerung über Choreographie oder Orchestration
    - Choreographie: Implizite Sequenzsteuerung, verteilte Koordination über
      Events =\> einfach, lose gekoppelt aber u.U. Zyklen, hohe Komplexität,
      Ablauf implizit, Kopplung nur pseudo lose (Services wissen was sie bei
      bestimmten Events tun müssen, WF-Änderungen u.U. schwierig)
    - Orchestration: Explizite, zentrale Steuerung ("Saga-Koordinator"), Command
      / Handler-Pattern, beteiligte Services haben kein "Wissen" über
      Gesamtworkflow. Pro: Logik an zentraler Stelle, Contra: zu viel Business
      Logik in Orchestrator
      Saga Frameworks oder Lightweight Workflow Engines verwenden, nicht selbst
      bauen!
  - Aktion und Erfolgsnachricht muss transaktional erfolgen!
  - SAGA = ACD (Isolation fehlt)
