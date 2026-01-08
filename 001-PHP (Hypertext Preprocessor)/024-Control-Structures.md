# Control-Structures

## 🧭 PHP Control Structures

Control structures in PHP allow you to **make decisions**, **repeat actions**, and **control the flow** of your scripts.

---

## ✅ 1. Comparison Operators

Used to compare two values.

| Operator | Description |
|---------|-------------|
| `==` | Equal (values only) |
| `===` | Identical (value + type) |
| `!=` | Not equal |
| `!==` | Not identical |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |
| `<>` | Not equal (alternative to `!=`) |

---

## ✅ 2. Logical Operators

Used to **combine** or **invert** conditions.

| Operator | Description |
|---------|-------------|
| `&&` | And (both conditions must be true) |
| `||` | Or (at least one condition must be true) |
| `!` | Not (inverts the result) |

---

## ✅ 3. If Statements

### 🔹 Basic `if`

```php
if ($a > $b)
    echo "a is larger than b";
````

---

### 🔹 If–Else

```php
if ($a > $b) {
    echo "a is larger than b";
} else {
    echo "a is not larger than b";
}
```

---

### 🔹 If–Elseif–Else

```php
if ($a > $b) {
    echo "a is larger";
} elseif ($a < $b) {
    echo "a is smaller";
} else {
    echo "a is equal";
}
```

---

## ✅ 4. Switch Statement

Efficient for checking a variable against **many values**.

```php
switch ($fruit) {
    case "apple":
        echo "You chose apple";
        break;

    case "banana":
        echo "You chose banana";
        break;

    default:
        echo "Unknown fruit";
}
````

---

## 🔑 Key Notes

* `break;` → prevents **fall-through**
* `default:` → runs if **no case matches**

---

## ✅ Best Practices

* Use `===` instead of `==` to avoid **unexpected type juggling**
* Always include `break;` in `switch` unless fall-through is intentional
* Indent and group logic with `{}` even for one-liners to avoid bugs

---


