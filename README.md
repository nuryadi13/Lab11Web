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

![img1!](praktikum11/foto1.png)

Pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan
diaktifkan. Kemudian simpan kembali filenya dan restart Apache web server.
![img1!](praktikum11/foto2.png)

• Unduh Codeigniter dari website https://codeigniter.com/download

• Extrak file zip Codeigniter ke direktori htdocs/lab11_ci.

• Ubah nama direktory framework-4.x.xx menjadi ci4.

• Buka browser dengan alamat http://localhost/lab11_ci/ci4/public/

![img1!](praktikum11/foto3.png)

## Menjalankan CLI (Command Line Interface)
Codeigniter 4 menyediakan CLI untuk mempermudah proses development. Untuk
mengakses CLI buka terminal/command prompt.

![img1!](praktikum11/foto4.png)
Perintah yang dapat dijalankan untuk memanggil CLI Codeigniter adalah:

php spark

![img1!](praktikum11/foto5.png)

## Mengaktifkan Mode Debugging

Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk
mengetahui pesan error apabila terjadi kesalahan dalam membuat kode program.
Secara default fitur ini belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan
pesan kesalahan seperti berikut.

![img1!](praktikum11/foto6.png)

Semua jenis error akan ditampilkan sama. Untuk memudahkan mengetahui jenis errornya, maka perlu diaktifkan mode debugging dengan mengubah nilai konfigurasi pada environment variable CI_ENVIRONMENT menjadi development

![img1!](praktikum11/foto7.png)

Ubah nama file env menjadi .env kemudian buka file tersebut dan ubah nilai variable
CI_ENVIRINMENT menjadi development.

![img1!](praktikum11/foto8.png)

Gambar  di atas merupakan contoh error yang terjadi. Untuk mencoba error tersebut, ubah kode pada file app/Controller/home.php

![img1!](praktikum11/foto9.png)

## Struktur Direktori

Untuk lebih memahami Framework Codeigniter 4 perlu mengetahui struktur direktori
dan file yang ada. Buka pada Windows Explorer atau dari Visual Studio Code ->
Open Folder.
Terdapat beberapa direktori dan file yang perlu dipahami fungsi dan kegunaannya.

• .github folder ini kita butuhkan untuk konfigurasi repo github, seperti konfigurasi
untuk build dengan github action;

• app folder ini akan berisi kode dari aplikasi yang kita kembangkan;

• public folder ini berisi file yang bisa diakses oleh publik, seperti file index.php,
robots.txt, favicon.ico, ads.txt, dll;

• tests folder ini berisi kode untuk melakukan testing dengna PHPunit;
vendor folder ini berisi library yang dibutuhkan oleh aplikasi, isinya juga termasuk
kode core dari system CI.

• writable folder ini berisi file yang ditulis oleh aplikasi. Nantinya, kita bisa pakai
untuk menyimpan file yang di-upload, logs, session, dll.
Sedangkan file-file yang berada pada root direktori CI sebagai berikut.

• .env adalah file yang berisi variabel environment yang dibutuhkan oleh aplikasi.

• .gitignore adalah file yang berisi daftar nama file dan folder yang akan diabaikan
oleh Git.

• build adalah script untuk mengubah versi codeigniter yang digunakan. Ada versi
release (stabil) dan development (labil).

• composer.json adalah file JSON yang berisi informasi tentang proyek dan daftar
library yang dibutuhkannya. File ini digunakan oleh Composer sebagai acuan.

• composer.lock adalah file yang berisi informasi versi dari libraray yang digunakan
aplikasi.

• license.txt adalah file yang berisi penjelasan tentang lisensi Codeigniter;

• phpunit.xml.dist adalah file XML yang berisi konfigurasi untuk PHPunit.

• README.md adalah file keterangan tentang codebase CI. Ini biasanya akan
dibutuhkan pada repo github atau gitlab.

• spark adalah program atau script yang berfungsi untuk menjalankan server,
generate kode, dll.

![img1!](praktikum11/foto10.png)

