# Service discovery for machines and humans
*Referent: Oliver Wehrens*

- E-Post/DHL Lessons learned
- Monolith->Microservices
- New challenge: service discovery
- Technical: Find services, all instances, handle fail-over
- HA-Proxy, static list of HA-Proxy addresses configured in services
- Problem: add new service-dependency, add to service-configuration
- Problem: same machine, different service -> update
- Problem: Excessive health-checking between services
- Goal: Catalog of all services
- Service announces itself to directory, services ask directory for other
  service
- Options: etcd, Consul, Zookeeper, Eureka
- Chose Consul
- Cluster of at least three for consensus finding algorithm
- High availability requirement
- Can act as DNS
- Connect different data centers
- Security with read/write ACLs
- Gossip protocol to distribute information
- Transparent migration possible if health-check-mechanism is in place
- Low dev-team impact
- Netflix Ribbon - Failsafe-mechanism
- Lightweight wrapper around ribbon to integrate with consul
- 120 days to get infrastructure right - zones,templates,networking,ACLs
- recommendation: >30 services -> explore something like this
- Problem: capability-based service discovery, "is there a service to do X?"
- Manage licenses, library security incidents, documentation across services
- Standards or metadata in one place
- Wiki: Often write only, rarely updated, nothing can be found
- Metadata: Automate as much as possible
- Mandatory information in VCS root
- yaml -> generated wiki-article
- problem: HTML doesnt allow you to do other things with data
- System-Z by Spotify
- Services Directory by Soundcloud
- Problem: Very specific to their infrastructure, not open-source
- [http://pivio.io]
- pivio: metadata -> server (elasticsearch) -> query / web-ui
- pivio.yaml in vcs root, extendable to own needs
- DNS-Name, Description, Runtime Information, ...
- Newsfeed: Changes in System
- ElasticSearch queries directly usable
- Problem: Data Quality, especially if owner doesnt benefit
- Put owner-relevant information there
- Dirty data is to be expected
- Use cases: machine sizing, service names for consul, documentation, visualize
  dependencies, impact analysis of API-changes
- software version dependency check
- death star view easily generable
- Metadata helps to understand system
- metadata-as-code to not put any barriers in front of devs, editable in IDE
- future: analyse runtime-information to get reality not just how it is supposed
  to be
