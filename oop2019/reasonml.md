# ReasonML

- Benötigt Bucklescript-Compiler
- npm i -g bs-platform
- bsb -init . -theme basic-reason
- bsb-native: native / micro kernel compilation target
- ReasonML = OCaml + JS-Syntax
- Viele original OCaml-Libs arbeiten mit Exceptions, wird langsam gefixed (bspw.
  mit Hilfe von Option)
- Zugriff auf JS-Funktionen: JS.String.split(...)
- Piping bzw. reverse function composition über |>
- Hindley-Milner Typsystem wie bspw. in Haskell => Typalias über bspw. type
  firstName = string
- type firstName = FirstName(String); => Typconstructor, also Tagged Type
- Compiler als "Helfer" der Hints gibt
- Sum-Types: type distance = Meter(float) | KiloMeter(float);
- Keine Typeclasses wie bspw. in Haskell, daher auch keine allgemeingültigen
  Implementierungen für Monoid usw
- Structural Typing: Es muss die Struktur des Objekts übereinstimmen (wie in
  Typescript aber ohne zwingend Interface zu definieren)
- OCaml: Es gibt Objekte:
  {
    pub name = "Bob";
    pub printString = () => "Hello " ++ name;
  }
- Bsp: printable => Js.log(printable#printString())
- Alternativ Record-Typ, bei dem alle Felder übereinstimmen müssen
- Es gibt kein null, stattdessen none:
- Polymorphic Variant/Sum Type: type option('a) = None | Some('a);
- Option.map(optionalValue, fn)
- Im Gegensatz zu z.B. Typescript immer 100% Typcoverage
- IDE-Support: Language Server implementiert, damit Support für alle gängigen
  IDEs
- Einfache Integration mit JS: Mutability möglich
- High Performance Compilation-Outputs
- Interop: "bs.raw" für Plain-JS-Embedding, kann auch untypisiert erfolgen
  (nicht empfohlen)
- Lib bs-glob zur Anbindung von node-libs, es gibt Tool für
  Typescript-Annotations -\> Reason-Annotations
- "Pure by default" aber Mutability möglich (let counter = ref(5); counter =
  counter^ + 1)
- Es gibt auch Loops statt Higher Order Functions
- Tooling: refmt analog zu elm-format
- Language Features wie Keyword Params (Referenzierung der Fn-Parameter über
  Namen statt Position)
- Reason-React
