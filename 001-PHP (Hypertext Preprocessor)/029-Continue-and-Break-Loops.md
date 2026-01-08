# 🔁 Continue-and-Break-Loops

## 🔄 PHP `continue` and `break` in Loops

In PHP, **`continue`** and **`break`** are used to **control the flow of execution inside loops** such as  
`for`, `while`, and `foreach`.

---

## ✅ Syntax & Behavior

### 🔹 `continue`
- **Skips the current iteration**
- Control jumps directly to the **next loop iteration**

### 🔹 `break`
- **Exits the loop immediately**
- Skips **all remaining iterations**

---

## 📌 Summary Table

| Keyword   | What it Does |
|----------|--------------|
| `continue` | Skips current iteration, continues loop |
| `break`    | Terminates the loop completely |

---
## 🔁 Continue and Break Loops in PHP

## 📄 File: `continue-break-loops.php`

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Continue and Break Loops</title>
</head>
<body>

<?php
// 🔹 Basic loop
for ($i = 0; $i <= 10; $i++) {
    echo $i . ",";
}

echo "<br />";

// 🔹 Using continue to skip value 5
for ($i = 0; $i <= 10; $i++) {
    if ($i == 5) {
        continue; // Skip printing 5
    }
    echo $i . ",";
}

echo "<br />";

// 🔹 Using break to stop loop at 5
for ($i = 0; $i <= 10; $i++) {
    if ($i == 5) {
        break; // Stop the loop completely
    }
    echo $i . ",";
}
?>

</body>
</html>
````

---

## 🔍 Output

```text
0,1,2,3,4,5,6,7,8,9,10,
0,1,2,3,4,6,7,8,9,10,
0,1,2,3,4,
```

---
