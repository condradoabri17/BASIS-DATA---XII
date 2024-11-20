# 1.Mengapa ERD penting dalam perancangan basis data?
Mengapa ERD penting dalam perancangan basis data? Karna kalo kita menggunakan erd pada saat perancangan basis data itu dapat mempermudah kita dalam memahami arah atau alur dari basis data.
# 2.di dalam perancangan ERD, apa saja elemen dan simbol yang mesti ada?

- ENTITAS: Suatu objek yang dapat di identifikasi dalam lingkungan pemakai.
- RELASI:  Hubungan antara beberapa entitas yang berbeda.
- ATRIBUT:  Mendeskripsikan karakter entitas. Atribut yang berperan sebangai "key" di beri garis bawah.
- GARIS: Sebangai penghubung antara relasi dengan entitas atau entitas dengan atribut.
# 3.Apa yang dimaksud entitas dan apa saja contoh entitas yang ada di sekitar kalian?

Entitas adalah sebuah objek atau hal yang dapat dikenali, memiliki karakteristik tertentu, dan dapat dibedakan dari objek lainnya. Entitas memiliki karakteristik tertentu dan karakteristik itu berupa atribut. Contoh entitas disekitar kita adalah manusia, benda, tempat, kegiatan atau peristiwa, produk jasa, dsb.
# 4.Apa itu relasi dalam ERD dan seperti apa contohnya?

Dalam ERD (Entity Relationship Diagram), relasi adalah hubungan antara dua atau lebih entitas yang menunjukkan bagaimana entitas-entitas tersebut saling terhubung dalam sebuah database. Relasi ini membantu memahami alur data dan keterkaitan antar entitas dalam sistem.
## Jenis-jenis Relasi dalam ERD

1. ***One-to-One (1:1)***: Setiap entitas di A terhubung dengan satu entitas di B, dan sebaliknya. Contoh: Setiap warga memiliki satu KTP, dan setiap KTP hanya dimiliki oleh satu warga.

2. ***One-to-Many (1:N)***: Satu entitas di A dapat terhubung dengan banyak entitas di B, tetapi entitas di B hanya terhubung dengan satu entitas di A. Contoh: Satu guru dapat mengajar banyak siswa, tetapi setiap siswa hanya memiliki satu guru wali kelas.

4. ***Many-to-Many (M:N)***: Setiap entitas di A bisa terhubung ke banyak entitas di B, dan sebaliknya. Contoh: Mahasiswa dapat mengikuti banyak mata kuliah, dan setiap mata kuliah dapat diikuti oleh banyak mahasiswa.
## Contoh ERD dengan Relasi

Misalkan kita memiliki tiga entitas: ***Mahasiswa**, **Dosen, dan Mata Kuliah*. Relasi di antara entitas tersebut dapat digambarkan sebagai berikut:

1. Mahasiswa - Mata Kuliah (Many-to-Many): Mahasiswa bisa mengambil banyak mata kuliah, dan setiap mata kuliah bisa diikuti oleh banyak mahasiswa. Dalam database, relasi ini sering kali diwujudkan melalui tabel penghubung (misalnya tabel *KRS atau Pendaftaran).

2. *Dosen - Mata Kuliah (One-to-Many)*: Seorang dosen bisa mengajar banyak mata kuliah, tetapi setiap mata kuliah hanya memiliki satu dosen yang bertanggung jawab. 

Dalam ERD, relasi biasanya dihubungkan dengan garis yang mengindikasikan jenis relasi (1 atau M/N) dan menunjukkan arah hubungan antar entitas.

# 5. Setiap Entitas dapat berhubungan satu sama lain dalam bentuk kardinalitas. Apa-apa saja kardinalitas dalam ERD.

Dalam Entity Relationship Diagram (ERD), kardinalitas menggambarkan jumlah instans dari satu entitas yang dapat berhubungan dengan instans entitas lainnya. Kardinalitas penting untuk menentukan batasan hubungan antar entitas. Berikut adalah jenis-jenis kardinalitas yang umum dalam ERD:
## Jenis-jenis Kardinalitas

1. ***One-to-One (1:1)***:
   Setiap entitas dalam set A berhubungan dengan tepat satu entitas dalam set B, dan sebaliknya. Contoh: Setiap warga memiliki satu KTP, dan setiap KTP hanya dimiliki oleh satu warga.

2. ***One-to-Many (1:N)***:
   Satu entitas dalam set A dapat berhubungan dengan banyak entitas dalam set B, tetapi setiap entitas dalam set B hanya terhubung dengan satu entitas dalam set A. Contoh: Satu guru dapat mengajar banyak siswa, tetapi setiap siswa hanya memiliki satu guru wali kelas.

3. ***Many-to-One (M:1)***:
   Banyak entitas dalam set A dapat berhubungan dengan satu entitas dalam set B. Contoh: Banyak *siswa bisa terdaftar dalam satu kelas.

4. ***Many-to-Many (M:N**)*:
   Banyak entitas dalam set A dapat berhubungan dengan banyak entitas dalam set B, dan sebaliknya. Contoh: *Mahasiswa dapat mengambil banyak mata kuliah, dan setiap mata kuliah dapat diambil oleh banyak mahasiswa.
   Dalam implementasi database, hubungan ini biasanya membutuhkan tabel penghubung (junction table).






