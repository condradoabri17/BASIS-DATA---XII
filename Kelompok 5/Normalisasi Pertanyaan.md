# NORMALISASI PERTANYAAN

## 1. Jelaskan apa yang dimaksud dengan normalisasi database.
## 2. Apa yang menjadi tujuan pembuatan database perlu dinormalisasikan?
## 3. Uraikan proses singkat tentang normalisasi dari tahap 1NF hingga 5NF.
## 4. Buatlah contoh normalisasi database minimal dari tahap 1NF hingga 3NF pada kasus database proyek basis data sekolah masing-masing.

**Jawaban:** 
1. Normalisasi adalah proses memecah tabel besar menjadi beberapa tabel kecil agar data tidak berulang-ulang (redundan) dan lebih terstruktur.

2. Tujuan normalisasi ada 3 yaitu:
   - Mengurangi pengulangan data.
   - Memastikan data tetap konsisten.
   - Menghemat ruang penyimpanan.

3. Berikut penjelasan dari 1NF hingga 5NF:
   - **1NF (First Normal Form):** Yaitu proses menghilangkan data yang berulang dengan cara memecah tabel besar yang memiliki data berulang didalamnya.
   - **2NF (Seconf Normal Form):** Yaitu proses merelasikan dua tabel yang sudah dipecah tadi dengan sebuah tabel pivot. Tujuannya agar data bergantung pada relasi sehingga jika salah satu data diubah, maka cukup mengganti 1 baris ditabel referensi masing-masing. 
   - **3NF (Third Normal Form) :** Yaitu tahap lanjutan dari 1NF dimana kita kembali menganalisis jika ada data yang dapat berdiri sendiri maka dapat kita pecah kembali menjadi tabel baru.
   - **4NF (Fourth Normal Form) :** yaitu tahap normalisasi yang memastikan bahwa tidak ada ketergantungan multi-nilai parsial (nilai yang bergantung pada sebagian dari kunci primer, bukan pada seluruh kunci primer) pada kunci primer.
   - **5NF (Fifth Normal Form) :** Yaitu  tahap normalisasi yang memastikan bahwa tidak ada ketergantungan join parsial pada kunci primer.

4. Pada contoh kasus database sekolah, kami mengambil contoh dari bagian eskul, dimana pada awalnya terdapat tabel yang memiliki kolom sebagai berikut:     
    - id
    - nama_siswa 
    - kelas
    - jurusan
    - jenis_kelamin
    - nama_eskul
    - profil_eskul

tabel ini belum mendapat rasionalisasi sehingga ketika data akan dimasukkan, maka akan terdapat **data yang berulang** pada bagian `nama_eskul` dan `profil_eskul` jika terdapat siswa yang memiliki eskul yang sama dengan siswa lainnya. Solusinya adalah melakukan rasionalisasi pada tabel dengan tahap berikut:

- **1NF:** Menghilangkan data yang berulang dengan cara memecah tabel menjadi 2 yaitu tabel eskul dan tabel siswa sehingga menjadi sebagai berikut:
   
   **siswa:**
   - id_siswa
   - nama_siswa
   - kelas
   - jurusan
   - jenis_kelamin
     
    **eskul:**
   - eskul_id
   - namaeskul
   - profil_eskul

- **2NF:** Tahap selanjutnya yaitu merelasikan kedua tabel dengan menggunakan 1 tabel pivot. Tujuannya agar data bergantung pada relasi sehingga jika salah satu data diubah, maka cukup mengganti 1 baris ditabel referensi masing-masing. Berikut tabel pivot yang akan dinamakan dengan tabel **eskul_siswa**:

	**eskul_siswa:**
	- id
	- id_siswa
	- eskul_id
	- tanggal_gabung

- **3NF:** Jika ada ada yang dapat berdiri sendiri maka bisa kita pecah kembali menjadi tabel baru. di tabel ini kita akan memecah profil_eskul menjadi tabel **profil_eskul:**
  - ProfilEskulID 
  - logo
  - deskripsi





