# Pertemuan 4 — Sistem Informasi Akademik, Layanan Hasil Studi

## Langkah 1 — Catat kebutuhan dan batas

Tugas ini berbeda dari tugas pertemuan sebelumnya. Tugas Pertemuan 2
adalah jadwal kuliah dan tugas Pertemuan 3 adalah pengajuan KRS. Tugas
Pertemuan 4 adalah layanan hasil studi, dengan teknik generalization dan
collaboration yang sama seperti studi kasus, tetapi diterapkan pada skenario
baru tanpa contoh jawaban.
Skenario tugas berikut fiktif untuk praktikum dan berbeda dari tugas
Pertemuan 2 (jadwal kuliah) dan Pertemuan 3 (pengajuan KRS).
Mahasiswa dan dosen sama-sama merupakan Civitas Akademika yang
dapat melihat kalender akademik. Dosen menginput nilai mata kuliah yang
diampunya setelah masa perkuliahan berakhir. Mahasiswa melihat Kartu
Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. Admin
Akademik mengelola data mahasiswa: menambah data mahasiswa baru,
mengubah data mahasiswa, dan menghapus data mahasiswa. Dua use case
utama, Input Nilai Mata Kuliah dan Lihat KHS, ditunjukkan realisasinya oleh
collaboration yang bersesuaian.

## Langkah 2 — Identifikasi Aktor dan Use Case

### A. Katalog Use Case

| ID       | Nama Use Case             | Aktor Terkait                  | Sumber Kebutuhan | Status |
| -------- | ------------------------- | ------------------------------ | ---------------- | ------ |
| SIA-UC01 | Lihat Jadwal Kuliah       | Mahasiswa                      | SIA-R01          | Tetap  |
| SIA-UC02 | Kelola Jadwal Kuliah      | Admin Akademik                 | SIA-R02          | Tetap  |
| SIA-UC03 | Ajukan KRS                | Mahasiswa                      | SIA-R03          | Tetap  |
| SIA-UC04 | Validasi KRS              | Sistem (bagian dari pengajuan) | SIA-R04          | Tetap  |
| SIA-UC05 | Unduh Bukti Pengajuan KRS | Mahasiswa                      | SIA-R05          | Tetap  |
| SIA-UC06 | Proses Keputusan KRS      | Dosen Wali                     | SIA-R06          | Tetap  |
| SIA-UC07 | Lihat Kalender Akademik   | Civitas Akademika              | SIA-R07          | Baru   |
| SIA-UC08 | Input Nilai Mata Kuliah   | Dosen                          | SIA-R08          | Baru   |
| SIA-UC09 | Lihat KHS                 | Mahasiswa                      | SIA-R09          | Baru   |
| SIA-UC10 | Kelola Data Mahasiswa     | Admin Akademik                 | SIA-R10          | Baru   |
| SIA-UC11 | Tambah Data Mahasiswa     | Admin Akademik                 | SIA-R11          | Baru   |
| SIA-UC12 | Ubah Data Mahasiswa       | Admin Akademik                 | SIA-R11          | Baru   |
| SIA-UC13 | Hapus Data Mahasiswa      | Admin Akademik                 | SIA-R11          | Baru   |

### B. Daftar Aktor

| Nama Aktor        | Jenis        | Keterangan                                                                               |
| ----------------- | ------------ | ---------------------------------------------------------------------------------------- |
| Civitas Akademika | Aktor umum   | Dapat melihat kalender akademik.                                                         |
| Mahasiswa         | Aktor khusus | Dapat melihat jadwal kuliah, mengajukan KRS, mengunduh bukti pengajuan, dan melihat KHS. |
| Dosen             | Aktor khusus | Dapat menginput nilai mata kuliah yang diampunya dan melihat kalender akademik.          |
| Admin Akademik    | Aktor utama  | Mengelola jadwal kuliah dan data mahasiswa.                                              |
| Dosen Wali        | Aktor utama  | Memproses keputusan pengajuan KRS mahasiswa.                                             |

### C. Catatan Identifikasi

Daftar use case ini merupakan gabungan fungsi yang telah dibuat pada Pertemuan 2 dan Pertemuan 3 dengan penambahan fungsi baru pada Pertemuan 4. Nomor SIA-UC01 hingga SIA-UC06 tetap digunakan seperti sebelumnya, sedangkan fungsi tambahan diberi nomor SIA-UC07 sampai SIA-UC13.

