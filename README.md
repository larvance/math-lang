# Math Lang

## Variables

```python
a = 10
;or
a := 10
```

Sets the value of `a` to 10.

Note: Variable names cannot include these
characters: `+`, `-`, `*`, `/`, `^`, `(`, `)`, `{`, `}`, `=`, `>`, `<`, `:`, `;`

***

```python
x = 10
y = 20
a := x + y
```

This sets the value of `a` to the sum of `x` and `y`.

***

```python
a = x + y
```

This will treat `a` as a function of `x` and `y`. Check the last example to see how you can use the immediate value
of `x` and `y` in the equation.

***

```python
ab := 10
```

You can also define variables with more than one character.

***

```python
f(x) = x + 10
y := f(10)
```

This basically defines a function and uses it.

***

```python
f(x) = {
  z := x + 10
  z
}
```

This makes a multi-line function which creates a scope-based variable called `z` and assigns it to the value
of `x + 10` and returns `z`.

***

```python
a := []
```

This defines a list. Lists are immediate values, so you cannot define a rule for them. Use functions if you want to make
a ruled list(Like `f(x) = f(x - 1) + f(x - 2)`).

```python
a[1] := 10
```

This sets the first element of the list `a` to 10.

```python
a[1 + 1] := 20
```

This sets the second element of the list `a` to 20. You can use parenthesis to give a variable-based input for the
index.

```python
a[-1] := 30
```

This sets the last element of the list `a` to 30. Negative numbers are counted from the end of the list.

```python
b := a[1:3]
```

This defines a list `b` that is a slice of the list `a` from 1 to 3. So if `a := [1, 2, 3, 4, 5]` then `b := [1, 2, 3]`.
The indexes are inclusive.

```python
b := a[::2]
```

This defines a list `b` that is a slice of the list `a` from the beginning to the end of the list with a step of 2. So
if `a := [1, 2, 3, 4, 5]` then `b := [1, 3, 5]`. The default start index is 1. The default end index is the end of the
list. The default step is 1.

```python
p := s(a)
```

The `s()` function is a function that takes a list and returns length of the list.

```python
m := sum(a)
```

If you give in a list to the `sum()` function it will return the sum of all the elements in the list.

***

```python
a := {x = 0, y = 10}
b := {}
```

Both of these define a dictionary.

```python
a["x"] := 10
```

This sets the `x` key of the dictionary `a` to 10.

***

```python
x^2 := x + 2
```

The given code solves for `x` in the given `x^2 = x + 2` equation. And I can already hear the questions: "x can both be
2 and -1, which one is it going to be assigned to?" "What if the equation has infinite roots like sin(x) = 0?"

The answer to all of those questions is that the x value it will be picking is going to be the closest x value to 0.

If you want to find other solutions or your function is just not defined at x=0 you can change the starting value:

```python
5: x^2 := x + 2
```

This solves the equation for the x value closest to 5. Which should result with a 2.

You can also change the variable like so:

```python
x=5: x^2 := x + 2
```

The variable will be picked automatically as the only variable in the equation.

You can still use multiple variables in the same equation, but it won't immediately solve the equation.

Note: You cannot use `:=` to solve multi-variable equations as it's an immediate set operation.

```python
x=5: x^2 = x + y
y = 2
print(x)
print(x)
y = 4
print(x)
```

The first line won't compute anything. In the third line, it will solve the equation for `x` as `y` is now defined.

In the line 4 where it prints `x` again, since the variables haven't changed, it will re-use the value of `x`.

In the last line it will re-compute `x` as `y` has changed.

## Holder types

- Number `1`, `1 + i`, `25.25124`, `125e-21`
- Infinity `inf`, `-inf`
- Does not exist `DNE`
- List `[1, 2, 3, 4]`
- Dictionary `{x = 1, y = 2}`
- Immediate Set `{0, 1}`
- Set `{x | x in R, x > 0}`, `R + Q + {0, 1}`

## Defining conditional sets

Examples:

