# Rise of the machines - automate your development
*Referent: @svenpet*

- beyond deployment, builds, scripts
- set up dev environment

## Coding bots

- Jira-workflow vs coding workflow
- automate jira state transitions
- smart commits: control issue tracker via commit messages
- prevent branch from red build
- bitbucket-plugin: auto-suggest reviewer
- auto merge bugfixes to all downstream branches

## Testing bots

- static analysis bot, "no more junit 3 tests allowed"
- compare ui-images
- test-dispatch bot, assign tests to build nodes
- flaky-test detector => quarantaine test and create issue

## Ops bots

- "pager duty"-bot connects ops to responsible dev team => end-to-end
  responsibility
- automate release notes from git commits and issues => think about customer
  value when creating issues
- log file entries -> confluence articles with machine readable part

## Report bots

- stand-up problems: too long, remind people, timezone differences,
  video-conference calls
- chat-bots: standups, build-failures, deployments, sentry found new exception
  in prod
