# Architecting for continuous delivery

- pushing smth to production should be boring
- tools sind nicht der kern des ganzen, erstes cd-projekt war nur cvs und bash
- "moving fast and breaking things" is NOT true
- increase quality AND stability
- pretty much the definition of a successful system is one that will change and evolve
- ingredients needed:
    - really good config management: 1 cmd for building 1 cmd for pushing to some testing env
    - automated and tested desaster recovery
    - CI: Not running jenkins against feature branches and ignoring the build when it breaks
    - merge to trunk at least daily and fix broken builds in under 10 minutes
    - continuous testing: the job of testers is not manual regression testing
    - testing pre-production AND in production (for example chaos engineering)
- orchestrated deployments are a smell => hard dependencies
- bind components at runtime: need really good tests
- strangle monolith => dispatcher
- start by delivering new functionality
- dont rewrite except to simplify
- deliver smth fast
- design for testability and deployability
- architect to run on a paas
- us government: cloud.gov => takes care of a lot of compliance and security requirements
- failures are inevitable
- when smth failes dont blame people but ask why they didnt have the information to make the right decisions
- Kripa Krishnan: disaster recovery testing at google
- jezhumble@sendyourslides.com Subject: devops