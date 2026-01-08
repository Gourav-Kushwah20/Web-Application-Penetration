# For-Loops

## 🔁 PHP `for` Loops

The **`for` loop** is a common looping structure in PHP.  
It is ideal when the **number of iterations is known ahead of time**.

---

## 🛠️ Syntax

```php
for (initial; condition; increment) {
    // code to be executed
}
```

### 📌 Loop Parts Explained

* **initial** → Sets the starting value of the loop counter
* **condition** → Evaluated before each iteration
* **increment** → Updates the counter after each iteration

---

## 📄 Basic Example

```php
<?php
for ($i = 0; $i <= 10; $i++) {
    echo $i . ",";
}
?>
```

---

## 🔍 Output

```text
0,1,2,3,4,5,6,7,8,9,10,
```

---

## 📄 File: `forloops.php`

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>For Loops</title>
</head>
<body>

<?php
// Basic for loop
for ($i = 0; $i <= 10; $i++) {
    echo $i . ",";
}

echo "<br />";
echo $i;
echo "<br />";

// For loop with even/odd check
for ($count = 0; $count <= 20; $count++) {
    if ($count % 2 == 0) {
        echo "{$count} is Even.<br />";
    } else {
        echo "{$count} is odd.<br />";
    }
}
?>

</body>
</html>
```

---

## 🔍 Output (Partial)

```text
0,1,2,3,4,5,6,7,8,9,10,
11
0 is Even.
1 is odd.
2 is Even.
3 is odd.
...
20 is Even.
```

---

# Foreach-Loops

## 🔁 PHP `foreach` Loops

The **`foreach` loop** is specifically designed for **iterating through arrays**.  
It simplifies working with both **indexed arrays** and **associative arrays**.

---

## 🛠️ Syntax

### 🔹 Iterate over values

```php
foreach ($array as $value) {
    // code to use $value
}
```

---

### 🔹 Iterate over keys and values

```php
foreach ($array as $key => $value) {
    // code to use $key and $value
}
```

---
## 📄 File: `foreachloops.php`

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Foreach Loops</title>
</head>
<body>

<?php
$array1 = array(20, 25, 78, 45, 96, 21);

// Looping through values only
foreach ($array1 as $num) {
    echo $num . ",";
}

echo "<br />";

// Looping through key–value pairs
foreach ($array1 as $key => $value) {
    echo $key . " : " . $value . "<br />";
}

$users = array(
    "id" => 2,
    "Name" => "Rahul",
    "Email" => "rahul@armour.com",
    "Password" => "@rmour123"
);

// Associative array key–value loop
foreach ($users as $key => $value) {
    echo $key . " : " . $value . "<br />";
}

echo $users['id'] . "<br />";

// Conditional loop based on value
foreach ($users as $key => $value) {
    if ($users['id'] == 1) {
        echo $key . " : " . $value . "<br />";
    }
}
?>
</body>
</html>
```

### Expected Output :

```text
 20,25,78,45,96,21,
0 : 20
1 : 25
2 : 78
3 : 45
4 : 96
5 : 21
id : 2
Name : Rahul
Email : rahul@armour.com
Password : @rmour123
2
```