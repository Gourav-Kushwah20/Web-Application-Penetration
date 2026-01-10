# $_POST – Superglobal

## 📮 PHP $_POST Superglobal

`$_POST` is a **superglobal associative array** in PHP used to collect form data after submitting an HTML form with the `method="POST"`.

---

## ✅ When is $_POST Used?

When a form is submitted using the **POST** method:

```html
<form method="POST" action="process.php">
    <input type="text" name="username" />
    <input type="password" name="password" />
    <input type="submit" value="Login" />
</form>
```

---

## 📄 process.php

In `process.php`, the submitted values are accessed using `$_POST`:

```php
<?php
$username = $_POST['username'];
$password = $_POST['password'];

echo "Username: $username";
echo "Password: $password";
?>
```

---

## 🧠 Key Points

| Feature         | Description                                                       |
| --------------- | ----------------------------------------------------------------- |
| **Visibility**  | Data is **not visible in the URL** (unlike `$_GET`)               |
| **Security**    | More secure for transmitting **sensitive data** (e.g., passwords) |
| **Size Limit**  | Controlled by `post_max_size` in `php.ini` (default: **8MB**)     |
| **Usage**       | Form submissions, login forms, file uploads, etc.                 |
| **Data Source** | `<form method="POST">` elements                                   |

---

## ⚠️ Security Reminder

Always **validate and sanitize** data received from `$_POST`:

```php
$username = htmlspecialchars(trim($_POST['username']));
```

This helps protect your application from:

* ❌ XSS (Cross-Site Scripting)
* ❌ SQL Injection
* ❌ Other user-input vulnerabilities

---

## 🔗 Related Superglobals

* **[`$_GET`](https://www.php.net/manual/en/reserved.variables.get.php)** – for query string parameters
* **[`$_REQUEST`](https://www.php.net/manual/en/reserved.variables.request.php)** – contains `$_GET`, `$_POST`, and `$_COOKIE`

---

## 📝 PHP Form Handling with POST Method

### 📄 form-post.php

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Forms POST</title>
</head>
<body>

<form action="process-post.php" method="POST">
    Username: <input type="text" name="username" value="" /><br />
    Password: <input type="password" name="passwd" value="" /><br />
    <input type="submit" name="submit" value="login" />
</form>

</body>
</html>
```

---

## 📄 process-post.php

This file receives and displays the data submitted via the **POST** method.

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
print_r($_POST);
?>
</pre>

<?php
$username = $_POST['username'];
$password = $_POST['passwd'];

echo "Username: {$username} <br />";
echo "Password: {$password} <br />";
?>
</body>
</html>
```

---

## 🧠 Notes on the POST Method

* 📦 The **POST** method sends data in the **body of the HTTP request**
* 👁️ Data is **not exposed** in the browser’s address bar
* 🔐 Suitable for **sensitive or large form data**, such as:

  * Passwords
  * File uploads
* ⚙️ No practical browser-side character limit
  (limited by server settings like `post_max_size` and `max_input_vars`)

---


## 🔐 Security Tip

Always **validate and sanitize** user inputs from `$_POST`:

```php
$username = htmlspecialchars(trim($_POST['username']));
$password = htmlspecialchars(trim($_POST['passwd']));
```

Use **prepared statements** if inserting data into a database to prevent
**SQL Injection**.


