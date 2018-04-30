# PHP Reference
Personal study notes for PHP

# Table of Contents
* [PHP Basics](#php-basics)
  * [PHP Tags](#php-tags)
    * [Standard Tags](#standard-tags)
    * [Short Tags](#short-tags)
    * [ASP Tags](#asp-tags)
  * [Comments](#comments)
  * [Operators](#operators)
    * [Modulus Operator](#modulus-operator)
    * [Combined Operator](#combined-operator)
    * [Assignment by Reference](#assignment-by-reference)
    * [Comparison Operators](#comparison-operators)
    * [Ternary Operator](#ternary-operator)
    * [Incrementing and Decrementing Operators](#incrementing-and-decrementing-operators)
    * [Logical Operators](#logical-operators)
    * [String Operators](#string-operators)
  * [Variables](#variables)
    * [Naming](#naming)
    * [Types](#types)
    * [Strings](#strings)
    * [Integer](#integer)
    * [Boolean](#boolean)
    * [Arrays](#arrays)
    * [Resource](#resource)
    * [null](#null)
    * [Variable Variables](#variable-variables)
    

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

[Table of Contents](#table-of-contents)

### Short Tags
```php
<? //code ?>
```
* Can be disabled in php.ini with the short_open_tag directive
* The code below can be used as a shorthand for echo
```php
<?= $variable ?>
```

[Table of Contents](#table-of-contents)

### ASP Tags
```php
<% //code %>
```
* Must be enabled in php.ini with the asp_tags directive

[Table of Contents](#table-of-contents)

## Comments
```php
<?php
  // This is a single line comment

  /* 
  This is a multi line comment
*/
?>
```
[Table of Contents](#table-of-contents)

## Operators

### Modulus Operator
```php
<?php
  echo 3 % 2; // prints 1
  echo 5 % 3; // prints 2
?>
```
[Table of Contents](#table-of-contents)

### Combined Operator
```php
<?php
  $a = 1; 
  $a += 2; // equal 3

  $b = 10;
  $b -= 2; // equals 8
?>
```
[Table of Contents](#table-of-contents)

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
[Table of Contents](#table-of-contents)

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
[Table of Contents](#table-of-contents)

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
[Table of Contents](#table-of-contents)

### Incrementing and Decrementing Operators
PHP support both pre- and post-increment and decrement operators
```php
<?php
 $a = 1;
 $a++; // $a = 2
 ++$a; // $a = 3
 
 $b = 10;
 $b--; // $b = 9
 --$b; // $b = 8
?>
```
[Table of Contents](#table-of-contents)

### Logical Operators
```php
<?php
 $a = TRUE;
 $b = FALSE;
 
 var_dump($a and $b); 
 var_dump($a && $b); // outputs bool(false). The (and) operator only outputs TRUE if both $a and $b are TRUE.
 
 var_dump($a or $b);
 var_dump($a || $b); // outputs bool(true). The (or) operator will output TRUE if either $a or $b is TRUE.
 
 var_dump($a xor $b); // outputs bool(true). The (xor) operator will output TRUE if either $a or $b is TRUE, but not both.
 var_dump(!$a); // outputs bool(false). The (not) operator will output TRUE if $a is not TRUE.
?>
```
[Table of Contents](#table-of-contents)

### String Operators
```php
<?php
 $a = "hello";
 $b = "world";
 
 echo $a . $b; // outputs "hello world". The (.) is the concatenation operator.
 
 $a .= $b;
 echo $a; // outputs "hello world". The (.=) is the concatenating assignment operator.
?>
```
[Table of Contents](#table-of-contents)

## Variables

### Naming
* Variable names can only contain letters, numbers or underscores
* Variable names must start with a letter or underscores

### Types
* Scalar types
  * boolean
  * string
  * integer
  * float
* Compound types
  * array
  * object
* Special types
  * resource
  * null
  
### Strings
* Single quotes - 'some text' - Characters within single quotes will be recorded as is, without variables or escape sequences intrepreted and replaced
* Double quotes - "some text" - Variables and esacpe sequences will be interpreted and replaced.
* Heredoc - <<< - Functions similar to double quotes, but is designed to span multiple lines and allows for use of quotes without esacping.
```php
<?php
 $str = <<<STR
 This is an example of heredoc.
 It allows multiple lines,
 and "quotes".
 STR;

 echo $str; // outputs This is an example of heredoc. It allows multiple lines, and "quotes".
?>
```
[Table of Contents](#table-of-contents)

### Integer
* Decimal (base 10)
* Hexidecimal (base 16) - precede with a 0x
* Octal (base 8) - precede with a 0

### Boolean
* Any integer other than 0 is cast to TRUE
* TRUE & FALSE are case-insenstive, although the all apps representation is common

### Arrays
* Arrays can contain any combination of other variable types, even arrays or objects

### Resource
* Resource is a special variable that represents some sort of operating system resource, generally an open file or database connection.

### null
* null has no value and no type
* null is not the same as the integer zero or a zero length string

### Variable Variables
A variable value can be used as a variable name by prepending the variable with an additional $.
```php
<?php
$a = "name";
$$a = "John";
echo $name; // outputs John
?>
```
[Table of Contents](#table-of-contents)


