# **PHP String Functions**
## **What are String Functions?**

**String functions** in PHP are built-in functions that allow you to perform operations and manipulations on strings.
These functions help you easily modify, search, and analyze strings.

---

## **Common PHP String Functions**

| **Function**    | **Description**                                                               | **Example**                                                |
| --------------- | ----------------------------------------------------------------------------- | ---------------------------------------------------------- |
| `strlen()`      | Returns the length of the string (number of characters).                      | `strlen("Armour")` → `6`                                   |
| `strtoupper()`  | Converts the string to uppercase.                                             | `strtoupper("hello")` → `HELLO`                            |
| `strtolower()`  | Converts the string to lowercase.                                             | `strtolower("HELLO")` → `hello`                            |
| `ucfirst()`     | Converts the first character of the string to uppercase.                      | `ucfirst("hello")` → `Hello`                               |
| `ucwords()`     | Converts the first letter of each word to uppercase.                          | `ucwords("hello world")` → `Hello World`                   |
| `str_replace()` | Replaces all occurrences of a substring with a new substring.                 | `str_replace("world","PHP","Hello world!")` → `Hello PHP!` |
| `strpos()`      | Finds the position of the first occurrence of a substring.                    | `strpos("hello world", "world")` → `6`                     |
| `substr()`      | Returns part of a string starting from a specific index.                      | `substr("Hello", 1, 3)` → `ell`                            |
| `trim()`        | Removes white spaces or other predefined characters.                          | `trim(" Hello ")` → `Hello`                                |
| `str_repeat()`  | Repeats a string a specified number of times.                                 | `str_repeat("PHP", 3)` → `PHPPHPPHP`                       |
| `strrev()`      | Reverses the string.                                                          | `strrev("Hello")` → `olleH`                                |
| `strstr()`      | Finds the first occurrence of a substring and returns the rest of the string. | `strstr("hello world", "world")` → `world`                 |
| `strchr()`      | Same as `strstr()`, but finds the first occurrence of a character.            | `strchr("hello world", "w")` → `world`                     |


---

## **Examples of PHP String Functions**


## **Example 1: `strlen()` — Find the Length of a String**

```php
<?php
$text = "Armour Infosec";
echo strlen($text);  // Output: 15 (length of the string)
?>
```

---

## **Example 2: `strtoupper()` — Convert to Uppercase**

```php
<?php
$text = "hello world";
echo strtoupper($text);  // Output: "HELLO WORLD"
?>
```

---

## **3. `strtolower()` – Convert to Lowercase**

```php
<?php
$text = "HELLO WORLD";
echo "Lowercase: " . strtolower($text);  
// Output: "hello world"
?>
```

---

## **4. `ucfirst()` – Capitalize the First Letter**

```php
<?php
$text = "hello world";
echo "First letter capitalized: " . ucfirst($text);  
// Output: "Hello world"
?>
```

---

## **5. `ucwords()` – Capitalize the First Letter of Each Word**

```php
<?php
$text = "hello world";
echo "Words capitalized: " . ucwords($text);  
// Output: "Hello World"
?>
```

---

## **6. `str_replace()` – Replace Text Inside a String**

```php
<?php
$text = "I love PHP!";
echo "Replaced text: " . str_replace("PHP", "Programming", $text);  
// Output: "I love Programming!"
?>
```

---

## **7. `strpos()` – Find Position of a Substring**

```php
<?php
$text = "hello world";
$position = strpos($text, "world");
echo "Position of 'world': " . $position;  
// Output: 6 (position where "world" starts)
?>
```

---

## **8. `substr()` – Extract Part of a String**

```php
<?php
$text = "Hello World";
echo "Substring: " . substr($text, 6, 5);  
// Output: "World"
?>
```

---

## **9. `trim()` – Remove Spaces from the Beginning and End**

```php
<?php
$text = "   Hello World!   ";
echo "Trimmed text: '" . trim($text) . "'";  
// Output: "Hello World!"
?>
```

---

## **10. `str_repeat()` – Repeat a String**

```php
<?php
$text = "PHP ";
echo "Repeated text: " . str_repeat($text, 3);  
// Output: "PHP PHP PHP "
?>
```

---

## **11. `strrev()` – Reverse the String**

```php
<?php
$text = "Hello";
echo "Reversed text: " . strrev($text);  
// Output: "olleH"
?>
```

---

