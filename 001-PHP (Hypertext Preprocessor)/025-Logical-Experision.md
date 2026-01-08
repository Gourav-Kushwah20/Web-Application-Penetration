# Logical-Expressions

## 🧠 PHP Logical Expressions

PHP logical expressions are used to **evaluate conditions** and **control program flow** using  
`if`, `else`, `elseif`, and logical operators like `&&`, `||`, and `!`.

---

## 📄 File: `logical.php` — Basic `if`, `else`, and `elseif`

```php
<html>
<head>
    <meta charset="utf-8">
    <title>logical Experision</title>
</head>
<body>
<?php
$a = 0;
$b = 10;

if ($a > $b) {
    echo "A is Larger than B";
}

if ($a > $b) {
    echo "A is Larger than B";
} else {
    echo "A is not Larger than B";
}

if ($a > $b) {
    echo "A is Larger than B";
} elseif ($a == $b) {
    echo "A Equals B";
} else {
    echo "A is not Larger than B";
}
?>
</html>
```

---

## 🔍 Output

```text
A is not Larger than B
A is not Larger than B
```

---

## 📄 File: `logical-1.php`

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Logical Expressions - 1</title>
</head>
<body>

<?php
$a = "10";

// Check if $a is set
if (isset($a)) {
    echo $a;
}

echo "<br />";

// Check if $a is not set
if (!isset($a)) {
    $a = 100;
    echo $a;
}

echo "<br />";

// Check if $a is an integer
if (is_int($a)) {
    echo gettype($a);
}
?>

</body>
</html>
```

### Output :

```
10
```
---

## 📄 File: `logical-2.php`

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Logical Expressions - 2</title>
</head>
<body>

<?php
$a = 10;
$b = 25;
$c = 10;
$d = 15;

// AND condition
if (($a > $b) && ($c > $d)) {
    echo "A is Larger than B AND C is Larger than D";
}

echo "<br />";

// OR condition
if (($a > $b) || ($c > $d)) {
    echo "A is Larger than B OR C is Larger than D";
}

echo "<br />";

// OR condition with else
if (($a > $b) || ($c > $d)) {
    echo "A is Larger than B OR C is Larger than D";
} else {
    echo "Neither A is larger than B NOR C is larger than D";
}
?>

</body>
</html>
```