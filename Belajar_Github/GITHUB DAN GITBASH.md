Pada masa sekarang proses pengembangan perangkat lunak sudah mengalami kemajuan yang signifikan. Selain mengalami kemajuan  pada bagiam bahasa pemrograman, kemajuan juga ditandai dengan adanya platform kolaborasi dengan para pemgembang perangkat lunak lainnya, dimana bertujuan untuk memudahkan pengerjaan proyek secara kolektiv dan dengab demikian mengefisienkan waktu serta sumber daya. Dalam hal ini, platform yang dimaksud adalah github. Github adalau sebuah aplikasi kolaborasi dimana kita dapat menaruh source code program kita GitHub adalah platform berbasis web yang digunakan untuk mengelola dan berbagi kode sumber. Ini memungkinkan banyak orang untuk berkolaborasi dalam proyek perangkat lunak dengan menggunakan sistem kontrol versi Git. Fitur utamanya termasuk repositori kode, pelacakan masalah, dan kemampuan untuk menggabungkan perubahan dari berbagai kontributor.

Untuk melakukan kolaborasi pada github diperlukan menghubungkan  proyek kita terlebih dahulu dari komputer lokal ke gihub kita. Berikut ini cara menghubungkan Proyek dengan Github.
# Instalasi Git Bash
Git Bash adalah aplikasi untuk Windows yang menyediakan antarmuka baris perintah (command line) yang mirip dengan lingkungan Unix/Linux serta alat-alat Git. Git Bash mengemulasi shell Unix/Linux dan memungkinkan pengguna untuk menjalankan perintah-perintah Git serta perintah-perintah Unix/Linux di dalam lingkungan Windows. Korelasinya dengan GitHub, Git Bash adalah alat yang digunakan untuk mengelola repositori Git secara lokal

Berikut ini langkah-langkah Instalasi Git Bash:

**Langkah 1:**
Masuk ke Browser lalu ketikan "Download Git-scm for windows". lalu carilah sampai menemukan link pada gambar. Setelah menemukannya klik agar masuk ke dalam link tersebut.
![[Belajar_Github/Asset/gambar1.png]]

**Langkah 2:**
Setelah masuk maka kita akan langsung diarahkan ke halaman download. klik tombol download sesuai dengan sistem operasi yang digunakan, dalam praktek ini, kita akan menggunakan lik download untuk windows.

![[Belajar_Github/Asset/gambar2.png]]

**Langkah 3:**
Klik link download yang sesuai dengan jenis bit pada perangkat kita. Pada praktik kali ini kita akan gunakan link yang 64-biit
![[Belajar_Github/Asset/gambar3.png]]

**Langkah 4:**
Setelah link diklik, maka program akan otomatis mengunduh file exe nya. tunggu sampai selesai.

![[Belajar_Github/Asset/gambar4.png]]

**Langkah 5:**
Setelah file exe berhasil ter-download, selanjutnya adalah masuk klik buka file atau buka file exe di folder download
/ima
![[Belajar_Github/Asset/gambar5.png]]
**Langkah 6:**
Setelah file exe diklik, maka kita akan diarahkan ke halaman penginstalan. untuk halaman penginstalan cukup di kllik tombol next setiap kali berpindah halaman, sampai pada akhirnya, proses penginstalan mulai berjalan dan selesai. 

**Langkah 7:**
Setelah penginstalan selesai maka kita akan otomatis masuk ke aplikasi Git Bash nya
![[Belajar_Github/Asset/gambar6.png]]

# Masuk ke Github
Sekarang kita akan mulai masuk ke dalam github. Berikut langkah-langkahnya:

**Langkah 1:**
Buka browser lalu ketik "github.com" lalu setelah masuk, klik link seperti pada gambar

![[Belajar_Github/Asset/gambar7.png]]

