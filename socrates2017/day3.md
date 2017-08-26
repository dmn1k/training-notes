# Day 3

## Microservices demo

 - Sync vs async
 - Challenges: Service Discovery, Routing, Load Balancing, Resilience
 - Netflix-Stack: Eureka (performant with client caches), Zuul (key feature: dynamic filters), Ribbon (client based load balancing, java library, no bottleneck that comes with centralized load balancer), hystrix (java library, calls in different thread with timeout, circuit breaker)
 - Ribbon depends on Eureka
 - Java and Spring Cloud: Everything is in code (like registering the server in eureka) => java centric
 - Hashicorp Consul Stack: Consul (has DNS interface, SRV-Records: IP-Adress plus port), Apache httpd for routing (Consul template for httpd, containing all information of all microservices known, force httpd to re-read config) => could also work with nginx for example, Spring cloud provides integration between ribbon and consul, Resilience still with hystrix
 - Consul can provide configuration information too
 - Config change => new docker container might be good enough, dont need dynamic config updates at runtime
 - HLS, Dash: Video streaming via http
 - Kubernetes: DNS (built-in, automatically configured for all docker containers, automatic registration), Integrated Load Balancer or NodePort (One machine kubernetes runs on), Load Balancing via IP-magic (like virtual ip address) not via DNS (which has TTL so you cant be sure when addin new node), Hystrix or EnvoyProxy (http proxy with resilience stuff)
 - Kubernetes is pretty tech. neutral
 - Cloud Foundry: DNS, Router included, Hystrix
 - Cloud Foundry: You directly provide java app, kubernetes needs docker containers (coKncept of build packs: describes how it should build a container out of an app)
 - Async via Kafka: No need for service discovery any more (just topics), No need for routing and load balancing (kafka deals with it), Resilience: Kafka stores messages so no need
 - Kafka can run in cluster, sender needs to retry in worst case
 - Kafka: Topics where each has partitions, subscribe to one or many partitions => load balancing
 - Lock compaction: Two events/records with same id, remove old ones (only interested in last one)
 - Kafka vs JMS (RabbitMQ): Kafka stores all information ever sent persistently, very light-weight (just a few files) 
 - Atom: Feed-format (XML), Provider provides just Atom-feed, doesnt need to be Atom but Hypermedia (give me a list of orders and links to where to find them)
 - Atom vs Kafka: Kafka needs to be configured and run (non trivial), Atom is just HTTP
 - Exactly once is non trivial with Atom (maybe store information if message has been processed in database)
 - UI: ESI (Edge side includes) combining html fragments (Varnish)
 - Or use jQuery to load html fragments

 ## Cassandra

 - distributed database
 - datamodel: concept of table and columns
 - multi master system: all nodes can accept write requests, but not all can persist it themselves
 - nodes: token ring, hash function over primary key to determine node to write data to
 - resilience: need to specify a replication factor
 - replication runs async => safety is only there after a certain amount of time
 - Consistency level for writes: how many acknowledges are needed for write operation to finish
 - quorum consistency: more than half of nodes need acknowledge  
 - RF by table not by row
 - CL per individual write and/or read
 - trade consistency with availability
 - multi master setup for scaling writes primarily
 - reads with CL 1 => might get stale data if getting wrong node
 - apple: 100k node cluster
 - cluster replication possible, even easy to do => dedicated consistency levels for this scenario
 - "any quorum": other datacenter has to fulfill quorum too => pretty costly
 - access is only happening via "partitioning key" (can be same as primary key, partitioning key can include other column)
 - Clustering column: used to sort data on one node
 - Partition key => know server
 - Primary key is combination of partitioning key and clustering column
 - Partitioning problematic if it causes most of the data to go to the same node
 - Querying data over multiple nodes: query them individually and aggregate inside app (there is an IN-operator), could involve a lot of nodes 
 - One solution: second table with partitioning key containing the desired range (for example days)
 - Challenge: you need to know how you will interact with data to come up with a good datamodel and this is essential here
 - split clusters by products: lower utilization but maybe higher guarantuees
 - no row level consistency
 - cell level consistency: timestamp decides what updates will take place if they are conflicting
 - look up: vector clocks
 - same timestamp: lexically greater value wins
 - timestamps are on the cell not row
 - so it is a good idea to divide operations: update age and update name
 - so it is bad to update entity at once (which for example spring data does)
 - append only solves problem (basically no limit on number of columns)
 - thrift apis, today only CQL supported
 - column type set<string> => internally mapped to multiple rows
 - number of columns is not a function of the table! each row can have different columns
 - CRDT: consistent replicated datatype (same result independent of order)
 - set where you can only add is a CRDT
 - Riak support them more natively
 - otherwise you need semantic merge mechanism (for example addproduct always wins over removeproduct at amazon if they have same timestamp)
 - lightweight transactions: IF EXISTS in cql, has great effect: talks to complete cluster with "pexus"-protocol for distributed consensus, really expensive, kills availability

## Ethereum

 - bitcoin is basically txn system
 - bitcoinscript for not turing-complete smart contracts
 - etherum for turing-complete smart contracts
 - truffle: npm package, web framework
 - blockchain is about mutual trust because its distributed
 - truffle allows to call solidity contract from javascript
 - write solidity-contract via online IDE including a debugger
 - solidity:
    - constant functions (need to pay to write, dont need to read => constant term)
    - calculations have to be run by every participant in the network to validate it => costs money
    - transaction fee might not be enough because of acual CPU cost
    - fee is calculated upfront by adding up opcode-fees
    - extensive use of hashmaps to get values
 - test networks: testrpc and etherum.org
 - can put message on side channel like database if it is private (insurance claim)
 - everything is public in blockchain

## Emacs

 - Org-mode: generate presentations, Latex, ODT, ...
 - symbolics keyboard
 - Control, Meta, Shift
 - C-x C-c -> closes emacs, can just hold control
 - C-h k -> key sequence => explains key
 - C-x? => get all possible commands
 - C-h C-t => emacstutor
 - Neo-layout: dvorak for german
 - mark-all-like-this-dwim
 

## Idris

Just awesome and mind blowing!

## Team internal conflicts

- Make them transparent
- Talk to the person while emphasizing how you were hurt
- Retrospective with moderator and without name-calling
- Use agile coaches as mediators
- Point out future problems arising with this choices
- Pointing out problems is my job is a consultant

## Ideas

- Session on encoding semantics in type system
- Session on how to get from kata to real code
- Improve functional programming session
- Session on spock (spread the goodness)
- Codingame TDD
- Try to use personal kanban