SIA-UC10 Kelola Data Mahasiswa berperan sebagai fungsi umum. Sementara itu, SIA-UC11 Tambah Data Mahasiswa, SIA-UC12 Ubah Data Mahasiswa, dan SIA-UC13 Hapus Data Mahasiswa merupakan fungsi yang lebih spesifik. Hubungan generalization antara aktor maupun use case akan dijelaskan pada tahap selanjutnya.

## Langkah 3 — Tetapkan Generalization Aktor

### A. Hierarki Aktor

| Aktor Umum        | Aktor Khusus | Fungsi yang Diwarisi    | Alasan Pemodelan                                                                        |
| ----------------- | ------------ | ----------------------- | --------------------------------------------------------------------------------------- |
| Civitas Akademika | Mahasiswa    | Lihat Kalender Akademik | Mahasiswa merupakan bagian dari civitas akademika dan berhak melihat kalender akademik. |
| Civitas Akademika | Dosen        | Lihat Kalender Akademik | Dosen merupakan bagian dari civitas akademika dan berhak melihat kalender akademik.     |

### B. Penjelasan Generalization

Civitas Akademika digunakan sebagai aktor umum karena fungsi melihat kalender akademik dapat dimanfaatkan oleh mahasiswa maupun dosen. Kedua aktor tersebut menjadi aktor khusus yang memperoleh fungsi dari aktor umum melalui hubungan generalization.

Dengan menerapkan generalization, asosiasi terhadap use case Lihat Kalender Akademik cukup dihubungkan dengan aktor Civitas Akademika. Mahasiswa dan Dosen dapat mewarisi fungsi tersebut melalui hubungan generalization, sehingga hubungan yang sama tidak perlu digambarkan berulang kali.

## Langkah 4 — Tetapkan Generalization Use Case

### A. Hierarki Use Case

| Use Case Umum                  | Use Case Khusus                | Fungsi yang Diwarisi                   | Alasan Pemodelan                                                         |
| ------------------------------ | ------------------------------ | -------------------------------------- | ------------------------------------------------------------------------ |
| SIA-UC10 Kelola Data Mahasiswa | SIA-UC11 Tambah Data Mahasiswa | Fungsi umum pengelolaan data mahasiswa | Penambahan data merupakan salah satu bentuk pengelolaan data mahasiswa.  |
| SIA-UC10 Kelola Data Mahasiswa | SIA-UC12 Ubah Data Mahasiswa   | Fungsi umum pengelolaan data mahasiswa | Perubahan data merupakan salah satu bentuk pengelolaan data mahasiswa.   |
| SIA-UC10 Kelola Data Mahasiswa | SIA-UC13 Hapus Data Mahasiswa  | Fungsi umum pengelolaan data mahasiswa | Penghapusan data merupakan salah satu bentuk pengelolaan data mahasiswa. |

### B. Penjelasan Generalization

SIA-UC10 Kelola Data Mahasiswa dijadikan use case umum karena mencakup aktivitas pengelolaan data mahasiswa secara menyeluruh. Use case ini memiliki tiga fungsi khusus, yaitu SIA-UC11 Tambah Data Mahasiswa, SIA-UC12 Ubah Data Mahasiswa, dan SIA-UC13 Hapus Data Mahasiswa.

Ketiga fungsi khusus tersebut menjelaskan tindakan yang lebih terperinci dalam pengelolaan data mahasiswa. Generalization digunakan untuk memperlihatkan hubungan antara fungsi utama dan fungsi turunannya secara teratur, sehingga struktur use case lebih mudah dipahami tanpa harus mengulang penjelasan mengenai pengelolaan data mahasiswa.

### C. Ketentuan Penggambaran

- SIA-UC10 Kelola Data Mahasiswa berfungsi sebagai use case umum.
- SIA-UC11 Tambah Data Mahasiswa, SIA-UC12 Ubah Data Mahasiswa, dan SIA-UC13 Hapus Data Mahasiswa menjadi use case khusus.
- Hubungan generalization digambarkan menggunakan garis utuh dengan ujung segitiga kosong yang mengarah ke use case umum, yaitu SIA-UC10 Kelola Data Mahasiswa.

## Langkah 5 — Tetapkan Collaboration

### A. Daftar Collaboration

| ID Collaboration | Nama Collaboration      | Use Case yang Direalisasikan     | Aktor Terkait |
| ---------------- | ----------------------- | -------------------------------- | ------------- |
| SIA-CO01         | Input Nilai Mata Kuliah | SIA-UC08 Input Nilai Mata Kuliah | Dosen         |
| SIA-CO02         | Lihat KHS               | SIA-UC09 Lihat KHS               | Mahasiswa     |

