Mahasiswa mengajukan peminjaman peralatan dengan memilih alat,jumlah, dan rentang waktu. Sistem memeriksa ketersediaan. Jikatersedia dan data lengkap, sistem menyimpan pengajuan berstatusmenunggu keputusan. Pada tampilan konfirmasi, mahasiswa dapatmemilih mencetak bukti pengajuan. Petugas mengelola data peralatanserta menyetujui atau menolak pengajuan. Kepala laboratorium melihatlaporan peminjaman.

Skenario berikut merupakan bahan latihan yang ditetapkan untukjobsheet, bukan hasil pengumpulan kebutuhan laboratorium nyata.

Mahasiswa mengajukan peminjaman peralatan dengan memilih alat,jumlah, dan rentang waktu. Sistem memeriksa ketersediaan. Jikatersedia dan data lengkap, sistem menyimpan pengajuan berstatusmenunggu keputusan. Pada tampilan konfirmasi, mahasiswa dapatmemilih mencetak bukti pengajuan. Petugas mengelola data peralatanserta menyetujui atau menolak pengajuan. Kepala laboratorium melihatlaporan peminjaman.


## Tabel Kebutuhan Sistem

| ID Kebutuhan | Deskripsi Kebutuhan |
|---|---|
| LAB-R01 | Mahasiswa dapat melihat ketersediaan peralatan laboratorium. |
| LAB-R02 | Petugas dapat mengelola data peralatan laboratorium. |
| LAB-R03 | Mahasiswa dapat mengajukan peminjaman peralatan. Sistem memeriksa ketersediaan peralatan sebelum menyimpan pengajuan. |
| LAB-R04 | Mahasiswa dapat mencetak bukti konfirmasi pengajuan jika memilih opsi tersebut. |
| LAB-R05 | Petugas dapat menetapkan persetujuan atau penolakan pengajuan peminjaman. |
| LAB-R06 | Kepala laboratorium dapat melihat laporan peminjaman peralatan. |

LAB-R01 dan LAB-R02 mempertahankan fungsi yang diperkenalkan pada Pertemuan 2. Kebutuhan berikutnya menambah ruang lingkup analisis tanpamengubah arti kebutuhan lama.
Batas sistem dan aturan:
• Sistem mencatat dan menyediakan informasi; perpindahan fisik alat tidakterjadi di dalam perangkat lunak.
• Pengguna telah terautentikasi dan memiliki hak akses sesuai peran.
• Pengajuan yang diterima sistem berstatus Menunggu keputusan, bukanotomatis Disetujui.
• Pengajuan dengan peralatan tidak tersedia tidak disimpan sebagaipengajuan berhasil.
• Pencetakan bukti tidak menjadi syarat keberhasilan pengajuan.
• Persetujuan petugas belum dimodelkan sebagai reservasi teknis stok.
• Pengambilan, pengembalian, kondisi alat, dan denda belum dianalisispada potongan model ini.
Kriteria penerimaan model: semua kebutuhan di atas mempunyairepresentasi, include dan extend mempunyai alasan yang jelas, serta diagramkonsisten dengan deskripsinya.


| Aktor | Tujuan terhadap sistem |
|---|---|
|Mahasiswa| Melihat ketersediaan, mengajukan peminjaman, danmencetak bukti |
|Petugas Laboratorium | Mengelola peralatan dan memproses keputusan |
|Kepala Laboratorium | Melihat laporan peminjaman |