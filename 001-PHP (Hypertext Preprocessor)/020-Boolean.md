# Booleans

## Booleans in PHP

Booleans represent two possible values: `true` or `false`.  
These are used in conditionals, comparisons, and control logic.

---

## ✅ Boolean Basics

**File:** `booleans.php`

```php
<html>
<head>
    <meta charset="utf-8">
    <title>Booleans</title>
</head>
<body>

<?php
$bool1 = true;
$bool2 = false;
$str1  = "true";
$bool3 = 0;
?>

<!-- Output boolean values -->
$bool1: <?php echo $bool1; ?> <br />
$bool2: <?php echo $bool2; ?> <br />
$str1: <?php echo $str1; ?> <br />
$bool3: <?php echo $bool3; ?> <br />

<!-- Type checks -->
$bool1 is boolean: <?php echo is_bool($bool1); ?> <br />
$bool1 check type: <?php echo gettype($bool1); ?> <br />

$bool2 is boolean: <?php echo is_bool($bool2); ?> <br />
$bool2 check type: <?php echo gettype($bool2); ?> <br />

$str1 is boolean: <?php echo is_bool($str1); ?> <br />
$str1 check type: <?php echo gettype($str1); ?> <br />

$bool3 is boolean: <?php echo is_bool($bool3); ?> <br />
$bool3 check type: <?php echo gettype($bool3); ?> <br />

</body>
</html>
```
---

## 🧠 Important Concepts

| Variable | Value  | Is Boolean? | Type Detected |
|--------|--------|-------------|---------------|
| `$bool1` | `true`  | ✅ true  | boolean |
| `$bool2` | `false` | ✅ true  | boolean |
| `$str1`  | `"true"` | ❌ false | string |
| `$bool3` | `0`     | ❌ false | integer |

---

## 🔎 PHP Boolean Evaluation Rules

| Value | Boolean Result |
|------|----------------|
| `0`, `0.0` | false |
| `"0"` (string zero) | false |
| `""` (empty string) | false |
| `array()` | false |
| `null` | false |
| Anything else | true |

---

## 🛠️ Common Functions

| Function | Description |
|---------|-------------|
| `is_bool($var)` | Checks if a variable is a boolean |
| `gettype($var)` | Returns the type of a variable |

---

## ✅ Usage Example

```php
$user_is_logged_in = true;

if ($user_is_logged_in) {
    echo "Welcome back!";
} else {
    echo "Please log in.";
}
```

---

### 🔁 Summary

Booleans are the simplest data type in PHP but are powerful tools for flow control, conditionals, and validation logic.