Fokus kita pada folder app, dimana folder tersebut adalah area kerja kita untuk
membuat aplikasi. Dan folder public untuk menyimpan aset web seperti css, gambar,
javascript, dll.
Memahami Konsep MVC
Codeigniter menggunakan konsep MVC. MVC meripakan singkatan dari
Model-View-Controller. MVC merupakan konsep arsitektur yang umum digunakan
dalam pengembangan aplikasi. Konsep MVC adalah memisahkan kode program
berdasarkan logic proses, data, dan tampilan. Untuk logic proses diletakkan pada
direktori Contoller, Objek data diletakkan pada direktori Model, dan desain tampilan
diletakkan pada direktori View.
Codeigniter menggunakan konsep pemrograman berorientasi objek dalam
mengimplementasikan konsep MVC.
Model merupakan kode program yang berisi pemodelan data. Data dapat berupa
database ataupun sumber lainnya.
View merupakan kode program yang berisi bagian yang menangani terkait tampilan
user interface sebuah aplikasi. didalam aplikasi web biasanya pasti akan berhubungan
dengan html dan css.
Controller merupakaan kode program yang berkaitan dengan logic proses yang
menghubungkan antara view dan model. Controller berfungsi untuk menerima request
dan data dari user kemudian diproses dengan menghubungkan bagian model dan view.
Routing dan Controller
Routing merupakan proses yang mengatur arah atau rute dari request untuk menentukan
fungsi/bagian mana yang akan memproses request tersebut. Pada framework CI4,
routing bertujuan untuk menentukan Controller mana yang harus merespon sebuah
request. Controller adalah class atau script yang bertanggung jawab merespon sebuah
request.
Pada Codeigniter, request yang diterima oleh file index.php akan diarahkan ke Router
untuk meudian oleh router tesebut diarahkan ke Controller.
Router terletak pada file app/config/Routes.php

![img1!](praktikum11/foto11.png)

Pada file tersebut kita dapat mendefinisikan route untuk aplikasi yang kita buat.
Contoh :

|$routes->get('/', 'Home::index');|

Kode tersebut akan mengarahkan rute untuk halaman home.

## Membuat Route Baru.

Tambahkan kode berikut di dalam Routes.php

![img1!](praktikum11/foto12.png)

Untuk mengetahui route yang ditambahkan sudah benar, buka CLI dan jalankan
perintah berikut

![img1!](praktikum11/foto13.png)

Selanjutnya coba akses route yang telah dibuat dengan mengakses alamat url
http://localhost:8080/about

![img1!](praktikum11/foto14.png)

Ketika diakses akan mucul tampilan error 404 file not found, itu artinya file/page
tersebut tidak ada. Untuk dapat mengakses halaman tersebut, harus dibuat terlebih
dahulu Contoller yang sesuai dengan routing yang dibuat yaitu Contoller Page.
Membuat Controller
Selanjutnya adalah membuat Controller Page. Buat file baru dengan nama page.php
pada direktori Controller kemudian isi kodenya seperti berikut.

![img1!](praktikum11/foto15.png)

Selanjutnya refresh Kembali browser, maka akan ditampilkan hasilnya yaotu halaman
sudah dapat diakses.

![img1!](praktikum11/foto16.png)

## Auto Routing
Secara default fitur autoroute pada Codeiginiter sudah aktif. Untuk mengubah status
autoroute dapat mengubah nilai variabelnya. Untuk menonaktifkan ubah nilai true
menjadi false.
|$routes->setAutoRoute(true);|
Tambahkan method baru pada Controller Page seperti berikut.

![img1!](praktikum11/foto17.png)

Method ini belum ada pada routing, sehingga cara mengaksesnya dengan menggunakan
alamat: http://localhost:8080/page/tos

![img1!](praktikum11/foto18.png)

## Membuat View

Selanjutnya adalam membuat view untuk tampilan web agar lebih menarik. Buat file
baru dengan nama about.php pada direktori view (app/view/about.php) kemudian isi
kodenya seperti berikut.

![img1!](praktikum11/foto19.png)

Ubah method about pada class Controller Page menjadi seperti berikut:

![img1!](praktikum11/foto20.png)

Kemudian lakukan refresh pada halaman tersebut.

![img1!](praktikum11/foto21.png)

## Membuat Layout Web dengan CSS

