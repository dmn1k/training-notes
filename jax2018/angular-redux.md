# Angular mit Redux
@manuel_mauky - Saxonia Systems

- Problem: Häufig viele UIs mit noch mehr Services und undurchschaubarem Datenfluss dazwischen
- Was ist mein Zustand und wo liegt er?
- Warum ist der Zustand so (debugging)
- Fragestellung: Kann uns Funktionale Programmierung helfen? (UI ist traditionell eher keine FP-Domäne)
- Redux: Funktionales State-Management, kommt aus React-Welt
- UIs normalerweise hierarchisch, State wird also als Baum modelliert (Root bspw. auf welcher Seite im Wizard bin ich)
- Flux: Architekturmuster als Alternative zu bspw. MVC, entwickelt von Facebook 
- Store->View->Action->Dispatcher->Store
- Unidirektionaler Datenfluss (leichter zu verstehen)
- Actions werden an ALLE stores weitergeleitet, Stores entscheiden selbst, was sie interessiert
- Zusätzlich: ActionCreator, bspw. für Asynchronität (middleware in redux)
- Redux: nur 1 store der gesamten, unveränderlichen Zustandsbaum verwaltet (einzelne Zweige gehören zu einzelnen Fachlichkeiten)
- Reducer: (state, action) -> state
    - Eine funktion, aber in Realität komponiert aus vielen Sub-Reducern
- Store = State + Reducer
- Immutability in JS/TS:
    - Object.assign({}, state): Nimmt erstes Objekt und kopiert alle Felder vom zweiten Objekt rein (shallow copy!)
    - Object.assign({}, state, {loading: true}): Nimmt kompletten State und setzt loading auf true
    - ES7, TS 2.1: {...state, {loading: true}}: Spread-Operator
        - Prüft keine Tippfehler o.ä., abhilfe schafft tassign
    - Auf jeder Ebene nötig, da alles nur flach kopiert: Lieber Sub-Reducer benutzen (redux: combineReducers)
    - combineReducers: Daten aus anderem Modell nicht sichtbar
    - ImmutableJS optimiert darauf, nur das nötige zu kopieren
- Bibliothek: angular-redux, integriert original redux in angular
    - Alternative: ngrx, nutzt nicht original redux aber integriert etwas besser
- Store wird injected: NgRedux<AppState>
    - ngRedux.dispatch(action)
    - Selector: (state) -> T
    - @select(isLoading) public loading: Observable<boolean>
    - Selectors greifen auf bestimmten Teil des States zu, damit einzige Stelle die bei Refactoring der Struktur geändert werden muss

## Vorteile

- Redux DevTools
    - Chrome Plugin
    - Zeichnet alle Actions auf
    - Historie kann angeschaut und verändert werden
    - Inklusive Seitenänderungen (redux-router)
    - Ermöglicht klaren Weg für Bugfixing

- Gute Testbarkeit (pure functions)
- Erleichtert evtl. Umstieg auf React (Know-How, viel direkt übernehmbarer Code)


## Nachteile
- Boilerplate: Mehr Dateien (Reducer, Selectors, ActionTypes, ActionCreators)
- Ist halt was anderes / neues => gewisse einstiegshürde, funktionale Denkweise nötig