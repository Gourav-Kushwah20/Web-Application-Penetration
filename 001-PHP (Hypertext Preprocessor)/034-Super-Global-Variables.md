# 🌐 Super-Global-Variables

## ✅ PHP Super Global Variables

**Superglobals** are built-in variables in PHP that are always accessible, regardless of scope — **no need to declare `global`** to use them inside functions or classes.

---

## 🌍 1. `$_GET`

### 📌 Description:
Contains data sent via the **URL (query string)** using the HTTP **GET** method.

### 🧩 Usage:
Used when a user submits a form with `method="GET"` or clicks a link with query parameters.

### 🔗 Example URL:
```

[https://example.com/page.php?name=John](https://example.com/page.php?name=John)

````

### 💻 Example Code:
```php
echo $_GET['name']; // Output: John
````

---

## 📮 2. `$_POST`

### 📌 Description:

Contains data submitted through an HTML form using the HTTP **POST** method.

### 🧩 Usage:

Safer for sensitive data like passwords and emails.

### 💻 Example Code:

```php
echo $_POST['email'];
```

## 🔁 3. `$_REQUEST`

### 📌 Description:
Contains data from **`$_GET`**, **`$_POST`**, and **`$_COOKIE`**.

### ⚠️ Usage:
Flexible but **less secure** and **not recommended** when method-specific data is required.

### 💻 Example:
```php
echo $_REQUEST['username'];
````

---

## 🖥️ 4. `$_SERVER`

### 📌 Description:

Contains information about the **server** and the **execution environment**.

### 🔑 Common Keys:

* `$_SERVER['HTTP_HOST']`
* `$_SERVER['REQUEST_METHOD']`
* `$_SERVER['SCRIPT_NAME']`

### 💻 Example:

```php
echo $_SERVER['REQUEST_METHOD']; // Output: GET or POST
```

---

## 📁 5. `$_FILES`

### 📌 Description:

Handles **file uploads** from forms (`<input type="file">`).

### 🔑 Keys:

* `name`
* `type`
* `size`
* `tmp_name`
* `error`

### 💻 Example:

```php
echo $_FILES['file']['name'];
```

## 🍪 6. `$_COOKIE`

### 📌 Description:
Stores **cookie data** sent from the client (browser).

### 💻 Example:
```php
echo $_COOKIE['user'];
```

---

## 🔐 7. `$_SESSION`

### 📌 Description:

Stores **session data** across multiple pages.

### ⚠️ Requires:

`session_start()` at the beginning of each session-using script.

### 💻 Example:

```php
session_start();
$_SESSION['user'] = 'admin';
echo $_SESSION['user'];
```

---

## 🌍 8. `$GLOBALS`

### 📌 Description:

References **all global variables** in the script.

### 🎯 Use Case:

Access a global variable inside a function.

### 💻 Example:

```php
$x = 5;

function test() {
    echo $GLOBALS['x'];
}

test(); // Output: 5
```
---

## 🔁 Summary Table

| Superglobal | Purpose |
|------------|---------|
| `$_GET` | URL query string data (GET method) |
| `$_POST` | Form data (POST method) |
| `$_REQUEST` | Combination of GET, POST, and COOKIE |
| `$_SERVER` | Server and execution environment info |
| `$_FILES` | Uploaded file data |
| `$_COOKIE` | Client-side cookies |
| `$_SESSION` | Session variables |
| `$GLOBALS` | All global variables |

---