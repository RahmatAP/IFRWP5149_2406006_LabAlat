Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap pengajuan menjalankan validasi KRS yang memeriksa kelengkapan,prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil,sistem menyimpan pengajuan berstatus menunggu persetujuan dosenwali. Pada konfirmasi penyimpanan, mahasiswa dapat memilihmengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRSdan memberikan catatan keputusan.

|ID | Kebutuhan Tugas | 
|--|--|
|SIA-R01 | Mahasiswa dapat melihat jadwal kuliah |
|SIA-R02 | Admin akademik dapat mengelola jadwal kuliah |
|SIA-R03 | Mahasiswa dapat mengajukan KRS |
|SIA-R04 | Sistem memvalidasi KRS sebagai bagian pengajuan |
|SIA-R05 | Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasipengajuan |
|SIA-R06 | Dosen wali dapat memproses persetujuan atau penolakan KRS |

Kode dimulai dari R03 agar kebutuhan jadwal SIA-R01 dan SIA-R02 dariPertemuan 2 tetap mempunyai identitas berbeda.
Batas dan asumsi:
• Pengguna telah terautentikasi.
• Data mata kuliah, prasyarat, dan jadwal tersedia.
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
• KRS tersimpan belum berarti disetujui.
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luartugas.

Langkah 2 Identifikasi Aktor dan use case

|ID | Aktor          | Tujuan terhadap sistem |  
|--|--|--|
|SIA-UC01| Mahasiswa      | Pengajuan KRS, unduh bukti, melihat jadwal kuliah |
|SIA-UC02| Wali dosen     | Memproses Persetujuan atau penoloakan KRS |

Langkah 3 - Tentukan Include


Langkah 4 - Tentukan extend

