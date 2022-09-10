# install laravel 8 with roles and permissions
In this Repository you will get complete laravel 8 application with roles and auth. you can clone this repository and boom you setup your laravel application.

## System Requirements

* Windows 10
* XAMPP, WAMPP server [Download](https://www.apachefriends.org/download.html)
* PHP 7.4 or better
* nodejs [Download](https://nodejs.org/en/download/)
* composer [Download](https://getcomposer.org/Composer-Setup.exe)
* git bash [Download](https://git-scm.com/downloads)

I hope you already install xampp server

## 1. Install Git Bash

* Download git bash from this link -> [Download](https://git-scm.com/downloads)
* simply install
* after installation process complete
* open folder where you want to install your laravel application
* right click in folder and click in project folder and click on **Git Bash Here** option then run this command

## 2. install composer

* Download composer from this lnik -> [Download](https://getcomposer.org/Composer-Setup.exe)
* simply install

## 3. install nodeJs

* download link for nodejs -> [Download](https://nodejs.org/en/download/)
* simple install

# Setup Application

## 1. Create application
run this command. replace **your-app-name** with your app name

    composer create-project laravel/laravel:^8.0 your-app-name

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
    
## 4. install spatie package for assign roles and permissions

    composer require spatie/laravel-permission
    
[Spatie Package Website Link](https://spatie.be/docs/laravel-permission/v4/installation-laravel)

## 5. add this code in config/app.php in providers

    Spatie\Permission\PermissionServiceProvider::class,

## 6. run this in git bash

    php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider"
    
to publish the migration and permission.php file

## 7.  Set User Roles and Permissions

* add this file (UserSeeder) in database/seeders directory to create user roles [UserSeeder](https://www.mediafire.com/file/cdnz4kda8ky5zfv/UserSeeder.php/file)
* make changes in this file according to you need.

## 8. add this code in User Model 

    use Spatie\Permission\Traits\HasRoles;
    use Spatie\Permission\Models\Role;
    use Spatie\Permission\Models\Permission;
    use Auth;

add this under User class

    use HasFactory,HasRoles;
    
    protected $guarded = [];
    
## 9. add this code in http/kernal => routeMiddleware

    //roles and permission
    'role' => \Spatie\Permission\Middlewares\RoleMiddleware::class,
    'permission' => \Spatie\Permission\Middlewares\PermissionMiddleware::class,
    'role_or_permission' => \Spatie\Permission\Middlewares\RoleOrPermissionMiddleware::class,
    
## 10. run this command

    php artisan optimize:clear
    php artisan config:clear

## 11. create your table migration files if needed otherwise run this command 
    
    php artisan migrate:fresh --seed

## Now install Authentication (Login/Register Screens)

Run the bolow commands to install laravel ui package

    1. composer require laravel/ui:*
    2. php artisan ui bootstrap --auth you can use (vue/bootstrap/react)
    3. npm install && npm run dev
    4. php artisan ui:auth
    5. run laravel project with -> php artisan serve
    5. visit -> [http://127.0.0.1:8000/](http://127.0.0.1:8000/)

**Auther**: [Inaam ul haq](https://github.com/Inaam-ul-haq)

**YouTube:** [Techzhubb](https://www.youtube.com/c/techzhub)

**Instagram:** [Techzhubb](https://www.instagram.com/techzhubb/)

**Facebook:** [Techzhubb](https://www.facebook.com/techzhubb/)
