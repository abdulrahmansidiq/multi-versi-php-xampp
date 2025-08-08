# 🚀 INSTALASI & SETTING MULTI VERSI PHP DALAM 1 XAMPP

<div align="center">

![Project Logo](https://www.apachefriends.org/images/xampp-logo-ac950edf.svg)

![⭐GitHub stars](https://img.shields.io/github/stars/abdulrahmansidiq/multi-versi-php-xampp?style=flat)
![👁️GitHub watchers](https://img.shields.io/github/watchers/abdulrahmansidiq/multi-versi-php-xampp?style=flat)
![🍴GitHub forks](https://img.shields.io/github/forks/abdulrahmansidiq/multi-versi-php-xampp?style=flat)
![📥GitHub all releases](https://img.shields.io/github/downloads/abdulrahmansidiq/multi-versi-php-xampp/total?style=flat)

</div>

## 📚 DOKUMENTASI

**Disini saya akan berikan solusi terbaik buat kalian untuk menambahkan multi versi php di 1 XAMPP, dan ini juga sudah banyak digunakan oleh para programmer dan salah satunya saya sendiri. karna memang sangat efektif tanpa harus install ulang XAMPP.**

**Silahkan download versi php yang kamu perlukan dibawah ini dan sudah saya setting di file php.ini dan ikuti langkah-langkahnya dibawah ini untuk konfigurasi di control panel XAMPP**

---

### 🔧 SETTING EXTENSION PHP XAMPP

---

1. **Buka folder C:/xampp/php/NAMA-FOLDER-VERSI-PHP (PHP5_6 / PHP7_4, dll)**
2. **Ubah format file php.ini.production menjadi php.ini**
3. **Aktifkan extension default dibawah dengan cara menghapus komentar yang ditandai tanda ;**
4. **Contoh ; extension_dir ubah menjadi extension_dir**
5. **Daftar extensi yang perlu diaktifkan dibawah ini:**
   - extension_dir = "ext"
   - extension=bz2
   - extension=curl
   - extension=ftp
   - extension=fileinfo
   - extension=gd2
   - extension=gettext
   - extension=gmp
   - extension=intl
   - extension=mbstring
   - extension=exif
   - extension=mysqli
   - extension=openssl
   - extension=pdo_mysql
   - extension=pdo_sqlite
   - extension=php_sqlite3

---

### 🔧 SETTING APACHE XAMPP

---

### 🎯 LANGKAH-LANGKAH

1. **BUKA CONTROL PANEL**
   ![gambar1](https://github.com/abdulrahmansidiq/multi-versi-php-xampp/blob/main/1.png)

2. **KLIK TOMBOL CONFIG APACHE**
   ![gambar2](https://github.com/abdulrahmansidiq/multi-versi-php-xampp/blob/main/2.png)

3. **TEMPELKAN SCRIPT DI FILE CONFIG APACHE "httpd-xampp.conf" YANG ADA DIBAWAH INI SESUAI KEINGINAN KALIAN**
   ![gambar3](https://github.com/abdulrahmansidiq/multi-versi-php-xampp/blob/main/3.png)

4. **JALANKAN APACHE DAN MYSQL DI CONTROL PANEL XAMPP**
   ![gambar4](https://github.com/abdulrahmansidiq/multi-versi-php-xampp/blob/main/4.png)

---

### 🚀 VERSI PHP

---

### PHP 5.6 (2014)

- Ini versi terakhir di keluarga PHP 5 sebelum loncat ke PHP 7.
- Fitur penting:
  - Variadic functions → bikin fungsi terima banyak parameter tanpa repot.
  - Exponentiation operator (\*\*) → gampang buat perhitungan pangkat.
  - phpdbg → debugger bawaan PHP.
- Kelemahan: udah lumayan tua, performa masih kalah jauh sama versi baru.

#### 📥 Download : [PHP 5.6](https://github.com/abdulrahmansidiq/multi-versi-php-xampp/blob/main/php%20version/php5_6.zip)

```httpd-xampp.conf
# PHP5_6
 ScriptAlias /php5_6/ "C:/xampp/php5_6/"
<Directory "C:/xampp/php5_6">
    AllowOverride None
    Options None
    Require all denied
    <Files "php-cgi.exe">
          Require all granted
    </Files>
</Directory>

Listen 8056
<VirtualHost *:8056>
    UnsetEnv PHPRC
    <FilesMatch "\.php$">
        php_flag engine off
        SetHandler application/x-httpd-php5_6
        Action application/x-httpd-php5_6 "/php5_6/php-cgi.exe"
    </FilesMatch>
</VirtualHost>
```

---

### PHP 7.4 (2019)

- Typed properties → properti di class bisa punya tipe data.
- Arrow functions (fn() =>) → fungsi singkat ala JavaScript.
- Preloading → loading kode di awal untuk boost performa.
- Ini versi yang banyak dipakai sebelum migrasi ke PHP 8.

#### 📥 Download : [PHP 7.4](https://github.com/abdulrahmansidiq/multi-versi-php-xampp/blob/main/php%20version/php7_4.zip)

```httpd-xampp.conf
# PHP7_4
 ScriptAlias /php7_4/ "C:/xampp/php7_4/"
<Directory "C:/xampp/php7_4">
    AllowOverride None
    Options None
    Require all denied
    <Files "php-cgi.exe">
          Require all granted
    </Files>
</Directory>

Listen 8074
<VirtualHost *:8074>
    UnsetEnv PHPRC
    <FilesMatch "\.php$">
        php_flag engine off
        SetHandler application/x-httpd-php7_4
        Action application/x-httpd-php7_4 "/php7_4/php-cgi.exe"
    </FilesMatch>
</VirtualHost>
```

---

### PHP 8.0 (2020)

- JIT Compiler → eksekusi kode PHP lebih cepat (terutama perhitungan kompleks).
- Union types → parameter/return bisa punya beberapa tipe data.
- Named arguments → bisa tentuin argumen berdasarkan nama parameter.
- Match expression → alternatif switch yang lebih rapih.

#### 📥 Download : [PHP 8.0](https://github.com/abdulrahmansidiq/multi-versi-php-xampp/blob/main/php%20version/php8_0.zip)

```httpd-xampp.conf
# PHP8_0
 ScriptAlias /php8_0/ "C:/xampp/php8_0/"
<Directory "C:/xampp/php8_0">
    AllowOverride None
    Options None
    Require all denied
    <Files "php-cgi.exe">
          Require all granted
    </Files>
</Directory>

Listen 8080
<VirtualHost *:8080>
    UnsetEnv PHPRC
    <FilesMatch "\.php$">
        php_flag engine off
        SetHandler application/x-httpd-php8_0
        Action application/x-httpd-php8_0 "/php8_0/php-cgi.exe"
    </FilesMatch>
</VirtualHost>
```

---

### PHP 8.1 (2021)

- Enums → bikin daftar nilai tetap yang aman.
- Readonly properties → properti yang gak bisa diubah setelah di-set.
- Fibers → bikin async programming lebih mudah.

#### 📥 Download : [PHP 8.1](https://github.com/abdulrahmansidiq/multi-versi-php-xampp/blob/main/php%20version/php8_1.zip)

```httpd-xampp.conf
# PHP8_2
 ScriptAlias /php8_1/ "C:/xampp/php8_1/"
<Directory "C:/xampp/php8_1">
    AllowOverride None
    Options None
    Require all denied
    <Files "php-cgi.exe">
          Require all granted
    </Files>
</Directory>

Listen 8081
<VirtualHost *:8081>
    UnsetEnv PHPRC
    <FilesMatch "\.php$">
        php_flag engine off
        SetHandler application/x-httpd-php8_1
        Action application/x-httpd-php8_1 "/php8_1/php-cgi.exe"
    </FilesMatch>
</VirtualHost>
```

---

### PHP 8.2 (2022)

- Readonly classes → semua properti otomatis readonly.
- Disallow dynamic properties → larang properti yang dibuat sembarangan.
- True type → tipe data boolean yang spesifik ke true.

#### 📥 Download : [PHP 8.2](https://github.com/abdulrahmansidiq/multi-versi-php-xampp/blob/main/php%20version/php8_2.zip)

```httpd-xampp.conf
# PHP8_2
 ScriptAlias /php8_2/ "C:/xampp/php8_2/"
<Directory "C:/xampp/php8_2">
    AllowOverride None
    Options None
    Require all denied
    <Files "php-cgi.exe">
          Require all granted
    </Files>
</Directory>

Listen 8082
<VirtualHost *:8082>
    UnsetEnv PHPRC
    <FilesMatch "\.php$">
        php_flag engine off
        SetHandler application/x-httpd-php8_2
        Action application/x-httpd-php8_2 "/php8_2/php-cgi.exe"
    </FilesMatch>
</VirtualHost>
```

---

### PHP 8.3 (2023)

- Typed class constants → konstanta di class punya tipe data.
- json_validate() → cek JSON valid atau enggak dengan mudah.
- Peningkatan performa & keamanan.

#### 📥 Download : [PHP 8.3](https://github.com/abdulrahmansidiq/multi-versi-php-xampp/blob/main/php%20version/php8_3.zip)

```httpd-xampp.conf
# PHP8_3
 ScriptAlias /php8_3/ "C:/xampp/php8_3/"
<Directory "C:/xampp/php8_3">
    AllowOverride None
    Options None
    Require all denied
    <Files "php-cgi.exe">
          Require all granted
    </Files>
</Directory>

Listen 8083
<VirtualHost *:8083>
    UnsetEnv PHPRC
    <FilesMatch "\.php$">
        php_flag engine off
        SetHandler application/x-httpd-php8_3
        Action application/x-httpd-php8_3 "/php8_3/php-cgi.exe"
    </FilesMatch>
</VirtualHost>
```

---

### PHP 8.4 (2022)

- Fokus di efisiensi & fitur modern.
- New async features → bikin proses paralel lebih gampang.
- Readonly amendments → fleksibilitas readonly makin luas.
- Lebih hemat memori & lebih cepat dari 8.3.

#### 📥 Download : [PHP 8.4](https://github.com/abdulrahmansidiq/multi-versi-php-xampp/blob/main/php%20version/php8_4.zip)

```httpd-xampp.conf
# PHP8_4
 ScriptAlias /php8_4/ "C:/xampp/php8_4/"
<Directory "C:/xampp/php8_4">
    AllowOverride None
    Options None
    Require all denied
    <Files "php-cgi.exe">
          Require all granted
    </Files>
</Directory>

Listen 8084
<VirtualHost *:8084>
    UnsetEnv PHPRC
    <FilesMatch "\.php$">
        php_flag engine off
        SetHandler application/x-httpd-php8_4
        Action application/x-httpd-php8_4 "/php8_4/php-cgi.exe"
    </FilesMatch>
</VirtualHost>
```

---

### 💡 KESIMPULAN

- PHP 5.6 → jadul, udah gak direkomendasi.
- PHP 7.x → stabil & cepat, tapi udah mulai ditinggalkan.
- PHP 8.x → masa depan PHP, modern, kencang, aman, dan siap bersaing.

---

<div align="center">
⭐ Jangan lupa beri star jika proyek ini membantu! ⭐
<br />
Made with ❤️ by Abdul Rahman Sidiq
</div>

---
