# Hasil Review Jobsheet — Sistem Informasi Akademik

| No. | Temuan | Perbaikan yang perlu dilakukan | Alasan |
| --- | --- | --- | --- |
| 1 | Kondisi pada relasi `<<extend>>` belum dituliskan | Cantumkan kondisi `[pengajuan berhasil disimpan dan mahasiswa memilih unduh]` pada relasi `<<extend>>`. | Memperjelas situasi ketika use case Unduh Bukti Pengajuan dijalankan. |
| 2 | Extension point belum dijelaskan secara langsung | Tambahkan extension point pada UC-01 Ajukan KRS apabila hal tersebut diwajibkan dalam modul. | Memperlihatkan bagian yang menjadi titik perluasan bagi perilaku opsional pada use case. |
| 3 | Garis asosiasi dari Mahasiswa ke UC-03 melintasi bagian tengah diagram | Sesuaikan letak use case atau atur kembali jalur garis agar tampilan diagram lebih teratur. | Mempermudah pembaca dalam memahami hubungan antara aktor dan use case. |
| 4 | Konsistensi pascakondisi pengajuan masih perlu diperiksa | Pastikan bahwa pengajuan yang berhasil disimpan memiliki status menunggu persetujuan dosen wali, sedangkan validasi yang gagal tidak menghasilkan pengajuan yang berhasil disimpan. | Memastikan kesesuaian antara diagram, deskripsi use case, dan skenario pengujian. |

## Kesimpulan Review

Dari hasil peninjauan, diagram use case Sistem Informasi Akademik telah memuat aktor, batas sistem, serta hubungan `<<include>>` dan `<<extend>>` yang sesuai. Perbaikan yang perlu diperhatikan meliputi penambahan keterangan kondisi perluasan, pengecekan extension point berdasarkan ketentuan modul, penataan diagram agar lebih rapi, serta penyelarasan pascakondisi. Setelah seluruh perbaikan selesai, diagram dan deskripsi use case disimpan sebagai versi yang telah direvisi.