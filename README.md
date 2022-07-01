| Nama      | Nuryadi |
| ----------- | ----------- |
| NIM     | 312010621       |
| Kelas   | TI.20.A.1        |

## Langkah langkah praktikum 11

Berikut beberapa ekstensi yang perlu diaktifkan:

• php-json ekstension untuk bekerja dengan JSON;

• php-mysqlnd native driver untuk MySQL;

• php-xml ekstension untuk bekerja dengan XML;

• php-intl ekstensi untuk membuat aplikasi multibahasa;

• libcurl (opsional), jika ingin pakai Curl.

Untuk mengaktifkan ekstentsi tersebut, melalu XAMPP Control Panel, pada bagian
Apache klik Config -> PHP.ini

![img1!](spraktikum11/foto1.png)

## 1. Buat file baru dengan nama header.php
### Instalasi Codeigniter 4
Untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara
manual dan menggunakan composer. Pada praktikum ini kita menggunakan cara
manual

• Unduh Codeigniter dari website https://codeigniter.com/download

• Extrak file zip Codeigniter ke direktori htdocs/lab11_ci.

• Ubah nama direktory framework-4.x.xx menjadi ci4.

• Buka browser dengan alamat http://localhost/lab11_ci/ci4/public/

![img1!](assets/img/1/11.png)

## 2. Menjalankan CLI (Command Line Interface)
Codeigniter 4 menyediakan CLI untuk mempermudah proses development. Untuk
mengakses CLI buka terminal/command prompt.

![img1!](assets/img/2/1.png)

## 3. Mengaktifkan Mode Debugging
Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk
mengetahui pesan error apabila terjadi kesalahan dalam membuat kode program.

![img1!](assets/img/3/1.png)

Ubah nama file env menjadi .env kemudian buka file tersebut dan ubah nilai variable
CI_ENVIRINMENT menjadi development.

## 4. Membuat Route Baru.
Tambahkan kode berikut di dalam Routes.php

![img1!](assets/img/4/1.png)

Selanjutnya coba akses route yang telah dibuat dengan mengakses alamat url http://localhost:8080/about

![img1!](assets/img/4/2.png)

Ketika diakses akan mucul tampilan error 404 file not found, itu artinya file/page
tersebut tidak ada. Untuk dapat mengakses halaman tersebut, harus dibuat terlebih
dahulu Contoller yang sesuai dengan routing yang dibuat yaitu Contoller Page.

## 5. Membuat Controller
Selanjutnya adalah membuat Controller Page. Buat file baru dengan nama page.php
pada direktori Controller kemudian isi kodenya seperti berikut.

![img1!](assets/img/5/1.png)

Selanjutnya refresh Kembali browser, maka akan ditampilkan hasilnya yaitu halaman
sudah dapat diakses.

![img1!](assets/img/5/2.png)

## 6. Auto Routing
Secara default fitur autoroute pada Codeiginiter sudah aktif. Untuk mengubah status
autoroute dapat mengubah nilai variabelnya. Untuk menonaktifkan ubah nilai true
menjadi false.

![img1!](assets/img/5/3.png)

Tambahkan method baru pada Controller Page seperti berikut.

![img1!](assets/img/5/4.png)

Method ini belum ada pada routing, sehingga cara mengaksesnya dengan menggunakan alamat: http://localhost:8080/page/tos

![img1!](assets/img/5/5.png)

## 7. Membuat View
Selanjutnya adalam membuat view untuk tampilan web agar lebih menarik. Buat file
baru dengan nama about.php pada direktori view (app/view/about.php) kemudian isi
kodenya seperti berikut.

![img1!](assets/img/6/1.png)

Ubah method about pada class Controller Page menjadi seperti berikut:

![img1!](assets/img/6/2.png)

Kemudian lakukan refresh pada halaman tersebut.

![img1!](assets/img/6/3.png)

