# Null-and-Empty

## NULL and Empty in PHP

This lesson explains the difference between `null`, `empty()`, `isset()`  
and how `unset()` affects variables.

---

## 📄 File: `null-empty.php`

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>NULL and Empty</title>
</head>
<body>

<?php
$var1 = 4;
$var2 = "";
$var3 = 0;
$var4; // undefined but declared
?>

<!-- isset() checks if a variable is set and not null -->
<h3>isset()</h3>
$var1 is set: <?php echo isset($var1); ?> <br />
$var2 is set: <?php echo isset($var2); ?> <br />
$var3 is set: <?php echo isset($var3); ?> <br />
$var4 is set: <?php echo isset($var4); ?> <br />

<!-- is_null() checks if the value is explicitly null -->
<h3>is_null()</h3>
$var1 is null: <?php echo is_null($var1); ?> <br />
$var2 is null: <?php echo is_null($var2); ?> <br />
$var3 is null: <?php echo is_null($var3); ?> <br />
$var4 is null: <?php echo is_null($var4); ?> <br />

<!-- empty() checks if a variable is considered empty -->
<h3>empty()</h3>
$var1 is empty: <?php echo empty($var1); ?> <br />
$var2 is empty: <?php echo empty($var2); ?> <br />
$var3 is empty: <?php echo empty($var3); ?> <br />
$var4 is empty: <?php echo empty($var4); ?> <br />

<!-- unset() removes a variable -->
<h3>unset()</h3>
<?php unset($var1); ?>

$var1 is set: <?php echo isset($var1); ?> <br />
<?php echo $var1; ?>
$var1 is null: <?php echo is_null($var1); ?> <br />
$var1 is empty: <?php echo empty($var1); ?> <br />

</body>
</html>
```
---

## 🧠 Summary Table

| Variable | Value | isset() | is_null() | empty() |
|--------|-------|---------|-----------|---------|
| `$var1` | `4` | ✅ true | ❌ false | ❌ false |
| `$var2` | `""` | ✅ true | ❌ false | ✅ true |
| `$var3` | `0` | ✅ true | ❌ false | ✅ true |
| `$var4` | undefined | ❌ false | ✅ true | ✅ true |
| `$var1` (after `unset()`) | unset | ❌ false | ✅ true | ✅ true |

---

## 🔍 Function Descriptions

| Function | Description |
|---------|-------------|
| `isset($var)` | Returns `true` if variable exists and is **not null** |
| `is_null($var)` | Returns `true` if variable **is null** |
| `empty($var)` | Returns `true` if variable is empty: `""`, `0`, `"0"`, `null`, `false`, or empty array |
| `unset($var)` | Destroys the variable, making it as if it was never set |

---

## ✅ Best Practices

- Use `isset()` to **check if a variable exists**
- Use `is_null()` to **check for null explicitly**
- Use `empty()` to **validate input or empty state**
- Use `unset()` to **clear sensitive data or clean up memory**
