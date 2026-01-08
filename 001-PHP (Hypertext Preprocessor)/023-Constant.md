# Constants

## 🔒 PHP Constants

## ❓ What is a Constant in PHP?

A **constant** is a name for a simple, immutable value.  
Unlike variables, once a constant is defined, it **cannot be changed or undefined**.

Constants are useful for **fixed configuration values** or **settings** used throughout a script.

---

## ✅ Key Characteristics

- Declared using `define()` or `const`
- **No `$` prefix** (unlike variables)
- **Cannot be changed or redefined**
- **Global scope by default**
- Conventionally written in **UPPERCASE**

---

## 🧩 Syntax

### Using `define()`

```php
define("CONSTANT_NAME", value);
````

### Using `const` (PHP 5.3+)

```php
const CONSTANT_NAME = value;
```

---

## 📄 Example with `define()`

```php
<?php
define("SITE_NAME", "MyWebsite");
echo SITE_NAME; // Output: MyWebsite
?>
```

---

## ⚠️ Attempt to Redefine a Constant

```php
define("SITE_NAME", "NewName");
// Warning: Constant SITE_NAME already defined
````

> Once a constant is defined, it **cannot be redefined or changed**.

---

## 📄 Example with `const`

```php
class Config {
    const DB_NAME = "my_database";
}

echo Config::DB_NAME; // Output: my_database
```

📝 Notes:

* `const` can be used **inside classes**
* Access class constants using the `ClassName::CONSTANT_NAME` syntax

---

## 🔍 Accessing Constants

### 🔹 Direct Access

```php
echo SITE_NAME;
```

### 🔹 Dynamic Access

```php
echo constant("SITE_NAME");
```

📝 Notes:

* `constant()` is useful when the constant name is stored in a variable
* Direct access is simpler and preferred when the name is known

---
## 🚫 Constants vs Variables

| Feature | Constant | Variable |
|-------|----------|----------|
| Starts with `$` | ❌ No | ✅ Yes |
| Can be changed | ❌ No | ✅ Yes |
| Global Scope | ✅ Yes | ❌ Depends |
| Declared using | `define()` / `const` | `$variable = value;` |

---

## 📄 File: `constants.php`

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Constants</title>
</head>
<body>

<?php
define("var1", 1080);        // Define a constant named var1
echo constant("var1");      // Output: 1080
echo "<br />";

define("var1", 720);        // Attempt to redefine var1 (will generate a warning)
echo var1;                  // Output: 1080
?>

</body>
</html>
```
