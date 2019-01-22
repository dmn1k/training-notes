# Der eilige Gral

- Java VM Stack-basiert
- HotSpot C1 (Methode wird mehr als einmal aufgerufen): Bytecode -\> Maschinencode 1:1
- C2 (bei weiteren Aufrufen): Optimiert alles mögliche inkl. Dead Code Analyse (implementiert in C/C++)
- Neuer C2, in Java geschrieben: Graal
- Stackorientierte Maschine: Einfache Transformation Sourcecode-\>Bytecode,
  Leicht in Baum zu transformieren
- Bäume ermöglichen Transformationen wie Inlining und Spezialisierungen für
  bestimmte Parametertypen
- Unlock Graal ab Java 9: -XX:+UnlockExperimentalVMOptions -XX:+UseJVMCICompiler
- Graal ermöglicht Anbindung beliebiger Sprachen (auch dynamisch) an JVM
- Interop zwischen den verschiedenen Sprachen inkl. Optimierungen
- Läuft auf OpenJDK, node, Oracle- und MySQL-Datenbanken sowie standalone
- Initialer Interpretierschritt fällt durch AOT-Option weg: Schneller Startup,
  dafür dynamisch geladene Klassen funktionieren nicht mehr, Garbage Collection
  u.U. langsamer
- Indy (invokedynamic) bei Lambdas: Graal optimiert
- Seit Java 11: constantdynamic statt vier Bytecodebefehle pro Array-Element
