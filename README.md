ProcessWire Filter module

Overview:
=========

A developers module that adds a few functions to filter data in a similar way to WordPress' filters feature. 

Designed and tested on PW 2.5.3
http://processwire.com



Installation:
=============

- Copy Filter.module to your site/modules/ directory.

- Install the module
  - Login into ProcessWire Admin > Modules. 
  - Click "Check for new modules".
  - Click "install" next to the new <module-name>.



Usage:
======

Once the module is installed you have 2 functions ready to be used anywhere in your app: `addFilter` and `applyFilter`

```php
function my_function1($value)
{
	return 'filtered by my_function1';
}

function my_function2($value)
{
	return 'filtered by my_function2';
}

// Parameters: filter name, function name or array(class, method), priority
// Higher priority means later execution, default is 10
addFilter('some_filter_name', 'my_function1', 10);
addFilter('some_filter_name', 'my_function2', 10);

$result = 'default value';
$result = applyFilter('some_filter_name', $result);

// $result = 'filtered by my_function2'
```