# Laravel Docker

Laravel application "dockerized".

## Requirements

You will need Docker up & running on your machine. That's it!

## Stack

This will create the following containers:

- app: php & nginx are installed
- node: node & yarn are installed

**Notes: we use the same container for PHP & nginx for convenience, this way we can leverage the PHP-FPM socket and we only have to attach the volume once.**

## Docker commands can be long...

Typically, to run commands inside a container, you'd have to type a pretty long command, for example to run composer you would use:

```bash
$ docker run --rm -w /var/www/html app composer install
```

In this repository, we created a bash script to run commands more easily, for example the command above would be: 

```bash
$ ./develop composer install
```
## Bring the stack up!

 To bring the stack up and running, simply run:
 
 ```bash
$ ./develop up -d
```

To bring it down, run:

```bash
$ ./develop down
```

## Available command with ./develop

### Docker Compose

You can run any command that docker compose can support, for example: 

```bash
$ ./develop ps
$ ./develop up -d
$ ./develop down
```

### Composer

You can run any composer commands as well: 

```bash
$ ./develop composer install
$ ./develop composer require laravel/laravel
$ ./develop composer update
```

### Artisan

Because we are using Laravel here, you can also run any artisan commands as well: 

```bash
$ ./develop artisan key:generate
$ ./develop artisan make:controller PostsController
$ ./develop artisan migrate
```

### PHPUnit

PHPUnit is used to test the application (only the two default tests are available in this example application).
 
To run PHPUnit: 

```bash
$ ./develop phpunit
```

### npm

To run npm

```bash
$ ./develop npm install
```

### Yarn

If you prefer using Yarn:

```bash
$ ./develop yarn install
```