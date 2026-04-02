# Parameters for AI-Assisted Development

## General parameters

1. **Explicitness** — Everything visible in the code, no magic
2. **Thinness** — The framework does little but clearly, easy to build on top of
3. **Few transformation steps** — No long pipeline
4. **Small cognitive surface** — Few core concepts that combine powerfully
   - Counter-example: C++ STL — rich primitives (vector, map, string with powerful methods), but enormous cognitive surface. A thousand ways to do everything.
5. **Orthogonal layers** — Each part does one thing
6. **Buildable, not navigable** — AI builds better than it navigates
7. **Readability** — How naturally the code expresses intent
8. **Declarative** — SQL, HTML, HTMX: describe what, not how. Declarative is about what level of abstraction the code operates at.

## Backend language parameters

1. **Dynamic over static** — Dynamic languages perform consistently better (with caveats at large scale)
2. **Small foundation with rich primitives** — The Smalltalk principle: few verbs, but the right verbs
    - Counter-example: Lua — small cognitive surface and small foundation, but the primitives aren't rich. Tables can do everything but give you nothing for free.
3. **Design readability without enforcement. Scaffolding-friendliness.**
4. **Imperative paradigm** — When given multi-paradigm languages, AI consistently chooses imperative style with free-standing functions. No OO, minimal functional. The paradigm the AI naturally reaches for appears to be a factor in performance.

## Dismissed parameter

**Amount of training data** — secondary effect, not a primary driver.

The JavaScript outlier is interesting — it suggests there is a dataset effect, but that it's secondary. Perhaps we shouldn't dismiss it entirely, but rather downgrade it to a weaker parameter.
