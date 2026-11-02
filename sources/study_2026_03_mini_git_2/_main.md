https://github.com/kmizu/another-ai-coding-lang-bench

- Sibbling study to sources/study_2026_03_mini_git
- Same mini-git task as the original study, but each language runs with its standard toolchain (e.g. Java + Maven, Rust + cargo)from a prepared project scaffold instead of starting from an empty directory.
- Go and Ruby essentially swap places, while JavaScript and Python stay near the top. 
- The language set also differs in part: it adds more JVM and .NET languages, and TypeScript and C have no results.
- Rust (rust/cargo, a primary workflow) was run only once, versus 3 trials for the others. v1 passed 11/11 tests in 152s, but v2 produced an incomplete binary (4 LOC, 0 tests run), so the author excluded it from the summary table as a partial failure. One failed trial says little about Rust; in the original study Rust passed 38/40 runs across 20 trials.

## Results

Canonical track, average agent time over 3 trials (Python/uv: 1 trial). Rust/Cargo is excluded, see above.

| Language / toolchain | Time (s) | Code (Group) |
|----------------------|----------|--------------|
| Go / go              | 158      | Common       |
| JavaScript / Node    | 170      | Common       |
| Python / uv          | 174      | Common       |
| Python / pip         | 176      | Common       |
| Ruby / Bundler       | 218      | Medium       |
| Elixir / Mix         | 227      | Uncommon     |
| Kotlin / Gradle      | 234      | Medium       |
| F# / dotnet          | 258      | Uncommon     |
| Java / Maven         | 273      | Common       |
| C# / dotnet          | 277      | Common       |
| VB.NET / dotnet      | 295      | Uncommon     |
| Scala 3 / sbt        | 321      | Medium       |
| Java / Gradle        | 342      | Common       |
| Scala 2.13 / sbt     | 379      | Medium       |
| PHP / Composer       | 383      | Common       |
| Clojure / Lein       | 393      | Uncommon     |

