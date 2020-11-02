# Function Mapping

Suppose you have a class `TooManyFunctions` and a menu `Menu` defined as follows:

```python
class TooManyFunctions():
    def __init__(self, name: str) -> None:
        self.name = name

    def print_name(self) -> None:
        print(f"My name is {self.name}")

    def print_len(self) -> None:
        print(f"My name is {len(self.name)} characters long")

    def print_vowels(self) -> None:
        print(f"The vowels in my name are:\n" + 
        "\n".join(char for char in self.name if char in 'aeiou'))

    def print_consonants(self) -> None:
        print(f"The consonants in my name are:\n" + 
        "\n".join(char for char in self.name if not char in 'aeiou'))

    def print_reverse_name(self) -> None:
        print(f"My name reversed is {self.name[::-1]}")

    def print_upper(self) -> None:
        print(f"My uppercased name is {self.name.upper()}")

    def print_lower(self) -> None:
        print(f"My lowercased name is {self.name.lower()}")

    def print_title(self) -> None:
        print(f"My titlecased name is {self.name.title()}")


class Menu():
    DEFUALT = """MENU
n - calls print_name
l - calls print_len
v - calls print_vowels
c - calls print_consonants
r - calls print_reverse_name
u - calls print_upper
w - calls print_lower
t - calls print_title
q - quits the menu and terminates the program

Choose an option:\n"""

    def __init__(self, text: str = None) -> None:
        self.text = text or DEFAULT

    def get_option(self) -> str:
        return input(self.text)


func_map = {} #Define the appropriate function mapping


if __name__ == "__main__":
    pass #Implement your solution here
```

Define `func_map` such that the keys correspond to the choices on the menu and
the values correspond to the designated attribute in `TooManyFunctions`. Then, 
implement a solution under the boilerplate such that:

> 1. The input received from the menu should be processed in a case insensitive
> manner
> 2. The program quits when the user inputs `"q" or "Q"`
> 3. You are allowed to use only one `if` statement and there **must not** be 
> an `else` block after it

You are strongly encouraged to use `getattr`

[Next Problem](problem7.md)

[Previous Problem](problem5.md)

[Back to Problems List](../README.md)