# 📚 Arrays in PHP

PHP arrays are powerful data structures to store multiple values in a single variable.

---

## ➡️ Indexed Arrays

An **indexed array** is an ordered collection where keys are integers starting from **0**.

---

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

### Example: `associative_array.php`

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