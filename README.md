# php_genderize
PHP5 lib for handling genderize.io gender recognition

Basicaly, it's for guessing the gender by a given first name and using [genderize.io](http://genderize.io).

Author: Bart Tyrant bartlomiej@tyranowski.pl
License: The MIT License http://www.opensource.org/licenses/mit-license.php

==Usage:==

The simplest case:

```php
$recognizer = new \Genderize\Base\Recognizer('Peter');

$peter = $recognizer->recognize();
print_r($peter);
```

will give:

Genderize\Base\Name Object
(
    [_name:protected] => Peter
    [_count:protected] => 4284
    [_gender:protected] => male
    [_probability:protected] => 1.00
)


--

Also, country and language filters are supported:

```php
$Recognizer = Genderize::factory();

$asia = $Recognizer->set_name('Asia')->recognize();
print_r($asia);

$asiaPL = $Recognizer->set_country_id('pl')->set_name('Asia')->recognize();
print_r($asiaPL);
```

... will print out:


Genderize\Base\Name Object
(
    [_name:protected] => Asia
    [_count:protected] => 97
    [_gender:protected] => female
    [_probability:protected] => 0.99
)
Genderize\Base\Name Object
(
    [_name:protected] => Asia
    [_count:protected] => 26
    [_gender:protected] => female
    [_probability:protected] => 1.00
    [_country_id] => PL
)
