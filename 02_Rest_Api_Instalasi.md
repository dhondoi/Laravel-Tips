# Instalasi Laravel Sanctum & Spatie Permission
A. Setup Laravel Sanctum (API Auth)
Di Laravel 11, routing API dan Sanctum diinstal secara terintegrasi menggunakan satu perintah:

```Bash
php artisan install:api
```
Perintah ini akan secara otomatis mempublikasikan migrasi token dan membuat file routes/api.php.

B. Setup Spatie Permission
Instal paket spatie/laravel-permission dan publikasikan konfigurasi migrasinya:

```Bash
composer require spatie/laravel-permission
php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider"
```
Jalankan migrasi untuk membuat tabel bawaan (users, personal_access_tokens, roles, permissions, dll.):

```Bash
php artisan migrate
```
