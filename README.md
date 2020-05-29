## PHP Tips and Tricks for everyday use


        
Bit of error control 
```php
    // Turn off all error reporting
    error_reporting(0);
    
    // Report simple running errors
    error_reporting(E_ERROR | E_WARNING | E_PARSE);

    // Reporting E_NOTICE can be good too (to report uninitialized
    // variables or catch variable name misspellings ...)
    error_reporting(E_ERROR | E_WARNING | E_PARSE | E_NOTICE);

    // Report all errors except E_NOTICE
    // This is the default value set in php.ini
    error_reporting(E_ALL & ~E_NOTICE);
    // For PHP < 5.3 use: E_ALL ^ E_NOTICE

    // Report all PHP errors (see changelog)
    error_reporting(E_ALL);

    // Report all PHP errors
    error_reporting(-1);

    // Same as error_reporting(E_ALL);
    ini_set('error_reporting', E_ALL);
```

Just modify a .json file and write it back just like a snap 
```php
    $file = 'path/yoourfile.json';
    $json = json_decode(file_get_contents($file), true);
    $json['name'] = 'awesome';
    file_put_contents($file, json_encode($json, JSON_UNESCAPED_SLASHES | JSON_PRETTY_PRINT));
```