**Langkah 2:**
Setelah masuk ke link maka kita akan diarahkan ke landing-page. Di halaman ini cari tombol Sign in dan lakukan login dengan akun google saja.
![[Belajar_Github/Asset/gambar8.png]]

**Langkah 3:**
Setelah masuk ke halaman sign in maka lakukan login dengan akun github kita. Jika belum memiliki akun github, maka lakukan register atay sign up terlebih dahulu
![[Belajar_Github/Asset/gambar9.png]]

**Langkah 4:**
Setelah login berhasil maka kita akan masuk ke halaman utama github. Dengan demikian maka kita sudah berhasil login.
![[Belajar_Github/Asset/gambar10.png]]
# Membuat Repository di Github
Repository adalah adalah tempat penyimpanan proyek atau koleksi berkas yang dikelola dengan sistem kontrol versi Git. Setiap repositori dapat berisi kode sumber, file dokumentasi, dan berkas lain yang terkait dengan proyek. Repositori juga menyimpan riwayat perubahan, sehingga memungkinkan pengembang untuk melacak dan mengelola setiap perubahan yang dilakukan pada proyek tersebut.

Pada github mari kita membuat repository untuk dimasukan proyek didalamnya:

**Langkah 1:**
Klik ikon "+" pada bagian atas dekat avatar dan klik New repository
![[Belajar_Github/Asset/gambar11.png]]

**Langkah 2:**
Klik New, masukan nama Repository, lalu aturlah pengaturan seperti apakah proyek kita ingin agar dapat diakses secara umum atau hanya diakses oleh kita dengan mengatur pada bagian public atau private. Berikan juga deskripsi namun bersifat opsional.

![[Belajar_Github/Asset/gambar123.png]]

**Langkah 3:**
Setelah semua siap, klik create Repository 
![[Belajar_Github/Asset/gambar13.png]]

Dengan denikian selesailah pembuatan repository untuk proyek kita
# Konfigurasi Awal di Git Bash 
Untuk menghubungkan antara repository dengan proyek kita pertama-tama perlu melakuka konfigurasi dengan username dan email kita.Berikut langkah langkahnya:

**Langkah 1:**
Tampilkanlah semua konfig yang ada di Git pada komputer kita
```bash
git config --list
```
![[Belajar_Github/Asset/gambar14.png]]

**Langkah 2:**
Sekarang hubungkanlah username Github dengan Gitbash kita
```bash
git config --global user.name "condradoabri17"
```

![[Belajar_Github/Asset/gambar15.png]]

**Lamgkah 3:**
Sekarang hubungkanlah email github dengan gitbash kita.
```bash
git config --global user.email "condradoabri17@gmail.com"
```
![[Belajar_Github/Asset/gambar16.png]]

**Langkah 4:**
Dengan langkah-langkah diatas,username dan email Github akan terhubung. 
Cara mengeceknya, ketik perintah `config --list` dan muncul nama username dan email kita:

![[Belajar_Github/Asset/tambahan.png]]
# Akses Folder Proyek di Git Bash
Sekarang adalah menghubungkan folder kita dengan github. Untuk langkah awal kita akan mengubah direktori di Git Bash.
```bash
pwd
```
![[Belajar_Github/Asset/tambahan21.png]]

Berdasarkan `pwd` kita melihat bahwa direktori yang diakses adalah /c/Users/lenovo, sedangkan folder yang akan kita gunakan untuk dihubungkan ke Github berada di D. Untuk mengubahnya ikut langkah berikut:

**Langkah 1:**
Ubahlah direktori kita ke direktori dimana folder yang akan kita hubungkan disimpan menggunakan perinta `cd`. Pada praktek ini tujuan direktori kita adalah "D/Documents/ObsidianGit".

![[Belajar_Github/Asset/tambahan3.png]]

Dengan perintah `cd` dan tujuan direktori yang tepat, maka kita sudah berhasil masuk ke direktori folder yang akan digunakan untuk menghubungkannya.

