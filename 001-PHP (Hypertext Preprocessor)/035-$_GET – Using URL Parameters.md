# $_GET – Using URL Parameters

## 🌐 PHP $_GET – Using URL Parameters

The `$_GET` superglobal in PHP is used to retrieve data sent through the **query string** in URLs.  
It is commonly used in **links**, **search forms**, and **navigation systems**.

---

## 📌 Basic URL Query Examples

```text
https://www.armour.local/somepage.php?page=2
```
```text
https://www.armour.local/somepage.php?category=7&page=3
```
```text
https://www.armour.local/search?q=php
```

---
## Create a folder (Optional)
In Current location `/var/www/html/php/Super-Global-Variables`
```bash
mkdir Super-Global-Variables
```

## 📁 first_page.php

This page demonstrates how to generate links with query strings using both **HTML** and **PHP**.

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>First Page</title>
</head>
<body>

    <!-- Static HTML links -->
    <a href="second_page.php">Second Page</a><br />
    <a href="second_page.php?name=armour">Second Page with name</a><br />
    <a href="second_page.php?name=armour&id=1">Second Page with name and ID</a><br />

    <!-- PHP-generated links -->
    <?php
        $page_name = "Second Page";
        $name = "Rahul";
        $id = 1;
        
        echo '<a href="second_page.php?name=' . $name . '">' . $page_name . '</a><br />';
        echo '<a href="second_page.php?name=' . $name . '&id=' . $id . '">' . $page_name . '</a><br />';
    ?>

    <!-- Mixing HTML with PHP variables -->
    <a href="second_page.php?name=<?php echo $name; ?>&id=<?php echo $id; ?>"> <?php echo $page_name; ?> </a><br />

    <!-- With special characters -->
    <?php
        $name = "Johnson & Johnson";
        $id = 5;
    ?>

    <!-- Without encoding (unsafe) -->
    <a href="second_page.php?name=<?php echo $name; ?>&id=<?php echo $id; ?>"> <?php echo $page_name; ?> (Unencoded) </a><br />

    <!-- With encoding (safe) -->
    <a href="second_page.php?name=<?php echo urlencode($name); ?>&id=<?php echo $id; ?>"> <?php echo $page_name; ?> (urlencode) </a><br />

    <a href="second_page.php?name=<?php echo rawurlencode($name); ?>&id=<?php echo $id; ?>"> <?php echo $page_name; ?> (rawurlencode) </a>

</body>
</html>
```


## 📄 second_page.php

This file receives and processes the query parameters sent via the URL.

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Second Page</title>
</head>
<body>

    <h1>Second Page</h1>

    <!-- View the full GET array -->
    <?php print_r($_GET); ?><br />

    <!-- Safely accessing GET variables -->
    <?php
        $id   = $_GET['id']   ?? 'Not provided';
        $name = $_GET['name'] ?? 'Not provided';

        echo "ID: {$id}<br />";
        echo "Name: {$name}<br />";
    ?>

</body>
</html>
```

- When a browser sends this URL:
```
http://192.168.1.50/php/Super-Global-Variables/first_page.php
```
---

## 🔐 URL Encoding

When passing values with **spaces, ampersands, or special characters**, use encoding to avoid breaking URLs.

---

### 📋 Encoding Functions

| Function            | Description               | Example                     |
|---------------------|---------------------------|-----------------------------|
| `urlencode()`       | Encodes space as `+`      | `Johnson+%26+Johnson`       |
| `rawurlencode()`    | Encodes space as `%20`    | `Johnson%20%26%20Johnson`   |

---

## ✅ Best Practices

- ✅ Use `urlencode()` when embedding query parameters in URLs.
- ✅ Use the null coalescing operator (`??`) to provide fallback values: 

  ```php
  $_GET['key'] ?? 'default'
  ```

* ✅ Sanitize all input before using it in logic or database queries.
* ✅ Avoid exposing sensitive data in URLs (e.g., passwords).

---

## ✏️ Want to Extend?

You can combine this with:

* 🔍 Search forms using `method="get"`
* 📄 Pagination systems
* 🎯 Dynamic filters (e.g., category, tags)



