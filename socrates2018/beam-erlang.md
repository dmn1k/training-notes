# BEAM

- Erlang VM
- Multihreaded aber mit eigenen Schedulern (ähnlich zu OS) => very lightweight
  threads
- async io => process gets descheduled when doing IO => IO looks sync to
  programmer
- Process-isolation: every process has own heap => no GC pauses
  - there exists a shared heap for example for strings
- everything in BEAM is immutable
- has pattern matching on bit-level
- Message passing: p1 ! {};
- messages are async
- std library adds useful abstractions over pure message passing like wait until
  confirmation
- processes can link to each other: if p1 dies p2 dies too
- OTP: set of patterns/behaviors for solving problems in distributed systems
- Pattern: Supervisor => restarts killed "child"-processes
- Observer: inspect processes and messages visually
- Applications: Separate Set of processes
- high availability, low latency problems are best suited for erlang
- elixir: took a lot of ideas and packaged them nicely (modern syntax and stuff)
- erlang and elixir are compatible
- a lot of libraries are missing in comparison to the JVM or npm, ruby
- gen\_server: accepts messages to update state ( handle(old, msg) => {"reply", new, replyMsg})
