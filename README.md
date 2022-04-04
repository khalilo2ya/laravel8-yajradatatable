<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400"></a></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/d/total.svg" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/v/stable.svg" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/license.svg" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains over 1500 video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the Laravel [Patreon page](https://patreon.com/taylorotwell).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Cubet Techno Labs](https://cubettech.com)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[Many](https://www.many.co.uk)**
- **[Webdock, Fast VPS Hosting](https://www.webdock.io/en)**
- **[DevSquad](https://devsquad.com)**
- **[OP.GG](https://op.gg)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).





How to do first steps 


#####################################
urls:
https://github.com/yajra/laravel-datatables
https://jquery.com/
https://getbootstrap.com/
https://github.com/DataTables/DataTables
https://sweetalert2.github.io/
https://github.com/CodeSeven/toastr
#####################################

prerequirements:

composer

php7+ 

NodeJs

####################################
steps and codes:
**************************
1- first we create our project
composer create-project laravel/laravel=8 laravel8-yajradatatable --prefer-dist
**************************
2- cd laravel8-yajradatatable
3- lets test our project
php artisan serve
the adress :127.0.0.1:8000 
**************************

3- edit .env file and set the database name in our project lets say 'laravel8-yajradatatable'
DB_DATABASE=laravel8-yajradatatable
DB_USERNAME=root
DB_PASSWORD=

4- we should create an empty database using mysql phpmyadmin called laravel8-yajradatatable 
*************************
5- we start to set prerequirements and utilities for our projects

*** to use datatables yajra ***
https://github.com/yajra/laravel-datatables
composer require yajra/laravel-datatables-oracle:"~9.0"

config/app.php
'providers' => [
    ...,
    Yajra\DataTables\DataTablesServiceProvider::class,
]

'aliases' => [
    ...,
    'DataTables' => Yajra\DataTables\Facades\DataTables::class,
]

php artisan vendor:publish --provider="Yajra\DataTables\DataTablesServiceProvider"

***  download jquery scripts ****
https://jquery.com/
Download the compressed, production jQuery 3.6.0
save the file

*** get the bootstrap ***
https://getbootstrap.com/
choose v4.6 and download 

***   datatables ****
https://github.com/DataTables/DataTables
chosse tag release and download zip

*** sweet alert ****
https://sweetalert2.github.io/
https://github.com/sweetalert2/sweetalert2/releases/tag/v11.0.18
choose 11.0.18
downlad sweetalert2.min.css and sweetalert2.min.js
*** toastr github ****
https://github.com/CodeSeven/toastr
download the last version 2.1.1

==>
we create folders in public in our projets
bootstrap - datatbale - jquey - sweetalert2 - toastr
we copy only js and css file from the downloaded files
********************************

6- we start coding our project laravel by begining create controller countries
php artisan make:controller CountriesController
in the folder app/http/controllers you will see new file created CountriesController.php
7- seting the route 

use App\Http\Controllers\CountriesController;
Route::get('/countries-list',[CountriesController::class, 'index'])->name('countries.list');
as we see we create a route calling the function index from Countriescontroller so we have to creat the index function in the controller and also the view countries-list we have to create it in blade (resources/views)
this is how our blade file looks like countries-list.blade.php:
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Countries List</title>
</head>
<body>
    hello countries
</body>
</html>

8- create our model and table countries
php artisan make:model Country -m

