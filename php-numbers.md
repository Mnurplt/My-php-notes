# PHP Numbers — Study Notes

A quick-reference guide to numeric types and number-related functions in PHP.

## Table of Contents
- [Overview](#overview)
- [Checking Variable Types](#checking-variable-types)
- [Integers](#integers)
- [Floats](#floats)
- [Infinity](#infinity)
- [NaN (Not a Number)](#nan-not-a-number)
- [Numbers vs. Numeric Strings](#numbers-vs-numeric-strings)
- [Getting the Integer Value of a Variable](#getting-the-integer-value-of-a-variable)

---

## Overview

PHP has three main numeric types:

- **Integer**
- **Float**
- **Numeric String**

Plus two special numeric values:

- **Infinity**
- **NaN**

Variables get their numeric type automatically when a value is assigned:

```php
$a = 5;       // integer
$b = 5.34;    // float
$c = "25";    // numeric string
```

## Checking Variable Types

Use `var_dump()` to inspect the type and value of any variable:

```php
var_dump($a);
var_dump($b);
var_dump($c);
```

---

## Integers

An **integer** is a number without any decimal part (e.g. `2`, `256`, `-256`, `10358`, `-179567`).

### `is_int()`

Checks whether a variable is of type integer.

```php
$x = 5985;
var_dump(is_int($x)); // true

$y = 59.85;
var_dump(is_int($y)); // false
```

### Range

An integer is a non-decimal number:
- **32-bit systems:** `-2147483648` to `2147483647`
- **64-bit systems:** `-9223372036854775808` to `9223372036854775807`

Any value outside this range is automatically stored as a **float**.

> **Note:** Even though `4 * 2.5` equals `10`, the result is stored as a float — because one of the operands (`2.5`) is a float.

### Integer Rules

- Must have at least one digit
- Must **not** have a decimal point
- Can be positive or negative
- Can be written in four formats:
  - Decimal (base 10)
  - Hexadecimal (base 16, prefixed with `0x`)
  - Octal (base 8, prefixed with `0`)
  - Binary (base 2, prefixed with `0b`)

### Predefined Integer Constants

| Constant | Description |
|---|---|
| `PHP_INT_MAX` | The largest supported integer |
| `PHP_INT_MIN` | The smallest supported integer |
| `PHP_INT_SIZE` | Size of an integer, in bytes |

---

## Floats

A **float** is a number with a decimal point, or a number in exponential form (e.g. `2.0`, `256.4`, `10.358`, `7.64E+5`, `5.56E-5`).

### `is_float()`

Checks whether a variable is of type float.

```php
$x = 10.365;
var_dump(is_float($x)); // true
```

Floats can typically store values up to `1.7976931348623E+308` (platform-dependent), with a maximum precision of **14 digits**.

### Predefined Float Constants (PHP 7.2+)

| Constant | Description |
|---|---|
| `PHP_FLOAT_MAX` | Largest representable float |
| `PHP_FLOAT_MIN` | Smallest representable positive float |
| `PHP_FLOAT_DIG` | Number of decimal digits that survive a round-trip without precision loss |
| `PHP_FLOAT_EPSILON` | Smallest positive `x` such that `x + 1.0 != 1.0` |

---

## Infinity

- **`is_finite()`** — checks whether a value falls within the allowed range for a PHP float on the current platform.
- **`is_infinite()`** — checks whether a value falls *outside* that allowed range.

```php
$x = 1.9e411;
var_dump(is_infinite($x)); // true
```

---

## NaN (Not a Number)

`NAN` is returned when a mathematical operation is invalid.

**`is_nan()`** checks whether a value is `NAN`.

```php
$x = acos(8); // invalid input for acos()
var_dump($x); // float(NAN)

var_dump(is_nan($x)); // true
```

---

## Numbers vs. Numeric Strings

**`is_numeric()`** checks whether a variable is a number **or** a numeric string. Returns `true`/`false` accordingly.

```php
$x = 5985;
var_dump(is_numeric($x)); // true

$x = "5985";
var_dump(is_numeric($x)); // true

$x = "59.85" + 100;
var_dump(is_numeric($x)); // true

$x = "Hello";
var_dump(is_numeric($x)); // false
```

---

## Getting the Integer Value of a Variable

**`intval()`** extracts the integer value from a variable (float or numeric string).

```php
$x = 23465.768;
echo intval($x); // 23465

$x = "23465.768";
echo intval($x); // 23465
```

---

*Notes based on core PHP numeric type documentation — reorganized for personal study/reference.*
