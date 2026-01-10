# 📄 Detecting Form Submissions in PHP

This guide demonstrates different ways to detect form submissions and handle form data securely using PHP `$_POST`.

---

## 📝 Form: `detecting_form_submissions.php`

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Form - Detecting Form Submissions</title>
</head>
<body>

<form action="process-detecting-form-submissions.php" method="POST">
    Username: <input type="text" name="username" value="" /><br />
    Password: <input type="password" name="passw" value="" /><br />
    <input type="submit" name="submit" value="login" />
</form>

</body>
</html>
```


## ⚙️ Processing: `process-detecting-form-submissions.php`

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Detecting Form Submission (Beginner)</title>
</head>
<body>

<!-- Show all POST data (for learning/debugging) -->
<pre>
<?php
print_r($_POST);
?>
</pre>

<?php
/* 
   Step 1:
   Check if username field exists
*/
if (isset($_POST['username'])) {
    $username = $_POST['username'];
} else {
    $username = "";
}

/* 
   Step 2:
   Check if password field exists
*/
if (isset($_POST['passw'])) {
    $password = $_POST['passw'];
} else {
    $password = "";
}

/* 
   Step 3:
   Display values
*/
echo "Username : " . $username . "<br />";
echo "Password : " . $password . "<br />";

/* 
   Step 4:
   Check if form submit button was clicked
*/
if (isset($_POST['submit'])) {
    echo "Form was submitted <br />";
} else {
    echo "Form was not submitted <br />";
}
?>

</body>
</html>
```

---

## 🧠 Beginner Explanation (Simple Words)

### 🔹 `$_POST`

* Stores form data sent using **POST method**

### 🔹 `isset()`

* Checks **whether a value exists or not**
* Prevents errors if the form is not submitted

### 🔹 Why we check `submit`?

* If submit button exists → form **was submitted**
* If not → form **was not submitted**



## ✅ Best Beginner Practice (Optional Upgrade)

```php
$username = isset($_POST['username']) ? trim($_POST['username']) : "";
$password = isset($_POST['passw']) ? trim($_POST['passw']) : "";
```

---

## 📝 Form: `detecting_form_submissions1.php`

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Form - Detecting Form Submissions 1</title>
</head>
<body>

<form action="process-detecting-form-submissions1.php" method="POST">
    Username: <input type="text" name="username" value="" /><br />
    Password: <input type="password" name="passw" value="" /><br />
    <input type="submit" name="submit" value="login" />
</form>

</body>
</html>
```

### ✅ Notes

* Uses **POST** method to submit form data
* Sends data to `process-detecting-form-submissions1.php`
* Input fields:

  * `username` → text input
  * `passw` → password input
  * `submit` → submit button (used to detect submission)


## ⚙️ Processing: `process-detecting-form-submissions1.php`

### ✅ Beginner-Friendly Version (Easy to Understand)

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Detect Form Submission</title>
</head>
<body>

<!-- This shows all POST data for learning purpose -->
<pre>
<?php
print_r($_POST);
?>
</pre>

<?php
/*
 Step 1:
 Check if username is sent from the form
*/
if (isset($_POST['username'])) {
    $username = $_POST['username'];
} else {
    $username = "";
}

/*
 Step 2:
 Check if password is sent from the form
*/
if (isset($_POST['passw'])) {
    $password = $_POST['passw'];
} else {
    $password = "";
}

/*
 Step 3:
 Show the values on the screen
*/
echo "Username : " . $username . "<br />";
echo "Password : " . $password . "<br />";

/*
 Step 4:
 Check if submit button was clicked
*/
if (isset($_POST['submit'])) {
    echo "Form was submitted <br />";
} else {
    echo "Form was not submitted <br />";
}
?>

</body>
</html>
```


## 🧠 Beginner Explanation (Simple Words)

### 🔹 `$_POST`

* Stores form data sent using **POST method**
* Data comes from `<form method="POST">`



### 🔹 `isset()`

* Checks **value exists or not**
* Prevents PHP errors
* Example:

```php
isset($_POST['username'])
```

👉 means: *Did user enter username or not?*



