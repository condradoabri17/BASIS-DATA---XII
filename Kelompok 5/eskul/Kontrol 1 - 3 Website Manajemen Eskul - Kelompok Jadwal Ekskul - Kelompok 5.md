# Kontrol - 1

Pada praktik sebelumnya kita telah membuat database sekolah dimana database tiap kelompok disatukan ke dalam 1 database besar yang berelasi. Saat in kami akan merealisasikan databse tersebut menjadi sebuah website utuh, dan kami akan merealisasikan website ini untuk bagian table ekskul saja. berikut adalah 2 fitur yang telah kami buat untuk sementara:
## Fitur Data Siswa
### Gambar Fitur:
![[Fitur-1.png]]

### penjelasannya:
#### Deskripsi Fitur
Fitur ini dirancang untuk menampilkan dan mengelola data siswa dalam sistem. Fitur ini dilengkapi dengan kemampuan CRUD (Create, Read, Update, Delete) yang memungkinkan admin untuk:

- *Menambah Data Siswa*: Admin dapat memasukkan informasi siswa baru ke dalam sistem, termasuk nama, umur, kelas, dan informasi penting lainnya.
  
- *Menghapus Data Siswa*: Admin memiliki opsi untuk menghapus data siswa yang tidak lagi relevan atau diperlukan.

- *Mengedit Data Siswa*: Admin dapat memperbarui informasi siswa yang sudah ada untuk memastikan data selalu akurat dan up-to-date.
#### Integrasi dengan Ekstrakurikuler
Data siswa yang telah dikelola dalam fitur ini akan terhubung langsung dengan tabel siswaekskul. Tabel ini berfungsi untuk mencatat pendaftaran siswa ke berbagai ekstrakurikuler yang tersedia. Dengan demikian, admin dapat dengan mudah melihat siswa yang telah mendaftar dan mengikuti kegiatan ekstrakurikuler yang ditawarkan.
#### Akses Fitur
Fitur ini hanya dapat diakses oleh admin. Hal ini bertujuan untuk menjaga keamanan dan integritas data siswa, serta memastikan bahwa hanya pengguna yang berwenang yang dapat melakukan perubahan pada informasi yang sensitif.
#### Kesimpulan
Fitur manajemen data siswa ini merupakan komponen penting dalam sistem, memberikan kemudahan bagi admin untuk mengelola informasi siswa dengan efisien dan efektif, sekaligus mendukung proses pendaftaran ekstrakurikuler.
## Fitur Data Pembina
### Gambar Fitur:
![[Fitur-2.png]]
### penjelasannya:
#### Deskripsi Fitur
Fitur ini dirancang untuk menampilkan dan mengelola data Pembina ekstrakurikuler dalam sistem. Dilengkapi dengan kemampuan CRUD (Create, Read, Update, Delete), fitur ini memungkinkan admin untuk:

- *Menambah Data Pembina*: Admin dapat memasukkan informasi Pembina baru, termasuk nama, jabatan, dan kontak yang relevan.
- *Menghapus Data Pembina*: Admin memiliki opsi untuk menghapus data Pembina yang sudah tidak aktif atau tidak relevan.
- *Mengedit Data Pembina*: Admin dapat memperbarui informasi Pembina yang ada untuk memastikan data tetap akurat dan terkini.
#### Akses Fitur
Fitur ini hanya dapat diakses oleh admin. Hal ini bertujuan untuk menjaga keamanan data dan memastikan bahwa hanya pengguna yang berwenang yang dapat melakukan perubahan pada informasi Pembina.
#### Kesimpulan
Fitur manajemen data Pembina ekstrakurikuler ini sangat penting untuk mendukung pengelolaan dan pengawasan kegiatan ekstrakurikuler. Dengan adanya fitur ini, admin dapat dengan mudah mengelola informasi Pembina, sehingga proses administrasi ekstrakurikuler dapat berjalan dengan lebih efektif.


# Kontrol - 2
## 1.  *Deskripsi Fitur*
### Login 
- Admin : Kelola Siswa, Kelola Eskul, Kelola Pembina, Dan Kelola Profile Eskul.
- Siswa : Melihat Dasboard Yang Menampilkan Total Siswa, Total Eskul, Total Pembina.
### Manajemen Siswa
Admin Dapat : 
- Menambah, Mengedit, Menghapus Data Siswa.
## 2.  *Struktur Database*

