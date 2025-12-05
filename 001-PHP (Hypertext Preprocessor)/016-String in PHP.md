# **What is a String in PHP?**

A **string** is a sequence of characters — like letters, numbers, and symbols — **enclosed in quotes**.

In PHP, a string can be inside:

* **Double quotes (`" "`)** — allows variable parsing and escape sequences.
* **Single quotes (`' '`)** — takes content literally.

---

## **Examples**

```php
<?php
// Using double quotes
$greeting = "Hello, World!";

// Using single quotes
$greeting2 = 'Hello, World!';

// Display a string
echo $greeting;

echo "<br>";

echo $greeting2;

?>  
```

---

## **Important Points**

* A **string** is one of the most common data types in PHP.
* You can **combine (concatenate)** strings using the `.` operator.
* Double-quoted strings can **evaluate variables** inside them; single-quoted strings **do not**.

### Example:

```php
$name = "Armour Infosec";

echo "Welcome to $name!";  // Output: Welcome to Armour Infosec!
echo 'Welcome to $name!';  // Output: Welcome to $name!
```

---

## **String Functions**

PHP gives you **many built-in functions** to work with strings:

| **Function**    | **What it Does**                  |
| --------------- | --------------------------------- |
| `strlen()`      | Gets the length of a string       |
| `strtoupper()`  | Converts to uppercase             |
| `strtolower()`  | Converts to lowercase             |
| `str_replace()` | Replaces text inside a string     |
| `strpos()`      | Finds position of a substring     |
| `str_repeat()`  | Repeats the string multiple times |

---

## **Summary**

* A **string** = text data inside quotes (`" "` or `' '`).
* Strings are used to **store and display** words, sentences, or any combination of characters.
* PHP provides **many functions** to manipulate and modify strings easily.

