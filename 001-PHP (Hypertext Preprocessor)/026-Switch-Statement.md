# Switch-Statements

## 🔁 PHP Switch Statements

The **`switch` statement** is used to perform different actions based on different conditions.  
It is an alternative to using multiple `if–else` statements when there are **many conditions** to check.

---

## 🧩 Syntax of `switch`

```php
switch (value) {
    case test_value1:
        // Statement
        break;

    case test_value2:
        // Statement
        break;

    default:
        // Statement if no match found
        break;
}
````

---

## 🧠 How `switch` Works

* **`switch`**
  The expression is evaluated **once**, and its result is compared with each `case`.

* **`case`**
  If the value matches the case, the corresponding statement(s) are executed.

* **`break`**
  Stops execution of the switch block once a match is found
  (prevents *fall-through* to the next case).

* **`default`**
  Executes when **no case matches** the value.

---

## 📄 File: `switch.php` (Example)

```php
<?php
$day = "Monday";

switch ($day) {
    case "Monday":
        echo "Start of the work week";
        break;

    case "Friday":
        echo "Almost weekend!";
        break;

    case "Sunday":
        echo "Holiday!";
        break;

    default:
        echo "Just another day";
}
?>
```

---

## ✅ Best Practices

* Always use `break;` unless fall-through is **intentional**
* Prefer `switch` when:

  * One variable is compared
  * Against many fixed values
* For **strict comparisons**, consider `match` (PHP 8+)

---
## 📄 File: `switch.php`

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Switch</title>
</head>
<body>

<?php
$a = 40;

switch ($a) {
    case 0:
        echo "A Equals 0";
        break;

    case 10:
        echo "A Equals 10";
        break;

    case 20:
        echo "A Equals 20";
        break;

    default:
        echo "A is not 0, 10, or 20";
        break;
}
?>

</body>
</html>
````

---

## 🔍 Output

```text
A is not 0, 10, or 20
```

---

## 🧠 Explanation

* `$a = 40`
* No `case` (`0`, `10`, `20`) matches `40`
* Execution falls to the `default` block
* `break;` prevents fall-through after each case

---

## ✅ Key Notes

* `switch` compares the same variable against multiple values
* `break` is required to stop execution after a match
* `default` runs when no case matches

