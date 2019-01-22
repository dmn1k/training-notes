# Sollbruchstellen in Microservices

- Schnitt zu groß: Monolith, Teams stehen sich auf den Füßen, ...
- Schnitt zu klein: Verteilter Monolith, oft primär technisch, Fachliche
  Komplexität verlagert sich in Kommunikation, Debugging/Fehlersuche schwierig,
  Betrieb (kleinteilig, aufwändig, Ressourcenverbrauch), Performanceprobleme
  durch lange Aufrufketten
- "Monolith first" und Sollbruchstellen einbauen
- Event Storming für initialen Schnitt
- Technischer Feinschnitt am Ende: Speed, Isolation, Redundanz, Größe,
  Verteilung
- Technisch nur Feinjustierung
- Microservice-Referenzarchitektur definieren, bspw. hexagonale Architektur
- Zeitliche Entwicklung berücksichtigen, Domäne erst mal verstehen
- Erkenntnis: Fachlichkeit in dem einen Service wächst =\> Indikator hier
  evtl. aufzuteilen
- Sollbruchstellen über alle Schichten einziehen (Trennung auf Package-Level)
- Ermöglicht auch leichten Rollback auf Version ohne Sollbruchstelle.
  Fachlichkeit lässt sich beobachten und entsprechend reagieren
- Frühzeitig in Logging und Monitoring investieren: Der Preis für autonome
  Services
- Fachliches Monitoring wichtig
- Früher: Trennung nach Datenobjekten (Ziel: Möglichst keine Redundanz), in MS:
  Führt zu sehr hoher Kommunikationskomplexität
