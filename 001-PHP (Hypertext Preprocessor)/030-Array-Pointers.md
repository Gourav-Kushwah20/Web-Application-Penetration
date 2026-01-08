# 🧭 Array-Pointers

## 🧭 PHP Array Pointers

PHP **array pointer functions** allow you to **manipulate and traverse arrays manually** using an internal pointer.  
Each array has an internal pointer that tracks the **current element**.

---

## 📄 File: `pointers.php`

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Array Pointers</title>
</head>
<body>

<?php
$array1 = array(45, 41, 52, 98, 78, 50, 43, 11, 56);

// Print full array
print_r($array1);
echo "<br />";

// Current element (default: first)
echo current($array1) . "<br />";   // 45

// Move pointer forward
next($array1);
echo current($array1) . "<br />";   // 41

next($array1); // 52
next($array1); // 98
next($array1); // 78
echo current($array1) . "<br />";   // 78

// Move pointer backward
prev($array1); // 98
prev($array1); // 52
echo current($array1) . "<br />";   // 52

// Reset pointer to first element
reset($array1);
echo current($array1) . "<br />";   // 45

next($array1);
echo current($array1) . "<br />";   // 41

end($array1);
echo current($array1) . "<br />";   // 56
?>

</body>
</html>
```

---

## 🔍 Output (Example)

```text
Array ( [0] => 45 [1] => 41 [2] => 52 [3] => 98 [4] => 78 [5] => 50 [6] => 43 [7] => 11 [8] => 56 )
45
41
78
52
45
```

---

## 🧠 Explanation of Pointer Functions

| Function    | Description                                         |
| ----------- | --------------------------------------------------- |
| `current()` | Returns the element at the current pointer position |
| `next()`    | Moves pointer **forward**                           |
| `prev()`    | Moves pointer **backward**                          |
| `reset()`   | Resets pointer to the **first element**             |
| `end()`     | Moves pointer to the **last element**               |
| `key()`     | Returns the key of the current element              |

---

# 🧭 PHP Array Pointers with `while` Loop

## 📄 File: `pointers2.php`

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Pointers</title>
</head>
<body>

<?php
$array1 = array(1, 2, 3, 4, 5, 5, 6, 7, 8, 9);

while ($var1 = current($array1)) {
    echo $var1 . ", ";
    next($array1);
}
?>

</body>
</html>
```

---

## 🔍 Output

```text
1, 2, 3, 4, 5, 5, 6, 7, 8, 9,
```

