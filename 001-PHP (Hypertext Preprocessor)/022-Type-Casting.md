# Type-Casting

## 🧪 PHP Type Casting Example

**Type casting in PHP** refers to the process of converting a variable from one data type to another.  
Since PHP is a *loosely typed language*, it automatically converts (or casts) values between types when necessary.  
However, you can also perform **explicit (manual) type casting**.

---

## 🔹 Types of Type Casting in PHP

1. **Implicit Type Casting (Automatic)**
2. **Explicit Type Casting (Manual)**

---

## 1️⃣ Implicit Type Casting (Automatic Casting)

PHP automatically converts one data type to another when an operation requires a different type.  
For example, if you add a string and a number, PHP will automatically convert the string into a number.

### Example

```php
<?php
$var1 = "10";      // string
$var2 = $var1 + 8; // implicit casting of "10" to integer

echo $var2;        // Output: 18
?>
````

📌 In this case, the string `"10"` is automatically converted into an integer before performing the addition.

---

## 2️⃣ Explicit Type Casting (Manual Casting)

You can manually cast a variable to another type using **casting operators** or the `settype()` function.

---

### 🔸 Using Type Casting Operators

You can explicitly cast a variable using operators like:

* `(int)`
* `(float)`
* `(string)`
* `(bool)`
* `(array)`
* `(object)`

#### Example

```php
<?php
$var = "5";

$intVar = (int)$var;     // Cast string to integer
$floatVar = (float)$var; // Cast string to float

echo $intVar;            // Output: 5
echo gettype($intVar);   // Output: integer
?>
```

---

### 🔸 Using `settype()`

The `settype()` function changes the type of an existing variable.

```php
<?php
$var = "10";

settype($var, "integer");
echo gettype($var); // Output: integer
?>
```

---

## 🔧 PHP Type Casting Functions

Here are some common type casting methods in PHP:

- **`(int)` or `(integer)`**: Casts a value to an integer  
- **`(float)`**, **`(double)`**, or **`(real)`**: Casts a value to a float  
- **`(string)`**: Casts a value to a string  
- **`(bool)`**: Casts a value to a boolean  
- **`(array)`**: Casts a value to an array  
- **`settype()`**: Changes the type of a variable *in place*

---

## 🧪 Example of All Casting Methods

```php
<?php
$var1 = "10.5";   // string

// Cast string to integer
$var2 = (int)$var1;
echo $var2 . "<br />";   // Output: 10 (integer)

// Cast string to float
$var3 = (float)$var1;
echo $var3 . "<br />";   // Output: 10.5 (float)

// Cast string to boolean
$var4 = (bool)$var1;
echo $var4 . "<br />";   // Output: 1 (true)

// Cast string to array
$var5 = (array)$var1;
print_r($var5);
echo "<br />";           // Output: Array ( [0] => 10.5 )

// Using settype()
settype($var1, "integer");
echo $var1 . "<br />";   // Output: 10 (integer)
?>
```
---

## ⏰ When to Use Type Casting?

- **Implicit Casting**  
  Happens automatically in most PHP operations, such as adding a string and a number.

- **Explicit Casting**  
  Use this when you want to **control the data type conversion explicitly**, especially when working with **user input** or **database values**.

---

## 📌 Common Use Cases

- Converting a string to an **integer** or **float** when performing mathematical operations  
- Ensuring **user input** is treated as a specific data type  
- Handling **database results** that need conversion to proper PHP data types  

---

## ✅ Conclusion

- **PHP Type Casting** is a powerful tool for converting between data types, either **automatically** or **manually**.
- Use **implicit casting** for most situations where PHP handles conversion for you.
- Use **explicit casting** when you need **precision, safety, and control** over data types.

---
## 📄 File: `typecasting.php`

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Type Casting</title>
</head>
<body>

<?php

$var1 = "10";        // string
$var2 = $var1 + 8;  // "10" implicitly cast to integer

echo $var2 . "<br />";          // Output: 18
echo gettype($var1) . "<br />"; // Output: string
echo gettype($var2) . "<br />"; // Output: integer

settype($var1, "integer");      // Explicit cast to integer
echo gettype($var1) . "<br />"; // Output: integer

$var3 = (int)"5";               // Cast string to int using (int)
echo $var3 . "<br />";          // Output: 5
echo gettype($var3) . "<br />"; // Output: integer

?>

</body>
</html>
````

---

### 🧠 Explanation (Quick)

* `"10" + 8` → PHP **implicitly casts** the string to an integer
* `settype()` **modifies the variable itself**
* `(int)` casting creates a **new integer value**
* `gettype()` is used to verify the data type

