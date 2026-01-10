# Urlencode and Rawurlencode

## 🔐 PHP urlencode() vs rawurlencode()

This guide demonstrates how to safely encode URL parameters using  
`urlencode()` and `rawurlencode()` functions in PHP.

---

## 🧪 Use Case: Encoding URL Parameters

### 📌 Sample PHP Example

urlencode_rawurlencode.php

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Urlencode and Rawurlencode</title>
</head>
<body>

<?php
    $page_name = "Second Page";
    $link_name = "second_page";
    $id = 6;
    $name = "Johnson & Johnson";
?>

<!-- Without encoding -->
Link without encode:
<a href="<?php echo $link_name; ?>.php?name=<?php echo $name; ?>&id=<?php echo $id; ?>">
    <?php echo $page_name; ?>
</a><br />

<!-- With urlencode() -->
Link with urlencode:
<a href="<?php echo $link_name; ?>.php?name=<?php echo urlencode($name); ?>&id=<?php echo $id; ?>">
    <?php echo $page_name; ?>
</a><br />

📎 Ex. `second_page.php?name=Johnson+%26+Johnson&id=6`

<br /><br />

<!-- With rawurlencode() -->
Link with rawurlencode:
<a href="<?php echo $link_name; ?>.php?name=<?php echo rawurlencode($name); ?>&id=<?php echo $id; ?>">
    <?php echo $page_name; ?>
</a><br />

📎 Ex. `second_page.php?name=Johnson%20%26%20Johnson&id=6`

<br /><br />

<!-- Combined example -->
<?php
    $page  = "about as";
    $quote = "ethical hacking";

    $link1 = "/armourinfosec/" . rawurlencode($page) . "?quote=" . urlencode($quote);
    $link2 = "/armourinfosec/" . urlencode($page) . "?quote=" . rawurlencode($quote);

    echo "Rawurlencode Page + Urlencode Quote: $link1<br />";
    echo "Urlencode Page + Rawurlencode Quote: $link2<br />";
?>
```
---

## 🔤 URL Encoding Character Reference (PHP)

The table below shows how common characters are encoded using  
`urlencode()` and `rawurlencode()` in PHP.

| Character | `urlencode()` | `rawurlencode()` |
|----------|---------------|------------------|
| Space    | `+`           | `%20`            |
| `!`      | `%21`         | `%21`            |
| `@`      | `%40`         | `%40`            |
| `#`      | `%23`         | `%23`            |
| `$`      | `%24`         | `%24`            |
| `%`      | `%25`         | `%25`            |
| `^`      | `%5E`         | `%5E`            |
| `&`      | `%26`         | `%26`            |
| `*`      | `%2A`         | `%2A`            |
| `(`      | `%28`         | `%28`            |
| `)`      | `%29`         | `%29`            |
| `{`      | `%7B`         | `%7B`            |
| `}`      | `%7D`         | `%7D`            |
| `[`      | `%5B`         | `%5B`            |
| `]`      | `%5D`         | `%5D`            |
| `` ` ``  | `` ` ``       | `%7C`            |
| `\`      | `%5C`         | `%5C`            |
| `/`      | `%2F`         | `%2F`            |
| `;`      | `%3B`         | `%3B`            |
| `:`      | `%3A`         | `%3A`            |
| `,`      | `%2C`         | `%2C`            |
| `.`      | `%2E`         | `%2E`            |
| `<`      | `%3C`         | `%3C`            |
| `>`      | `%3E`         | `%3E`            |
| `?`      | `%3F`         | `%3F`            |
| `=`      | `%3D`         | `%3D`            |
| `+`      | `%2B`         | `%2B`            |
| `-`      | `-`           | `%2D`            |
| `_`      | `_`           | `%5F`            |
| `~`      | `~`           | `%7E`            |

---

## ✅ Best Practices

- 🔹 Use `urlencode()` for **query strings**  
  Example: `?key=value`

- 🔹 Use `rawurlencode()` when encoding **path segments**  
  Example: `/path/to/resource`

- 🔹 Always encode **dynamic data** passed via URLs to avoid:
  - Broken links
  - Injection or security issues

- 🔹 Use `htmlspecialchars()` when rendering values in **HTML output**
  to prevent **XSS attacks** 🔐

---

### 🧠 Quick Reminder
- **Encoding** → protects URLs  
- **Escaping** → protects HTML output  


