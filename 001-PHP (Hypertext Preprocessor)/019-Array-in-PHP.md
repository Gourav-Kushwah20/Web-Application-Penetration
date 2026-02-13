# 📚 Arrays in PHP

PHP arrays are powerful data structures to store multiple values in a single variable.

---

## ➡️ Indexed Arrays

An **indexed array** is an ordered collection where keys are integers starting from **0**.


### Example: `array.php`

```php
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Indexed Arrays</title>
</head>
<body>

<?php
$array1 = array(4, 5, 6, 7, 21, 34, 56, 77, 2);

echo $array1[1];   // Output: 5
echo "<br />";
echo $array1[0];   // Output: 4

// Modify array element
$array1[0] = 99;
echo "<br />";
echo $array1[0];   // Output: 99

// Array with mixed data
$array2 = array(88, "Rahul", "Jain", array("a", "b", "c"));

echo "<br />";
echo $array2[0];   // Output: 88
echo "<br />";
echo $array2[1] . " " . $array2[2]; // Output: Rahul Jain
echo "<br />";

// Nested array access
echo $array2[3][0]; // Output: a
echo "<br />";
echo $array2[3][1]; // Output: b
echo "<br />";
echo $array2[3][2]; // Output: c
echo "<br />";

// User info array
$user = array(1, "Rahul", "Jain", "rahul@armour.com", "password1");
echo $user[3]; // Output: rahul@armour.com
?>

</body>
</html>
```
---
## ➡️ Associative Arrays

An **associative array** uses named keys (strings) instead of numeric indexes.

---

### Example: `Associative-Array.php`

```php
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Associative Arrays</title>
</head>
<body>

<?php
// Normal indexed array
$user = array(1, "Rahul", "Jain", "rahul@armour.com", "password1");
print_r($user);
echo "<br />" . $user[3] . "<br />";

// Associative array
$user2 = array(
  "id"       => 1,
  "f_name"   => "Rahul",
  "l_name"   => "Jain",
  "email"    => "rahul@armour.com",
  "password" => "password1"
);

print_r($user2);

echo "<br />" . $user2["email"] . "<br />";
echo $user2["password"] . "<br />";

// Combining values
$user_full_name = $user2["f_name"] . " " . $user2["l_name"];
echo $user_full_name . "<br />";

$user_email = $user2["email"];
echo $user_email;
?>

</body>
</html>
```
---

## ➡️ Array Functions

PHP provide many built-in functions to work with arrays.

- Array_functions.php

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Array_functions</title>
</head>
<body>
    <?php
    $array1 = array(41,34,2,35,12,65,8,9,45);
    ?>

    Count: <?= count($array1) ?><br />
    Max Value: <?= max($array1) ?><br />
    Min Value: <?= min($array1) ?><br />
    
    <?php
    print_r($array1);
    ?>

    <br>

    Sort:
    <?php
    sort($array1);
    print_r($array1);
    ?>
    <br>

    Reverse sort:
    <?php
    rsort($array1);
    print_r($array1);
    ?>
    <br>

    Explode:
    <?php
    $str3 = "This is Demo";
    $array3 = explode(" ",$str3);
    print_r($array3);
    ?>
    <br>

    Implode(space):
    <?php
    $str1 = implode(" ",$array1);
    echo $str1;
    ?>
    <br>
      Implode(comma):
    <?php
    $str1 = implode(",",$array1);
    echo $str1;
    ?>
    <br>

    In Array (check if 45 is exists):
    <?php
    $int1 = in_array(45,$array1);
    echo $int1 ? "Found " : "Not Found";
    echo "<br />";
    echo gettype($int1); //boolean    
    ?>
</body>
</html>
```
---
## 📋 Key Notes

| Function     | Description                              |
|--------------|------------------------------------------|
| `count()`    | Count number of elements in an array     |
| `max()`      | Find maximum value                       |
| `min()`      | Find minimum value                       |
| `sort()`     | Sort an array (ascending)                |
| `rsort()`    | Sort an array (descending)               |
| `explode()`  | Split a string into an array             |
| `implode()`  | Join array elements into a string        |
| `in_array()` | Check if a value exists in an array      |

---

## ✅ Best Practices

- Always validate array keys before accessing them to avoid **warnings**.
- Use **associative arrays** when working with structured data (like user records).
- Prefer using **array functions** for better performance and cleaner code.