| Tabel        | Penjelasan                                        |
| ------------ | ------------------------------------------------- |
| siswa        | Menyimpan data siswa                              |
| eskul        | menyimpan data eskul                              |
| profil_eskul | menyimpan detail eskul                            |
| pembina      | menyimpan data pembina                            |
| siswa_eskul  | menyimpan data siswa yang masuk di eskul tertentu |

## 3.  *Agregasi (GROUP BY & HAVING)*
### Contoh Query:
```sql
<?php
 // Query untuk mendapatkan daftar anggota eskul berdasarkan eskul_id
$queryAnggota = mysqli_query(
 $koneksi,
 "SELECT es.id, s.nama_siswa, es.tanggal_gabung 
  FROM eskul_siswa es
 JOIN siswa s ON es.id_siswa = s.id_siswa
  WHERE es.eskul_id = '$eskul_id'"
 );

// Query untuk menghitung total anggota eskul berdasarkan eskul_id
 $queryTotal = mysqli_query(
 $koneksi,
 "SELECT COUNT(*) AS total_anggota 
 FROM eskul_siswa 
   WHERE eskul_id = '$eskul_id'"
    );
$totalAnggota = mysqli_fetch_assoc($queryTotal)['total_anggota'];
                                ?>
```

### Penjelasan:
***1. Mengambil Daftar Anggota Ekstrakurikuler*** 
- Query pertama digunakan untuk mengambil data anggota ekstrakurikuler berdasarkan eskul_id.  
- Data diambil dari tabel eskul_siswa, yang menyimpan informasi siswa yang tergabung dalam suatu ekstrakurikuler.  
- Tabel eskul_siswa di-join dengan tabel siswa menggunakan id_siswa untuk mendapatkan nama_siswa.  
- Kolom yang diambil dari query ini adalah:  
  - id dari tabel eskul_siswa  
  - nama_siswa dari tabel siswa  
  - tanggal_gabung, yaitu tanggal siswa tersebut bergabung dalam ekstrakurikuler  

**2. Menghitung Total Anggota***
- Query kedua bertujuan untuk menghitung jumlah total siswa yang tergabung dalam ekstrakurikuler tertentu.  
- Query ini menggunakan fungsi agregat COUNT(*) untuk menghitung jumlah baris dalam tabel eskul_siswa yang memiliki eskul_id tertentu.  
- Hasil perhitungan diambil menggunakan mysqli_fetch_assoc() dan disimpan dalam variabel untuk digunakan dalam tampilan.  
### Kesimpulan  
Kode ini memiliki dua fungsi utama:  
1. *Menampilkan daftar anggota ekstrakurikuler* berdasarkan eskul_id, termasuk informasi nama siswa dan tanggal bergabung.  
2. *Menghitung total jumlah anggota* dalam ekstrakurikuler tersebut menggunakan agregasi COUNT(*), yang kemudian ditampilkan dalam tampilan web.
### Fitur Terkait:
***fitur yang menggunakan agregasi ada pada fitur detail anggota eskul dimana berupa total anggota yang telah masuk di eskul tersbut***
## 4.  *Autentikasi & Proteksi Akses*
### Role User:
- ***siswa = hanya bisa mengakses fitur dasbor dimana dia akan melihat data diri nya beserta eskul yang telah dimasuki
- ***admin = punya kendali penuh atas web tersebut dan mengcrud data 
### Logika Proteksi:
```php
if ($queryPetugas && mysqli_num_rows($queryPetugas) > 0) {
    $data = mysqli_fetch_assoc($queryPetugas);
    $_SESSION['id_petugas'] = $data['id_petugas'];
    $_SESSION['nama'] = $data['nama_petugas'];
    $_SESSION['level'] = $data['level']; // Bisa 'admin' atau 'petugas'

    echo "<script>alert('Login berhasil sebagai petugas!'); window.location.href='petugas/index.php';</script>";
    exit();
```
### Tujuan:
Tujuan autentikasi ini adalah untuk memastikan keamanan akses, membedakan peran pengguna, menyimpan informasi login dalam sesi, memberikan notifikasi keberhasilan, dan mengarahkan pengguna ke halaman sesuai perannya.

### Fitur yang Diproteksi:

| Halaman              | Akses Role                      |
| -------------------- | ------------------------------- |
| manajemen_siswa.php  | admin                           |
| manajemen_produk.php | admin                           |
| transaksi.php        | siswa/admin (dengan batasan UI) |

## 5. Relasi Tabel

| Relasi                      | Penjelasan                                                              |
| --------------------------- | ----------------------------------------------------------------------- |
| table siswa dan eskul_siswa | menampilkan daftar siswa yang bisa ditambahkan ke dalam ekstrakurikuler |
| tabel                       |                                                                         |
|                             |                                                                         |

