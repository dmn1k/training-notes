# Parallel Code-Smells
*Referent: Luc Bläser*

## partly synchronized class

- Nebenläufigkeit klar in Architektur definieren
- Confined: Definierte synchronisierte Schnittstelle zu unsynchronisiertem
  Subsystem

## Nested Locking

- Deadlocks möglich
- Immer in gleicher Reihenfolge locken
- Architektur!

## Try-and-Fail Resource Aquisition

- Starvationeffekte
- "Kollaboratives gegeneinander ausspielen von Threads"

## Use of Explicit Threads

- OutOfMemory Probleme
- Besser: ThreadPool, Container-managed threads

## Thread Pool Task Dependencies

- Task wartet auf anderen Task
- Anderer Task kann evtl noch garnicht laufen wegen ThreadPool-Limitierung
- Task Continuations

## Fire and Forget

- Exceptions werden verschluckt und tauchen nirgends auf
- Kann ewig laufen ohne es direkt zu merken
- Thread wird evtl einfach zwischendrin beendet

## Uber-Asynchrony

- Make all the things async
- Viele Context-Switches
- Kompliziert zu verstehen

## Monitor Single Wait / Single Signal

- if(full) wait() -> while(full) wait()
- notify -> notifyAll
- Z.B. bei Single Producer Multiple Consumer

## Atomic, Volatile and Yield

- Lock-free is hard! Memory Model Kenntnisse notwendig
- Memory Barrier vor lesen notwendig
- Reordering-Probleme möglich

## Finalizers Accessing Shared State

- Finalizer sind nebenläufig
- Allg. bestehende Nebenläufigkeit in Plattform o.ä. beachten