## **12. `strstr()` – Find the First Occurrence of a Substring**

```php
<?php
$text = "We are learning PHP at Armour Infosec";
echo "Substring starting from 'learning': " . strstr($text, "learning");  
// Output: "learning PHP at Armour Infosec"
?>
```

---

## **13. `strchr()` – Find the First Occurrence of a Character**

```php
<?php
$text = "We are learning PHP at Armour Infosec";
echo "Substring starting from 'P': " . strchr($text, "P");  
// Output: "PHP at Armour Infosec"
?>
```

---

## **PHP String Functions – Full Code Example**

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>PHP String Functions</title>
</head>
<body>

<h1>PHP String Functions</h1>

<?php
// Example 1: strlen() - Find the Length of a String
$text1 = "Armour Infosec";
echo "Length of the string: " . strlen($text1) . "<br>";  
// Output: 14

// Example 2: strtoupper() - Convert to Uppercase
$text2 = "hello world";
echo "Uppercase: " . strtoupper($text2) . "<br>";  
// Output: "HELLO WORLD"

// Example 3: strtolower() - Convert to Lowercase
$text3 = "HELLO WORLD";
echo "Lowercase: " . strtolower($text3) . "<br>";  
// Output: "hello world"

// Example 4: ucfirst() - Capitalize the First Letter
$text4 = "hello world";
echo "First letter capitalized: " . ucfirst($text4) . "<br>";  
// Output: "Hello world"

// Example 5: ucwords() - Capitalize the First Letter of Each Word
$text5 = "hello world";
echo "Words capitalized: " . ucwords($text5) . "<br>";  
// Output: "Hello World"

// Example 6: str_replace() - Replace Text Inside a String
$text6 = "I love PHP!";
echo "Replaced text: " . str_replace("PHP", "Programming", $text6) . "<br>";  
// Output: "I love Programming!"

// Example 7: strpos() - Find Position of a Substring
$text7 = "hello world";
$position = strpos($text7, "world");
echo "Position of 'world': " . $position . "<br>";  
// Output: 6 (position where "world" starts)
?>

// Example 8: substr() - Extract Part of a String
$text8 = "Hello World";
echo "Substring: " . substr($text8, 6, 5) . "<br>";  
// Output: "World"

// Example 9: trim() - Remove Spaces from the Beginning and End
$text9 = "    Hello World!    ";
echo "Trimmed text: '" . trim($text9) . "'<br>";  
// Output: "Hello World!"

// Example 10: str_repeat() - Repeat a String
$text10 = "PHP ";
echo "Repeated text: " . str_repeat($text10, 3) . "<br>";  
// Output: "PHP PHP PHP "

// Example 11: strrev() - Reverse the String
$text11 = "Hello";
echo "Reversed text: " . strrev($text11) . "<br>";  
// Output: "olleH"

// Example 12: strstr() - Find the First Occurrence of a Substring
$text12 = "We are learning PHP at Armour Infosec";
echo "Substring starting from 'learning': " . strstr($text12, "learning") . "<br>";  
// Output: "learning PHP at Armour Infosec"

// Example 13: strchr() - Find the First Occurrence of a Character
$text13 = "We are learning PHP at Armour Infosec";
echo "Substring starting from 'P': " . strchr($text13, "P") . "<br>";  
// Output: "PHP at Armour Infosec"
?>
</body>
</html>
```

---

## **Summary**

* These **string functions** in PHP can be used to manipulate and manage strings effectively.
* You can **convert cases**, **search for substrings**, **replace text**, and perform **many other operations** using PHP’s built-in string functions.

---

## **Summary of Key Functions**

* **strlen()** — Get the length of a string.
* **strtoupper()** — Convert string to uppercase.
* **strtolower()** — Convert string to lowercase.
* **ucfirst()** — Capitalize the first character of a string.
* **ucwords()** — Capitalize the first letter of each word.
* **str_replace()** — Replace text within a string.
* **strpos()** — Find the position of a substring.
* **substr()** — Extract a portion of a string.
* **trim()** — Remove spaces from the beginning and end.
* **str_repeat()** — Repeat a string.
* **strrev()** — Reverse a string.
* **strstr()** and **strchr()** — Find the first occurrence of a substring or character.

---

## **Conclusion**

* PHP provides a wide range of **string functions** for manipulating text.
* These functions are essential for processing user input, handling data, and customizing output.
