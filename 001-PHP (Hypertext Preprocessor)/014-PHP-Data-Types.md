# **PHP Data Types**

In PHP, **data types** define the kind of data a variable can hold.

---

## **1. Scalar Data Types**

### **• Integer (`int`)**

Whole numbers (positive, negative, or zero).

```php
$num = 100;
```

---

### **• Float (`float`, also called `double`)**

Numbers with decimals.

```php
$price = 10.99;
```

---

### **• String (`string`)**

Sequence of characters (text).

```php
$name = "Armour Infosec";
```

---

### **• Boolean (`bool`)**

Represents `true` or `false`.

```php
$isAvailable = true;
```

---

## **2. Compound Data Types**

### **• Array**

Collection of values in a single variable.

```php
$colors = ["red", "green", "blue"];
```

---

### **• Object**

Instance of a class.

```php
class Car {
    public $brand = "Toyota";
}

$myCar = new Car();
```

---

## **3. Special Data Types**

### **• NULL**

Represents a variable with no value.

```php
$data = null;
```

---

### **• Resource**

Special handlers for external resources like database connections or file handles.

```php
$handle = fopen("file.txt", "r");
```

---

## **Quick Summary Table**

| **Type** | **Example**                   | **Description**                 |
| -------- | ----------------------------- | ------------------------------- |
| Integer  | `100`, `-25`                  | Whole numbers                   |
| Float    | `10.5`, `-2.7`                | Decimal numbers                 |
| String   | `"Hello World"`               | Text                            |
| Boolean  | `true`, `false`               | Logical values                  |
| Array    | `["a", "b", "c"]`             | Multiple values in one variable |
| Object   | `new ClassName()`             | Object-oriented instances       |
| NULL     | `null`                        | No value                        |
| Resource | `fopen()`, `mysqli_connect()` | Special external data           |

---

## **Extra**

You can check the data type of any variable using **`var_dump()`**:

```php
$var = 123;
var_dump($var); // Output: int(123)
```

Or using **`gettype()`**:

```php
echo gettype($var); // Output: integer
```

---
