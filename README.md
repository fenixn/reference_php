# PHP Reference
Personal study notes for PHP

# PHP Basics

## PHP Tags

### Standard Tags
```php
<?php
  //code 
?>
```
* Always available and best for compatibility
* Cannot be disabled by changing the PHP configuration file

### Short Tags
```php
<? //code ?>
```
* Can be disabled in php.ini with the short_open_tag directive
* The code below can be used as a shorthand for echo
```php
<?= $variable ?>
```

### ASP Tags
```php
<% //code %>
```
* Must be enabled in php.ini with the asp_tags directive

## Comments
```php
<?php
// This is a single line comment

/* 
This is a multi line comment
*/
?>
```

## Operators

### Modulus Operator
```php
<?php
echo 3 % 2; // prints 1
echo 5 % 3; // prints 2
?>
```

### Combined Operator
```php
<?php
$a = 1; 
$a += 2; // equal 3

$b = 10;
$b -= 2; // equals 8
?>
```

### Assignment by Reference
```php
<?php
$a = 2;
$b = &$a; // $b is now a reference to $a

echo $a; // prints 2
echo $b; // prints 2

$a = 5;

echo $a; // now prints 5
echo $b; // now prints 5 as well, since $b is a reference to $a
?>
```
