# Single Page Form Processing in PHP

## 📄 Single Page Form Processing in PHP

- All logic related to the form (**display, validation, processing**) is handled in **one file**.
- On errors, the form is **redisplayed** with:
  - ❌ Error messages
  - 🔁 Previously entered values populated in the form fields


## Example 1: Basic Single Page Form

- `single_page_form.php`
```php
<?php

if (isset($_POST['submit'])) {
    $username = $_POST['username'];
    $password = $_POST['passwd'];

    $var1 = "You are logging in : {$username}";
} else {
    $var1 = "Please Log in";
}

?>

<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Single Page Form Processing</title>
</head>
<body>

<?php echo $var1; ?>

<form action="singel_page_form.php" method="POST">
    Username:
    <input type="text" name="username" value="" /><br />
    Password:
    <input type="password" name="passwd" value="" /><br />
    <input type="submit" name="submit" value="login" />
</form>

</body>
</html>
```

---

### 🧠 What’s happening here?

* The **same PHP file**:

  * Shows the form
  * Processes the form
* When the form is submitted:

  * `$_POST['submit']` becomes available
  * Username and password are read
  * A message is shown: *“You are logging in : username”*
* When the form is **not submitted**:

  * Message shown: *“Please Log in”*

This is called **Single Page Form Processing** because everything happens in **one file** 👍

---
## Example 2: Single Page Form with Simple Validation and Redirect

**File:** `singel_page_form2.php`

```php
<?php

/* 
 Function to redirect user to another page
 after some time
*/
function redirect_to($new_location) {
    header("refresh: 5; url={$new_location}");
}

/*
 Check if form is submitted
*/
if (isset($_POST['submit'])) {

    $username = $_POST['username'];
    $password = $_POST['passwd'];

    /*
     Simple validation
    */
    if ($username == "admin" && $password == "armour123") {

        $var1 = "You are logging in : {$username}";
        redirect_to("../phpinfo.php");

    } else {

        $var1 = "There were some errors.";
    }

} else {

    $var1 = "Please Log in";
}

?>

<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Single Page Form Processing - 2</title>
</head>
<body>

<?php echo $var1; ?>

<form action="singel_page_form2.php" method="POST">
    Username:
    <input type="text" name="username" value="" /><br />
    Password:
    <input type="password" name="passwd" value="" /><br />
    <input type="submit" name="submit" value="login" />
</form>

</body>
</html>
```

+++++++
### 🧠 Beginner-Friendly Explanation

#### 🔹 What is happening here?

This is a **single-page form** example where:

* Form display
* Validation
* Redirect logic

👉 All are handled in **one PHP file**.

---

### 🔹 Step-by-Step Flow

1. **Function `redirect_to()`**

   * Redirects user to another page after **5 seconds**
   * Example: `phpinfo.php`

2. **Check form submission**

   ```php
   if (isset($_POST['submit']))
   ```

   ✔ Checks if user clicked the submit button

3. **Get form values**

   ```php
   $username = $_POST['username'];
   $password = $_POST['passwd'];
   ```

4. **Simple validation**

   ```php
   if ($username == "admin" && $password == "armour123")
   ```

   * Username must be `admin`
   * Password must be `armour123`

5. **If correct**

   * Shows login message
   * Redirects to `phpinfo.php`

6. **If wrong**

   * Shows error message

7. **If form not submitted**

   * Displays: *Please Log in*

---


