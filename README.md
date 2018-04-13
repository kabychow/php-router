PHP Router
====================

Sample usage
-----------------------------
```php
<?php

require 'Router.php';
$router = new Router();

$router->route('GET', '/', function() {
  return 'Hello World';
});

$router->route('POST', '/user/[i:id]', function($id) {
  $user = [
    'id' => $id
  ];
  return json_encode($user);
});

$router->route('PUT|PATCH', '/user/[a:name]', function($name) {
  $user = [
    'name' => $name
  ];
  return json_encode($user);
});

$router->route('DELETE', '/user/[i:id]', function($id) {
  return 'Error while deleting user with id ' . $id;
});

$router->run();
```
