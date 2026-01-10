# HTML Forms with GET Method in PHP

## 📩 HTML Forms with GET Method in PHP

This example demonstrates how to use a basic HTML form with the **GET** method in PHP and retrieve the submitted data in `process-get.php`.

---

## 📄 forms-get.php

This file contains a simple login form that uses the **GET** method.

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Forms Get</title>
</head>
<body>

<form action="process-get.php" method="GET">
    Username: <input type="text" name="username" value="" /><br />
    Password: <input type="password" name="passwd" value="" /><br />
    <input type="submit" name="submit" value="login" />
</form>

<!--
Notes:
- When using the GET method, all form data is appended to the URL.
- GET requests are visible in the browser's address bar.
- They are suitable for non-sensitive data.
- GET requests have a maximum limit of about 2048 characters.
-->

</body>
</html>
```

- Example URL after submission:

```text
http://192.168.1.50/php/Super-Global-Variables/%20forms-get.php
```
---

## 📄 process-get.php

This file receives and displays the data submitted via the **GET** method.

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Process Form</title>
</head>
<body>

<pre>
<?php
print_r($_GET);
?>
</pre>

<?php
$username = $_GET['username'];
$password = $_GET['passwd'];

echo "Username: {$username} <br />";
echo "Password: {$password} <br />";
?>

</body>
</html>
````

---

## ⚠️ Security Warning

❌ **Never use the GET method for sensitive data like passwords.**

GET parameters are:

* 📝 Logged in **browser history** and **server logs**
* 👁️ Visible directly in the **URL** (may be cached or shared)
* 📏 **Limited in size** (≈ 2048 characters)

