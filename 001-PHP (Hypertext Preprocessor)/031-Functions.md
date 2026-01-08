# Functions

## 🧠 PHP Functions

Functions in PHP are reusable blocks of code that perform specific tasks.  
You define them once and use them multiple times to make your code **modular** and **maintainable**.

## 📄 File: `functions.php`

```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Functions</title>
</head>
<body>

<?php
// Function with no parameters
function fun_hello() {
    echo "Armour Infosec ! <br />";
}

fun_hello(); // Call the function


// Function with one parameter
function fun_hello2($name) {
    echo "Hello {$name} ! <br />";
}

fun_hello2("Rahul");

$var1 = "Admin";
fun_hello2($var1);


// Function with multiple parameters
function say_hello($name1, $name2, $name3) {
    echo $name1 . ", " . $name2 . ", " . $name3 . "<br />";
}

say_hello("Rahul", "Pankaj", "Ankit");
?>

</body>
</html>
```