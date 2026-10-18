# 🚀 Panduan Hosting Laravel dari GitHub ke VPS Ubuntu

<p align="center">
  <img src="images/laravel-logo.png" alt="Laravel Logo" width="160" />
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</p>

<p align="center">
  <strong>Web Dokumentasi Interaktif & Panduan Deployment Terpadu</strong><br>
  Deploy aplikasi Laravel dari repository GitHub ke Virtual Private Server (VPS) Ubuntu dengan Nginx, PHP-FPM, MySQL, dan SSL Let's Encrypt secara otomatis dan anti-salah.
</p>

---

## 📖 Tentang Aplikasi

Website ini merupakan aplikasi dokumentasi interaktif satu halaman (*single-page interactive documentation*) yang dirancang khusus untuk mempermudah developer dalam menghosting proyek Laravel ke server VPS Ubuntu.

Dilengkapi dengan **Generator Parameter Proyek Realtime**, Anda cukup memasukkan detail proyek (URL Git, nama folder, domain, versi PHP, konfigurasi database, nama aplikasi), dan seluruh perintah terminal serta file konfigurasi (`.env`, Virtual Host Nginx, MySQL queries) akan langsung ter-generate secara otomatis dan siap disalin dengan satu klik.

---

## ✨ Fitur Unggulan

| Fitur | Deskripsi |
| :--- | :--- |
| **⚡ Generator Parameter Real-time** | Menyesuaikan perintah Git, Nginx, PHP, dan MySQL secara dinamis tanpa perlu edit manual baris per baris. |
| **🐘 Pilihan Versi PHP Lengkap** | Mendukung PHP 8.4, 8.3 (Stable), 8.2 (LTS), 8.1, 8.0, hingga 7.4 (Legacy). Konfigurasi Nginx dan CLI otomatis tersinkronisasi. |
| **📋 Salin Perintah Cepat (*1-Click Copy*)** | Setiap blok kode terminal memiliki tombol salin ke clipboard dengan fallback andal. |
| **✅ Checklist Progres Interaktif** | Lacak progres deployment langkah demi langkah dengan status tersimpan otomatis di browser (`localStorage`). |
| **🔍 Fitur Pencarian Cepat** | Filter perintah terminal atau kata kunci penting secara instan. |
| **🎨 Tampilan Bersih & Minimalis** | Desain bertema putih modern berbasis Tailwind CSS, ringan, cepat, dan tanpa dependensi icon eksternal. |

---

## 🛠️ Stack Teknologi Server yang Digunakan

- **OS Server:** Ubuntu 22.04 LTS / 24.04 LTS
- **Web Server:** Nginx (Reverse Proxy & FastCGI)
- **Bahasa Pemrograman:** PHP (versi 7.4 s/d 8.4 dengan PHP-FPM)
- **Database:** MySQL Server 8.0+
- **Manajemen Dependensi:** Composer & Node.js (LTS v20)
- **Keamanan & SSL:** Certbot Let's Encrypt (HTTPS otomatis)

---

## 📌 7 Langkah Utama Alur Deployment

```
[1. Persiapan Server] ➔ [2. Clone Repo Git] ➔ [3. Setup MySQL] ➔ [4. Setup .env & Migrasi]
                                                                        ↓
[7. Pasang SSL HTTPS] 🠔 [6. Konfigurasi Nginx] 🠔 [5. Permission & Cache]
```

1. **Persiapan Server & Instalasi Dependensi**  
   Update sistem Ubuntu, pasang PPA resmi PHP (`ppa:ondrej/php`), PHP-FPM pilihan, Nginx, MySQL Server, Composer, dan Node.js LTS.

2. **Clone Repo GitHub & Build Aset**  
   Clone repositori ke `/var/www/`, pasang dependensi backend via `composer install --no-dev --optimize-autoloader`, dan compile frontend menggunakan `npm run build`.

3. **Konfigurasi Database MySQL**  
   Buat database dan user MySQL khusus dengan password kuat serta hak akses penuh (`GRANT ALL PRIVILEGES`).

4. **Setup File `.env`, App Key & Migrasi**  
   Salin `.env.example` ke `.env`, generate `APP_KEY`, sesuaikan kredensial database & `APP_URL`, lalu jalankan `php artisan migrate --force`.

5. **Pengaturan Permission & Optimasi Cache**  
   Beri kepemilikan user web server `www-data` pada folder `storage` & `bootstrap/cache`, serta jalankan caching konfigurasi, route, dan view untuk performa maksimal.

6. **Konfigurasi Nginx Server Block (Virtual Host)**  
   Setup konfigurasi Nginx untuk mengarahkan root direktori ke `/public`, integrasi socket PHP-FPM, uji konfigurasi dengan `nginx -t`, dan reload Nginx.

7. **Aktivasi SSL Gratis dengan Let's Encrypt (Certbot)**  
   Pasang sertifikat SSL otomatis menggunakan Certbot Nginx dan perbarui `APP_URL` menjadi `https://`.

---

## 🌐 Akses Website (Live Demo)

Aplikasi dokumentasi interaktif ini sudah di-deploy dan dapat diakses langsung secara online melalui:

👉 **[https://masmas99.github.io/caradeploylaravelkevps/](https://masmas99.github.io/caradeploylaravelkevps/)**

---

<p align="center">
  Dibuat untuk mempermudah proses deployment Laravel yang cepat, aman, dan terstandarisasi.
</p>
