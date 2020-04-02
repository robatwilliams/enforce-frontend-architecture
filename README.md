# Enforce frontend architecture

> [ArchUnit](https://www.archunit.org/) for JavaScript doesn't exist. What can we do about that?

## Use cases

### Dependencies

Restrict dependencies between certain parts of the application. _Don't use that from there._

Restrict where certain libraries can be used from. _Don't use jQuery in new areas._

Restrict where certain browser APIs can be used from. _Don't `fetch()` directly from UI components._

Restrict where certain data types can travel. _Don't pass Backbone model to React component._

Prohibit cyclic dependencies.

### Structure

Require a certain kind of structure in certain places. _Those should all look like this._

Restrict where certain types of files can exist. _Don't put that there._

### Build-time

Restrict which bundles certain parts of the application end up in. _Don't ruin code splitting via accidental transitive imports._

### Defining the rules

Define what is allowed, what is not allowed, or both. _Anything is ok except this, vs. only this is ok._

Provide an explanation as to why a restriction exists. _So you remember, so someone doesn't remove it or add an ignore without understanding it (see: [Chesterton's fence](https://en.wikipedia.org/wiki/Wikipedia:Chesterton%27s_fence)), to suggest alternatives when a violation occurs._

Make exceptions to the rules. _For special cases, or things which have become entangled with absolutely everything, it's less repetitive to have an exception than to have lots of ignores._

### Violations

Ignore a violation. _There may be good reason, or it might be pre-existing._

Require justification for ignoring a violation. _Documentation, encourages thinking. Distinguishes acceptable exceptions from pre-existing problems to avoid the latter being taken as precedent._

Conveniently ignore pre-existing violations when applying to an existing codebase. _Start enforcing the future without first needing to finish soring out the past. There may be hundreds, or thousands._

### Usage

Display violations in the editor/IDE. _Like ESLint._

Use with TypeScript or Flow, which may be necessary for some features.

Use with a bundler, which may be necessary for some features.

## Existing capabilities

- https://eslint.org/docs/rules/no-restricted-imports
- https://github.com/benmosher/eslint-plugin-import/blob/master/docs/rules/no-restricted-paths.md
- https://github.com/benmosher/eslint-plugin-import/blob/master/docs/rules/no-internal-modules.md
- https://github.com/benmosher/eslint-plugin-import/blob/master/docs/rules/no-cycle.md