Pada dasarnya layout web dengan css dapat diimplamentasikan dengan mudah pada
codeigniter. Yang perlu diketahui adalah, pada Codeigniter 4 file yang menyimpan asset
css dan javascript terletak pada direktori public.
Buat file css pada direktori public dengan nama style.css (copy file dari praktikum
lab4_layout. Kita akan gunakan layout yang pernah dibuat pada praktikum 4.

![img1!](praktikum11/foto22.png)

Kemudian buat folder template pada direktori view kemudian buat file header.php dan
footer.php
File app/view/template/header.php

![img1!](praktikum11/foto23.png)

File app/view/template/footer.php

![img1!](praktikum11/foto24.png)

Kemudian ubah file app/view/about.php seperti berikut.

![img1!](praktikum11/foto25.png)

Selanjutnya refresh tampilan pada alamat http://localhost:8080/about
Selanjutnya refresh browser untuk melihat hasilnya

![img1!](/praktikum11/foto26.png)

## PRAKTIKUM 12 ##

Langkah-langkah Praktikum 12

Persiapan.

Untuk memulai membuat aplikasi CRUD sederhana, yang perlu disiapkan adalah

database server menggunakan MySQL. Pastikan MySQL Server sudah dapat dijalankan

melalui XAMPP.

Membuat database

![img1!](/praktikum12/foto01.png)

# Membuat Tabel

![img1!](/praktikum12/foto02.png)

# struktur tabel

![img1!](/praktikum12/foto03.png)

# Konfigurasi koneksi database

Selanjutnya membuat konfigurasi untuk menghubungkan dengan database server.

Konfigurasi dapat dilakukan dengan du acara, yaitu pada file app/config/database.php

atau menggunakan file .env. Pada praktikum ini kita gunakan konfigurasi pada file .env.

![img1!](/praktikum12/foto04.png)

# Membuat Model

Selanjutnya adalah membuat Model untuk memproses data Artikel. Buat file baru pada

direktori app/Models dengan nama ArtikelModel.php

![img1!](/praktikum12/foto05.png)

# Membuat Controller

Buat Controller baru dengan nama Artikel.php pada direktori app/Controllers.

![img1!](/praktikum12/foto06.png)

# Membuat View

Buat direktori baru dengan nama artikel pada direktori app/views, kemudian buat file

baru dengan nama index.php.

![img1!](/praktikum12/foto07.png)

 Selanjutnya buka browser kembali, dengan mengakses url http://localhost:8080/artikel

![img1!](/praktikum12/foto08.png)

# Belum ada data yang diampilkan. Kemudian coba tambahkan beberapa data pada database agar dapat ditampilkan datanya.

Menambahkan data

![img1!](/praktikum12/foto09.png)

Refresh kembali browser, sehingga akan ditampilkan hasilnya.

![img1!](/praktikum12/foto10.png)

# Membuat Tampilan Detail Artikel

Tampilan pada saat judul berita di klik maka akan diarahkan ke halaman yang berbeda.

Tambahkan fungsi baru pada Controller Artikel dengan nama view().

![img1!](/praktikum12/foto11.png)

# Membuat View Detail

Buat view baru untuk halaman detail dengan nama app/views/artikel/detail.php.

![img1!](/praktikum12/foto12.png)

# Membuat Routing untuk artikel detail

Buka Kembali file app/config/Routes.php, kemudian tambahkan routing untuk artikel detail.

![img1!](/praktikum12/foto13.png)

selanjutnya refresh dan lihat hasilnya

![img1!](/praktikum12/foto14.png)

# Membuat Menu Admin

Menu admin adalah untuk proses CRUD data artikel. Buat method baru pada

Controller Artikel dengan nama admin_index().

![img1!](/praktikum12/foto15.png)

# Selanjutnya buat view untuk tampilan admin dengan nama admin_index.php

![img1!](/praktikum12/foto16.png)

# Tambahkan routing untuk menu admin seperti berikut:

![img1!](/praktikum12/foto17.png)

Akses menu admin dengan url http://localhost:8080/admin/artikel

![img1!](/praktikum12/foto18.png)

# Menambah Data Artikel

Tambahkan fungsi/method baru pada Controller Artikel dengan nama add().

Kemudian buat view untuk form tambah dengan nama form_add.php

![img1!](/praktikum12/foto19.png)

# Kemudian buat view untuk form tambah dengan nama form_add.php

![img1!](/praktikum12/foto20.png)

Selanjutnya jalankan pada browser

![img1!](/praktikum12/foto21.png)

# Kemudian buat view untuk form tambah dengan nama form_edit.php

![img1!](/praktikum12/foto22.png)

# Kemudian buat view untuk form tambah dengan nama form_edit.php

![img1!](/praktikum12/foto23.png)

Kemudian lihat hasilnya pada beowser

![img1!](/praktikum12/foto24.png)

# Menghapus Data

Tambahkan fungsi/method baru pada Controller Artikel dengan nama delete().

![img1!](/praktikum12/foto25.png)


## PRAKTIKUM 13 ##

# Langkah-langkah Praktikum 13
Persiapan.

Untuk memulai membuat modul Login, yang perlu disiapkan adalah database server

menggunakan MySQL. Pastikan MySQL Server sudah dapat dijalankan melalui XAMPP.

Membuat Tabel: User Login

![img1!](/praktikum13/foto1.png)

# Membuat Model User

Selanjutnya adalah membuat Model untuk memproses data Login. Buat file baru pada
direktori app/Models dengan nama UserModel.php

![img1!](/praktikum13/foto2.png)

# Membuat Controller User

Buat Controller baru dengan nama User.php pada direktori app/Controllers.
Kemudian tambahkan method index() untuk menampilkan daftar user, dan method
login() untuk proses login.

![img1!](/praktikum13/foto3.png)


# Membuat View Login

Buat direktori baru dengan nama user pada direktori app/views, kemudian buat file
baru dengan nama login.php

![img1!](/praktikum13/foto4.png)


#Membuat Database Seeder

Database seeder digunakan untuk membuat data dummy. Untuk keperluan ujicoba modul
login, kita perlu memasukkan data user dan password kedaalam database. Untuk itu buat
database seeder untuk tabel user. Buka CLI, kemudian tulis perintah berikut:

php spark make:seeder UserSeeder

Selanjutnya, buka file UserSeeder.php yang berada di lokasi direktori
/app/Database/Seeds/UserSeeder.php kemudian isi dengan kode berikut:

![img1!](/praktikum13/foto5.png)

Selanjutnya buka kembali CLI dan ketik perintah berikut:
php spark db:seed UserSeeder

# Uji Coba Login
Selanjutnya buka url http://localhost:8080/user/login seperti berikut:


![img1!](/praktikum13/foto6.png)

#Menambahkan Auth Filter

Selanjutnya membuat filer untuk halaman admin. Buat file baru dengan nama Auth.php
pada direktori app/Filters.

![img1!](/praktikum13/foto7.png)

Selanjutnya buka file app/Config/Filters.php tambahkan kode berikut:

'auth' => App\Filters\Auth::class

![img1!](/praktikum13/foto8.png)

# Percobaan Akses Menu Admin

Buka url dengan alamat http://localhost:8080/admin/artikel ketika alamat tersebut
diakses maka, akan dimuculkan halaman login.

![img1!](/praktikum13/foto9.png)

# Fungsi Logout

Tambahkan method logout pada Controller User seperti berikut:

![img1!](/praktikum13/foto10.png)

# PRAKTIKUM 14 #

# Membuat Pagination
Pagination merupakan proses yang digunakan untuk membatasi tampilan yang panjang
dari data yang banyak pada sebuah website. Fungsi pagination adalah memecah
tampilan menjadi beberapa halaman tergantung banyaknya data yang akan ditampilkan
pada setiap halaman.
Pada Codeigniter 4, fungsi pagination sudah tersedia pada Library sehingga cukup
mudah menggunakannya.
Untuk membuat pagination, buka Kembali Controller Artikel, kemudian modifikasi
kode pada method admin_index seperti berikut.

![img1!](/praktikum14/foto1.png)

Selanjutnya buka kembali menu daftar artikel tambahkan data lagi untuk melihat hasilnya

![img1!](/praktikum14/foto2.png)

# Membuat Pencarian
Pencarian data digunakan untuk memfilter data.
Untuk membuat pencarian data, buka kembali Controller Artikel, pada method
admin_index ubah kodenya seperti berikut

![img1!](/praktikum14/foto3.png)

# Upload Gambar
Menambahkan fungsi unggah gambar pada tambah artikel. Buka kembali Controller
Artikel, sesuaikan kode pada method add seperti berikut:

![img1!](/praktikum14/foto4.png)

Kemudian pada file views/artikel/form_add.php tambahkan field input file seperti
berikut.
<p>
<input type="file" name="gambar">
</p>
Dan sesuaikan tag form dengan menambahkan ecrypt type seperti berikut.
<form action="" method="post" enctype="multipart/form-data">

Ujicoba file upload dengan mengakses menu tambah artikel.

![img1!](/praktikum14/foto5.png)

Isi data pada form di atas dan lihat hasilnya pada browser


![img1!](/praktikum14/foto6.png)

refresh pada browser

![img1!](/praktikum14/foto7.png)

![img1!](/Lab11Web/praktikum14/artikel3.png)










