- Z+
- Z+ & {0}
- Z- & {1}
- {x | x in Z}
- {x | x in Z, x mod 2 = 1}
- {x | x in R, 5 <= x <= 10}

### Checking if a number is in a set

```python
is_in_set := 10 in R

; or

is_in_set := 10 ∈ R
```

This sets the value of `is_in_set` to either `0` or `1`. `0` notating it is not in the set and `1` notating that it is
in the set.

## Default constants and functions

### Constants

- e
- π or pi
- φ or phi = (1+sqrt(5))/2
- ε or epsilon = Built in small value close to 0 and positive. Also, this can be used like: 2^+, 2^-
- inf = A variable that represents infinity

### Functions

- **sqrt(x)**: Takes the square root of the given x value.
- **cbrt(x)**: Takes the cube root of the given x value.
- **rand()**: Gives a random real number in the interval [0,1].
- **min(x, y, z, ...)**: Gives the minimum value in the input.
- **max(x, y, z, ...)**: Gives the maximum value in the input.
- **sign(x)**: 0 if x = 0, else x / |x|
- **exit(x) or exit()**: Exits the program with the given error code.
- **⌊x⌋ or floor(x)**: Rounds x down to the closest integer.
- **⌈x⌉ or ceil(x)**: Rounds x up to the closest integer.
- **⌈x⌋ or ⌊x⌉ or round(x)**: Rounds x to the closest integer.
- **|x|**: Finds the absolute value of x.
- **x!**: Finds the factorial of x.
- **Γ(x) or gamma(x)**: Gamma function
- **ζ(x) or zeta(x)**: Riemann zeta function

#### Trigonometric functions

Most of the trigonometric functions are included. Here's a
list: `sin`, `cos`, `tan`, `csc`, `sec`, `cot`, `asin`, `acos`, `atan`, `acsc`, `asec`, `acot`, `sinh`, `cosh`, `tanh`, `csch`, `sech`, `coth`, `asinh`, `acosh`, `atanh`, `acsch`, `asech`, `acoth`

#### Sum and product notations

```python
sum(0 -> 10, 2x^2 + sin(x))
```

Sums for every integer from 0 to 10(inclusive). Uses the only undefined variable `x`. If there are more than one
undefined variables, it will throw an error.

```python
sum(0 -> inf, 1/x^2)
```

Sums for every integer from 0 to infinity, if the threshold is reached it will be set to either `inf`, `-inf` or `DNE`
depending on the case.

```python
sum(-inf -> inf - {0}, 1/x^2)
```

Sums for every integer from -infinity to infinity, excluding 0.

```python
prod(0 -> 10, x + 1)
```

This takes the product of the given equation for every integer from 0 to 10(inclusive).

#### Limit notation

```python
lim(x -> 2, (x^2 - 4) / (x - 2))
```

Takes the limit as x approaches 2 but never is 2. Results with 4.

```python
lim(x -> 2^+, (x^2 - 4) / |x - 2|)
```

Takes the limit as x approaches 2 from the right side so x > 2. Results with a number slightly bigger than 4.

```python
lim(x -> 2, y -> 3, x^2 + y^2)
```

Takes the multi-variable limit of x approaching 2 and y approaching 3. Results with 13.

#### Derivative notation

```python
f(x) = x^2
f'(10) ; this is 20
```

You can use the usual `f'(x)` notation for single variable functions.

```python
f(x) = x^2
f''(10) ; this is 2
```

#### Integral notation

```python
int(x, 0, 1, 3x^2)
```

Integrates 3x^2 from 0 to 1.

Gamma example:

```python
int(x, 0, inf, x^4 e^(-x)) ; similar to gamma, results with 4! = 24
```

## Conditionals

Examples:

```python
if x > 0:
    x := 10
```

```python
if x < 0:
    x := 20
else if x > 0:
    x := 30
else:
    x := 50
```

## Loops

```python
for (x in 0 -> 10):
    print(x)
```

## Inputs and outputs

```python
a := 10
print('Hello, world!')
print('My variable is: ', a)

; The following expression gets a real number from the user and assigns it to a variable.
b := input('Please enter a real number: ', R)
```
