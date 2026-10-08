# PHP Type Casting — Study Notes

## Table of Contents
- [Overview](#overview-1)
- [Cast to String](#cast-to-string)
- [Cast to Integer](#cast-to-integer)
- [Cast to Float](#cast-to-float)
- [Cast to Boolean](#cast-to-boolean)
- [Cast to Array](#cast-to-array)
- [Cast to Object](#cast-to-object)
- [Cast to NULL](#cast-to-null)

## Overview

Type casting is the **explicit** process of converting a value from one data type to another (e.g. float → integer). It gives the developer direct control over a variable's type.

To cast a variable, place the target type in parentheses before the variable or value:

```php
(string) $x;
```

### Casting Operators

| Operator | Converts to |
|---|---|
| `(string)` | String |
| `(int)` | Integer |
| `(float)` | Float |
| `(bool)` | Boolean |
| `(array)` | Array |
| `(object)` | Object |
| `(unset)` | NULL — **deprecated** in PHP 7.2.0, **removed** in PHP 8.0.0 |

---

## Cast to String

Use `(string)` before the variable or value:

```php
$a = 5;       // Integer
$b = 5.34;    // Float
$c = "hello"; // String
$d = true;    // Boolean
$e = NULL;    // NULL

$a = (string) $a;
$b = (string) $b;
$c = (string) $c;
$d = (string) $d;
$e = (string) $e;

// Use var_dump() to verify the data type
var_dump($a);
var_dump($b);
var_dump($c);
var_dump($d);
var_dump($e);
```

---

## Cast to Integer

Use `(int)` before the variable or value:

```php
$a = 5;       // Integer
$b = 5.34;    // Float
$c = "25 km"; // String
$d = "km 25"; // String
$e = "hello"; // String
$f = true;    // Boolean
$g = NULL;    // NULL

$a = (int) $a;
$b = (int) $b;
$c = (int) $c;
$d = (int) $d;
$e = (int) $e;
$f = (int) $f;
$g = (int) $g;
```

---

## Cast to Float

Use `(float)` before the variable or value:

```php
$a = 5;       // Integer
$b = 5.34;    // Float
$c = "25 km"; // String
$d = "km 25"; // String
$e = "hello"; // String
$f = true;    // Boolean
$g = NULL;    // NULL

$a = (float) $a;
$b = (float) $b;
$c = (float) $c;
$d = (float) $d;
$e = (float) $e;
$f = (float) $f;
$g = (float) $g;
```

---

## Cast to Boolean

Use `(bool)` before the variable or value:

```php
$a = 5;       // Integer
$b = 5.34;    // Float
$c = 0;       // Integer
$d = -1;      // Integer
$e = 0.1;     // Float
$f = "hello"; // String
$g = "";      // String
$h = true;    // Boolean
$i = NULL;    // NULL

$a = (bool) $a;
$b = (bool) $b;
$c = (bool) $c;
$d = (bool) $d;
$e = (bool) $e;
$f = (bool) $f;
$g = (bool) $g;
$h = (bool) $h;
$i = (bool) $i;
```

> **Rule of thumb:** `0`, `NULL`, `false`, and empty values (`""`) cast to `false`. Everything else — **including `-1`** — casts to `true`.

---

## Cast to Array

Use `(array)` before the variable or value:

```php
$a = 5;       // Integer
$b = 5.34;    // Float
$c = "hello"; // String
$d = true;    // Boolean
$e = NULL;    // NULL

$a = (array) $a;
$b = (array) $b;
$c = (array) $c;
$d = (array) $d;
$e = (array) $e;
```

**Conversion rules:**
- Most scalar types convert into an indexed array with a single element.
- `NULL` converts into an empty array.
- An **object** converts into an associative array, where property names become keys and property values become values.

**Example — converting an object into an array:**

```php
class Car {
  public $color;
  public $model;
  public function __construct($color, $model) {
    $this->color = $color;
    $this->model = $model;
  }
  public function message() {
    return "My car is a " . $this->color . " " . $this->model . "!";
  }
}

$myCar = new Car("red", "Volvo");
$myCar = (array) $myCar;
var_dump($myCar);
```

---

## Cast to Object

Use `(object)` before the variable or value:

```php
$a = 5;       // Integer
$b = 5.34;    // Float
$c = "hello"; // String
$d = true;    // Boolean
$e = NULL;    // NULL

$a = (object) $a;
$b = (object) $b;
$c = (object) $c;
$d = (object) $d;
$e = (object) $e;
```

**Conversion rules:**
- Most scalar types convert into an object with a single property named `scalar`, holding the original value.
- `NULL` converts into an empty object.
- An **indexed array** converts into an object where index numbers become property names.
- An **associative array** converts into an object where keys become property names.

**Example — converting arrays into objects:**

```php
$a = array("Volvo", "BMW", "Toyota");                 // indexed array
$b = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");  // associative array

$a = (object) $a;
$b = (object) $b;
```

---

## Cast to NULL

> **Note:** The `(unset)` casting operator was deprecated in PHP 7.2.0 and removed in PHP 8.0.0.

To set a variable to NULL, simply assign it directly:

```php
$a = 5;       // Integer
$b = 5.34;    // Float
$c = "hello"; // String
$d = true;    // Boolean
$e = NULL;    // NULL

$a = NULL;
$b = NULL;
$c = NULL;
$d = NULL;
$e = NULL;
```

---

*Notes based on core PHP documentation — reorganized for personal study/reference.*