#  *Fitur: Manajemen Eskul*
##  Tujuan
***untuk mengelola esktrakurikuler yang ada di sebuah sekolah seperti mendata anggota eskul,pembina dan sebangai nya 
## Tampilan (UI/UX)
- ***dasbord admin =  total siswa dan total eskul
- ***tampilan data siswa = terdapat beberapa data siswa 
- ***tampilan data eskul = terdapat beberapa data esktrakulikuler 
- ***tampilan data pembina = terdapat beberapa data pembina yang membinbing eskul
- ***tampilan profile eskul = berisi beberapa data profil eskul

##  Front-End (HTML + Bootstrap)

### From Tambah Pembina
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Tambah Pembina</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>
    <div class="container mt-5">
        <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#tambahPembinaModal">
            Tambah Pembina
        </button>
    </div>

    <!-- Modal -->
    <div class="modal fade" id="tambahPembinaModal" tabindex="-1" aria-labelledby="modalLabel" aria-hidden="true">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="modalLabel">Tambah Pembina</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body">
                    <form>
                        <div class="mb-3">
                            <label for="nip" class="form-label">NIP</label>
                            <input type="text" class="form-control" id="nip" placeholder="Masukkan NIP">
                        </div>
                        <div class="mb-3">
                            <label for="namaGuru" class="form-label">Nama Guru</label>
                            <input type="text" class="form-control" id="namaGuru" placeholder="Masukkan Nama Guru">
                        </div>
                        <div class="mb-3">
                            <label for="noTelepon" class="form-label">No. Telepon</label>
                            <input type="text" class="form-control" id="noTelepon" placeholder="Masukkan No. Telepon">
                        </div>
                        <div class="mb-3">
                            <label for="alamat" class="form-label">Alamat</label>
                            <textarea class="form-control" id="alamat" rows="3" placeholder="Masukkan Alamat"></textarea>
                        </div>
                        <div class="mb-3">
                            <label for="bidang" class="form-label">Bidang</label>
                            <input type="text" class="form-control" id="bidang" placeholder="Masukkan Bidang">
                        </div>
                    </form>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-primary">Simpan</button>
                    <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Batal</button>
                </div>
            </div>
        </div>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>

### Tabel Pembina
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rekapitulasi Master Guru</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</head>
<body>
    <div class="container mt-4">
        <h3>Rekapitulasi Master Guru</h3>
        <button class="btn btn-primary mb-3">+ Tambah</button>
        <table class="table table-bordered table-striped">
            <thead class="table-light">
                <tr>
                    <th>No.</th>
                    <th>NIP</th>
                    <th>Nama Guru</th>
                    <th>Nomor Telepon</th>
                    <th>Alamat</th>
                    <th>Bidang</th>
                    <th>Aksi</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>3.</td>
                    <td>2002</td>
                    <td>Pak Ibrahim</td>
                    <td>08123456789</td>
                    <td>Jl. Tanjung Bunga</td>
                    <td>desain</td>
                    <td>
                        <button class="btn btn-sm btn-primary"><i class="bi bi-pencil-square"></i>📝</button>
                        <button class="btn btn-sm btn-danger"><i class="bi bi-trash"></i>🗑️</button>
                    </td>
                </tr>
                <tr>
                    <td>4.</td>
                    <td>2004</td>
                    <td>Pak Salhe</td>
                    <td>085744333444</td>
                    <td>11</td>
                    <td>-</td>
                    <td>
                        <button class="btn btn-sm btn-primary"><i class="bi bi-pencil-square"></i>📝</button>
                        <button class="btn btn-sm btn-danger"><i class="bi bi-trash"></i>🗑️</button>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</body>
</html>


##  Back-End (PHP + MySQLi)

### Proses Tambah Anggota
```php
<?php
$queryPembina = mysqli_query($koneksi, "SELECT * FROM guru WHERE eskul_id = '$eskul_id'");
while ($pembina = mysqli_fetch_assoc($queryPembina)) :
?>
    <li class="list-group-item d-flex justify-content-between align-items-center">
        <div>
            <strong><?= htmlspecialchars($pembina['nama_guru']); ?></strong> <br>
            <small><?= htmlspecialchars($pembina['bidang']); ?></small>
        </div>
        <div>
            <button class="btn btn-danger btn-sm" title="Hapus" onclick="hapusPembina('<?= htmlspecialchars($pembina['nip']); ?>')">
                <i class="fas fa-trash"></i>
            </button>
        </div>
    </li>
<?php endwhile; ?>

```

