# Cloud-native stack

- GIFEE - Googles infrastructure for everyone else
- Microservices, Containers, dynamic execution
- MTTR->MTTF
- Eight fallacies of distributed computing
- Everything fails all the time
- Treat resources as cattle, not pets
- Scale out, not up
- Design for performance, automation, resiliency, elasticity, delivery,
  diagnosability
- Maturity model: Virtualized, Loose Coupled, Abstracted (fehlertolerant,
  infrastruktur-agnostisch), Adaptive (skaliert automatisch anhand von stimuli)
- 12 Factor App Principles
- Cloud native stack: Cluster virtualization abstrahiert von hardware, cluster
  scheduler führt container auf ressourcen aus, cluster orchestrator fuehrt
  applikationen aus, platform
- Viele Optionen, einige etablierte Kombinationen
- PaaS wie OpenShift, Heroku
- GiantSwarm = Managed Kubernetes
- Dekomposition in Microservices: Tradeoff Komplexität vs Skalierbarkeit
- Hystrix u.a. Circuit Breaker, gute Spring-Integration
- Dockerfiles: Umfang Base-Image beachten, Layering beachten (Platz,
  Maximalanzahl aber Caching-Mechanismus), Umgebungsvariablen definieren,
  Versionierung!
- Es gibt Docker-QA-Tools
- Spring Boot: executable=true => ausführbare jar-datei
- Spring Boot erzeugt hier Bash-Skript in Jar-File, Bash muss installiert sein!
- API-Gateway: Im Prinzip Reverse Proxy, Routing => Traefik, Nginx, ...
- Monitoring: ELK, Prometheus
- Docker Compose
- Docker Swarm nicht production ready, hat sich viel von Kubernetes abgeschaut
- Consul: Service discovery und distributed configuration
- Minikube: single node kubernetes cluster lokal
- https://get.k8s.io
- Kubernetes: Master-Minions
- Master: API, Scheduler, etcd für Clusterstate
- Minions: Kubelet->führt Pods mit Containern aus
- Pod: Kleinste Einheit, enthält 1..n Container
- Pod stirbt als Ganzes
- Labels können an allem hängen zur Identifikation
- Service: Abstraktion über logische Pod-Sammlung, hat DNS-Name
- Service: Load Balancing auf Pods, findet diese über Labels
- Replica Set: Instanzen an Pods, für Skalierung
- Deployment: Deklaration für Pods, Replica-Sets => Management-Einheit
- Architekturentscheidungen: Single vs Multi-Container Pods
- Deploymentdeskriptor über YAML-File
- Servicedefinitionen in YAML-File finden Pods über Selector
- Vorsicht: Ressourcendefinitionen, groß genug für Mindestlimits wählen
- Liveness/Readiness-Probes => Healthchecks
- Readiness: Ab wann kann Pod Requests annehmen
- Liveness: Muss Pod gekillt werden?
- Geht beides über HTTP-Status-Code
- Kubernetes: Consul nicht unbedingt notwendig, da DNS verfügbar
- "ConfigMap"
- Ingress statt Traefik o.ä.
- Wenn K8s einzige Zielplattform kann man sich ein paar Dinge sparen
- Dann aber kein Docker Compose mehr möglich
