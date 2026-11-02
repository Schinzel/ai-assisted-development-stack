# ai-assisted-development-stack

Which stack is the most effective for AI assisted development

This assumes a human setting the patterns, system design, architecture and reviewing the code. I.e. the purpose is not identifying a language for vibe coding.

This primary parameter is time to produce a feature. 

Excluded parameters
- Correctness - this is not an issue with a good workflow
- Measuring on the amount of tokens which several studies to can be deceiving. 
  - This as you can dense languages like Clojure which will use fewer tokens.
  - This omits the time the LLM spend thinking

## Amount of training data per language

Code (Group) in the studies is a rough approximation of how common a language is. It is based on the amount of code per language in the StarCoder training data, after filtering, from 2023 (tables 1-2 in https://arxiv.org/abs/2305.06161). It is not the training data of the models used in the studies.

The grouping is our own: Common is 20 GB or more, Medium is 4-10 GB, Uncommon is under 4 GB. No language falls between 10 and 20 GB. Swift, J and Factor are not listed in the source.

| Language   | Code (GB) | Code (Group) |
|------------|-----------|--------------|
| Java       | 86.9      | Common       |
| JavaScript | 64.7      | Common       |
| PHP        | 60.9      | Common       |
| Python     | 60.4      | Common       |
| C          | 53.9      | Common       |
| C++        | 48.9      | Common       |
| C#         | 44.7      | Common       |
| TypeScript | 26.5      | Common       |
| Go         | 23.8      | Common       |
| Rust       | 9.1       | Medium       |
| Ruby       | 6.8       | Medium       |
| Kotlin     | 5.7       | Medium       |
| Scala      | 4.7       | Medium       |
| Lua        | 2.9       | Uncommon     |
| Haskell    | 2.2       | Uncommon     |
| Perl       | 2.2       | Uncommon     |
| Fortran    | 1.8       | Uncommon     |
| Assembly   | 1.6       | Uncommon     |
| VB.NET     | 1.4       | Uncommon     |
| Julia      | 1.3       | Uncommon     |
| OCaml      | 1.0       | Uncommon     |
| Elixir     | 0.7       | Uncommon     |
| F#         | 0.6       | Uncommon     |
| Clojure    | 0.5       | Uncommon     |
| Tcl        | 0.4       | Uncommon     |
| Scheme     | 0.2       | Uncommon     |
| Zig        | 0.2       | Uncommon     |
