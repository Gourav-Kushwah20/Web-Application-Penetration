# 📄 PHP-Script-To-Display-A-Basic-Webpage

## 🌐 PHP Script: Display Basic Webpage

This PHP script outputs a simple HTML page titled and headed **"Armour Infosec."**

---

## 📝 Steps

### ▶️ Start PHP:

### 🧱 Output HTML structure using `echo`:

```php
<?php
echo "<html>";
echo "<title>Armour Infosec</title>";
echo "<body>";
echo "<h1>Armour Infosec</h1>";
echo "</body>";
echo "</html>";
?>
```

> ℹ️ No need to close PHP (`?>`) if the file contains only PHP.

---

## 🚀 Improved Version

Use a single `echo` with better structure:

```php
<?php
echo "
<html>
<head>
    <title>Armour Infosec</title>
</head>
<body>
    <h1>Armour Infosec</h1>
</body>
</html>
";
?>
```
---

## 📌 Using Heredoc (Optional)

```php
<?php
echo <<<HTML
<html>
<head>
    <title>Armour Infosec</title>
</head>
<body>
    <h1>Armour Infosec</h1>
</body>
</html>
HTML;
?>
```

---
