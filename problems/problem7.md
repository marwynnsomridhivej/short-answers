# Join

We've all done something like this before:

```python
for num in range(1, 11):
    print(num)
```

Thats all well and good. It works fine, and is easily understandable. However, 
there is another way to do this:

```python
print("\n".join(str(num) for num in range(1, 11)))
```

The join method is useful for condensing statements into simple, one-liners that
are easy to understand. Here is essentially how it works:

```python
"sep".join(iterable)
```

This produces a string value where each element of `iterable` is "stitched" 
together using the `sep` value to separate them. For example:

```python
>>> print(" ".join(str(num) for num in range(1, 11)))
1 2 3 4 5 6 7 8 9 10

>>> print(", ".join(str(num) for num in range(1, 11)))
1, 2, 3, 4, 5, 6, 7, 8, 9, 10

>>> print(" | ".join(str(num) for num in range(1, 11)))
1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10
```

Notice how the separator is only inserted *between* values. This means that it
will be inserted between every value, but not after the last. This is why the
examples do not end with `10, ` or `10 | `.

Using `join`, do the following:

> 1. Print numbers 1 through 100, separated by a newline
> 2. Print letters a through z, separated by a comma and space
> 3. Print all even numbers between 1 and 1000 that are divisible by 4 or 6, but
> not both 4 and 6. Separate these values by the pipe character surrounded by 
> spaces, like `" | "`
> 4. Print your full name in reverse ***without*** using string slicing

\* *It is possible to do all of these in just 4 lines, 1 line for each statement*

[Next Problem](problem8.md)

[Previous Problem](problem6.md)

[Back to Problems List](../README.md)