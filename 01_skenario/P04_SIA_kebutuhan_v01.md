# Pertemuan 4 — Sistem Informasi Akademik, Layanan Hasil Studi

## 1. Kebutuhan Tugas

| ID      | Kebutuhan tugas                                                                                     |
| ------- | --------------------------------------------------------------------------------------------------- |
| SIA-R07 | Mahasiswa dan Dosen, sebagai Civitas Akademika, dapat melihat kalender akademik.                    |
| SIA-R08 | Dosen dapat menginput nilai mata kuliah yang diampunya.                                             |
| SIA-R09 | Mahasiswa dapat melihat KHS untuk semester yang nilainya sudah dipublikasikan.                      |
| SIA-R10 | Admin Akademik dapat mengelola data mahasiswa.                                                      |
| SIA-R11 | Pengelolaan data mahasiswa terdiri dari tiga fungsi khusus: tambah, ubah, dan hapus data mahasiswa. |
| SIA-R12 | Model menunjukkan collaboration yang merealisasikan Input Nilai Mata Kuliah dan Lihat KHS.          |

## 2. Batas Sistem

- Sistem yang menjadi objek analisis adalah Sistem Informasi Akademik (SIA).
- Kalender akademik mengacu pada jadwal resmi yang telah ditetapkan oleh institusi.
- Proses pengisian nilai dilakukan oleh dosen yang bertanggung jawab atas mata kuliah tersebut.
- Mahasiswa hanya dapat mengakses KHS apabila nilai pada semester terkait telah dipublikasikan.
- Penghapusan data mahasiswa hanya diperbolehkan jika mahasiswa tersebut tidak memiliki data akademik yang masih aktif.
- Pengajuan KRS tetap dimasukkan dalam diagram kumulatif yang telah dibuat pada Pertemuan 3.
- Pembahasan mengenai pembayaran dan perancangan basis data tidak termasuk dalam cakupan tugas ini.

## 3. Asumsi

- Setiap pengguna telah melakukan login dan memperoleh hak akses sesuai dengan perannya masing-masing.
- Informasi mengenai kalender akademik telah tersedia di dalam sistem.
- Data mata kuliah beserta dosen pengampunya sudah tersedia sebelum proses penginputan nilai dimulai.
- Nilai yang dimasukkan oleh dosen belum dinyatakan resmi sebelum melalui proses publikasi sesuai aturan institusi.
- KHS hanya dapat menampilkan nilai semester yang sudah diumumkan secara resmi.
- Admin Akademik berhak melakukan penambahan, perubahan, dan penghapusan data mahasiswa dengan tetap mengikuti ketentuan yang berlaku.