## 8. Membuat Layout Web dengan CSS
Buat file css pada direktori public dengan nama style.css (copy file dari praktikum
lab4_layout. Kita akan gunakan layout yang pernah dibuat pada praktikum 4.

![img1!](assets/img/7/1.png)

Kemudian buat folder template pada direktori view kemudian buat file header.php dan
footer.php

![img1!](assets/img/7/22.png)

File app/view/template/footer.php

![img1!](assets/img/7/3.png)

Kemudian ubah file app/view/about.php seperti berikut.

![img1!](assets/img/7/4.png)

Selanjutnya refresh tampilan pada alamat http://localhost:8080/about

![img1!](assets/img/7/5.png)

# Lab 11 (Lanjutan)

## 1. Membuat Database: Studi Kasus Data Artikel

![img1!](assets/img/11/1.png)

## 2. Konfigurasi koneksi database
Selanjutnya membuat konfigurasi untuk menghubungkan dengan database server.

![img1!](assets/img/11/2.png)

## 3. Membuat Model
Selanjutnya adalah membuat Model untuk memproses data Artikel. Buat file baru pada direktori app/Models dengan nama ArtikelModel.php

![img1!](assets/img/11/3.png)

## 4. Membuat Controller
Buat Controller baru dengan nama Artikel.php pada direktori app/Controllers.

![img1!](assets/img/11/4.png)

## 5. Membuat View
Buat direktori baru dengan nama artikel pada direktori app/views, kemudian buat file baru dengan nama index.php.

![img1!](assets/img/11/5.png)

Selanjutnya buka browser kembali, dengan mengakses url http://localhost:8080/artikel

![img1!](assets/img/11/6.png)

Belum ada data yang diampilkan. Kemudian coba tambahkan beberapa data pada database agar dapat ditampilkan datanya.

![img1!](assets/img/11/7.png)

Refresh kembali browser, sehingga akan ditampilkan hasilnya.

![img1!](assets/img/11/8.png)

## 6. Membuat Tampilan Detail Artikel
Tampilan pada saat judul berita di klik maka akan diarahkan ke halaman yang berbeda. Tambahkan fungsi baru pada Controller Artikel dengan nama view().

![img1!](assets/img/11/9.png)

## 7. Membuat View Detail
Buat view baru untuk halaman detail dengan nama app/views/artikel/detail.php.

![img1!](assets/img/11/10.png)

## Membuat Routing untuk artikel detail
Buka Kembali file app/config/Routes.php, kemudian tambahkan routing untuk artikel detail.

![img1!](assets/img/11/11.png)

![img1!](assets/img/11/12.png)

## 8. Membuat Menu Admin
Menu admin adalah untuk proses CRUD data artikel. Buat method baru pada
Controller Artikel dengan nama admin_index(). 

![img1!](assets/img/11/13.png)

Selanjutnya buat view untuk tampilan admin dengan nama admin_index.php

![img1!](assets/img/11/14.png)

Tambahkan routing untuk menu admin seperti berikut:

![img1!](assets/img/11/15.png)

Akses menu admin dengan url http://localhost:8080/admin/artikel

![img1!](assets/img/11/16.png)

## 9. Menambah Data Artikel
Tambahkan fungsi/method baru pada Controller Artikel dengan nama add(). 

![img1!](assets/img/11/17.png)

Kemudian buat view untuk form tambah dengan nama form_add.php

![img1!](assets/img/11/18.png)

![img1!](assets/img/11/19.png)

## 10. Mengubah Data
Tambahkan fungsi/method baru pada Controller Artikel dengan nama edit(). 

![img1!](assets/img/11/20.png)

Kemudian buat view untuk form tambah dengan nama form_edit.php

![img1!](assets/img/11/21.png)

![img1!](assets/img/11/22.png)

## 11. Menghapus Data
Tambahkan fungsi/method baru pada Controller Artikel dengan nama delete().

![img1!](assets/img/11/23.png)


# Lab 11 Framework Lanjutan (Modul Login)

## 1. Membuat Tabel User

![img1!](assets/img/12/1.png)

## 2. Membuat Model User
Selanjutnya adalah membuat Model untuk memproses data Login. Buat file baru pada direktori app/Models dengan nama UserModel.php

![img1!](assets/img/12/2.png)

## 3. Membuat Controller User
Buat Controller baru dengan nama User.php pada direktori app/Controllers.
Kemudian tambahkan method index() untuk menampilkan daftar user, dan method
login() untuk proses login.

![img1!](assets/img/12/3.png)

## 4. Membuat View Login
Buat direktori baru dengan nama user pada direktori app/views, kemudian buat file
baru dengan nama login.php.

![img1!](assets/img/12/44.png)

## 5. Membuat Database Seeder
Database seeder digunakan untuk membuat data dummy. Untuk keperluan ujicoba modul
login, kita perlu memasukkan data user dan password kedaalam database.

![img1!](assets/img/12/5.png)

Uji Coba Login, Selanjutnya buka url http://localhost:8080/user/login seperti berikut:

![img1!](assets/img/12/6.png)

## 6. Menambahkan Auth Filter
Selanjutnya membuat filer untuk halaman admin. Buat file baru dengan nama Auth.php
pada direktori app/Filters.

![img1!](assets/img/12/7.png)

Selanjutnya buka file app/Config/Filters.php tambahkan kode berikut:

![img1!](assets/img/12/8.png)

Selanjutnya buka file app/Config/Routes.php dan sesuaikan kodenya.

![img1!](assets/img/12/9.png)

## 7. Percobaan Akses Menu Admin
Buka url dengan alamat http://localhost:8080/admin/artikel ketika alamat tersebut
diakses maka, akan dimuculkan halaman login.

![img1!](assets/img/12/10.png)

## 8. Fungsi Logout
Tambahkan method logout pada Controller User seperti berikut:

![img1!](assets/img/12/11.png)

# Lab 11 Pagination dan Pencarian

## 1. Membuat Pagination
Untuk membuat pagination, buka Kembali Controller Artikel, kemudian modifikasi
kode pada method admin_index seperti berikut.

![img1!](assets/img/13/1.png)

Kemudian buka file views/artikel/admin_index.php dan tambahkan kode berikut dibawah deklarasi tabel data.

![img1!](assets/img/13/2.png)

Selanjutnya buka kembali menu daftar artikel, tambahkan data lagi untuk melihat hasilnya.

![img1!](assets/img/13/3.png)

## 2. Membuat Pencarian
Pencarian data digunakan untuk memfilter data.

![img1!](assets/img/13/4.png)

Kemudian buka kembali file views/artikel/admin_index.php dan tambahkan form pencarian sebelum deklarasi tabel seperti berikut:

![img1!](assets/img/13/5.png)

Dan pada link pager ubah seperti berikut.

![img1!](assets/img/13/6.png)

Selanjutnya ujicoba dengan membuka kembali halaman admin artikel, masukkan kata kunci tertentu pada form pencarian.

![img1!](assets/img/13/7.png)

## 3. Upload Gambar
Menambahkan fungsi unggah gambar pada tambah artikel. Buka kembali Controller Artikel, sesuaikan kode pada method add seperti berikut:

![img1!](assets/img/13/8.png)

Kemudian pada file views/artikel/form_add.php tambahkan field input file seperti berikut.

![img1!](assets/img/13/9.png)

Dan sesuaikan tag form dengan menambahkan ecrypt type seperti berikut.

![img1!](assets/img/13/10.png)

Ujicoba file upload dengan mengakses menu tambah artikel.

![img1!](assets/img/13/11.png)