### 🔹 Why `print_r($_POST);` ?

* Shows **all form data**
* Used only for **learning / debugging**
* ❌ Do not use in real login systems



### 🔹 How form submission is detected?

```php
if (isset($_POST['submit']))
```

* If submit button exists → form **submitted**
* If not → form **not submitted**



## ✅ Short Version (After Learning)

When you understand basics, you can write shorter code:

```php
$username = $_POST['username'] ?? "";
$password = $_POST['passw'] ?? "";
```


## ⚠️ Important Beginner Warning

❌ Never use POST like this in real login systems
✔ Always use:

* `htmlspecialchars()`
* Password hashing
* Database prepared statements


---

## 📝 Form: `detecting_form_submissions2.php`

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Form - Detecting Form Submissions 2</title>
</head>
<body>

<form action="process-detecting-form-submissions2.php" method="POST">
    Username: <input type="text" name="username" value="" /><br />
    Password: <input type="password" name="passw" value="" /><br />
    <input type="submit" name="submit" value="login" />
</form>

</body>
</html>
````

---

### ✅ Notes

* This is the **second variation** of the form example
* Uses `POST` to send data securely
* Fields submitted:

  * `username`
  * `passw`
  * `submit`
* Data is handled in `process-detecting-form-submissions2.php`


## ⚙️ Processing: `process-detecting-form-submissions2.php`



```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Detect Form Submission - Simple</title>
</head>
<body>

<?php
/*
 Step 1:
 Check if the form submit button was clicked
*/
if (isset($_POST['submit'])) {

    echo "Form was submitted <br />";

    /*
     Step 2:
     Get username value safely
    */
    if (isset($_POST['username'])) {
        $username = $_POST['username'];
    } else {
        $username = "";
    }

    /*
     Step 3:
     Get password value safely
    */
    if (isset($_POST['passw'])) {
        $password = $_POST['passw'];
    } else {
        $password = "";
    }

    /*
     Step 4:
     Show values
    */
    echo "Username : " . $username . "<br />";
    echo "Password : " . $password . "<br />";

} else {

    /*
     Step 5:
     If form is not submitted
    */
    echo "Form was not submitted <br />";
}
?>

</body>
</html>
```

## 🧠 Very Simple Explanation (Beginner Level)

### 🔹 `$_POST`

* Stores data sent from a form using **POST method**

### 🔹 `isset()`

* Checks **value exists or not**
* Prevents errors

Example:

```php
isset($_POST['submit'])
```

👉 Means: *Did the user click the submit button?*


### 🔹 Why check `submit` first?

✔ If submit button exists → form **was submitted**
❌ If not → form **was not submitted**

This is the **correct and clean way** 👍



## ✅ Easy Flow (How Code Works)

1. User opens page → **Form not submitted**
2. User submits form → **Form submitted**
3. PHP reads username & password
4. Values are printed


## ✨ Short Version (After You Learn Basics)

```php
if (isset($_POST['submit'])) {
    $username = $_POST['username'] ?? "";
    $password = $_POST['passw'] ?? "";

    echo "Username : $username <br />";
    echo "Password : $password <br />";
} else {
    echo "Form was not submitted";
}
```

## ⚠️ Beginner Warning (Very Important)

❌ Never use this code for real login systems
✔ Always use:

* `htmlspecialchars()`
* `password_hash()`
* Database prepared statements


---

## 📊 Summary: Form Submission Detection

| Technique                         | Method     | Safe for Processing | Summary                              |
|----------------------------------|------------|---------------------|--------------------------------------|
| `isset($_POST['submit'])`        | POST / GET | ✅ Yes              | Basic and common form detection      |
| `$_POST['username'] ?? ''`       | POST       | ✅ Yes              | Compact null-coalescing operator     |
| `htmlspecialchars()`             | Any        | ✅ Yes              | Sanitize output                      |

---

## 🔐 Security Tips

- Always **sanitize user inputs** before displaying or using them.
- Avoid directly trusting `$_POST` data for sensitive operations.
- Use **prepared statements** to prevent **SQL Injection**.
- For login forms, consider implementing **CSRF protection**.

---
