# Kebutuhan Sistem Informasi Akademik

## 1. Kebutuhan Fungsional

| ID      | Kebutuhan                                                                  |
| ------- | -------------------------------------------------------------------------- |
| SIA-R03 | Mahasiswa dapat melakukan pengajuan KRS.                                   |
| SIA-R04 | Sistem melakukan pemeriksaan dan validasi terhadap KRS yang diajukan.      |
| SIA-R05 | Mahasiswa dapat mengunduh bukti pengajuan apabila memilih opsi tersebut pada konfirmasi pengajuan. |
| SIA-R06 | Dosen wali dapat memberikan persetujuan atau penolakan terhadap KRS.       |

## 2. Kebutuhan dari Pertemuan Sebelumnya

| ID      | Kebutuhan                                      |
| ------- | ---------------------------------------------- |
| SIA-R01 | Mahasiswa dapat mengakses informasi jadwal kuliah. |
| SIA-R02 | Admin akademik dapat melakukan pengelolaan jadwal kuliah. |

## 3. Batasan dan Asumsi

1. Pengguna sudah berhasil melakukan autentikasi.
2. Informasi mata kuliah, prasyarat, dan jadwal kuliah telah tersedia.
3. Apabila proses validasi tidak berhasil, pengajuan belum dapat disimpan sebagai pengajuan yang berhasil.
4. Pengunduhan bukti tidak menjadi ketentuan wajib agar pengajuan berhasil.
5. KRS yang sudah tersimpan belum tentu memperoleh persetujuan dari dosen wali.
6. Proses pembayaran, pengisian nilai, dan penerapan basis data tidak termasuk dalam ruang lingkup tugas.

## 4. Alur Utama

1. Mahasiswa menentukan mata kuliah yang ingin diambil.
2. Sistem memeriksa kelengkapan pengajuan, prasyarat mata kuliah, serta kemungkinan benturan jadwal.
3. Apabila semua pemeriksaan berhasil, sistem menyimpan pengajuan KRS dengan status menunggu persetujuan dosen wali.
4. Sistem memberikan konfirmasi bahwa pengajuan telah tersimpan.
5. Mahasiswa menentukan apakah ingin mengunduh bukti pengajuan.
6. Dosen wali memiliki kewenangan untuk menyetujui atau menolak KRS disertai catatan keputusan.

## Langkah 2 — Mengidentifikasi Aktor dan Use Case

### A. Daftar Aktor

| No. | Nama Aktor | Deskripsi                                                                    |
| --- | ---------- | ---------------------------------------------------------------------------- |
| 1   | Mahasiswa  | Melakukan pengajuan KRS dan menentukan apakah bukti pengajuan akan diunduh.  |
| 2   | Dosen Wali | Menangani persetujuan atau penolakan KRS serta menambahkan catatan keputusan. |

### B. Katalog Use Case

| ID    | Nama Fungsi           | Aktor Terkait                                      | Sumber Kebutuhan |
| ----- | --------------------- | -------------------------------------------------- | ---------------- |
| UC-01 | Ajukan KRS            | Mahasiswa                                          | SIA-R03          |
| UC-02 | Validasi KRS          | Sistem, sebagai bagian dari proses pengajuan mahasiswa | SIA-R04      |
| UC-03 | Unduh Bukti Pengajuan | Mahasiswa                                          | SIA-R05          |
| UC-04 | Proses Keputusan KRS  | Dosen Wali                                         | SIA-R06          |

### C. Batas Identifikasi

Proses identifikasi aktor dan use case dibatasi pada pengajuan KRS, pemeriksaan validitas pengajuan, pengunduhan bukti, dan penanganan keputusan oleh dosen wali. Kebutuhan SIA-R01 dan SIA-R02 tetap digunakan dengan ID yang sama sebagai kebutuhan dari Pertemuan 2. Namun, kedua kebutuhan tersebut tidak dicantumkan sebagai fungsi utama dalam katalog use case ini.

## Langkah 3 — Menentukan Include

### Relasi Include

- **Sumber:** UC-01 — Ajukan KRS
- **Tujuan:** UC-02 — Validasi KRS
- **Proses yang disertakan:** Memeriksa kelengkapan pengajuan, persyaratan mata kuliah, dan kemungkinan jadwal yang saling berbenturan.

### Alasan Relasi

Hubungan `<<include>>` diterapkan karena validasi merupakan tahapan wajib yang harus dilalui setiap kali mahasiswa mengajukan KRS. Apabila pemeriksaan tidak berhasil, pengajuan tersebut belum dapat dinyatakan berhasil tersimpan.

