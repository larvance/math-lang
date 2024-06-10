# Math Lang

## Variables

```python
a = 10

; or

a := 10
```

Sets the value of `a` to 10.

Note: Variable names cannot include these characters: `+`, `-`, `*`, `/`, `^`, `(`, `)`, `{`, `}`, `=`, `>`, `<`, `:`, `;`

***

```python
a := x + y
```

This sets the value of `a` to the sum of `x` and `y`.

***

```python
a = x + y
```

Does not set the value of `a` to the sum of `x` and `y`.

This line of code instead defines `a` as a function that depends on the values of `x` and `y`.

This is similar to this:

```python
a(x, y) = x + y
```

But the example given before doesn't require function notations and uses the `x` `y` variables that are already defined in the global scope.

***

```python
ab := 10
```

You can also define variables with more than one character.

***

```python
f(x) = x + 10
```

This basically defines a function and can be executed like: `f(10)`

***

```python
a := {}
```

This defines a set.

```python
a_1 := 10
```

This sets the first element of the set `a` to 10.

```python
a_(1 + 1) := 20
```

This sets the second element of the set `a` to 20. You can use parenthesis to give a variable-based input for the index.

Note: Sets usually are known to not include unique elements but these can. This is somewhat required since if it were to only include unique elements it would be hard for the user of the language to keep track of which index has what value.

Note 2: Sets can also have more than one characters for their names.

***

```python
x^2 = x + 2
```

The given code solves for `x` in the given `x^2 = x + 2` equation. And I can already here the questions: "x can both be 2 and -1, which one is it gonna be assigned to?" "What if the equation has infinite roots like sin(x) = 0?"

The answer to all of those questions is that the x value it will be picking is gonna be the closest x value to 0.

You can change this too if you want to find other solutions or your function is just not defined at x=0:

```python
5: x^2 = x + 2
```

This solves the equation for the x value closest to 5. Which should result with a 2.

You can also change the variable like so:

```python
x=5: x^2 = x + 2
```

The variable will be picked automatically as the only variable in the equation. If there are more than one variables in the equation it will throw an error telling you to specify the variable.

## Holder types

- Numbers (0) `1`, `1 + i`, `25.25124`, `125e-21`
- Infinity (1) `inf`
- Does not exist (2) `DNE`
- Set (3) `{1, 2, 3, 4}`

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

This sets the value of `is_in_set` to either `0` or `1`. `0` notating it is not in the set and `1` notating that it is in the set.

## Default constants and functions

### Constants

- e
- π or pi
- φ or phi = (1+sqrt(5))/2
- ε or epsilon = Built in extremely small value close to 0 and positive. Also can be used like: 2^+, 2^-
- inf = A variable that represents infinity

### Functions

- **sqrt(x)**: Takes the square root of the given x value.
- **cbrt(x)**: Takes the cube root of the given x value.
- **rand()**: Gives a random real number in the interval [0,1].
- **min(x, y, z, ...)**: Gives the minimum value in the input.
- **max(x, y, z, ...)**: Gives the maximum value in the input.
- **sign(x)**: Gives 1 if positive, 0 if zero, -1 if negative.
- **exit(x) or exit()**: Exits the program with the given number.
- **⌊x⌋ or floor(x)**: Rounds x up to the closest integer.
- **⌈x⌉ or ceil(x)**: Rounds x down to the closest integer.
- **⌈x⌋ or ⌊x⌉ or round(x)**: Rounds x to the closest integer.
- **|x|**: Finds the absolute value of x.
- **x!**: Finds the factorial of x.
- **Γ(x) or gamma(x)**: Gamma function
- **ζ(x) or zeta(x)**: Riemann zeta function

#### Trigonometric functions

Most of the trigonometric functions are included. Here's a list: `sin`, `cos`, `tan`, `csc`, `sec`, `cot`, `asin`, `acos`, `atan`, `acsc`, `asec`, `acot`, `sinh`, `cosh`, `tanh`, `csch`, `sech`, `coth`, `asinh`, `acosh`, `atanh`, `acsch`, `asech`, `acoth`

#### Sum and product notations

```python
sum(x = 0 -> 10, 2x^2 + sin(x))
```

Sums for every integer from 0 to 10(inclusive).

```python
sum(x = 0 -> inf, 1/x^2)
```

Sums for every integer from 0 to infinity, if the threshold is reached it will be set to either `inf`, `-inf` or `DNE` depending on the case.

```python
prod(x = 0 -> 10, x + 1)
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
int(x, 0, inf, x^2 e^(-x)) ; similar to gamma, results with 2! = 2
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

## Inputs and outputs

```python
a := 10
print('Hello, world!')
print('My variable is: ', a)

; The following expression gets a real number from the user and assigns it to a variable.
b := input('Please enter a real number: ', R)
```
