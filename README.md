<div align="center">
  <h3 align="center">PEMROGRAMAN MOBILE</h3>
  <h3 align="center">JOBSHEET LAYOUT DAN NAVIGASI</h3>
  <a href="https://github.com/othneildrew/Best-README-Template">
    <img src="img/logo_polinema.png" alt="Logo" width="300" height="300">
  </a>

  <h3 align="center">Abiyasa Putra Prasetya</h3>
  <h3 align="center">3G - D4TI</h3>
  <h3 align="center">01</h3>
  <h3 align="center">2141720203</h3>
</div>


# Praktikum 1: Membangun Layout di Flutter

<h3>Langkah 1: Buat Project Baru<h3>

Buatlah sebuah project flutter baru dengan nama layout_flutter. Atau sesuaikan style laporan praktikum yang Anda buat.

<h3>Langkah 2: Buka file lib/main.dart<h3>

Buka file main.dart lalu ganti dengan kode berikut. Isi nama dan NIM Anda di text title.

![Alt text](img/praktikum_1/1.png)

<h3>Langkah 3: Identifikasi layout diagram<h3>

Langkah pertama adalah memecah tata letak menjadi elemen dasarnya:

- Identifikasi baris dan kolom.

- Apakah tata letaknya menyertakan kisi-kisi (grid)?

- Apakah ada elemen yang tumpang tindih?

- Apakah UI memerlukan tab?

- Perhatikan area yang memerlukan alignment, padding, atau borders.

Pertama, identifikasi elemen yang lebih besar. Dalam contoh ini, empat elemen disusun menjadi sebuah kolom: sebuah gambar, dua baris, dan satu blok teks.

<p align="center">
  <img src="img/praktikum_1/2.png" alt="Alt text">
</p>

Selanjutnya, buat diagram setiap baris. Baris pertama, disebut bagian Judul, memiliki 3 anak: kolom teks, ikon bintang, dan angka. Anak pertamanya, kolom, berisi 2 baris teks. Kolom pertama itu memakan banyak ruang, sehingga harus dibungkus dengan widget yang Diperluas.

<p align="center">
  <img src="img/praktikum_1/3.png" alt="Alt text">
</p>

Baris kedua, disebut bagian Tombol, juga memiliki 3 anak: setiap anak merupakan kolom yang berisi ikon dan teks.

<p align="center">
  <img src="img/praktikum_1/4.png" alt="Alt text">
</p>

Setelah tata letak telah dibuat diagramnya, cara termudah adalah dengan menerapkan pendekatan bottom-up. Untuk meminimalkan kebingungan visual dari kode tata letak yang banyak bertumpuk, tempatkan beberapa implementasi dalam variabel dan fungsi.

<h3>Langkah 4: Implementasi title row<h3>

Pertama, Anda akan membuat kolom bagian kiri pada judul. Tambahkan kode berikut di bagian atas metode build() di dalam kelas MyApp:

<p align="center">
  <img src="img/praktikum_1/5.png" alt="Alt text">
</p>

/* soal 1 */ Letakkan widget Column di dalam widget Expanded agar menyesuaikan ruang yang tersisa di dalam widget Row. Tambahkan properti crossAxisAlignment ke CrossAxisAlignment.start sehingga posisi kolom berada di awal baris.

<p align="center">
  <img src="img/praktikum_1/soal_1.png" alt="Alt text">
</p>

/* soal 2 */ Letakkan baris pertama teks di dalam Container sehingga memungkinkan Anda untuk menambahkan padding = 8. Teks ‘Batu, Malang, Indonesia' di dalam Column, set warna menjadi abu-abu.

<p align="center">
  <img src="img/praktikum_1/soal_2.png" alt="Alt text">
</p>

/* soal 3 */ Dua item terakhir di baris judul adalah ikon bintang, set dengan warna merah, dan teks "41". Seluruh baris ada di dalam Container dan beri padding di sepanjang setiap tepinya sebesar 32 piksel. Kemudian ganti isi body text ‘Hello World' dengan variabel titleSection seperti berikut:

<p align="center">
  <img src="img/praktikum_1/soal_3.png" alt="Alt text">
</p>

<p align="center">
  <img src="img/praktikum_1/jawab_3.png" alt="Alt text">
</p>

Output:

<p align="center">
  <img src="img/praktikum_1/run.png" alt="Alt text">
</p>

# Praktikum 2: Implementasi button row

Selesaikan langkah-langkah praktikum berikut ini dengan melanjutkan dari praktikum sebelumnya.

<h3>Langkah 1: Buat method Column _buildButtonColumn<h3>

Bagian tombol berisi 3 kolom yang menggunakan tata letak yang sama—sebuah ikon di atas baris teks. Kolom pada baris ini diberi jarak yang sama, dan teks serta ikon diberi warna primer.

