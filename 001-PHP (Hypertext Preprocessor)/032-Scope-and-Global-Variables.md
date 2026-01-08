# Scope-and-Global-Variables

## 🧠 PHP Scope and Global Variables

PHP variables have different **scopes** that determine where they can be accessed within a script.  
Understanding **local**, **global**, and **function scopes** is essential for managing variables effectively.

---

## 📄 File: `functions_scope.php`

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Scope and Global Variables</title>
</head>
<body>

<?php
$var1 = "Outside";

function fun1() {
    // Use global keyword to access global $var1
    global $var1;
    $var1 = "Inside";
}

echo $var1 . "<br />"; // Output: Outside

fun1();

echo $var1 . "<br />"; // Output: Inside


$var2 = "Outside";

function fun2() {
    // This $var2 is local to the function
    $var2 = "Inside";
    return $var2;
}

echo $var2 . "<br />"; // Outputs: Outside

fun2(); // This changes nothing globally

echo $var2 . "<br />"; // Still outputs: Outside

$var3 = fun2(); // Assign returned value from fun2

echo $var3; // Outputs: Inside
?>

</body>
</html>
```

---

## 🔍 Output

```text
Outside
Inside
Outside
Outside
Inside 
```

---

## 🧠 Explanation

### 1️⃣ Global Scope

```php
$var1 = "Outside";
```

* Declared **outside** any function
* Accessible globally **only if explicitly referenced**

---

### 2️⃣ Using `global` Keyword

```php
global $var1;
```

* Allows a function to **access and modify** a global variable
* Changes persist **outside the function**

---

### 3️⃣ Local Scope

```php
$var2 = "Inside";
```

* Declared **inside a function**
* Exists **only within that function**
* Does NOT affect variables with the same name outside

---

## 📌 Scope Summary Table

| Scope Type | Where Defined    | Accessibility                        |
| ---------- | ---------------- | ------------------------------------ |
| Global     | Outside function | Accessible everywhere using `global` |
| Local      | Inside function  | Only inside that function            |
| Function   | Parameters       | Only inside the function             |

---
