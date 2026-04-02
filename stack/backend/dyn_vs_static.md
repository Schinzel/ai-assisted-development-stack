# Dynamic vs Static Languages

Why are dynamic languages more efficient for AI coding?

Gemini validated and nuanced the theories. Summary:

## Theory 1: More code
Weak as a primary cause. Generating extra tokens takes almost no time. The cost is deciding which tokens satisfy the type system.

## Theory 2: The feedback loop
Very strong. Gemini highlights that it's a double loop: first the AI fixes type errors (before the code can even run), then it fixes test errors (which can break the types again). Dynamic languages have only one loop.

## Theory 3: Cognitive surface
Strong. Explains why loop 2 is so costly. Type errors are cryptic and low-signal — "Dict[str, Any] is incompatible with Dict[str, int]" gives the AI little to work with compared to a concrete "expected 10, got 9".

## Theory 4: Buildability
Very strong. Gemini reframes it as incremental vs holistic validation. Dynamic languages let the AI test one function at a time. Static languages require the entire type graph to hold together first.

## Theories Gemini added

### Theory 5: Training data familiarity
The AI has seen more dynamic code snippets in training data — more "fluent" in that style.

### Theory 6: Error signal quality
Behavioral errors (dynamic) have high signal. Type errors (static) have low signal and often require non-local changes.

### Theory 7: Edge case deferral
Static types force the AI to handle edge cases immediately (User | None), while dynamic languages let it take the happy path first and fix the rest later.
