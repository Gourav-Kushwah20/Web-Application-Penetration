# **PHP-Script-Understanding-Comments**

## **PHP Script Understanding Comments**

This script demonstrates how to insert comments in PHP and HTML, along with dynamic outputs.

---

## **Inserting Comments**

### **PHP Comments**

* **Single-line** comment using `//`
* **Single-line (alternative)** comment using `#`
* **Multi-line** comment using `/* ... */`

**Example:**

```php
// This is a single-line comment

# This is another single-line comment (less commonly used)

/*
This is a multi-line comment
spanning multiple lines
*/
```

---

### **HTML Comments**

* HTML comments use `<!-- comment -->`

**Example:**

```html
<!-- This is an HTML comment -->
```

---

## 💻 **Code**

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>
        <?php echo "Armour Infosec"; ?>
    </title>
</head>
<body>

    <!--
        test1234….
    -->

<?php

    // echo "1. Armour Infosec"; (commented out)

    echo "<br>";

    # echo "2. Armour"; (commented out)

    /*
    echo "<br>";
    echo "3. Armour" . " " . "Infosec";
    echo "<br>";
    */

?>

<h1>
    <?php echo "Armour Infosec"; ?>
</h1>

<?php echo 3 + 3; ?>
<br>

<?php echo 2 + 3; ?>
<br>

<?php echo "2 + 3"; ?>
<br>

<?php echo "Armour Infosec"; ?>
<br>
```

---

## **Explanation**

* **HTML comments** are visible in the page source but not rendered on the page.
* **PHP comments** disable code from running, useful for notes or debugging.
* Regular PHP outputs (`echo`, `print`) display content on the webpage.
* `<br>` is used to insert line breaks in the output.

---

## **Quick Tips**

* Use `//` for quick notes inside PHP.
* Use `/* */` for longer PHP explanations or to temporarily block large code sections.
* Avoid leaving sensitive information inside HTML comments—they can be seen in the browser’s page source!

---
