# Tag 2

## Clojure

 - http://clojurescriptkoans.com
 - Production like code on innoq github (twitter clone)
 - '(): list, []: vector, #{}: set, {}: map, (defn square [n] (* n n))
 - (#(%1 2) (defn square [n] (* n n))
 - https://www.grammarly.com/jobs/engineering

## Cloud setup dev env

 - Dont need everything all the time
 - local development much faster and easier
 - replicating whole cloud locally bad idea
 - need production equal copies for testing purposes

## Teaching functional programming

 - Bookstore: find Books matching name
 - go from full procedural to functional
 - focus on sideeffects

## Code reviews

 - Leave your ego at the door
 - Be clear about what you expect of your reviews
 - Have review meetings to establish common understanding of quality
 - use moderators => dont be personal
 - Define what should be done in case of different opinions
 - At least track every issue found if it is not fixable immediately
 - Maybe dont just review deltas but include context (whole class, module, ...)
 - Finding defects is very hard and not the main reason to do them => improve readability, establish common understanding, share knowledge
 - No one writes bad code on purpose

 ## Personal Kanban

  - Send new tasks per email
  - let you remind automatically at end of day to update board -> IFTTT?!
  - Retrospectives!
  - small tasks
  - different from team kanban - purely there to help you not to coordinate

## Cost of code reuse

- Coupling
- Shared ownership - responsibility?
- Wrong abstractions
- Overengineering
- Premature optimization
- Effort
- DRY applies to concepts not to actual lines of code
- KISS
- dont reuse upfront but after you have a solid understanding why you have duplications

## Wikimedia DDD

 - Shared DB like accessing instance variables of another class
 - bounded context used by two different groups of users might be actually two bounded contexts
 - heuristic: use same word in different contexts
 - bounded context != specific domain model, should raise questions (maybe payment should be part of multiple bounded contexts)
 - library: books lend vs search two very different domains
 - domain events to sync databases
 - patterns for relations between domain models -> shared kernel (which has tight coupling as drawback)
 - another one is customer-supplier
 - dependencies between bounded contexts => you need to organize the collaboration
 
 ## vim

  - inoremap kj <ESC>
  - escape pedal
  - macro: q -> f-movement, shift-b, 
  - norm @a
  - norm! @a => ignores mappings
  - " @a ^R => paste register content, modify, delete line to restore it to register
  
  - generate ascending numbers per line:
  - ctrl-a increases numbers, ctrl-x decreases
  - q => yy p ^A
  - visual block mode can replace (complete, only beginning) blockwise ($ A I)
  - :set relativenumber
  - :set scrolloff=5 5 lines always visible
  - plugin fireplace
  - clojure repl connect to vim
  - nrepl-port
  - vim-javacomplete2
  - vim-surround: adds verbs like "change surrounding parenthesis"
  - guns/vim-sexp: slurp
  - neovim: async stuff
  - qfdo
  - set columns beyond certain point to red color
  - youcompleteme
  - gf => open file under cursor
  - vimux
  - vimperator
  - vcsh

## haskell

 - stack new <project-name>
 - src vs app folder (for executable)
 - yaml vs cabal  build tools
 - spacemacs including haskell repl
 - warp = webserver
 - servant = web-lib
 - enable whole bunch of lang extensions like OverloadedStrings...