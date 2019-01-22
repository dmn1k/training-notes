# SPAs and Microservices: How does this come together?
softwarearchitekt.at

- Deploment-Monolith: Client-Fragmente zusammenkompilieren und monolithisch
  ausliefern (einfach, leicht optimierbar, konsistent aber auch nicht einzeln
  deploybar, technologien mixen schwer, kopplung)
- Umsetzung: npm-Pakete (registries wie nexus, artifactory, tfs, verdaccio)
- Projektintern aufwändig (und: wie wird projektintern neuste version
  sichergestellt?, Versionskonflikte), daher evtl. Monorepo
- VS-Solution und Eclipse Workspace sind quasi Monorepos
- Vorteil JS/TS-Libs: public\_api.ts exportiert explizit API
- Import über fixen Namen, nicht über relativen Pfad (paths in tsconfig.json)
- Probleme: One Arch/Tech Stack (one size fits all), hard to change, no
  self-contained teams
- Weitere Option: Integration über Hyperlinks
- WebComponents: Framework-unabhängige Komponenten, kann bis IE11 über Polyfills
  nachgerüstet werden
- Kommunikation zwischen Micro-Frontends: Über Backend (HTTP, WebSockets, SSE),
  über Deep Links
- Integration von Legacy-Anwendungen (wie bspw. AngularJS) über WebComponents
  möglich
- Shell: Integration über IFrames, Bootstrapping multiple SPAs, WebComponent
  (bietet einheitliches Interface für Shell)
- WebComponents können genested werden (Makro/Mirkoebene)
- Polyfills nicht mehrfach laden!
- Routing: Shell muss wissen, welche SPA angezeigt wird (bspw. erstes
  URL-Segment = App-Name)
- Bundles: Will man Libs immer mitladen? Ansonsten: Angular Ivy, Stencil,
  lit-html => Kompilieren Frameworkcode nach VanillaJS
- Für Libraries wird Ivy usw. nichts bringen
- Teilen der Libs als UMD-Bundles (Allerdings: Komplex, Isolation geht verloren)
- IFrame: Routing erforder Sync mit Shell, IFrame-Größe muss angepasst werden,
  Es kann nichts überlappt werden
