---

## 🧑‍💻 Praktikum 7 – PHP Dasar

---

**Nama:** ZAENAL MAULANA RIZKI

**NIM:** 312410332

**Kelas:** TI.2A.A.4

**Mata Kuliah:** Pemrograman Web1

**Dosen:** Agung Nugroho, S.Kom., M.Kom.

---
### TUGAS 

<img width="587" height="291" alt="image" src="https://github.com/user-attachments/assets/512e720c-7557-4af6-98e0-2ade8e657d0a" />

---

### 🔧 Persiapan

1. Install **XAMPP** dari [https://www.apachefriends.org](https://www.apachefriends.org)
2. Jalankan **Apache** dan **MySQL** melalui XAMPP Control Panel.
3. Buat folder baru bernama **`lab7_php_dasar`** di direktori:

   ```
   C:\xampp\htdocs\
   ```
4. Buka folder tersebut di **VS Code** atau text editor pilihanmu.

---

### 🧩 Langkah-langkah Praktikum

#### 1. Membuat File PHP Dasar

**File:** `php_dasar.php`

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>PHP Dasar</title>
</head>
<body>
    <h1>Belajar PHP Dasar</h1>
    <?php
        echo "Hello World";
    ?>
</body>
</html>
```

**Hasil:**
Tampilkan di browser melalui URL:
`http://localhost/lab7_php_dasar/php_dasar.php`
🖼️ *[Screenshot hasil tampilan Hello World]*

---

#### 2. Variabel PHP

**File:** `variable.php`

```php
<?php
$nim = "41231234";
$nama = "Fajar";
echo "NIM: $nim <br>";
echo "Nama: $nama";
?>
```

🖼️ *[Screenshot hasil tampilan variabel]*

---

#### 3. Predefine Variable `$_GET`

**File:** `latihan2.php`

```php
<?php
echo 'Selamat Datang ' . $_GET['nama'];
?>
```

Akses dengan URL:
`http://localhost/lab7_php_dasar/latihan2.php?nama=Fajar`

🖼️ *[Screenshot hasil tampilan]*

---

#### 4. Form Input

```php
<!DOCTYPE html>
<html>
<head><title>Form Input</title></head>
<body>
<h2>Form Input</h2>
<form method="post">
    <label>Nama: </label>
    <input type="text" name="nama">
    <input type="submit" value="Kirim">
</form>

<?php
echo 'Selamat Datang ' . $_POST['nama'];
?>
</body>
</html>
```

🖼️ *[Screenshot hasil form input]*

---

#### 5. Operator Aritmatika

```php
<?php
$gaji = 3000000;
$pajak = 0.1;
$thp = $gaji - ($gaji * $pajak);
echo "Gaji Sebelum Pajak = Rp. $gaji <br>";
echo "Gaji Bersih = Rp. $thp";
?>
```

🖼️ *[Screenshot hasil]*

---

#### 6. Struktur Kondisi dan Perulangan

**IF ELSE:**

```php
<?php
$hari = date("l");
if ($hari == "Sunday") echo "Minggu";
elseif ($hari == "Monday") echo "Senin";
else echo "Hari lainnya";
?>
```

**FOR Loop:**

```php
<?php
for ($i=1; $i<=10; $i++) {
    echo "Perulangan ke-$i <br>";
}
?>
```

🖼️ *[Screenshot hasil kondisi dan perulangan]*

---

### 🧮 Tugas Akhir

Buat program **Form Biodata** dengan input:

* Nama
* Tanggal Lahir
* Pekerjaan (pilihan dropdown)

Hitung **umur otomatis** berdasarkan tanggal lahir, dan tampilkan **gaji berdasarkan pekerjaan**.

**File:** `form_biodata.php`

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Form Biodata</title>
</head>
<body>
<h2>Form Biodata</h2>
<form method="post">
    Nama: <input type="text" name="nama"><br>
    Tanggal Lahir: <input type="date" name="tgl_lahir"><br>
    Pekerjaan:
    <select name="pekerjaan">
        <option value="Programmer">Programmer</option>
        <option value="Designer">Designer</option>
        <option value="Manager">Manager</option>
    </select><br><br>
    <input type="submit" value="Kirim">
</form>

<?php
if ($_POST) {
    $nama = $_POST['nama'];
    $tgl = $_POST['tgl_lahir'];
    $pekerjaan = $_POST['pekerjaan'];

    $umur = date_diff(date_create($tgl), date_create('today'))->y;

    switch ($pekerjaan) {
        case 'Programmer': $gaji = 8000000; break;
        case 'Designer': $gaji = 6000000; break;
        case 'Manager': $gaji = 10000000; break;
        default: $gaji = 0; break;
    }

    echo "<h3>Hasil Output:</h3>";
    echo "Nama: $nama <br>";
    echo "Umur: $umur tahun <br>";
    echo "Pekerjaan: $pekerjaan <br>";
    echo "Gaji: Rp. " . number_format($gaji, 0, ',', '.');
}
?>
</body>
</html>
```

🖼️ *[Screenshot hasil form dan output]*

---

### 📤 Pengumpulan

1. Commit semua file ke repository GitHub bernama **`Lab7Web`**
2. Tambahkan file `README.md` berisi laporan seperti ini.
3. Upload semua screenshot hasil ke dalam folder `screenshot/`
4. Kirim link repo GitHub ke e-learning ecampus.

---

Kalau kamu mau, aku bisa bantu buatin **struktur folder + file README.md siap upload ke GitHub** (format Markdown lengkap).
Apakah kamu mau saya buatkan file `.zip` atau isi `README.md`-nya langsung?