## Langkah 4 — Menentukan Extend

### Relasi Extend

- **Sumber:** UC-03 — Unduh Bukti Pengajuan
- **Tujuan:** UC-01 — Ajukan KRS
- **Kondisi:** Pengajuan KRS telah berhasil disimpan, sistem sudah menampilkan konfirmasi penyimpanan, dan mahasiswa memilih opsi untuk mengunduh bukti.
- **Proses tambahan:** Sistem menyiapkan bukti pengajuan agar dapat diunduh oleh mahasiswa.

### Alasan Relasi

Relasi `<<extend>>` digunakan karena mengunduh bukti bukan tahapan yang wajib dilakukan ketika mengajukan KRS. Mahasiswa memiliki pilihan untuk mengunduh bukti atau melewatkannya. Apabila mahasiswa tidak memilih opsi tersebut, pengajuan yang telah berhasil disimpan tetap dinyatakan berhasil.

## Langkah 5 — Deskripsi Use Case

### UC-01 — Ajukan KRS

**Aktor:** Mahasiswa

**Tujuan:** Mengirimkan rencana pengambilan mata kuliah agar dapat diperiksa dan disetujui oleh dosen wali.

**Prasyarat:**

- Mahasiswa telah melakukan autentikasi.
- Informasi mata kuliah dan jadwal kuliah sudah tersedia.

**Alur Utama:**

1. Mahasiswa menentukan mata kuliah yang ingin diajukan.
2. Mahasiswa mengirimkan pengajuan KRS.
3. Sistem melakukan pemeriksaan KRS melalui UC-02.
4. Jika pemeriksaan berhasil, sistem menyimpan pengajuan dengan status menunggu persetujuan dosen wali.
5. Sistem menampilkan pemberitahuan bahwa pengajuan berhasil disimpan.
6. Mahasiswa dapat memilih untuk mengunduh bukti pengajuan melalui UC-03.

**Alur Alternatif:**

- Apabila validasi tidak berhasil, sistem menampilkan keterangan mengenai kegagalan tersebut dan pengajuan belum berhasil disimpan.

**Pascakondisi:**

- Jika proses berhasil, pengajuan KRS tersimpan dengan status menunggu persetujuan dosen wali.
- Jika proses gagal, pengajuan belum berhasil tersimpan.

### UC-02 — Validasi KRS

**Aktor:** Sistem, sebagai bagian dari UC-01.

**Tujuan:** Memastikan bahwa pengajuan KRS telah memenuhi persyaratan yang berlaku.

**Prasyarat:**

- Mahasiswa telah menentukan mata kuliah yang akan diajukan.
- Data mata kuliah, persyaratan, dan jadwal kuliah telah tersedia.

**Alur Utama:**

1. Sistem memeriksa apakah seluruh bagian pengajuan sudah lengkap.
2. Sistem memastikan persyaratan mata kuliah telah terpenuhi.
3. Sistem memeriksa apakah terdapat jadwal kuliah yang berbenturan.
4. Jika semua pemeriksaan memenuhi ketentuan, sistem menyatakan bahwa validasi berhasil.

**Alur Alternatif:**

- Jika terdapat pemeriksaan yang tidak terpenuhi, sistem menyatakan validasi gagal dan memberikan informasi mengenai penyebabnya.

**Pascakondisi:**

- Hasil pemeriksaan tersedia sebagai dasar untuk menentukan apakah pengajuan KRS dapat disimpan.

### UC-03 — Unduh Bukti Pengajuan

**Aktor:** Mahasiswa.

**Tujuan:** Memperoleh dokumen atau bukti dari pengajuan KRS yang telah berhasil disimpan.

**Prasyarat:**

- Pengajuan KRS sudah berhasil disimpan.
- Sistem telah menampilkan konfirmasi penyimpanan.

**Alur Utama:**

1. Sistem memberikan pilihan kepada mahasiswa untuk mengunduh bukti pengajuan.
2. Mahasiswa memilih pilihan unduh bukti.
3. Sistem menyiapkan bukti pengajuan agar dapat diunduh.

**Alur Alternatif:**

- Jika mahasiswa tidak memilih pilihan unduh, proses pengajuan KRS tetap dinyatakan berhasil.
- Jika sistem tidak berhasil menyediakan bukti, pengajuan KRS yang sudah tersimpan tetap berlaku dan tidak dibatalkan.

**Pascakondisi:**

- Bukti pengajuan dapat diunduh apabila proses penyediaannya berhasil.
- Status pengajuan tidak mengalami perubahan hanya karena mahasiswa melakukan atau tidak melakukan pengunduhan bukti.

