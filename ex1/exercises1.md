# Exercises on Go Programming (part 1)

You may have a look to the [standard library documentation](https://pkg.go.dev/std) to find useful functions and methods for solving the following exercises. 

## Exercise 1
The *series expansion* of $e^x$ is given by:

$$1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \frac{x^4}{4!} + \dots$$

Evaluate $e^x$ for given values of **x** by using the above expansion for the first 10 terms.


## Exercise 2
We define *super digit* of an integer *x* as follows:
1. if *x* has only 1 digit, then its super digit is *x*;
2. otherwise, the super digit of *x* is equal to the super digit of the sum of its digits.

For example, the super digit of *3* is calculated as
```
super_digit(3) = 3
```
Instead, the super digit of
```
super_digit(148148148) = super_digit(1+4+8+1+4+8+1+4+8)
                       = super_digit(39)
                       = super_digit(3+9)
                       = super_digit(12)
                       = super_digit(1+2)
                       = super_digit(3)
                       = 3.
```
Write a function `super_digit` that given an integer `n` returns the super digit of `n`.

## Exercise 3

Write a function `array_replication` that, given an array `l` and a natural number `n`, returns a new slice where each element is replicated `n` times. For example, if `l = [1;2;3;4]` and `n = 3`, the result of `list_replication l n` is `[1;1;1;2;2;2;3;3;3;4;4;4]`.

## Exercise 4
Write a function `array_replication1` that, given a list `l` and a natural number `n`, returns a new list that is obtained by concatenating `l` with itself `n` times. For example, if `l = [1;2;3;4]` and `n = 3`, the result of `list_replication l n` is `[1;2;3;4;1;2;3;4;1;2;3;4]`.

## Exercise 5
Write a function `swap_adjacent` that given a string of length `l` with `l` even swap the characters at position `i` and `i+1` for all `i` even in `[0, l - 1]`. For example, swap_adjacent `"abcdpqrs"` returns `"badcqpsr"`.

## Exercise 6
Write a function `mingle_string` that given two string `p` and `q` of the same lenght and mingles them together.
For example, `mingle_string "abcde" "pqrst"` returns `"apbqcrdset"`.

## Exercise 7
Write a function `anagrams` that given a slice of strings (`[]string`) returns a slice of slices of string (`[][]string`), where each row contains words that are one the anagram of the others.
