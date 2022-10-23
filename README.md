## requirements

1. Composer = https://getcomposer.org/download/
2. PHP/xampp versi 8.* = https://www.apachefriends.org/download.html
3. MongoDB versi 4.2 = https://www.mongodb.com/docs/v4.2/tutorial/install-mongodb-on-windows/

## Instalation
1. install project laravel = composer create-project laravel/laravel:^8.* crud
2. install package jenssegers = composer require jenssegers/mongodb:^3.8 --ignore-platform-req=ext-mongodb
3. Konfigurasi pada config/app.php 
   Jenssegers\Mongodb\MongodbServiceProvider::class,
4. Konfigurasi pada config/database.php
   'mongodb' => [
      'driver' => 'mongodb',
      'host' => env('MG_HOST', '127.0.0.1'),
      'port' => env('MG_PORT', 27017),
      'database' => env('MG_DATABASE', 'penjualan'),
      'username' => env('MG_USERNAME', ''),
      'password' => env('MG_PASSWORD', ''),
      'options' => [
        'database' => env('MG_DATABASE', 'penjualan'), // required with Mongo 3+
      ],
    ],
    'default' => env('DB_CONNECTION', 'mongodb'),
5. Konfigurasi file .env
    MG_HOST=127.0.0.1
    MG_PORT=27017
    MG_DATABASE=penjualan
    MG_USERNAME=
    MG_PASSWORD=


## Job List
1. Membuat database : penjualan, collection: kendaraans
2. Membuat Model "Kendaraan"
3. Membuat controller "Kendaraan"
4. Membuat ApiFormatter pada folder Helpers
5. Mendaftarkan url di routers api
   (get)http://127.0.0.1:8000/api/kendaraan --> test di postman berhasil
   (post)http://127.0.0.1:8000/api/kendaraan/store --> test di postman berhasil
   (get)http://127.0.0.1:8000/api/kendaraan/show/63554203ca25a70c220cf712 --> test di postman berhasil
   (post)http://127.0.0.1:8000/api/kendaraan/update/63554203ca25a70c220cf712 --> test di postman berhasil
   (delete)http://127.0.0.1:8000/api/kendaraan/delete/63554203ca25a70c220cf712 --> test di postman berhasil
6. 
