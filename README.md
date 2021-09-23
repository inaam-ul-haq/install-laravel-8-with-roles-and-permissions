# Steps-to-setup-Laravel-8-Application-with-Roles-and-Auth
In this Repository you will get complete laravel 8 application with roles and auth. you can clone this repository and boom you setup your laravel application.

## System Requirements

* Windows 10
* XAMPP, WAMPP server
* PHP 7.4 or better
* nodejs
* composer

## 1. Create application
run this command. replace **your-app-name** with your app name

    composer create-project laravel/laravel your-app-name

[Larave Composer Link](https://laravel.com/docs/8.x/installation#installation-via-composer)

## 2. Change Directory

    cd your-app-name
     
## 3. create database

* go to [phpmyadmin](http://localhost/phpmyadmin/index.php?route=/server/databases&server=1)
* create new database

## 4. edit in .env file

    DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE=database_name
    DB_USERNAME=root
    DB_PASSWORD=
    
