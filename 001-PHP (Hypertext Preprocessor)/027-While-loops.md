# While-Loops

## 🔁 PHP While Loops

A **`while` loop** executes a block of code **as long as a specified condition is true**.  
It is ideal when the **number of iterations is not known in advance**.

---

## 🛠️ Syntax

```php
while (condition) {
    // code to be executed
}
```

### 📌 How it works

* The **condition is evaluated before each iteration**
* If the condition is **true**, the loop runs
* If the condition becomes **false**, the loop stops

---

## 📄 Example: Basic `while` Loop

```php
<?php
$count = 0;

while ($count <= 10) {
    echo $count . ",";
    $count++;
}
?>
```

---

## 🔍 Output

```text
0,1,2,3,4,5,6,7,8,9,10,
```
---

## 📄 File: `whileloops.php`

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>While Loops</title>
</head>
<body>

<?php
$count = 0;

while ($count <= 10) {
    echo $count . ",";
    $count++;
}

echo "<br />";
echo $count;
?>

</body>
</html>
```

---

## 🔍 Output

```text
0,1,2,3,4,5,6,7,8,9,10,
11
```

---

## 📄 File: `whileloops2.php` (With Conditional)

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>While Loops</title>
</head>
<body>

<?php
$count = 0;

while ($count <= 10) {
    if ($count == 5) {
        echo "FIVE,";
    } else {
        echo $count . ",";
    }
    $count++;
}

echo "<br />";
echo $count;
?>

</body>
</html>
````

---

## 🔍 Output

```text
0,1,2,3,4,FIVE,6,7,8,9,10,
11
```

---

