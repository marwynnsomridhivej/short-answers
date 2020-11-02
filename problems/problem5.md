# More Detailed Extraction

In [problem 1](problem1.md), we managed to extract elements in a list by their 
name attribute. Sometimes, we need to go deeper. Take this as an example:

```python
class Name():
    def __init__(self, name: str) -> None:
        self.value = name


class Cost():
    def __init__(self, cost: float) -> None:
        self.exact = cost
        self.truncated = round(cost, 2)
        self.formatted = f"${self.truncated}"


class Item():
    def __init__(self, name: str, cost: float, sale: bool = False) -> None:
        self.name = Name(name)
        self.cost = Cost(cost)
        self.sale = sale
```

Suppose you have an arbitrarily long list where every element in the list is an
instance of `Item`. Extract the following from the long list `items`:

> 1. Elements where `element.name.value` is `"Strawberry"`
> 2. Elements where `element.cost.formatted` is `$5.99`
> 4. Elements where `element.name.value` is `"Strawberry"` and `element.cost.formatted`
> is `$4.20` and `element.sale` is `True`
*Note: `element` represents any arbitrary element in the list `items`*

In order to perform the extractions, you will write one function that is capable
of performing these extractions. It must be able to handle all of these cases on
its own. You cannot use `operator.attrgetter`, but you may and should use `getattr`