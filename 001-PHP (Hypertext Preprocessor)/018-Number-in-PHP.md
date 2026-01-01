# 📘 Numbers in PHP

This guide covers basic operations with **integers** and **floats** in PHP, including arithmetic operations, assignment operators, and random number generation.

---

## ➡️ Integers Example

**integers.php**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Integers Example</title>
</head>
<body>

<?php
$var1 = 4;
$var2 = 8;
?>

<h2>Basic Math</h2>
<p><?= 1 + 2 ?></p>
<p><?= ((1 + 2 + $var1) * $var2) / 2 - 4 ?></p>

<h2>Assignment Operators</h2>
<p>+= : <?= $var2 += 4 ?></p>
<p>-= : <?= $var2 -= 4 ?></p>
<p>*= : <?= $var2 *= 4 ?></p>
<p>/= : <?= $var2 /= 4 ?></p>

<h2>Increment & Decrement</h2>
<p>Increment: <?= ++$var1 ?></p>
<p>Decrement: <?= --$var1 ?></p>

</body>
</html>
```
---

## ➡️ Floats Example

**floats.php**

```php
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Floats Example</title>
</head>
<body>

<?php
$var1 = 3.15;
?>

<h2>Division and Float Value</h2>
<p>4 ÷ 3 = <?= 4 / 3 ?></p>
<p>Value of var1: <?= $var1 ?></p>

<?php $myFloat = 3.14; ?>

<h2>Floating Point Functions</h2>
<p>Floating Point Value: <?= $myFloat ?></p>
<p>Round (1 decimal place): <?= round($myFloat, 1) ?></p>
<p>Ceiling (next integer): <?= ceil($myFloat) ?></p>
<p>Floor (previous integer): <?= floor($myFloat) ?></p>
<p>Absolute Value of -300: <?= abs(-300) ?></p>
<p>Exponent (2⁸): <?= pow(2, 8) ?></p>
<p>Square Root (√100): <?= sqrt(100) ?></p>
<p>Modulo (20 % 7): <?= fmod(20, 7) ?></p>

<h2>Random Numbers</h2>
<p>Random (any): <?= rand() ?></p>
<p>Random (1000–9999): <?= rand(1000, 9999) ?></p>

</body>
</html>