### Proses Edit Anggota
```php
<?php
session_start();
include '../config/koneksi.php';
include '../config/session.php';

if ($_SERVER['REQUEST_METHOD'] == 'POST') {
    $id = $_POST['id'];
    $tanggal_gabung = $_POST['tanggal_gabung'];

    // Pastikan ID valid
    if (empty($id) || empty($tanggal_gabung)) {
        echo "<script>alert('Data tidak boleh kosong!'); window.location.href='edit_anggota.php?id=$id';</script>";
        exit;
    }

    // Update data dalam database
    $sql = "UPDATE eskul_siswa SET tanggal_gabung = ? WHERE id = ?";
    $stmt = mysqli_prepare($koneksi, $sql);
    mysqli_stmt_bind_param($stmt, "si", $tanggal_gabung, $id);

    if (mysqli_stmt_execute($stmt)) {
        echo "<script>alert('Data berhasil diperbarui!'); window.location.href='eskul.php';</script>";
    } else {
        echo "<script>alert('Gagal memperbarui data!'); window.location.href='edit_anggota.php?id=$id';</script>";
    }

    mysqli_stmt_close($stmt);
} else {
    echo "<script>alert('Akses tidak valid!'); window.location.href='eskul.php';</script>";
}

tampilannya:
$sql = "SELECT es.id, es.id_siswa, es.eskul_id, es.tanggal_gabung, 
                s.nama_siswa, s.id_siswa, 
                e.namaeskul
        FROM eskul_siswa es
        JOIN siswa s ON es.id_siswa = s.id_siswa
        JOIN eskul e ON es.eskul_id = e.eskul_id
        WHERE es.id = '$id'";
```

### Proses Hapus Anggota
```php
<?php
session_start();
include '../config/koneksi.php';
include '../config/session.php';


if (isset($_GET['id'])) {
    $id = $_GET['id'];

    // Query hapus anggota 
    $query = "DELETE FROM siswa WHERE id = '$id'";
    $result = mysqli_query($koneksi, $query);

    if ($result) {
        echo "<script>
                alert('Anggota berhasil dihapus!');
                window.location.href = 'eskul.php'; // Ganti dengan halaman yang sesuai
              </script>";
    } else {
        echo "<script>
                alert('Gagal menghapus anggota! Error: " . mysqli_error($koneksi) . "');
                window.history.back();
              </script>";
    }
} else {
    echo "<script>
            alert('ID tidak ditemukan!');
            window.history.back();
          </script>";
}
?>
```

## Struktur Tabel MySQL
### Tabel : pendaftaran
| kolom      | Tipe Data        | Keterangan           |
| ---------- | ---------------- | -------------------- |
| id_daftar  | INT, Primary Key | ID unik pendaftaran  |
| id_siswa   | INT, Foreign Key |                      |
| id_event   | INT, Foreign Key |                      |
| nama_siswa | Varchar(100)     | menampung nama siswa |

- Tabel ini mencatat data siswa yang mendaftar ke event ekstrakurikuler tertentu.
- Menggunakan **Foreign Key** untuk menjaga keterhubungan data dengan tabel siswa dan event.
- **Primary Key (`id_daftar`)** memastikan setiap pendaftaran memiliki ID unik.
### Tabel : profile_eskul
| kolom          | Tipe Data       | Keterangan             |
| -------------- | --------------- | ---------------------- |
| ProfileEskulID | INT,Primary Key | ID unik profile        |
| Logo           | text            | Menyimpan Gambar Siswa |
| Visi_Misi      | text            |                        |
- Tabel ini mencatat informasi tentang ekstrakurikuler, seperti logo dan visi-misi.
- **Primary Key (`ProfileEskulID`)** memastikan setiap profil ekstrakurikuler memiliki ID unik.m     i
#  Fitur Siswa 

## File: Manajemen_Siswa.php

