## Review dan Revisi

Berdasarkan hasil pemeriksaan diagram dan pengujian konsistensi yang telah dilakukan, terdapat beberapa bagian yang masih perlu diperbaiki, yaitu sebagai berikut.

| No. | Temuan | Perbaikan yang Diperlukan | Alasan |
|---|---|---|---|
| 1 | Hubungan generalization antaraktor belum terlihat dengan baik. | Perjelas hubungan antara Mahasiswa dan Dosen dengan Civitas Akademika menggunakan garis utuh serta segitiga kosong yang mengarah ke aktor umum. | Generalization menunjukkan bahwa aktor khusus mewarisi fungsi dari aktor umum. |
| 2 | Dosen memiliki hubungan dengan use case Ajukan KRS. | Hapus garis asosiasi tersebut apabila menghubungkan Dosen dengan UC-01 Ajukan KRS. | Pengajuan KRS merupakan tugas mahasiswa, bukan dosen. |
| 3 | ID collaboration pada diagram berbeda dengan yang tercantum dalam katalog. | Sesuaikan ID pada diagram menjadi SIA-CO01 untuk Input Nilai Mata Kuliah dan SIA-CO02 untuk Lihat KHS. | Penamaan ID harus sama agar tidak menimbulkan perbedaan antara diagram dan dokumentasi. |
| 4 | Penggunaan notasi collaboration masih perlu diperiksa. | Periksa dan sesuaikan simbol serta hubungan collaboration dengan notasi yang dicontohkan dalam modul. | Penggunaan notasi yang tepat diperlukan agar diagram sesuai dengan ketentuan tugas. |
| 5 | Beberapa aktor berada terlalu dekat atau menyentuh batas sistem. | Atur kembali posisi aktor agar berada di luar batas sistem dan rapikan garis asosiasi yang menghubungkannya. | Aktor merupakan pihak di luar sistem yang berinteraksi dengan sistem tersebut. |

## Kesimpulan

Berdasarkan pengujian terhadap tiga situasi yang telah ditentukan, model Sistem Informasi Akademik sudah dapat menggambarkan aturan akses dan pengelolaan data sesuai dengan skenario pengujian. Meskipun demikian, masih terdapat beberapa bagian diagram yang perlu diperbaiki, terutama hubungan generalization antaraktor, asosiasi antara aktor dan use case, kesesuaian ID collaboration, serta penggunaan notasi collaboration.

Setelah seluruh perbaikan dilakukan, diagram dan deskripsi use case perlu disimpan sebagai versi revisi agar dokumentasi akhir sesuai dengan hasil pemeriksaan.