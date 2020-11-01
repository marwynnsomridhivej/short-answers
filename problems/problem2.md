# Prime Factorisation

The prime factorisation of a number is breaking down a number into a set of prime
numbers where multiplying them yields the original number. For example, the prime
factorisation of 12 is 2 * 2 * 3. 3 * 4 does not work since 4 is not a prime number.

Write a function `prime_factorisation` that takes one integer argument and returns
a tuple of tuples containing the prime factorisation in the following form:

> For each unique prime factor, create a tuple with the value `(factor, power)`,
> where `factor` is the unique prime factor and `power` is the power of that factor. For example
> ```python
> print(prime_factorisation(12))
> print(prime_factorisation(864))
> print(prime_factorisation(23))
> print(prime_factorisation(1000000))
> >>> ((2, 2), (3, 1))
> >>> ((2, 5), (3, 3))
> >>> ((23, 1))
> >>> ((2, 6), (5, 6))

\* *Note: Using the [Sieve of Eratosthenes](https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes)
can be very helpful in reducing computation times. Using a modified version 
combined with numpy allows for computing the prime factors of 1,000,000 in less
than a second*