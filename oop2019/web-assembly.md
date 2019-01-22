# Web Assembly

- MVP mittlerweile abgeschlossen
- Browser bringen Basis-Support mit
- GC, Multithreading, Tooling usw. noch nicht implementiert
- DOM-Zugriffe gehen aktuell nicht, außer per Javascript-Bridge
- Multithreading funktioniert schon, wird über Service Worker implementiert
- Anwendungsfälle: Grafik, berechnungsintensive Vorgänge wie Encryption,
  Cross-Compilation
- Java, .NET usw: Just-in-time und Ahead-of-time möglich
- AoT erfordert Garbage Collection in WASM
- wasdk.github.io/WasmFiddle
- 4 Datentypen: Int32/64, Float32/64 => Kodierung von Strings usw. muss manuell
  erfolgen
- import/export von Funktionen/Speicherbereichen
- C# -\> WASM:
  - AOT in ein großes Modul inkl. aller genutzten Bibliotheksfunktionen
    (mscorlib, System usw.) => erfordert GC, aktuell noch nicht möglich
  - JIT: Auslieferung der Runtime (z.B. Mono), compiliert nach WASM
    Blazor: C# -> WASM (SPA-Framework)
- Sourcemaps noch nicht implementiert =\> Debugging nur auf WASM-Text-Ebene
  möglich
- Unity / C -\> WASM -\> WebGL
