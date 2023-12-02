# Lab9Web
# Lab9Web
## Profil
| Variable | Isi |
| -------- | --- |
| **Nama** | Ricky alfian saputra |
| **NIM** | 312210279 |
| **Kelas** | TI.22.A4 |
| **Mata Kuliah** | Pemrograman WEB |

# Intruksi Praktikum
1. Buatlah repository baru dengan nama Lab9Web.
2. Kerjakan semua latihan yang diberikan sesuai urutannya.
3. Screenshot setiap perubahannya.
4. Buatlah file README.md dan tuliskan penjelasan dari setiap langkah praktikum
beserta screenshotnya.
5. Commit hasilnya pada repository masing-masing.
6. Kirim URL repository pada.

# Pertanyaan dan Tugas
Implementasikan konsep modularisasi pada kode program praktikum 8 tentang
database, sehingga setiap halamannya memiliki template tampilan yang sama.

# Langkah-langkah Praktikum
## Buat file baru dengan nama header.php
```php
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>Contoh Modularisasi</title>
    <style>
        * {
            padding: 0;
            margin: 0;
            font-family: "Roboto", sans-serif;
        }

        body {
            margin: 0;
            padding: 0;
            height: 611px;
            /* Mengisi seluruh tinggi viewport */
            position: relative;
        }

        nav {
            width: 100%;
            background-color: rgb(44, 174, 253);
            padding: 0px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        nav>a {
            text-decoration: none;
            color: white;
            padding: 10px;
            margin: 10px 5px;
            border-radius: 5px;
        }

        nav>a:hover,
        nav>a.active {
            background-color: rgb(4, 149, 237);
        }

        header {
            text-align: center;
            padding: 30px;
        }

        header code {
            color: crimson;
        }

        .content {
            background-color: rgb(165, 165, 165);
            color: white;
            width: 90%;
            margin: auto;
            margin-bottom: 50px;
            padding: 20px;
            border-radius: 5px;
        }

        .content h2 {
            margin-bottom: 20px;

        }

        .content span {
            color: rgb(52, 55, 57);
        }

        footer {
            position: absolute;
            bottom: 0;
            width: 100%;
            background-color: rgb(44, 174, 253);
            text-align: center;
            padding: 20px 0;
            color: white;
        }
    </style>
</head>

<body>
    <div class="container">
        <header>
            <h1>Modularisasi Menggunakan Require</h1>
        </header>
        <nav>
            <a href="home.php">Home</a>
            <a href="about.php">Tentang</a>
            <a href="kontak.php">Kontak</a>
            <a href="data_barang.php">Data barang</a>
        </nav>
```
**Hasil :**

![1](https://github.com/ricky1211/Lab9Web/blob/main/LAB9/Screenshot%20(344).png?raw=true)

#### *Note :*
Include footer.

- require vs include:
  
require dan include digunakan untuk menyisipkan kode dari file eksternal ke dalam skrip PHP utama.
Perbedaan utama adalah, jika require tidak dapat menemukan atau memuat file yang diminta, itu akan menyebabkan kesalahan fatal dan menghentikan eksekusi skrip. 
Sementara include hanya akan menampilkan peringatan, dan eksekusi skrip akan tetap berlanjut.

## Buat file baru dengan nama footer.php
```php
<footer>
    <p>&copy; 2023, Informatika, Universitas Pelita Bangsa</p>
</footer>
</div>
</body>

</html>
```
#### *Note :*


## Buat file baru dengan nama home.php
```php
<?php require('header.php'); ?>
<div class="content">
    <h2>Ini Halaman <span>Home</span></h2>
    <p>Ini adalah bagian content dari halaman.</p>
</div>
<?php require('footer.php'); ?>
```
**Hasil :**

*Contoh di atas*

## Buat file baru dengan nama about.php
```php
<?php require('header.php'); ?>
<div class="content">
    <h2>Ini Halaman <span>About</span></h2>
    <p>Ini adalah bagian content dari halaman.</p>
</div>
<?php require('footer.php'); ?>
```
**Hasil :**

![2](https://github.com/ricky1211/Lab9Web/blob/main/LAB9/Screenshot%20(345).png?raw=true)

#### *Note :*
`<?php require('footer.php'); ?>` 
Pemanggilan require('footer.php'); adalah suatu pernyataan dalam bahasa pemrograman PHP yang digunakan untuk memasukkan dan menjalankan kode dari file footer. php ke dalam skrip PHP saat itu juga. Ini termasuk isi dari file tersebut seolah-olah menjadi bagian dari skrip yang memanggilnya.

## Buat file baru dengan nama kontak.php
```php
<?php require('header.php'); ?>
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        /* Kontak */
        .contact-form {
            width: 300px;
            margin: auto;
            margin-top: -40px;
        }

        .form-group label {
            display: block;
            margin-bottom: 1px;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 8px;
            box-sizing: border-box;
        }

        .form-group textarea {
            height: 100px;
        }

        .submit-btn {
            width: 100%;
            padding: 10px;
            background-color: rgb(44, 174, 253);
            color: white;
            border: none;
            cursor: pointer;
            border-radius: 20px;
        }

        .submit-btn:hover {
            background-color: rgb(138, 142, 146);
        }
    </style>
</head>

<body>
    <div class="content">
        <h2>Ini Halaman <span>Kontak</span></h2>
        <p>Ini adalah bagian content dari halaman.</p>
    </div>
    <div class="contact-form" id="kontak"> <!--Kontak-->
        <h2>Contact Us</h2>
        <form action="#" method="post">
            <div class="form-group">
                <label for="name">Nama:</label>
                <input type="text" id="name" name="name" required>
            </div>
            <div class="form-group">
                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required>
            </div>
            <div class="form-group">
                <label for="message">Pesan:</label>
                <textarea id="message" name="message" required></textarea>
            </div>
            <button type="submit" class="submit-btn">Kirim Pesan</button>
        </form>
    </div>
</body>

</html>
<?php require('footer.php'); ?>
```
**Hasil :**

![2](https://github.com/ricky1211/Lab9Web/blob/main/LAB9/Screenshot%20(342).png?raw=true)

#### *Note :*

## Buat file baru dengan nama kontak.php

- **[link File 1](https://github.com/GilarSumilar/Lab9Web/blob/main/data_barang.php)**
- **[link File 2](https://github.com/GilarSumilar/Lab9Web/blob/main/tambah_barang.php)**
- **[link Filae 3](https://github.com/GilarSumilar/Lab9Web/blob/main/ubah.php)**
  
**Hasil :**

![2](https://github.com/ricky1211/Lab9Web/blob/main/LAB9/Screenshot%20(343).png?raw=true)

#### *Note :*


**[---KEMBALI-->](#Profil)**

