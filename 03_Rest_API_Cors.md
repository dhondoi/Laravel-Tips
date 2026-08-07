- Karena ini adalah API, Nginx cukup meneruskan traffic-nya saja, dan sebaiknya urusan CORS (siapa saja yang boleh mengakses API Anda) diatur langsung dari dalam Laravel agar lebih fleksibel.
- Setelah Anda menginstal API di atas, pastikan Anda mengatur file konfigurasi CORS. Anda bisa mempublikasikan konfigurasinya dengan:
```Bash
php artisan config:publish cors
```
- Lalu buka file config/cors.php dan pastikan bagian ini diatur sesuai kebutuhan frontend Anda:
```PHP
    'paths' => ['api/*', 'sanctum/csrf-cookie'], // Endpoint yang diizinkan CORS
    'allowed_methods' => ['*'],                  // Izinkan GET, POST, dll
    'allowed_origins' => ['https://frontendanda.com'], // Ganti dengan domain frontend Anda, atau ['*'] untuk publik
    'allowed_origins_patterns' => [],
    'allowed_headers' => ['*'],
    'exposed_headers' => [],
    'max_age' => 0,
    'supports_credentials' => true,              // Penting jika frontend pakai cookie/session
```