### B. Penjelasan Collaboration

**1. SIA-CO01 — Input Nilai Mata Kuliah**

Collaboration ini digunakan untuk merealisasikan proses Input Nilai Mata Kuliah. Dosen terlebih dahulu memilih mata kuliah yang diampunya, kemudian memasukkan nilai mahasiswa. Setelah itu, sistem melakukan pemeriksaan dan menyimpan nilai sesuai dengan ketentuan yang berlaku. Nilai yang sudah disimpan tetapi belum dipublikasikan belum dapat dinyatakan sebagai nilai resmi yang ditampilkan pada KHS.

**2. SIA-CO02 — Lihat KHS**

Collaboration ini menggambarkan proses mahasiswa dalam mengakses Kartu Hasil Studi (KHS). Mahasiswa memilih semester yang ingin diperiksa, lalu sistem mengecek apakah nilai pada semester tersebut telah dipublikasikan. Apabila publikasi sudah dilakukan, sistem menampilkan KHS kepada mahasiswa. Sebaliknya, jika nilai belum dipublikasikan, sistem memberikan informasi bahwa KHS belum tersedia sebagai hasil studi resmi.

### C. Hubungan Collaboration dengan Use Case

Nama setiap collaboration disesuaikan dengan use case yang diwujudkannya. SIA-CO01 berhubungan dengan SIA-UC08 Input Nilai Mata Kuliah, sedangkan SIA-CO02 berhubungan dengan SIA-UC09 Lihat KHS.

Kedua collaboration tersebut memiliki keterkaitan dalam proses akademik. Nilai yang dimasukkan oleh dosen perlu dipublikasikan sesuai ketentuan terlebih dahulu agar mahasiswa dapat melihatnya melalui KHS.

## Langkah 6 — Susun Use Case Description

### A. SIA-UC08 — Input Nilai Mata Kuliah

| Elemen        | Deskripsi                                                                             |
| ------------- | ------------------------------------------------------------------------------------- |
| ID Use Case   | SIA-UC08                                                                              |
| Nama Use Case | Input Nilai Mata Kuliah                                                               |
| Aktor Utama   | Dosen                                                                                 |
| Tujuan        | Memasukkan nilai mahasiswa pada mata kuliah yang menjadi tanggung jawab dosen.        |
| Prasyarat     | Dosen telah login, mempunyai hak akses yang sesuai, serta data mata kuliah dan mahasiswa sudah tersedia. |
| Pemicu        | Dosen memilih menu input nilai mata kuliah.                                           |

**Alur Utama**

1. Dosen membuka menu untuk memasukkan nilai mata kuliah.
2. Sistem menampilkan daftar mata kuliah yang diajar oleh dosen tersebut.
3. Dosen menentukan mata kuliah yang akan diisi nilainya.
4. Sistem menampilkan daftar mahasiswa yang terdaftar pada mata kuliah yang dipilih.
5. Dosen mengisi nilai masing-masing mahasiswa.
6. Dosen menyimpan nilai yang telah dimasukkan.
7. Sistem memeriksa apakah nilai sudah lengkap dan sesuai dengan ketentuan.
8. Apabila nilai dinyatakan valid, sistem menyimpan data nilai dan memberikan konfirmasi kepada dosen.

**Alur Alternatif**

- Jika proses berhasil, data nilai tersimpan di dalam sistem.
- Nilai yang berhasil disimpan belum otomatis berstatus resmi sebelum dipublikasikan.
- Jika proses gagal, penyimpanan nilai tidak dianggap berhasil.

**Pascakondisi**

- Jika proses berhasil, data nilai tersimpan di dalam sistem.
- Nilai yang berhasil disimpan belum otomatis berstatus resmi sebelum dipublikasikan.
- Jika proses gagal, penyimpanan nilai tidak dianggap berhasil.

<!-- Deskripsi Use Case — Lihat KHS -->

### B. SIA-UC09 — Lihat KHS

| Elemen        | Deskripsi                                                                          |
| ------------- | ---------------------------------------------------------------------------------- |
| ID Use Case   | SIA-UC09                                                                           |
| Nama Use Case | Lihat KHS                                                                          |
| Aktor Utama   | Mahasiswa                                                                          |
| Tujuan        | Mengakses Kartu Hasil Studi untuk semester yang nilai-nilainya telah dipublikasikan.|
| Prasyarat     | Mahasiswa sudah login dan mempunyai data akademik pada semester yang dipilih.      |
| Pemicu        | Mahasiswa membuka menu Kartu Hasil Studi (KHS).                                    |

