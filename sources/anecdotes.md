# Anekdotiskt stöd

Observationer från verklig användning som saknar kontrollerad mätning. De är svagare belägg än studierna i `sources/study_*`, men tas med när de är tydliga och upprepade.

## Raw SQL: LLM:er skriver komplex SQL snabbt och felfritt
- **Observerat av:** Henrik, flera andra utvecklare
- **Sammanhang:** Främst projektet Process Oak (`~/code/poak`), 2026.
- **Observation:** Långa stycken komplicerad SQL skrivs rasande snabbt och utan fel.
- **Stödjer:** `stack.md` → Database access: Raw SQL

## Javalin: LLM:er arbetar extremt snabbt med biblioteket
- **Observerat av:** Henrik
- **Sammanhang:** Process Oak (`~/code/poak`), Java + Javalin, från januari 2026.
- **Observation:** LLM:en byggde ett eget ramverk för file system routing ovanpå Javalin på 20–30 minuter som mest. Det har sedan fungerat i många månader utan ett enda fel. Varje tillägg till ramverket går blixtsnabbt att implementera och blir felfritt.
- **Stödjer:** `stack.md` → Web library: ett minimalt bibliotek i Javalins stil (rekommendationen är i dag Starlette, "Python's Javalin equivalent"). Filbaserad routing finns även i `study_2025_08_wms` (wms7).
