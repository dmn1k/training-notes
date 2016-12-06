# Everything as code
*Referent: Leander Reimer*

- Software Industrialisierung => Automatisierung, Tool-Chain, höhere
  Produktivität und Teamzufriedenheit
- Right tool for the job
- Einheitliche Software-Entwicklungsumgebung im Team (SEU)
- Gradle erzeugt SEU, Software-Pakete als Dependencies
- SEU auch versioniert, d.h. Codestand und passender SEU-Stand
- seu-as-code, open source by qaware
- Gradle: Inkrementelle Builds, reduziert Build-Zeiten drastisch
- Java immernoch sehr weit verbreitet, Kotlin evtl als gute, nicht fundamental
  andere Alternative
- Kotlin: JDK 6 kompatibel, Null Safety, sehr guter IDE-Support
- Frontend: HTML5, CSS3 DAZU Typescript oder ECMAScript2015 mit Babel
- Frontend: node, npm, webpack
- Tests: Groovy and Spock
- Lasttests: Scala and Gatling
- Gatling: Akka unter der Haube, schöner HTML-Report, weniger Ressourcen für
  Clients als JMeter
- Pipeline: Jenkinsfile => Groovy-DSL
- Lokaler Jenkins in Dockercontainer, wird über Gradle-Task gestartet
- Infrastructure-as-code: Docker, Docker Compose
- Vagrant, Ruby für lokale VMs
- Chef, Puppet: Agent auf Zielsystem; Ansible mit Python braucht nur SSH-Zugriff
- Ansible: YAML-File, Module in Python (aber wahrscheinlich nicht notwendig)
- Kubernetes: YAML-File
- Documentation: Liegt neben Quellcode, schnell und einfach zu schreiben
- Markdown, Asciidoc
- arc42.github.io Asciidoc-template
- AsciidoctorJ, Gradle-Task
- Presentation-as-code
