# Decorators

As we saw in [problem 3](problem3.md), we were able to recycle code by creating
a function that accepts another function as its argument. This concept transitions
us into something called *"decorators"*. Decorators are essentially what you did
in problem 3, but with a little modification. In problem 3, in order to call your
function and have it print its execution time, you needed to do something like this:

```python
import time


def print_range():
    print("\n".join(str(num) for num in range(10000)))


def duration(func: callable): ...
    """This is the function you coded in problem 3, which displays
    the time it took for func to execute
    """


if __name__ == "__main__":
    duration(print_range)
```

This is OK, but it can be a bit confusing to have to call `duration` every time
you want to find out how long a function took to run. Ideally, you'd want to
be able to call the original function, `print_range`, and have it display its
execution time WITHOUT having to put the code to calculate that inside the function
definition. This is where decorators come into play.

With decorators, you are able to call the original function while still adding
functionality to it. Suppose you want to print out `"Before execution"` before 
execution and `"Done"` after execution, without defining these print statements
within the original function's body while still being able to call the original
function. New code will look as follows:

```python
import functools
import time


def duration(func: callable):
    @functools.wraps(func) # Optional, but highly recommended
    def decorator(*args, **kwargs):
        print("Before execution")
        ret = func(*args, **kwargs)
        print("Done")
        return ret
    return decorator


@duration # This is how you decorate a function using the decorator syntax
def print_range():
    print("\n".join(str(num) for num in range(10000)))


if __name__ == "__main__":
    print_range()
```

Output:
```
Before execution
1
...
9999
Done
```

Complete the definition for `duration` and `decorator` that would allow you to
track the execution time for a function decorated with `@duration`. Optionally,
you can also include a definition for `async def` functions inside `duration` 
so that the decorator works for both regular and asynchronous functions

[Next Problem](problem5.md)

[Previous Problem](problem3.md)

[Back to Problems List](../README.md)