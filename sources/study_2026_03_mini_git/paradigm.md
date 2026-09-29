# Paradigm Analysis of Benchmark Results

## By language category

**Multi-paradigm (primarily imperative/OO):** Ruby (73s), Python (75s), JavaScript (81s) — all top 3

**Statically imperative:** Go (102s), Java (115s), C (156s) — medium to slow

**Functional:** OCaml (128s), Scheme (131s), Haskell (174s) — consistently slow

**Multi-paradigm (but with functional traits):** Rust (114s), Perl (130s), Lua (144s)

Functional languages performed worst. Unambiguously.

## Top 3 paradigm usage

For the top 3, which are multi-paradigm, we examined the generated code to determine which paradigm Claude actually used:

|            | Ruby                    | Python                  | JavaScript              |
|------------|-------------------------|-------------------------|-------------------------|
| Paradigm   | Imperative              | Imperative              | Imperative              |
| Structure  | Free-standing functions | Free-standing functions | Free-standing functions |
| Router     | case/when               | if/elif                 | switch/case             |
| OO         | No                      | No                      | No                      |
| Functional | Minimal                 | Minimal                 | No                      |

