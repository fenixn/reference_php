# PHP Reference
Personal study notes for PHP

* [PHP Basics](#php-basics)
  * [PHP Tags](#php-tags)
    * [Standard Tags](#standard-tags)
    * [Short Tags](#short-tags)

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

### Comparison Operators
```php
<?php
  $a = "5";
  $b = 5;
  
  var_dump($a == $b); // Equal operator
  // Example outputs bool(true) because $a and $b are the equal after type juggling
  
  var_dump($a === $b); // Identical operator
  // Example outputs bool(false) because $a and $b are different types
  
  var_dump($a != $b); // Not Equal operator
  var_dump($a <> $b); // Not Equal operator
  // Example outputs bool(false) because $a and $b are equal after type juggling.
  
  var_dump($a !== $b); // Not Identical operator
  // Example outputs bool(true) because $a and $b are different types and not identical.
  
  $c = 5;
  $d = 10;
  
  var_dump($c < $d); // Less Than operator
  // Example outputs bool(true) because $c is less than $d
  
  var_dump($c > $d); // Greater Than operator
  // Example outputs bool(false) because $c is not greater than $d
  
  $e = 7;
  $f = 7;
  
  var_dump($e <= $f); // Less Than or Equal To operator
  // Example outputs bool(true) because while $e is not less than $f, it is equal to it.
  
  var_dump($e >= $f); // Greater Than or Equal To operator
  // Example outputs bool(true) because while $e is not greater than $f, it is equal to it.
?>
```

### Ternary Operator
The ternary operator is a conditional operator. (expr1) ? (expr2) : (expr3) evaluates to expr2 is expr1 is TRUE. If expr1 is instead FALSE, it will evaluate to expr3 instead.
```php
<?php
  $a = "output a";
  $b = "output b";

  echo 2 == "2" ? $a : $b; // outputs a
  echo 2 === "2" ? $a : $b; // outputs b
?>
```
