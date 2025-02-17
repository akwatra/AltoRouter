# AltoRouter [![Build Status](https://api.travis-ci.org/dannyvankooten/AltoRouter.png)](http://travis-ci.org/dannyvankooten/AltoRouter) [![Latest Stable Version](https://poser.pugx.org/altorouter/altorouter/v/stable.svg)](https://packagist.org/packages/altorouter/altorouter) [![License](https://poser.pugx.org/altorouter/altorouter/license.svg)](https://packagist.org/packages/altorouter/altorouter) [![Code Climate](https://codeclimate.com/github/dannyvankooten/AltoRouter/badges/gpa.svg)](https://codeclimate.com/github/dannyvankooten/AltoRouter) [![Test Coverage](https://codeclimate.com/github/dannyvankooten/AltoRouter/badges/coverage.svg)](https://codeclimate.com/github/dannyvankooten/AltoRouter)
AltoRouter is a small but powerful routing class for PHP 5.3+, heavily inspired by [klein.php](https://github.com/chriso/klein.php/).

> ## This fork Fixed trailing slash issue.
> ### Now you need not to worry about user forgot trailing slash to uri.

```php

$router->map( 'GET', '/tests' , function()  {

	echo 'Hello world.';
  
});

or 

$router->map( 'GET', '/tests/' , function()  {

	echo 'Hello world.';
  
});

### Both same, use any one. will save half time and file size. ###

```


> ## Also added support for call direct get or post request method rather map on router object.
> ### Hope this will save time and more verbose.

```php

$router->get('/test_get' , function()  {

	echo 'Hello world. from GET Request Method';
  
});	

$router->post('/test_post' , function()  {

	echo 'Hello world. from POST Request Method';
  
});	
```

```php
$router = new AltoRouter();

// map homepage
$router->map( 'GET', '/', function() {
    require __DIR__ . '/views/home.php';
});

// dynamic named route
$router->map( 'GET|POST', '/users/[i:id]/', function( $id ) {
  $user = .....
  require __DIR__ . '/views/user/details.php';
}, 'user-details' );

// echo URL to user-details page for ID 5
echo $router->generate( 'user-details', array( 'id' => 5 ) ); // Output: "/users/5"
```

## Features

* Can be used with all HTTP Methods
* Dynamic routing with named route parameters
* Reversed routing
* Flexible regular expression routing (inspired by [Sinatra](http://www.sinatrarb.com/))
* Custom regexes

## Getting started

You need PHP >= 5.3 to use AltoRouter, although we highly recommend you [use an officially supported PHP version](https://secure.php.net/supported-versions.php).

- [Install AltoRouter](http://altorouter.com/usage/install.html)
- [Rewrite all requests to AltoRouter](http://altorouter.com/usage/rewrite-requests.html)
- [Map your routes](http://altorouter.com/usage/mapping-routes.html)
- [Match requests](http://altorouter.com/usage/matching-requests.html)
- [Process the request your preferred way](http://altorouter.com/usage/processing-requests.html)

## Contributors
- [Danny van Kooten](https://github.com/dannyvankooten)
- [Koen Punt](https://github.com/koenpunt)
- [John Long](https://github.com/adduc)
- [Niahoo Osef](https://github.com/niahoo)

## License

MIT License

Copyright (c) 2012 Danny van Kooten <hi@dannyvankooten.com>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
