ProcessWire Filter module

Overview:
=========

A developers module that adds a few functions to filter data in a similar way to WordPress' filters feature. 

Designed and tested on PW 2.5.3
http://processwire.com

Installation:
=============

1. Copy Filter.module to your site/modules/ directory.

2.
  a. Login into ProcessWire Admin > Modules. 
  b. Click "Check for new modules".
  c. Click "install" next to the new <module-name>.

Usage:
======

Once the module is installed you have 2 functions ready to be used anywhere in your app: `addFilter` and `applyFilter`

`
function my_function1($value)
{
	return 'filtered by my_function1';
}

function my_function2($value)
{
	return 'filtered by my_function2';
}

addFilter('some_filter_name', 'my_function1');
addFilter('some_filter_name', 'my_function2');

$result = 'default value';
$result = applyFilter('some_filter_name', $result);

// $result = 'filtered by my_function2'
`