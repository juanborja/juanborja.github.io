---
layout: post
title:  "Notas sobre Codeception"
date:   2018-10-17 20:44:53 -0300
categories: node
---
# Primeros pasos

Instalar via composer

~~~php
composer require "codeception/codeception" --dev
~~~

Crear directorios y archivos basicos de test 

~~~php
./vendor/bin/codecept bootstrap
~~~

Ademas se debe configurar un base de datos de test en config/test.php y configurar los archivos .yml

Para crear test en yii advanced debe especificarse el entorno

~~~bash
php vendor/bin/codecept generate:test unit Example -- -c common
~~~

https://github.com/yiisoft/yii2-app-advanced/blob/master/docs/guide/start-testing.md

Comandos

https://codeception.com/docs/reference/Commands

https://phpunit.de/manual/6.5/en/writing-tests-for-phpunit.html