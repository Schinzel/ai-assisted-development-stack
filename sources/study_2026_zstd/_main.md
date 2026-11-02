https://danluu.com/pl-tokens/

Dan Luu, "How does programming language affect token efficiency and correctness?". The post has no date. 
It is from 2026 and was written after the mini_git benchmark from March 2026.

## The task

Agents get the zstd RFC plus errata and must implement a complete zstd decoder, a program that unpacks zstd-compressed data. 
They run in a container without internet access and do not see the tests. Agents were told to ignore performance.
Each language was run with GPT-5.6 Sol through Codex.

## Medium vs ultra

Medium and ultra are effort levels in Codex. The post does not define exactly what they change. 
What it shows is that ultra keeps working for longer, about 2.5 times longer here, and reaches higher scores.
Medium stops earlier. The Clojure results illustrate the gap: 36 of 40 medium runs and 5 of 40 ultra runs failed tests because of the same byte conversion bug.

## Results

Mean agent time. All values are read by eye from the post's charts and are approximate. The charts have no error bars.

Code (Group) is explained in the root README. Swift, J and Factor have no value there.

### Zstd, medium

| Language    | Time (min) | Type    | Paradigm        | Code (Group) |
|-------------|------------|---------|-----------------|--------------|
| Python      | 13         | dynamic | Multi-paradigm  | Common       |
| Ruby        | 13.5       | dynamic | Multi-paradigm  | Medium       |
| Rust        | 14.5       | static  | Multi-paradigm  | Medium       |
| C#          | 15         | static  | Object-oriented | Common       |
| Go          | 15         | static  | Imperative      | Common       |
| Swift       | 15         | static  | Multi-paradigm  | n/a          |
| JavaScript  | 15.5       | dynamic | Multi-paradigm  | Common       |
| C++         | 16         | static  | Multi-paradigm  | Common       |
| F#          | 16         | static  | Functional      | Uncommon     |
| Java        | 16         | static  | Object-oriented | Common       |
| Julia       | 16         | dynamic | Multi-paradigm  | Uncommon     |
| Perl        | 16         | dynamic | Multi-paradigm  | Uncommon     |
| PHP         | 16         | dynamic | Multi-paradigm  | Common       |
| TypeScript  | 16         | static  | Multi-paradigm  | Common       |
| C           | 16.5       | static  | Imperative      | Common       |
| Haskell     | 17         | static  | Functional      | Uncommon     |
| Tcl         | 17         | dynamic | Multi-paradigm  | Uncommon     |
| Elixir      | 17.5       | dynamic | Functional      | Uncommon     |
| Clojure     | 18         | dynamic | Functional      | Uncommon     |
| Zig         | 18.5       | static  | Imperative      | Uncommon     |
| Fortran     | 20         | static  | Imperative      | Uncommon     |
| x86-64 asm  | 23         | asm     | Imperative      | Uncommon     |
| aarch64 asm | 24         | asm     | Imperative      | Uncommon     |
| J           | 28         | dynamic | Array           | n/a          |
| Factor      | 29         | dynamic | Concatenative   | n/a          |

### Zstd, ultra

| Language    | Time (min) | Type    | Paradigm        | Code (Group) |
|-------------|------------|---------|-----------------|--------------|
| Swift       | 35         | static  | Multi-paradigm  | n/a          |
| Go          | 36         | static  | Imperative      | Common       |
| Python      | 38         | dynamic | Multi-paradigm  | Common       |
| Rust        | 39         | static  | Multi-paradigm  | Medium       |
| Ruby        | 40         | dynamic | Multi-paradigm  | Medium       |
| Perl        | 40         | dynamic | Multi-paradigm  | Uncommon     |
| Haskell     | 41         | static  | Functional      | Uncommon     |
| Java        | 41         | static  | Object-oriented | Common       |
| TypeScript  | 41         | static  | Multi-paradigm  | Common       |
| C++         | 41         | static  | Multi-paradigm  | Common       |
| F#          | 41         | static  | Functional      | Uncommon     |
| Clojure     | 41         | dynamic | Functional      | Uncommon     |
| C#          | 41.5       | static  | Object-oriented | Common       |
| Elixir      | 42         | dynamic | Functional      | Uncommon     |
| JavaScript  | 42         | dynamic | Multi-paradigm  | Common       |
| PHP         | 42         | dynamic | Multi-paradigm  | Common       |
| Julia       | 43         | dynamic | Multi-paradigm  | Uncommon     |
| C           | 43.5       | static  | Imperative      | Common       |
| Zig         | 44         | static  | Imperative      | Uncommon     |
| Tcl         | 45         | dynamic | Multi-paradigm  | Uncommon     |
| Fortran     | 48         | static  | Imperative      | Uncommon     |
| aarch64 asm | 49         | asm     | Imperative      | Uncommon     |
| Factor      | 53         | dynamic | Concatenative   | n/a          |
| J           | 58         | dynamic | Array           | n/a          |
| x86-64 asm  | 60         | asm     | Imperative      | Uncommon     |

## Conclusions

- Functional languages are never in the top.
- Static vs dynamic typing does not decide the time. Dynamic Python and Ruby are fastest on medium, static Swift and Go are fastest on ultra.
- Dense languages are not faster. J, Factor and Clojure are far down on medium, and J and Factor also on ultra.
- Python is the most stable of the fast languages: 1st on medium and 3rd on ultra. Ruby falls from 2nd to about 5th. Rust is also even, about 3rd and 4th.
- No Uncommon language reaches the top 4. All functional languages here are also Uncommon, so the two effects cannot be separated.