### Koneksi ke database
```php
koneksi:
<?php
	$koneksi = mysqli_connect("localhost","root","","skaven_rpl_2");
	if(!$koneksi){
		echo "<h1 align='center'>Database tidak terhubung!</h1>";	
		exit();
	}
?>

edit data anggota:

 <?php
session_start();
include '../config/koneksi.php';
include '../config/session.php';

// Debugging: Cek apakah ID diterima
if (!isset($_GET['id']) || empty($_GET['id']) || !is_numeric($_GET['id'])) {
    die("Debugging: ID tidak ditemukan atau tidak valid! URL yang diterima: " . $_SERVER['REQUEST_URI']);
}

$id = intval($_GET['id']); // Konversi ke angka

// Query untuk mendapatkan data anggota eskul
$sql = "SELECT es.id, es.id_siswa, es.eskul_id, es.tanggal_gabung, 
                s.nama_siswa, s.id_siswa, 
                e.namaeskul
        FROM eskul_siswa es
        JOIN siswa s ON es.id_siswa = s.id_siswa
        JOIN eskul e ON es.eskul_id = e.eskul_id
        WHERE es.id = '$id'";

$query = mysqli_query($koneksi, $sql);

if (!$query) {
    die("Query error: " . mysqli_error($koneksi));
}

$data = mysqli_fetch_array($query);

if (!$data) {
    die("Debugging: Data tidak ditemukan di database untuk ID " . $id);
}

// Simpan data ke variabel
$id_siswa = $data['id_siswa'];
$nama_siswa = $data['nama_siswa'];
$eskul_id = $data['eskul_id'];
$namaeskul = $data['namaeskul'];
$tanggal_gabung = $data['tanggal_gabung'];

$fullname = $_SESSION['nama'];
?>

<?php
session_start();
include '../config/koneksi.php';
include '../config/session.php';

if ($_SERVER['REQUEST_METHOD'] == 'POST') {
    $id = $_POST['id'];
    $tanggal_gabung = $_POST['tanggal_gabung'];

    // Pastikan ID valid
    if (empty($id) || empty($tanggal_gabung)) {
        echo "<script>alert('Data tidak boleh kosong!'); window.location.href='edit_anggota.php?id=$id';</script>";
        exit;
    }

    // Update data dalam database
    $sql = "UPDATE eskul_siswa SET tanggal_gabung = ? WHERE id = ?";
    $stmt = mysqli_prepare($koneksi, $sql);
    mysqli_stmt_bind_param($stmt, "si", $tanggal_gabung, $id);

    if (mysqli_stmt_execute($stmt)) {
        echo "<script>alert('Data berhasil diperbarui!'); window.location.href='edit_anggota_eskul.php?id=$id';</script>";
    } else {
        echo "<script>alert('Gagal memperbarui data!'); window.location.href='edit_anggota.php?id=$id';</script>";
    }

    mysqli_stmt_close($stmt);
} else {
    echo "<script>alert('Akses tidak valid!'); window.location.href='eskul.php';</script>";
}


tambah:
<?php
session_start();
include '../config/koneksi.php';
include '../config/session.php';


if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $eskul_id = $_POST['eskul_id'];
    $id_siswa = $_POST['id_siswa'];
    $tanggal_gabung = $_POST['tanggal_gabung'];

    // Cek apakah siswa sudah terdaftar dalam eskul ini
    $cek = mysqli_query($koneksi, "SELECT * FROM eskul_siswa WHERE id_siswa = '$id_siswa' AND eskul_id = '$eskul_id'");
    if (mysqli_num_rows($cek) > 0) {
        echo "<script>alert('Siswa sudah terdaftar dalam eskul ini!'); window.history.back();</script>";
        exit;
    }

    // Insert ke tabel eskul_siswa
    $sql = "INSERT INTO eskul_siswa (id_siswa, eskul_id, tanggal_gabung) VALUES ('$id_siswa', '$eskul_id', '$tanggal_gabung')";
    if (mysqli_query($koneksi, $sql)) {
        echo "<script>alert('Siswa berhasil ditambahkan ke eskul!'); window.location.href='eskul.php';</script>";
    } else {
        echo "<script>alert('Gagal menambahkan siswa!'); window.history.back();</script>";
    }
}
?>


hapus:
<?php
session_start();
include '../config/koneksi.php';
include '../config/session.php';


if (isset($_GET['id'])) {
    $id = $_GET['id'];

    // Query hapus anggota dari eskul_siswa
    $query = "DELETE FROM eskul_siswa WHERE id = '$id'";
    $result = mysqli_query($koneksi, $query);

    if ($result) {
        echo "<script>
                alert('Anggota berhasil dihapus!');
                window.location.href = 'detail_anggota_eskul.php'; // Ganti dengan halaman yang sesuai
              </script>";
    } else {
        echo "<script>
                alert('Gagal menghapus anggota! Error: " . mysqli_error($koneksi) . "');
                window.history.back();
              </script>";
    }
} else {
    echo "<script>
            alert('ID tidak ditemukan!');
            window.history.back();
          </script>";
}
?>
```

