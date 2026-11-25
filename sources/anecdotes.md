# Anecdotal evidence

Observations from real-world use that lack controlled measurement. They are weaker evidence than the studies in `sources/study_*`, but are included when they are clear and repeated.

## Raw SQL: LLMs write complex SQL quickly and without errors
- **Observed by:** Henrik, several other developers
- **Context:** Mainly the Process Oak project (`~/code/poak`), 2026.
- **Observation:** Long stretches of complicated SQL are written blazingly fast and without errors.
- **Supports:** `stack.md` → Database access: Raw SQL

## Javalin: LLMs work extremely fast with the library
- **Observed by:** Henrik
- **Context:** Process Oak (`~/code/poak`), Java + Javalin, since January 2026.
- **Observation:** The LLM built its own file system routing framework on top of Javalin in 20–30 minutes at most. It has since worked for many months without a single error. Every addition to the framework is implemented lightning fast and comes out error-free.
- **Supports:** `stack.md` → Web library: a minimal library in the style of Javalin (the current recommendation is Starlette, "Python's Javalin equivalent"). File-based routing also appears in `study_2025_08_wms` (wms7).