**Alur Utama**

1. Mahasiswa membuka menu KHS pada sistem.
2. Sistem menampilkan daftar semester yang dapat dipilih.
3. Mahasiswa menentukan semester yang ingin dilihat.
4. Sistem memeriksa status publikasi nilai pada semester tersebut.
5. Apabila nilai telah dipublikasikan, sistem mengambil data hasil studi mahasiswa.
6. Sistem menampilkan KHS sesuai semester yang dipilih.

**Alur Alternatif**

- Jika nilai belum dipublikasikan, sistem menampilkan pemberitahuan bahwa KHS belum dapat diakses.
- Jika mahasiswa belum memiliki data akademik pada semester yang dipilih, sistem memberikan informasi bahwa data KHS belum tersedia.
- Apabila terjadi gangguan ketika mengambil data, sistem menampilkan pemberitahuan bahwa KHS belum dapat ditampilkan.

**Pascakondisi**

- Jika proses berjalan dengan baik, KHS untuk semester yang dipilih     akan ditampilkan kepada mahasiswa.

- Jika nilai belum dipublikasikan, sistem tidak menampilkan KHS sebagai hasil studi yang sudah tersedia.

- Aktivitas melihat KHS tidak menyebabkan perubahan pada nilai akademik mahasiswa.



## Langkah 7 — Gambar Diagram

Pembuatan diagram dilakukan dengan mengikuti tahapan yang sama seperti Langkah 8 pada studi kasus. Prosesnya dimulai dengan membuat salinan diagram SIA dari Pertemuan 3 tanpa mengubah berkas aslinya. Selanjutnya, tambahkan aktor umum dan aktor khusus beserta hubungan generalization, use case layanan hasil studi, serta use case pengelolaan data mahasiswa dengan hubungan generalization-nya. Setelah itu, tambahkan dua collaboration beserta hubungan realization.

Simpan diagram di dalam folder 04_model_analisis/P04/SIA/ dengan nama P04_<2406032>_SIA_notasi_usecase_v01.drawio. Ekspor diagram tersebut ke format PNG dengan nama versi yang sama.

Diagram akhir harus mencakup fungsi jadwal kuliah, pengajuan KRS, dan layanan hasil studi yang tergabung dalam satu diagram Sistem Informasi Akademik.

# Langkah 8 — Uji Konsistensi, Review, dan Revisi

## A. Uji Konsistensi

### Situasi A — Mahasiswa melihat kalender akademik tanpa asosiasi langsung

**Hasil pengujian:** Mahasiswa tetap dapat menggunakan fungsi melihat kalender akademik meskipun tidak memiliki hubungan asosiasi secara langsung dengan use case tersebut. Hal ini karena Mahasiswa merupakan aktor khusus dari Civitas Akademika dan mewarisi fungsi yang dimiliki aktor umum melalui generalization.

**Kesimpulan:** Model dinyatakan konsisten apabila hubungan generalization antaraktor digambarkan dengan tepat, sehingga Mahasiswa memperoleh hak untuk melihat kalender akademik melalui Civitas Akademika.

### Situasi B — Dosen yang bukan pengampu mencoba menginput nilai

**Hasil pengujian:** Sistem menolak permintaan penginputan nilai apabila dosen tidak mengampu mata kuliah yang dipilih. Sistem kemudian memberikan pemberitahuan bahwa dosen tersebut tidak memiliki kewenangan untuk memasukkan nilai pada mata kuliah tersebut.

**Kesimpulan:** Hasil pengujian sesuai dengan ketentuan bahwa penginputan nilai hanya dapat dilakukan oleh dosen yang mengampu mata kuliah terkait.

### Situasi C — Admin menghapus data mahasiswa yang masih memiliki data akademik aktif

**Hasil pengujian:** Sistem menolak permintaan penghapusan data mahasiswa yang masih mempunyai data akademik aktif. Penolakan tersebut disertai informasi mengenai alasan penghapusan tidak dapat dilakukan agar data akademik tetap terlindungi.

**Kesimpulan:** Hasil pengujian sesuai dengan batasan sistem, yaitu data mahasiswa yang masih memiliki data akademik aktif tidak diperbolehkan untuk dihapus.

<!-- Riview & Revisi disimpan di folder 06_laporan/P04_2406020_jobsheet_review_v01.md -->