Untuk memeriksa isi file direktori kita  gunakan perintah `ls`.

![[Belajar_Github/Asset/tambahan4.png]]
Pada direktori ini terdapat foldrr bernama "BelajarGit". Folder ini yang akan kita gunakan untuk menghubungkannya dengan Github.
# Hubungkan Folder Proyek Lokal ke Github

**Langkah 1:**
Inisialisasi sebuah repositori Git baru kedalam direktori saat ini dengan perintah `git init`.
![[null]]
![[Belajar_Github/Asset/tambahan5.png]]
Jika sudah muncul tulisan `(master)` disamping direktori kita maka kita sudah berhasi melakukan inisialisasi.

**Langkah 2:**
Sekarang buatkanlah remote repository dari Repository di Git ke repositori Git lokal. Copy terlebih dahulu link repository git kita:

![[Belajar_Github/Asset/gambar21.png]]
![[null]]
Lalu kolaborasikan dengan perintah berikut:
```bash
git remote add origin "https://github.com/condradoabri17/BelajatGit.git"
```
![[Belajar_Github/Asset/tambahan6.png]]

**Langkah 3:**
Sekarang cek status commit/koneksi file ke github dengan perintah `git status`.

![[Belajar_Github/Asset/gambar17.png]]
Dengan demikian kita sudah berhasil menghubungkan antara Github dengan direktori kita. 

**Langkah 4:**
Tambahkan semua file-file baru atau perubahan menggunakan Ketik `git add.` 
![[Belajar_Github/Asset/gambar18.png]]

Perintah `git add` digunakan untuk menambahkan perubahan yang telah Anda buat pada file ke dalam staging area (area penampungan) di Git. Staging area adalah langkah antara pengeditan file dan melakukan komit (commit) dalam repositori Git. Dengan menambahkan file ke staging area, Anda memberi tahu Git bahwa perubahan pada file tersebut siap untuk dicommit.

**Langkah 5:**
Sekarang tambahkan pesan commit menggunakan `git commit -m "Awal belajar"`. Jadi nantinya pesan perubahan kita di Github adalah "Awal belajar".

![[Belajar_Github/Asset/gambar19.png]]

**Langkah 6:**
Sekarang setelah perubahan yang dilakukan berhasil ditambahkan pesannya, langkah selanjutnya adalah unggah seluruh perubahan menggunakan `git push origin master`

![[Belajar_Github/Asset/gambar20.png]]

Dengan perintah `git push origin master` Maka kita sudah berhasil mengunggah pesan commit perubahan kita ke dalam Github kita.

Berikut tampilannya:

*Sebelum:*
![[Belajar_Github/Asset/gambar21.png]]

*Sesudah:*
![[Belajar_Github/Asset/gambar22.png]]

Dengan munculnya File kita pada repository Github maka kita telah berhasil menghubungkan file lokal kita dengan GitHub.

Jadi setiap kali kita melakukan perubahan pada file kita maka kita harus selalu membuat commit baru untuk menampung semua perubahan yang kita lakuakan. Contohnya  pada commit sebelumnya bernama `$ git commit -m "Awal belajar "` maka jika kita telah melakukan perubahan kita harus membuat commit baru dengan nama yang berbeda.

Contohnya adalah perubahan ini. Setelah melakukan perubahan kita membuat commit baru dengan nama yang berbeda, yaitu "Awal belajar 3" 

```bash
$ git commit -m "Awal belajar 3"
```
![[Belajar_Github/Asset/gambar23.png]]

Setelah itu unggah kembali perubahan kita dengan perintah `git push origin master` Untuk mengupdate perubahan pada repository kita.

*Sebelum:*
![[Belajar_Github/Asset/gambar24.png]]

*Sesudah:*
![[Belajar_Github/Asset/gambar25.png]]

Dengan Demikian kita sudah berhasil melakukan update dari data lokal dan terelasi juga pada Repository kita.