### Proses Edit
```php
<?php
session_start();
include '../config/koneksi.php';
include '../config/session.php';

if ($_SERVER['REQUEST_METHOD'] == 'POST') {
    $id = $_POST['id'];
    $tanggal_gabung = $_POST['tanggal_gabung'];

    if (empty($id) || empty($tanggal_gabung)) {
        echo "<script>alert('Data tidak boleh kosong!'); window.location.href='edit_anggota.php?id=$id';</script>";
        exit;
    }
    $sql = "UPDATE eskul_siswa SET tanggal_gabung = ? WHERE id = ?";
    $stmt = mysqli_prepare($koneksi, $sql);
    mysqli_stmt_bind_param($stmt, "si", $tanggal_gabung, $id);

    if (mysqli_stmt_execute($stmt)) {
        echo "<script>alert('Data berhasil diperbarui!'); window.location.href='edit_anggota_eskul.php?id=$id';</script>";
    } else {
        echo "<script>alert('Gagal memperbarui data!'); window.location.href='edit_anggota.php?id=$id';</script>";
    }
    mysqli_stmt_close($stmt);
} else {
    echo "<script>alert('Akses tidak valid!'); window.location.href='eskul.php';</script>";

}
```

### Proses Tambah Pembina
```php
<?php
session_start();
include "../config/koneksi.php";
 

if (isset($_POST['eskul_id']) && isset($_POST['nip'])) {
    $eskul_id = $_POST['eskul_id'];
    $nip = $_POST['nip'];

    $queryCek = mysqli_query($koneksi, "SELECT eskul_id FROM guru WHERE nip = '$nip'");
    $dataCek = mysqli_fetch_assoc($queryCek);

    if (!empty($dataCek['eskul_id'])) {
        echo "<script>
                alert('Guru ini sudah menjadi pembina eskul lain!');
                window.location.href = 'pembina.php';
              </script>";
        exit;
    }

    $queryUpdate = mysqli_query($koneksi, "UPDATE guru SET eskul_id = '$eskul_id' WHERE nip = '$nip'");
    if ($queryUpdate) {
        echo "<script>
                alert('Pembina berhasil ditambahkan!');
                window.location.href = 'eskul.php';
              </script>";
    } else {
        echo "<script>
                alert('Gagal menambahkan pembina!');
                window.location.href = 'eskul.php';
              </script>";
    }
} else {
    echo "<script>
            alert('Data tidak lengkap!');
            window.location.href = 'eskul.php';
          </script>";
}
```

### Proses Hapus Data Pembina
```php
<?php
session_start();
include "../config/koneksi.php";

if (isset($_GET['nip'])) {
    $nip = $_GET['nip'];
    $queryCek = mysqli_query($koneksi, "SELECT * FROM guru WHERE nip = '$nip'");
    if (mysqli_num_rows($queryCek) > 0) {

        // Hapus keterkaitan guru dengan eskul (set eskul_id menjadi NULL)

        $queryHapus = mysqli_query($koneksi, "UPDATE guru SET eskul_id = NULL WHERE nip = '$nip'");
        if ($queryHapus) {
            echo "<script>
                    alert('Pembina berhasil dihapus dari eskul!');
                    window.location.href = 'eskul.php';
                  </script>";
        } else {
            echo "<script>
                    alert('Gagal menghapus pembina!');
                    window.location.href = 'eskul.php';
                  </script>";
        }
    } else {
        echo "<script>
                alert('Data pembina tidak ditemukan!');
                window.location.href = 'eskul.php';
              </script>";
    }
} else {
    echo "<script>
            alert('NIP tidak valid!');
            window.location.href = 'eskul.php';
          </script>";
}
?>
```

### Ambil Data untuk Form Edit
```php
$edit_data = null;
if (isset($_GET['edit'])) {
    $id_edit = $_GET['edit'];
    $result = $koneksi->query("SELECT * FROM siswa WHERE id_siswa = $id_edit");
    $edit_data = $result->fetch_assoc();
}
```

### Form Tambah/Edit Siswa
- Menggunakan method POST

### Teknologi & Library Front-End
- *Bootstrap 5* → styling dan layout
- *Font Awesome* → ikon
- *AOS (Animate on Scroll)* → animasi elemen masuk saat scroll
- *Custom CSS*:
    - Hover card
    - Badge saldo dan transaksi
    - Responsive form dan tabel

### Fitur Utama
- Tambah, Edit, dan Hapus data anggotam  