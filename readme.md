
Configuration Database
-------------

Change your default database connection name in `config/database.php`:

```php
'default' => env('DB_CONNECTION', 'mongodb'),
```

And add a new mongodb connection:

```php
'mongodb' => [
    'driver'   => 'mongodb',
    'host'     => env('DB_HOST', 'localhost'),
    'port'     => env('DB_PORT', 27017),
    'database' => env('DB_DATABASE'),
    'username' => env('DB_USERNAME'),
    'password' => env('DB_PASSWORD'),
    'options'  => [
        'database' => 'admin' // sets the authentication database required by mongo 3
    ]
],
```

You can connect to multiple servers or replica sets with the following configuration:

```php
'mongodb' => [
    'driver'   => 'mongodb',
    'host'     => ['server1', 'server2'],
    'port'     => env('DB_PORT', 27017),
    'database' => env('DB_DATABASE'),
    'username' => env('DB_USERNAME'),
    'password' => env('DB_PASSWORD'),
    'options'  => [
		'replicaSet' => 'replicaSetName'
	]
],
```

Collection
-------------

Create collection 'users' on your database mongdb, or you can import json file on folder database users.json, and bellow one of example structure document users.json : 

```php
{ 
    "_id" : ObjectId("5975b2669a892009f3581472"), 
    "username" : "admin", 
    "display_name" : "Admin", 
    "email" : "admin@testemail.com", 
    "password" : "$2y$10$hjxLOf/sb2pZve.74YZ78e5PF9aCN.oBPw1E2irVDed7jnajMGYTq"
}
```