Karena kode untuk membangun setiap kolom hampir sama, buatlah metode pembantu pribadi bernama buildButtonColumn(), yang mempunyai parameter warna, Icon dan Text, sehingga dapat mengembalikan kolom dengan widgetnya sesuai dengan warna tertentu.

lib/main.dart (_buildButtonColumn)

<p align="center">
  <img src="img/praktikum_2/1.png" alt="Alt text">
</p>

<h3>Langkah 2: Buat widget buttonSection<h3>

Buat Fungsi untuk menambahkan ikon langsung ke kolom. Teks berada di dalam Container dengan margin hanya di bagian atas, yang memisahkan teks dari ikon.

Bangun baris yang berisi kolom-kolom ini dengan memanggil fungsi dan set warna, Icon, dan teks khusus melalui parameter ke kolom tersebut. Sejajarkan kolom di sepanjang sumbu utama menggunakan MainAxisAlignment.spaceEvenly untuk mengatur ruang kosong secara merata sebelum, di antara, dan setelah setiap kolom. Tambahkan kode berikut tepat di bawah deklarasi titleSection di dalam metode build():

lib/main.dart (buttonSection)

<p align="center">
  <img src="img/praktikum_2/2.png" alt="Alt text">
</p>

<h3>Langkah 3: Tambah button section ke body<h3>

Tambahkan variabel buttonSection ke dalam body seperti berikut:

<p align="center">
  <img src="img/praktikum_2/3.png" alt="Alt text">
</p>

<p align="center">
  <img src="img/praktikum_2/4.png" alt="Alt text">
</p>

Output:

<p align="center">
  <img src="img/praktikum_2/run.png" alt="Alt text">
</p>

# Praktikum 3: Implementasi text section

Selesaikan langkah-langkah praktikum berikut ini dengan melanjutkan dari praktikum sebelumnya.

<h3>Langkah 1: Buat widget textSection<h3>

Tentukan bagian teks sebagai variabel. Masukkan teks ke dalam Container dan tambahkan padding di sepanjang setiap tepinya. Tambahkan kode berikut tepat di bawah deklarasi buttonSection:

<p align="center">
  <img src="img/praktikum_3/teks1.png" alt="Alt text">
</p>

<p align="center">
  <img src="img/praktikum_3/teks2.png" alt="Alt text">
</p>


Dengan memberi nilai softWrap = true, baris teks akan memenuhi lebar kolom sebelum membungkusnya pada batas kata.

<h3>Langkah 2: Tambahkan variabel text section ke body<h3>

Tambahkan widget variabel textSection ke dalam body seperti berikut:

<p align="center">
  <img src="img/praktikum_3/1.png" alt="Alt text">
</p>

<p align="center">
  <img src="img/praktikum_3/2.png" alt="Alt text">
</p>

Output:

<p align="center">
  <img src="img/praktikum_3/run.png" alt="Alt text">
</p>

# Praktikum 4: Implementasi image section

Selesaikan langkah-langkah praktikum berikut ini dengan melanjutkan dari praktikum sebelumnya.

<h3>Langkah 1: Siapkan aset gambar<h3>

Anda dapat mencari gambar di internet yang ingin ditampilkan. Buatlah folder images di root project layout_flutter. Masukkan file gambar tersebut ke folder images, lalu set nama file tersebut ke file pubspec.yaml seperti berikut:

<p align="center">
  <img src="img/praktikum_4/1.png" alt="Alt text">
</p>

Contoh nama file gambar di atas adalah lake.jpg

Jawab:

<p align="center">
  <img src="img/praktikum_4/2.png" alt="Alt text">
</p>

<h3>Langkah 2: Tambahkan gambar ke body<h3>

Tambahkan aset gambar ke dalam body seperti berikut:

<p align="center">
  <img src="img/praktikum_4/3.png" alt="Alt text">
</p>

BoxFit.cover memberi tahu kerangka kerja bahwa gambar harus sekecil mungkin tetapi menutupi seluruh kotak rendernya.

<p align="center">
  <img src="img/praktikum_4/4.png" alt="Alt text">
</p>

<h3>Langkah 3: Terakhir, ubah menjadi ListView<h3>

Pada langkah terakhir ini, atur semua elemen dalam ListView, bukan Column, karena ListView mendukung scroll yang dinamis saat aplikasi dijalankan pada perangkat yang resolusinya lebih kecil.

<p align="center">
  <img src="img/praktikum_4/5.png" alt="Alt text">
</p>

Jawab:

<p align="center">
  <img src="img/praktikum_4/6.png" alt="Alt text">
</p>

Output:

<p align="center">
  <img src="img/praktikum_4/run.png" alt="Alt text">
</p>