### UC-04 — Proses Keputusan KRS

**Aktor:** Dosen Wali.

**Tujuan:** Menentukan hasil pengajuan KRS melalui keputusan persetujuan atau penolakan.

**Prasyarat:**

- Data pengajuan KRS telah tersimpan.
- Status pengajuan masih menunggu persetujuan dosen wali.

**Alur Utama:**

1. Dosen wali membuka data pengajuan KRS mahasiswa.
2. Dosen wali memeriksa isi pengajuan tersebut.
3. Dosen wali menentukan apakah KRS akan disetujui atau ditolak.
4. Dosen wali menambahkan catatan yang menjelaskan keputusan.
5. Sistem menyimpan keputusan beserta catatan yang diberikan.

**Alur Alternatif:**

- Apabila data pengajuan belum tersedia atau belum memenuhi ketentuan untuk diproses, sistem belum dapat mencatat keputusan.

**Pascakondisi:**

- Keputusan berupa persetujuan atau penolakan, beserta catatan dari dosen wali, telah tercatat pada data pengajuan.

## Langkah 6 — Membuat Diagram Use Case

Pada tahap ini, diagram use case dibuat menggunakan dua aktor dan empat use case yang telah diidentifikasi berikut.

| Jenis   | Nama                          |
| ------- | ----------------------------- |
| Aktor   | Mahasiswa                     |
| Aktor   | Dosen Wali                    |
| Use Case | UC-01 - Ajukan KRS            |
| Use Case | UC-02 - Validasi KRS          |
| Use Case | UC-03 - Unduh Bukti Pengajuan |
| Use Case | UC-04 - Proses Keputusan KRS  |

## Langkah 7 — Melakukan Uji Konsistensi

### a. Validasi Berhasil dan Mahasiswa Tidak Mengunduh Bukti

Validasi KRS dinyatakan berhasil karena seluruh persyaratan telah dipenuhi. Selanjutnya, sistem menyimpan pengajuan KRS dengan status menunggu persetujuan dosen wali dan menampilkan konfirmasi penyimpanan. Mahasiswa memutuskan untuk tidak mengunduh bukti sehingga proses pengunduhan tidak dijalankan.

**Hasil pengujian:** Konsisten. Use case `UC-01 Ajukan KRS` tetap dapat diselesaikan dengan berhasil meskipun `UC-03 Unduh Bukti Pengajuan` tidak dijalankan. Hal ini karena pengunduhan bukti merupakan proses tambahan yang bersifat opsional (`<<extend>>`).

### b. Validasi Gagal

Validasi KRS tidak berhasil karena terdapat ketentuan yang belum dipenuhi, seperti jadwal kuliah yang bertabrakan atau persyaratan mata kuliah yang belum terpenuhi. Sistem kemudian menampilkan pesan kegagalan sehingga pengajuan KRS tidak disimpan sebagai pengajuan yang berhasil.

**Hasil pengujian:** Konsisten. Use case `UC-02 Validasi KRS` menjadi bagian wajib (`<<include>>`) dari `UC-01 Ajukan KRS`. Ketika validasi gagal, proses pengajuan tidak dapat dilanjutkan ke tahap penyimpanan yang berhasil. Oleh karena itu, mahasiswa juga tidak dapat mengunduh bukti dari pengajuan yang berhasil.

### c. Validasi Berhasil dan Mahasiswa Memilih Mengunduh Bukti

Validasi KRS berhasil dilakukan, kemudian sistem menyimpan pengajuan dengan status menunggu persetujuan dosen wali. Setelah sistem menampilkan konfirmasi penyimpanan, mahasiswa memilih opsi untuk mengunduh bukti pengajuan. Sistem selanjutnya menyediakan bukti tersebut untuk diunduh.

**Hasil pengujian:** Konsisten. Use case `UC-03 Unduh Bukti Pengajuan` dapat dijalankan sebagai proses tambahan (`<<extend>>`) apabila mahasiswa memilih untuk mengunduh bukti setelah pengajuan KRS berhasil disimpan.

### Kesimpulan Uji Konsistensi

Berdasarkan ketiga kondisi pengujian tersebut, diagram dan deskripsi use case telah menunjukkan alur yang konsisten. Validasi merupakan tahapan wajib dalam pengajuan KRS, sedangkan pengunduhan bukti hanya dilakukan jika pengajuan berhasil disimpan dan mahasiswa memilih opsi tersebut. Selain itu, pengajuan yang berhasil disimpan tetap berstatus menunggu persetujuan dosen wali dan tidak langsung dianggap telah disetujui.