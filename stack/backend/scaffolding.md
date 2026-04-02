# Scaffolding Readability

The human's primary role is reviewing scaffolding — classes, functions, relationships, naming — before the AI fills in the code. 
This makes a specific quality critical: how well the language expresses structure and intention at a high level, without implementation details.

This shifts the balance between languages.

## Python
Reads extremely well as scaffolding:

```python
class OrderService:
    def calculate_total(self, order: Order) -> Money:
        """Apply discounts, tax, and shipping"""
        ...
```

Reads almost like a spec. Type annotations help here — not for the AI writing code, but for the human reviewing structure. You immediately see that the function takes an Order and returns Money.

## Ruby
Readable in implementation but weaker as structural documentation — it lacks type annotations as design communication.

## Elixir
`@spec` works, but is less familiar to most people.

## Conclusion
If the human's role is system designer reviewing scaffolding, Python may be the strongest choice — not for the AI's sake, but for the human's.
