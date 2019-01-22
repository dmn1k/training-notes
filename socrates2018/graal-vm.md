# Graal-VM

- Hotspot needs to evolve (functional languages, new patterns of usage)
- Hotspot-Codebase is very old and hard to change
- JVM 9+: jvmci (jvm compiler interface) -> one can add own JIT (in theory)
- Graal implements jvmci
- all JVM-languages out-of-the-box can run on GraalVM
- Graal is a JIT, the ahead-of-time-compilers (javac, scalac, ...) stay
  untouched (they compile to .class-files)
- Twitter: Reports about using GraalVM for scala-services
- Graal brings substantial improvements for JIT/language-authors
- Truffle: Transforms your language to bytecode
- TruffleRuby: A lot faster than JRuby, now merged to JRuby
- Sulong: Truffle-based implementation of LLVM-bytecode
- Graal is excellent at aggressively inlining between source-languages
- jar -> native-image
- SubstrateVM: Takes class-files and compiles to native, statically-linked
  binary (runnable without jvm and libraries)
  - slower run performance, but a lot faster startup-time (milliseconds vs
    seconds) and lower memory-footprint
  - targets linux and macos, amd64
  - perfect for CLI-tools
- legal stuff:
  - GraalVM Community Edition (CE) => free, GPL with classpath exception (like
    OpenJDK)
  - Enterprise Edition => freely downloadable, extra optimizations, full license costs
- Limitations:
  - SubstrateVM: Reflections not all working, Oracle working on it
  - SubstrateVM: You cannot emit JVM-bytecode at runtime (like languages with eval)
  - Runtime bootstrapping like Spring Boot might be problematic
- supports chrome devtool debugging protocol
