# Application Performance Management with Open Source Tools
*Referent:*

- open-source APM: inspectIt
- Nachteil Lizenzkosten bei kommerziellen Lösungen v.a. bei Microservices oder
  IoT (sehr viele Agenten)
- Open Source: Keine one-fits-all Lösungen sondern Kombinationen notwendig
- Automatisch erstellte Flow-Maps z.B. über Pinpoint
- Time-series db (Influx, Prometheus)->Grafana/Kibana
- Alarmierung, Anomalieerkennung z.B. Grafana, InspectIt
- Perf-Zahlen nur in fachlichem Kontext sinnvoll bewertbar
- Mapping techn. Request auf fachliche Transaktion
- Tracing: OpenTracing, Dapper
- e2e Antwortzeiten aus z.B. JMeter extrahieren und in Jenkins/InspectIt
  verarbeiten/auswerten
- Jenkins Failure bei Threshold-Überschreitung inklusive Kontext z.B. über
  InspectIt
- WebPageTest, sitespeed.io
-

