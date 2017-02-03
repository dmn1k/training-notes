# Coole Web-Apps mit Angular 2, Typescript und Spring Boot
*Referent: Kai Toedter*

- Spring Boot: MockMvc, RestTemplate für IntegrationTests
- REST Maturity Model
- Level 3 Hypermedia
- HAL: Hypertext Application Language
- HAL: JSON oder XML, Links, Embedded Resources
- Unterstrich als HAL-Attribut: \_links, \_embedded
- URI: Uniform Resource Identifier
- Self-Link statt ID
- "Richtiger Link" => Gibt technische Möglichkeiten
- Spring Data Rest
- @RepositoryRestResource => HAL
- Mittlerweile alle Repository per default alle exposed als REST-Repository
- Deaktivierbar über Annotation
- Repository => List/Items-Resource
- Hypermedia: Nur ein Einstiegspunkt notwendig
- Bsp https://api.github.com
- Spring erzeugt automatisch REST-Resource mit Hypermedia aus Entities
- Klasse User => users-Resource per Default (überschreibbar über Annotationen)
- Erzeugt "type" => SEMANTIC, IDEMPOTENT, UNSAFE um zu sehen wie die
  Auswirkungen sind wenn Link aufgerufen wird
- Spring Security auf Repository-Ebene leicht möglich, ganzes Repository an
  Rollen klemmen unklar
- Nexus, JFrog, github.com/sw360
- Gibt Alternativen zu HAL, Spring gibt HAL aber umsonst
- ECMAScript 2015 == ECMAScript 6
- dartlang.org
- CoffeeScript, Ruby-ähnlich
- babeljs.io => Precompiler
- Traceur, vom Angular-Team urspr verwendet, Transpiler zw. Javascript-Versionen
- TypeScript, Transpiled nach JS, Typed Superset of JavaScript
- typescriptlang.org => REPL
- DefinitelyTyped => Github, Typeinformationen für JS-Libraries
- Typescript "any" wenn Typ nicht bekannt ist
- Typescript: Namespaces und Interfaces
- export interface, method(): type;
- JavaScript dev tools: npm dep management, build/test/script runner
- Jasmine for implementing tests
- Karma for running tests, untersch. Browser moeglich
- Grunt/Gulp fruehere Task-Runner, mittlerweile nicht mehr so verbreitet
- npm mandatory, input file is package.json
- TypeScript: "this" wie in Java ohne Verrenkungen, im neuen ECMAScript auch
- npm install @types/<module name>, z.B. npm install @types/jasmine
- TypeScript >= v2.0!
- MS scanned DefinitelyTyped-Repo und erzeugt npm-Module automatisch
- tsconfig.json konfiguriert TypeScript, z.B. Ziel-Javascriptversion,
  Experimental Features wie Decorators/Annotationen, typeRoots =
  node\_modules/@types
- Webpack: Bundled Module zusammen um weniger Abhängigkeiten zur Laufzeit zu
  haben, wie Maven Shade
- Webpack kann über Plugins z.B. Typescript-Module laden und in JS konvertieren
- Webpack kann auch mehrere Chunks erzeugen um nicht immer alles laden zu
  müssen, z.B. eines mit allen externen Abhängigkeiten, eines mit eigenem
  Sourcecode, eines mit Polyfills
- Polyfills: In JS geschriebene Hacks um neue Browserfeatures in alte Browser zu
  bekommen
- Webpack-Config: Entrypoint/Main, Output-Folder (wie Maven-Target), Plugins
  (z.B. Link-Änderungen), Module-Loader z.B. Typescript, CSS, HTML
- Angular2-template-loader inlined HTML-Template-Dateien
- Angular Mobile&Desktop
- Angular keine Widgets, z.B. ng-material
- Module: Jede App mindestens ein Modul, @NgModule, Root-Module als Konvention
  AppModule genannt
- Module: Declarations von View-Konzepten (Components, Directives, Pipes)
- Module: Exports/Imports, DI-Provider (wie Factory), Bootstrap in RootModule =
  root component
- import {X} from '@angular/core' => X aus angular importieren, kein namespace
  mehr notwendig da implizit da
- URL-Hash für Angular-internes Routing
- AppModule in der Regel leer, hier nur NgModule-Decorator wichtig mit globalen
  Settings z.B. HashLocationStrategy als LocationStrategy-impl (DI)
- Launch app by bootstrapping with platformBrowserDynamic (es ist auch möglich
  serverseitige Angular-Module zu schreiben)
- Jede Component kontrolliert eine View
- @Component: Selector im HTML, templateUrl oder Inline (das wird in selector
  gerendered), providers: DI
- OnInit-interface => ngOnInit, Wie PostConstruct in Java EE
- Angular-Templatesprache: {{binding}}, \*ngFor="let user of users"
- Binding an private Felder in Angular-Component das zu Template gehört
- One-Way-Databinding:
  - Component->DOM: <user-detail [user]="selectedUser">
  - DOM->Component: <li (click)="selectUser(user)">
- Two-Way-Databinding: <input [(ngModel)]="user.name">
- Prefer One-Way-Databinding for perf reasons
- DI in Angular1 über String-Benamung, in Angular 2 über zentralen Container
- Provider sind Rezept für Serviceerzeugung (analog zu Guice)
- Provider können in Modulen und Components definiert werden
- Services wie POJOs ("POTOs")
- Services sollten Presentation-Logik beinhalten => leicht testbar
- Services mit @Injectable annotieren um nested services zu realisieren
- @Injectable heißt nicht, dass Service automatisch injectbar ist
- @Injectable aktiviert Injizierung anderer Services in diesen Service
- Best practice/Angular-team recommendation: @Injectable über jeden Service
- Routing: Verschiedene Inhalte über URL-Fragment gesteuert
- <router-outlet> => Dort wird Content durch Router eingefügt
- import { Routes } from '@angular/router'
- routerConfig: Routes = { ... }
- Routing von Fragmentname zu Component
- <a [router-link]="['about']">
- Jede Komponente kann eigenes CSS haben (namespaced)
- getbootstrap.com
- CORS ServletFilter der alles erlaubt, in Spring nur in dev Profil
  hinzufuegen/laden
- Angular HTTP basiert auf rxjs
- IntelliJ: Debug-Config für JavaScript, URL: http://localhost:3000, Projectpath
  => JS-Debugging in der IDE
- Problematisch mit Chromium, default geht nur der echte Chrome rxjs => Observable
