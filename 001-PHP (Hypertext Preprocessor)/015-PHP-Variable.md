# **PHP Variables**

## **What is a Variable?**

A **variable** is a container to store data, like numbers, strings, arrays, etc.

In PHP, variables are **dynamic** — you don't have to declare their type beforehand.

---

## **Rules for PHP Variable Names**

* Must start with a **$** symbol.
* Followed by a **letter (A–Z, a–z)** or **underscore (`_`)**.
* Can contain **letters, numbers, and underscores** (no spaces or special characters like `!`, `%`, etc.).
* **No spaces allowed.**
* **Case-sensitive** (`$value` and `$Value` are different).

---

## **Examples of Valid Variable Names**

```php
$item
$Item
$myVariable
$this_variable
$product1
$_book
$__bookPage
```

Refer to: **PHP Reserved Keywords** https://www.php.net/manual/en/reserved.keywords.php


## **Examples**

```php
<?php
$age = 25;
$name = "Armour Infosec";
$price = 10.99;
$_product = "Book";
$Book_Page = 250;
?>
```

---

## **Good vs Bad Variable Names**

| **Valid**     | **Invalid**                           |
| ------------- | ------------------------------------- |
| `$username`   | `$ user name` (spaces not allowed)    |
| `$user1`      | `$1user` (cannot start with a number) |
| `$_user_name` | `$user-name` (dash `-` not allowed)   |

---

## **Assigning and Reassigning Variables**

```php
<?php
$item = "Laptop";
echo $item;   // Output: Laptop

$item = "Tablet";
echo $item;   // Output: Tablet
?>
```

* Variables can be **reassigned** at any time.

---

## **Displaying Variables**

Use **echo** or **print**:

```php
<?php
$name = "Armour Infosec";
echo $name;
print $name;
?>
```

Both will output: **Armour Infosec**

---

## **Important**

* Variable names should be **meaningful** (`$age`, `$totalPrice`), not random (`$a`, `$b`), for better code readability.
* Reserved PHP keywords (like `if`, `echo`, `class`) **cannot** be used as variable names.

Refer to: **[See Reserved Keywords](https://www.php.net/manual/en/reserved.keywords.php)**

---

## **`Variable.php` Code Example**

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Variables</title>
</head>
<body>

<?php
$var1 = 10;
echo $var1;

echo '<br>';

$my_variable = "Armour Infosec";
echo $my_variable;

echo '<br>';

$my_Variable = "Armour Infosec 2";
echo $my_Variable;

echo '<br>';

$my_Variable = "AI"; // Changing the value of the same variable
echo $my_Variable;
?>

</body>
</html>
```

---

## **Explanation**

* `$var1 = 10;` → Stores an integer value **10**.
* `$my_variable = "Armour Infosec";` → Stores a string.
* Variables are **case-sensitive**: `$my_variable` and `$my_Variable` are different.
* A variable's value can be **overwritten** later (`$my_Variable = "AI";`).

---

## **Tip**

In PHP, variable names should be meaningful and consistent (e.g., **camelCase** or **snake_case** for better readability).

