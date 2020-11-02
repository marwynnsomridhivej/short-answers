# Iteration and Extraction

Suppose you have the class `Item` defined below:

```python
# The : str, : int, and the -> str, -> None are called "typehints".
# Their only purpose is to denote the data type of the arguments of
# the function, as well as the data type of the return, if applicable

class Item():
    def __init__(self, name: str, index: int) -> None:
        self.name = name
        self.index = index

    def __repr__(self) -> str:
        return f"<Item name={self.name}, index={self.index}>"

    def set_index(self, new_index: int) -> None:
        self.index = new_index
```

Given an arbitrarily large list where each element of the list is an instance of
item, write a program that will extract all elements in that list given the 
following conditions:

> 1. The element's `name` attribute is equal to "Tom"
> 2. The element's `index` attribute is less than the length of the list divided
> by the greatest divisor of the length of the list (the greatest number that
> evenly divides a number but is not equal to the number, like how the greatest 
> divisor of 100 is 50)
> 3. However, if the length of the list is prime, subtract 1 to the length of
> the list and reapply condition 2

Once you have gathered the elements in the list that match those constraints, 
set each element's index in the gathered list equal to its current index in the
gathered list

[Next Problem](problem2.md)

[Back to Problems List](../README.md)