# Enforce frontend architecture

> [ArchUnit](https://www.archunit.org/) for JavaScript doesn't exist. What can we do about that?

## Use cases

Restrict dependencies between certain parts of the application. _Don't use that from there._

Restrict where certain libraries can be used from. _Don't use jQuery in new areas._

Restrict where certain browser APIs can be used from. _Don't `fetch()` directly from UI components._

Restrict where certain types of files can exist. _Don't put that there._

Restrict which bundles certain parts of the application end up in. _Don't ruin code splitting via accidental transitive imports._

Ignore existing violations when applying to an existing codebase. _Start enforcing against making it worse, without needing to first finish sorting out the past._

Ignore a violation from the "offender" side. _Normal type of error ignore._

Ignore a violation from the "target" side. _For "special" things which have become entangled with absolutely everything, it's less repetitive to ignore from this side._

Provide justification for ignoring a violation. _Forces you to think. Explains whether something is precedent for an acceptable ignore, or only exists due to being legacy._

Provide an explanation as to why a restriction exists. _So you remember, so someone doesn't remove it or add an ignore without understanding it (see: [Chesterton's fence](https://en.wikipedia.org/wiki/Wikipedia:Chesterton%27s_fence)), to suggest alternatives._

Define what is allowed, what is not allowed, or both. _Anything is ok except this, vs. only this is ok._

Prohibit cyclic dependencies.

Use with TypeScript or Flow, which may be necessary for some features.

Use with a bundler, which may be necessary for some features.

## Existing capabilities

- https://eslint.org/docs/rules/no-restricted-imports
- https://github.com/benmosher/eslint-plugin-import/blob/master/docs/rules/no-restricted-paths.md
- https://github.com/benmosher/eslint-plugin-import/blob/master/docs/rules/no-internal-modules.md
- https://github.com/benmosher/eslint-plugin-import/blob/master/docs/rules/no-cycle.md
