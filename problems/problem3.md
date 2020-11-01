# Computation Duration

In order to calculate a function's execution time, something like this can be made:

```python
import time


# Normal function
def print_range():
    print("\n".join(str(num) for num in range(10000000)))

# Modified to print out the execution time
def print_range():
    start = time.time()
    print("\n".join(str(num) for num in range(10000000)))
    end = time.time()
    print(f"Execution time: {end - start} seconds")
```

For just one function, adding in this code isn't a big deal at all. However, the 
amount of space taken up by something like this can add up if you want to see 
how long many functions take.

A solution to this is to implement a function that accepts a function that accepts
another function as its argument. That way, we can recycle the code to calculate 
how long a function runs.

Write a function that functions as described in the above paragraph. It should
take another function as its only argument (in this case, the function will be
`print_range` as defined normally), execute the function, and print to console
the time it took to execute the function.