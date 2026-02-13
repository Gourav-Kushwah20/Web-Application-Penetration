# 📘 Numbers in PHP

## 📚 Integers and Floats in PHP

PHP supports different types of numbers, mainly **Integers** and **Floats** (also called **Doubles** or **Floating-point numbers**).

---

## ➡️ Integers

- **Definition:** Whole numbers without a decimal point.

- **Examples:**  
  `-5`, `0`, `42`, `1000`

- **Size:**  
  - Usually **32-bit** or **64-bit** depending on the system.


## 🧮 Common Integer Operations

- Addition `+`  
- Subtraction `-`  
- Multiplication `*`  
- Division `/`  
- Modulus `%` (remainder)  

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
## ➡️ Floats

- **Definition:** Numbers with a decimal point or in exponential form.

- **Examples:**  
  `3.14`, `-0.99`, `2e3` (which is `2000`)

- **Precision:**  
  - Limited due to how computers store floating-point numbers (IEEE 754 standard).


## 🔢 Common Float Functions

- `round()` – Round a float  
- `ceil()` – Round up to the nearest integer  
- `floor()` – Round down to the nearest integer  
- `abs()` – Absolute value  
- `pow()` – Exponents  
- `sqrt()` – Square root  

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
