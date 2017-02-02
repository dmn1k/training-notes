# Blockchain im öffentlichen Sektor
*Referenten: Christof Tinnes, Phillip Pham, Carmen Eisenacher Capgemini*

- Verzeichnisse dokumentieren Aussagen zwischen "Handelspartnern"(z.B.
  Banktransaktionen)
- Problem nur wenn es Widersprüche gibt
- Bisher: Zentrale Instanz hat Hoheit über Verzeichnis
- Leichte Datenkonsistenz vs Vertrauen in Mittelsmänner, Transaktionskosten
- Verteilt: Konsens, Redundanz vs Vertrauen, Nachvollziehbarkeit, Schnelle
  Clearings
- Konsens durch Lösen einer komplizierten, zufälligen Aufgabe. Wer als erster
  löst darf Entscheidung festlegen
- Betrüger bräuchte deutlich mehr Rechenpower als Rest
- Transparenz, Integrität, Manipulationsresistent, Sicher, Alle Teilnehmer
  gleich
- Öffentliche Blockchain: Wert als Anreiz zum Lösen der Aufgaben
- Permissioned vs Permissionless
- Private vs Public
- Byzantinischer Fehler => Proof of Work
- Transaktion: Sender, Empfänger, Inhalt, Herkunft
- Peers holen Transaktion ab -> verteilt sich im Netzwerk
- Spezielle Knoten bündeln Transaktionen in Blöcken
- Nonce: Zufallszahl, Prüfsumme, muss unter Zielwert bleiben => Mining,
  aufwendig
- Wichtig: Sicherstellung der korrekten Transaktionsreihenfolge
- Uhrensynchronisation nicht-trivial
- Außerdem zentrale Instanz
- Implizite Uhr durch Blockquelle in jedem Block
- Double-spend-attack: Gleichzeitig zwei unterschiedliche Transaktionen
  erstellen (sich widersprechend)
- Fork in ca 1,8% der Fälle in Bitcoin
- Netzwerk garantiert Liveness in diesem Fall indem längste Kette überlebt
- Welche Transaktion überlebt ist zufällig
- RAFT-Algorithmus zur Konsensfindung bzgl. Masterwahl
- Verschiedene Konsensmechanismen möglich: Proof of Work(Der Schnellste), Stake, Activity(teilweise Stake, teilweise Work),
  Tendermint, Stellar Consensus Protocol(Jeder vertraut bestimmten Quellen)
- Sehr breites Anwendungsfeld in unterschiedlichsten Branchen
- Digitale Wahlen, transparente Ausschüttung staatlicher Leistungen usw
- E-Identität => Wahltokens
- Probleme bspw. Sicherstellung Anonymität und Beeinflussung durch öffentliche
  Zwischenergebnisse
- Bluemix Blockchain
- Dezentrale Dokumentenverifikation
- Dokumente müssen nicht zentral gespeichert werden (Führungszeugnis,
  Geburtsurkunde)
- Wenig Experten, völlig andere Sichtweise, Akzeptanz z.B. der Regierung,
  digitale Identität nicht vorhanden, tech. Probleme (diverse Attacken, DDoS)
- => Dezentraler Konsens, manipulationsresistent, stark gehyped, unausgereift,
  viel Potential
- OSS: blockstack, hyperledger
