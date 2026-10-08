# PHP Arrays — Study Notes

## Table of Contents
1. [Arrays Overview](#1-arrays-overview)
   - [Array Types](#array-types)
   - [Array Items](#array-items)
   - [Array Functions](#array-functions)
2. [Creating Arrays](#2-creating-arrays)
   - [The `array()` Function](#the-array-function)
   - [Short Syntax `[]`](#short-syntax-)
   - [Multiple Lines](#multiple-lines)
   - [Trailing Comma](#trailing-comma)
   - [Array Keys](#array-keys)
   - [Declaring an Empty Array](#declaring-an-empty-array)
   - [Mixing Array Keys](#mixing-array-keys)
3. [Indexed Arrays](#3-indexed-arrays)
   - [Accessing Items by Index](#accessing-items-by-index)
   - [Changing Items by Index](#changing-items-by-index)
   - [Looping Through an Indexed Array](#looping-through-an-indexed-array)
4. [Associative Arrays](#4-associative-arrays)
   - [Accessing Items by Key](#accessing-items-by-key)
   - [Changing Items by Key](#changing-items-by-key)
   - [Looping Through an Associative Array](#looping-through-an-associative-array)
5. [Updating Array Items](#5-updating-array-items)
   - [Updating Indexed and Associative Items](#updating-indexed-and-associative-items)
   - [Updating Items in a `foreach` Loop](#updating-items-in-a-foreach-loop)
6. [Adding Array Items](#6-adding-array-items)
   - [Adding a Single Item with `[]`](#adding-a-single-item-with-)
   - [Adding to Associative Arrays with `[]`](#adding-to-associative-arrays-with-)
   - [`array_push()`](#array_push)
   - [Adding Multiple Items to an Associative Array with `+=`](#adding-multiple-items-to-an-associative-array-with-)
   - [`array_unshift()`](#array_unshift)
   - [`array_splice()`](#array_splice)
   - [`array_merge()`](#array_merge)
7. [Removing Array Items](#7-removing-array-items)
   - [`array_splice()` for Removal](#array_splice-for-removal)
   - [`unset()`](#unset)
   - [Removing an Item from an Associative Array](#removing-an-item-from-an-associative-array)
   - [`array_diff()`](#array_diff)
   - [`array_pop()` — Remove Last Item](#array_pop--remove-last-item)
   - [`array_shift()` — Remove First Item](#array_shift--remove-first-item)
8. [Array Sorting Functions](#8-array-sorting-functions)
   - [`sort()` — Ascending Order](#sort--ascending-order)
   - [`rsort()` — Descending Order](#rsort--descending-order)
   - [`asort()` and `arsort()` — Sort by Value](#asort-and-arsort--sort-by-value)
   - [`ksort()` and `krsort()` — Sort by Key](#ksort-and-krsort--sort-by-key)
9. [Multidimensional Arrays](#9-multidimensional-arrays)
   - [Two-Dimensional Arrays](#two-dimensional-arrays)
   - [Looping Through Multidimensional Arrays](#looping-through-multidimensional-arrays)

---

# 1. Arrays Overview

An **array** is a special variable that can hold many values under a single name. You can access the values by referring to an **index number** or a **name**.

```php
$cars = array("Volvo", "BMW", "Toyota");
```

## Array Types

PHP has three types of arrays:

| Type | Description |
|---|---|
| **Indexed arrays** | Arrays with a numeric index |
| **Associative arrays** | Arrays with named keys |
| **Multidimensional arrays** | Arrays containing one or more arrays |

## Array Items

- Array items can be of **any data type**.
- The most common are strings and numbers, but items can also be objects, functions, or even other arrays.
- You can mix different data types in the same array.

```php
// Three different data types in one array
$myArr = array("Volvo", 15, ["apples", "bananas"]);
```

## Array Functions

The real strength of PHP arrays is the **built-in array functions**.

For example, `count()` returns the number of items in an array:

```php
$cars = array("Volvo", "BMW", "Toyota");
echo count($cars); // 3
```

---

# 2. Creating Arrays

## The `array()` Function

In PHP, the `array()` function is used to create an array.

```php
$cars = array("Volvo", "BMW", "Toyota");
```

## Short Syntax `[]`

> **Tip:** You can also use a shorter syntax to create an array, by using square brackets `[]`.

```php
$cars = ["Volvo", "BMW", "Toyota"];
```

## Multiple Lines

Line breaks are not important, so an array declaration can span multiple lines.

```php
$cars = [
  "Volvo",
  "BMW",
  "Toyota"
];
```

## Trailing Comma

A comma after the last item is allowed.

```php
$cars = [
  "Volvo",
  "BMW",
  "Toyota",
];
```

## Array Keys

When creating **indexed arrays**, the keys are given automatically, starting at `0` and increasing by `1` for each item. The array above could also be created with explicit keys:

```php
$cars = [
  0 => "Volvo",
  1 => "BMW",
  2 => "Toyota"
];
```

Indexed arrays are essentially the same as associative arrays — the difference is that **associative arrays use names instead of numbers**:

```php
$myCar = [
  "brand" => "Ford",
  "model" => "Mustang",
  "year" => 1964
];
```

## Declaring an Empty Array

You can declare an empty array first and add items to it later.

**Indexed array:**

```php
$cars = [];
$cars[0] = "Volvo";
$cars[1] = "BMW";
$cars[2] = "Toyota";
```

**Associative array:**

```php
$myCar = [];
$myCar["brand"] = "Ford";
$myCar["model"] = "Mustang";
$myCar["year"] = 1964;
```

## Mixing Array Keys

You can have arrays with both indexed and named keys.

```php
$myArr = [];
$myArr[0] = "apples";
$myArr[1] = "bananas";
$myArr["fruit"] = "cherries";
```

---

# 3. Indexed Arrays

In an **indexed array**, each item has an index number:

- The first item has index `0`
- The second item has index `1`
- ...and so on

```php
$cars = array("Volvo", "BMW", "Toyota");
var_dump($cars);
```

| Index | Value |
|---|---|
| `0` | `"Volvo"` |
| `1` | `"BMW"` |
| `2` | `"Toyota"` |

## Accessing Items by Index

To access a specific item, refer to its index number.

```php
$cars = array("Volvo", "BMW", "Toyota");
echo $cars[0]; // Volvo
```

## Changing Items by Index

To change the value of an item, use its index number.

```php
$cars = array("Volvo", "BMW", "Toyota");
$cars[1] = "Ford";
var_dump($cars); // "Volvo", "Ford", "Toyota"
```

## Looping Through an Indexed Array

To loop through and print all the values of an indexed array, use a `foreach` loop.

```php
$cars = array("Volvo", "BMW", "Toyota");
foreach ($cars as $x) {
  echo "$x <br>";
}
```

---

# 4. Associative Arrays

**Associative arrays** use **named keys** instead of numeric indices.

```php
$car = array("brand"=>"Ford", "model"=>"Mustang", "year"=>1964);
var_dump($car);
```

| Key | Value |
|---|---|
| `"brand"` | `"Ford"` |
| `"model"` | `"Mustang"` |
| `"year"` | `1964` |

## Accessing Items by Key

To access a specific item, refer to its key name.

```php
$car = array("brand"=>"Ford", "model"=>"Mustang", "year"=>1964);
echo $car["model"]; // Mustang
```

## Changing Items by Key

To change the value of an item, use its key name.

```php
$car = array("brand"=>"Ford", "model"=>"Mustang", "year"=>1964);
$car["year"] = 2024;
var_dump($car); // year is now 2024
```

## Looping Through an Associative Array

To loop through and print all the keys and values of an associative array, use a `foreach` loop with `$key => $value`.

```php
$car = array("brand"=>"Ford", "model"=>"Mustang", "year"=>1964);
foreach ($car as $x => $y) {
  echo "$x: $y <br>";
}
```

---

# 5. Updating Array Items

## Updating Indexed and Associative Items

To update an existing array item:

- For **indexed arrays**, refer to the **index number**.
- For **associative arrays**, refer to the **key name**.

**Indexed array** — change the second item from `"BMW"` to `"Ford"`:

```php
$cars = array("Volvo", "BMW", "Toyota");
$cars[1] = "Ford";
```

> **Note:** The first item has index `0`.

**Associative array** — update the `year`:

```php
$cars = array("brand" => "Ford", "model" => "Mustang", "year" => 1964);
$cars["year"] = 2024;
```

## Updating Items in a `foreach` Loop

There are different techniques for changing item values inside a `foreach` loop.

One way is to assign the item **by reference**, using the `&` character. This ensures any changes made to the item inside the loop are applied to the **original array**.

**Change all items to `"Ford"`:**

```php
$cars = array("Volvo", "BMW", "Toyota");
foreach ($cars as &$x) {
  $x = "Ford";
}
unset($x);
var_dump($cars);
```

> **Note:** Always call `unset()` after a by-reference `foreach` loop. If omitted, `$x` remains a reference to the **last array item** — meaning any later reassignment of `$x` will silently overwrite that element too.

**What happens if you forget `unset()`:**

```php
$cars = array("Volvo", "BMW", "Toyota");
foreach ($cars as &$x) {
  $x = "Ford";
}

$x = "ice cream";

var_dump($cars);
// The last element of $cars becomes "ice cream",
// because $x was still referencing it.
```

---

# 6. Adding Array Items

PHP offers several ways to add items to an array:

| Method | Description |
|---|---|
| `[]` | Adds a single item to the end of an array |
| `array_push()` | Adds one or more items to the end of an array |
| `array_unshift()` | Adds one or more items to the beginning of an array |
| `array_splice()` | Removes a portion of an array and replaces it with new elements (can also insert) |
| `array_merge()` | Merges two or more arrays |

## Adding a Single Item with `[]`

To add a single item to the end of an existing array, use the bracket `[]` syntax.

```php
$fruits = array("Apple", "Banana", "Cherry");
$fruits[] = "Orange";
var_dump($fruits);
```

You can add more items the same way — but one at a time:

```php
$fruits = array("Apple", "Banana", "Cherry");
$fruits[] = "Orange";
$fruits[] = "Pear";
var_dump($fruits);
```

## Adding to Associative Arrays with `[]`

To add an item to the end of an associative array, use brackets `[]` for the key name and assign a value with `=`.

```php
$cars = array("brand" => "Ford", "model" => "Mustang");
$cars["color"] = "Red";
var_dump($cars);
```

## `array_push()`

Adds one or more items to the end of an existing array.

```php
$fruits = array("Apple", "Banana", "Cherry");
array_push($fruits, "Orange", "Kiwi", "Lemon");
var_dump($fruits);
```

## Adding Multiple Items to an Associative Array with `+=`

To add multiple items to an existing associative array at once, use the `+=` operator.

```php
$cars = array("brand" => "Ford", "model" => "Mustang");
$cars += ["color" => "red", "year" => 1964];
var_dump($cars);
```

## `array_unshift()`

Adds one or more items to the **beginning** of an existing array.

```php
$fruits = array("Apple", "Banana", "Cherry");
array_unshift($fruits, "Orange", "Kiwi", "Lemon");
var_dump($fruits);
```

## `array_splice()`

Removes a portion of an array and replaces it with new items.

> If you specify an offset with a length of `0` (nothing to remove), `array_splice()` simply **inserts** the new item(s) at that position.

```php
$fruits = array("Apple", "Banana", "Cherry");
$new_fruit = "Orange";
array_splice($fruits, 1, 0, $new_fruit); // insert "Orange" at index 1
var_dump($fruits);
```

## `array_merge()`

Merges two or more arrays into one.

```php
$fruits1 = array("Apple", "Banana");
$fruits2 = array("Cherry", "Orange");
$result = array_merge($fruits1, $fruits2);
var_dump($result);
```

---

# 7. Removing Array Items

PHP offers several ways to remove items from an array:

| Function | Description |
|---|---|
| `array_splice()` | Removes a portion of the array, starting from a position, for a given length |
| `unset()` | Removes the element associated with a specific key |
| `array_diff()` | Returns a new array with specified values removed |
| `array_pop()` | Removes the **last** array item |
| `array_shift()` | Removes the **first** array item |

## `array_splice()` for Removal

Specify the index (where to start) and how many items to delete. After deletion, the array is **automatically re-indexed**, starting at `0`.

**Remove the second item:**

```php
$cars = array("Volvo", "BMW", "Toyota");
array_splice($cars, 1, 1);
var_dump($cars);
```

**Remove multiple items** — specify a length greater than 1:

```php
// Remove 2 items, starting at the second item (index 1)
$cars = array("Volvo", "BMW", "Toyota");
array_splice($cars, 1, 2);
var_dump($cars);
```

## `unset()`

Deletes an existing array item by key/index.

> **Note:** `unset()` does **not** re-index the array. If you remove the item at index 1, the remaining items (e.g. at index 0, 2, 3...) keep their **original indices**, leaving a "gap" in the sequence.

**Remove the second item:**

```php
$cars = array("Volvo", "BMW", "Toyota");
unset($cars[1]);
var_dump($cars);
```

**Remove multiple items** — `unset()` accepts an unlimited number of arguments:

```php
// Remove the first and second item
$cars = array("Volvo", "BMW", "Toyota");
unset($cars[0], $cars[1]);
var_dump($cars);
```

## Removing an Item from an Associative Array

Use `unset()` with the key name of the item to remove.

```php
$cars = array("brand" => "Ford", "model" => "Mustang", "year" => 1964);
unset($cars["model"]);
var_dump($cars);
```

## `array_diff()`

Returns a **new array**, without the specified items.

```php
// Create a new array, without "Mustang" and 1964
$cars = array("brand" => "Ford", "model" => "Mustang", "year" => 1964);
$newarray = array_diff($cars, ["Mustang", 1964]);
var_dump($newarray);
```

> **Note:** `array_diff()` compares by **values**, not keys.

## `array_pop()` — Remove Last Item

```php
$cars = array("Volvo", "BMW", "Toyota");
array_pop($cars);
var_dump($cars);
```

## `array_shift()` — Remove First Item

```php
$cars = array("Volvo", "BMW", "Toyota");
array_shift($cars);
var_dump($cars);
```

---

# 8. Array Sorting Functions

Array items can be sorted in alphabetical or numerical order, ascending or descending.

| Function | Description |
|---|---|
| `sort()` | Sorts an indexed array in ascending order |
| `rsort()` | Sorts an indexed array in descending order |
| `asort()` | Sorts an associative array in ascending order, by **value** |
| `ksort()` | Sorts an associative array in ascending order, by **key** |
| `arsort()` | Sorts an associative array in descending order, by **value** |
| `krsort()` | Sorts an associative array in descending order, by **key** |

## `sort()` — Ascending Order

Sorts an indexed array in ascending order.

```php
// Alphabetical
$cars = array("Volvo", "BMW", "Toyota");
sort($cars);
print_r($cars);
```

```php
// Numerical
$numbers = array(4, 6, 2, 22, 11);
sort($numbers);
print_r($numbers);
```

## `rsort()` — Descending Order

Sorts an indexed array in descending order.

```php
// Alphabetical
$cars = array("Volvo", "BMW", "Toyota");
rsort($cars);
print_r($cars);
```

```php
// Numerical
$numbers = array(4, 6, 2, 22, 11);
rsort($numbers);
print_r($numbers);
```

## `asort()` and `arsort()` — Sort by Value

`asort()` sorts an associative array in **ascending** order, according to the **value**:

```php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");
asort($age);
print_r($age);
```

`arsort()` sorts an associative array in **descending** order, according to the **value**:

```php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");
arsort($age);
print_r($age);
```

## `ksort()` and `krsort()` — Sort by Key

`ksort()` sorts an associative array in **ascending** order, according to the **key**:

```php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");
ksort($age);
print_r($age);
```

`krsort()` sorts an associative array in **descending** order, according to the **key**:

```php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");
krsort($age);
print_r($age);
```

---

# 9. Multidimensional Arrays

A **multidimensional array** is an array containing one or more arrays.

PHP supports multidimensional arrays that are two, three, four, five, or more levels deep. However, arrays more than three levels deep are hard to manage for most people.

## Two-Dimensional Arrays

A **two-dimensional array** is an array of arrays (a three-dimensional array is an array of arrays of arrays).

Example data:

| Name | Stock | Sold |
|---|---|---|
| Volvo | 22 | 18 |
| BMW | 15 | 13 |
| Saab | 5 | 2 |
| Land Rover | 17 | 15 |

This table can be stored as a two-dimensional array:

```php
$cars = array (
  array("Volvo", 22, 18),
  array("BMW", 15, 13),
  array("Saab", 5, 2),
  array("Land Rover", 17, 15)
);
```

The `$cars` array now contains four arrays, and has **two indices**: row and column.

To access an element, point to **both indices** (row, then column):

```php
echo $cars[0][0].": In stock: ".$cars[0][1].", sold: ".$cars[0][2].".<br>";
echo $cars[1][0].": In stock: ".$cars[1][1].", sold: ".$cars[1][2].".<br>";
echo $cars[2][0].": In stock: ".$cars[2][1].", sold: ".$cars[2][2].".<br>";
echo $cars[3][0].": In stock: ".$cars[3][1].", sold: ".$cars[3][2].".<br>";
```

> The **dimension** of an array indicates how many indices are needed to select an element:
> - A two-dimensional array needs **two** indices.
> - A three-dimensional array needs **three** indices.

## Looping Through Multidimensional Arrays

Use a `for` loop or a `foreach` loop — nested one inside the other.

**Nested `for` loops:**

```php
for ($row = 0; $row < 4; $row++) {
  echo "<p><b>Row number $row</b></p>";
  echo "<ul>";
    for ($col = 0; $col < 3; $col++) {
      echo "<li>".$cars[$row][$col]."</li>";
    }
  echo "</ul>";
}
```

**Nested `foreach` loops** — building an HTML table:

```php
echo "<table>";
echo "<tr><th>Brand</th><th>Stock</th><th>Sold</th></tr>";

foreach ($cars as $row) {
  echo "<tr>";
  foreach ($row as $cell) {
    echo "<td>" . $cell . "</td>";
  }
  echo "</tr>";
}
echo "</table>";
```

---

*Notes based on core PHP documentation — reorganized for personal study/reference.*
