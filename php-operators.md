# PHP Operators — Study Notes

Operators are special symbols used to perform operations on variables and values.

PHP groups operators into the following categories:

- [Arithmetic Operators](#arithmetic-operators)
- [Assignment Operators](#assignment-operators)
- [Comparison Operators](#comparison-operators)
- [Increment / Decrement Operators](#increment--decrement-operators)
- [Logical Operators](#logical-operators)
- [String Operators](#string-operators)
- [Array Operators](#array-operators)
- [Conditional Operators](#conditional-operators)

---

## Arithmetic Operators

Used with numeric values to perform common mathematical operations (addition, subtraction, multiplication, etc.).

| Operator | Name | Example | Result |
|---|---|---|---|
| `+` | Addition | `$x + $y` | Sum of `$x` and `$y` |
| `-` | Subtraction | `$x - $y` | Difference of `$x` and `$y` |
| `*` | Multiplication | `$x * $y` | Product of `$x` and `$y` |
| `/` | Division | `$x / $y` | Quotient of `$x` and `$y` |
| `%` | Modulus | `$x % $y` | Remainder of `$x` divided by `$y` |
| `**` | Exponentiation | `$x ** $y` | Result of raising `$x` to the `$y`-th power |

---

## Assignment Operators

Used with numeric values to assign values to variables.

| Assignment | Same as... | Description |
|---|---|---|
| `$x = $y` | `$x = $y` | Assign — left operand is set to the value of the expression on the right |
| `$x += $y` | `$x = $x + $y` | Add and assign |
| `$x -= $y` | `$x = $x - $y` | Subtract and assign |
| `$x *= $y` | `$x = $x * $y` | Multiply and assign |
| `$x /= $y` | `$x = $x / $y` | Divide and assign |
| `$x %= $y` | `$x = $x % $y` | Modulus and assign |

---

## Comparison Operators

Used to compare two values (number or string) and return a boolean result.

| Operator | Name | Example | Result |
|---|---|---|---|
| `==` | Equal | `$x == $y` | `true` if `$x` is equal to `$y` |
| `===` | Identical | `$x === $y` | `true` if `$x` is equal to `$y`, and they are of the same type |
| `!=` | Not equal | `$x != $y` | `true` if `$x` is not equal to `$y` |
| `<>` | Not equal | `$x <> $y` | `true` if `$x` is not equal to `$y` |
| `!==` | Not identical | `$x !== $y` | `true` if `$x` is not equal to `$y`, or they are not of the same type |
| `>` | Greater than | `$x > $y` | `true` if `$x` is greater than `$y` |
| `<` | Less than | `$x < $y` | `true` if `$x` is less than `$y` |
| `>=` | Greater than or equal to | `$x >= $y` | `true` if `$x` is greater than or equal to `$y` |
| `<=` | Less than or equal to | `$x <= $y` | `true` if `$x` is less than or equal to `$y` |
| `<=>` | Spaceship | `$x <=> $y` | Returns an integer less than, equal to, or greater than zero, depending on whether `$x` is less than, equal to, or greater than `$y`. Introduced in PHP 7. |

---

## Increment / Decrement Operators

Used to increment or decrement a variable's value by one.

| Operator | Same as... | Description |
|---|---|---|
| `++$x` | Pre-increment | Increments `$x` by one, then returns `$x` |
| `$x++` | Post-increment | Returns `$x`, then increments `$x` by one |
| `--$x` | Pre-decrement | Decrements `$x` by one, then returns `$x` |
| `$x--` | Post-decrement | Returns `$x`, then decrements `$x` by one |

---

## Logical Operators

Used to combine conditional statements and return a boolean result.

| Operator | Name | Example | Result |
|---|---|---|---|
| `and` | And | `$x and $y` | `true` if both `$x` and `$y` are true |
| `or` | Or | `$x or $y` | `true` if either `$x` or `$y` is true |
| `xor` | Xor | `$x xor $y` | `true` if either `$x` or `$y` is true, but not both |
| `&&` | And | `$x && $y` | `true` if both `$x` and `$y` are true |
| `\|\|` | Or | `$x \|\| $y` | `true` if either `$x` or `$y` is true |
| `!` | Not | `!$x` | `true` if `$x` is not true |

---

## String Operators

Used to concatenate strings.

| Operator | Name | Example | Result |
|---|---|---|---|
| `.` | Concatenation | `$txt1 . $txt2` | Concatenation of `$txt1` and `$txt2` |
| `.=` | Concatenation assignment | `$txt1 .= $txt2` | Appends `$txt2` to `$txt1` |

---

## Array Operators

Used to compare arrays.

| Operator | Name | Example | Result |
|---|---|---|---|
| `+` | Union | `$x + $y` | Union of `$x` and `$y` |
| `==` | Equality | `$x == $y` | `true` if `$x` and `$y` have the same key/value pairs |
| `===` | Identity | `$x === $y` | `true` if `$x` and `$y` have the same key/value pairs, in the same order, and of the same types |
| `!=` | Inequality | `$x != $y` | `true` if `$x` is not equal to `$y` |
| `<>` | Inequality | `$x <> $y` | `true` if `$x` is not equal to `$y` |
| `!==` | Non-identity | `$x !== $y` | `true` if `$x` is not identical to `$y` |

---

## Conditional Operators

Shorthand for `if...else`, used to set a value depending on a condition.

| Operator | Name | Example | Result |
|---|---|---|---|
| `?:` | Ternary | `$x = expr1 ? expr2 : expr3` | Value of `$x` is `expr2` if `expr1` is `TRUE`; otherwise `expr3` |
| `??` | Null coalescing | `$x = expr1 ?? expr2` | Value of `$x` is `expr1` if `expr1` exists and is not `NULL`; otherwise `expr2`. Introduced in PHP 7. |

---

*Notes based on core PHP documentation — reorganized for personal study/reference.*
