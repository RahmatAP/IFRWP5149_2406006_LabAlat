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

**Langkah 2 Identifikasi Aktor dan use case**

|ID | Aktor          | Tujuan terhadap sistem |  
|--|--|--|
|SIA-UC01| Mahasiswa      | Pengajuan KRS, unduh bukti, melihat jadwal kuliah |
|SIA-UC02| Wali dosen     | Memproses Persetujuan atau penoloakan KRS |

**Langkah 3 & 4 - menentukan include dan extend**

1. Inlude
Ajukan KRS -> Validasi KRS
Validasi selalu menjadi bagian dari proses pengajuan KRS. Sistem harus memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal sebelum menyimpan pengajuan.

2. Extend
Unduh bukti pengajuan KRS -> Ajukan KRS
Pengunduhan merupakan perilaku tambahan yang hanya dilakukan jika mahasiswa memilihnya setelah konfirmasi. Pengajuan tetap berhasil walaupun mahasiswa tidak mengunduh bukti.

| Elemen | Include | Extend | 
|--|--|--|
|Use case asal |	Ajukan KRS	| Unduh bukti pengajuan KRS |
| Use case tujuan |	Validasi KRS | Ajukan KRS |
| Arah panah |	Ajukan KRS menuju Validasi KRS | Unduh bukti menuju Ajukan KRS |
|Kondisi | 	Selalu dilakukan saat validasi pengajuan |	[mahasiswa memilih unduh bukti] |
|Extension point |	Tidak diperlukan |	Bukti pengajuan tersedia |
|Alasan |	Validasi merupakan bagian wajib pengajuan |	Pengunduhan tidak menentukan keberhasilan pengajuan |

## Langkah 5 — Susun Deskripsi Use Case

### A. SIA-UC01 — Ajukan KRS

| Elemen | Deskripsi |
|---|---|
| ID dan Nama | SIA-UC01 — Ajukan KRS |
| Sumber Kebutuhan | SIA-R03, SIA-R04, SIA-R05 |
| Tujuan | Mahasiswa memperoleh pengajuan KRS yang berhasil tersimpan. |
| Aktor Utama | Mahasiswa |
| Aktor Pendukung | Tidak ada aktor pendukung yang ditentukan dalam skenario. |
| Pemicu | Mahasiswa memilih fungsi pengajuan KRS. |
| Prasyarat | Mahasiswa telah terautentikasi; data mata kuliah, prasyarat, dan jadwal tersedia. |
| Pascakondisi Berhasil | Pengajuan tersimpan dengan nomor pengajuan dan status Menunggu persetujuan dosen wali. |
| Pascakondisi Gagal | Tidak ada pengajuan baru yang berhasil tersimpan. |
| Include | SIA-UC02 — Validasi KRS |
| Extend | SIA-UC03 — Unduh bukti pengajuan KRS |
| Extension Point | Bukti pengajuan tersedia. |
| Kondisi Extend | Mahasiswa memilih unduh bukti. |

**Alur Utama**

| Langkah | Tindakan Mahasiswa | Respons Sistem |
|---|---|---|
| 1 | Membuka fungsi pengajuan KRS. | Menampilkan formulir pengajuan. |
| 2 | Memilih mata kuliah yang akan diambil. | Menampung pilihan mahasiswa. |
| 3 | Mengirim pengajuan KRS. | Memeriksa kelengkapan data pengajuan. |
| 4 | — | Menjalankan SIA-UC02 untuk memvalidasi KRS. |
| 5 | — | Jika validasi berhasil, menyimpan pengajuan dan memberikan nomor pengajuan. |
| 6 | Melihat konfirmasi penyimpanan. | Menampilkan nomor pengajuan dan status Menunggu persetujuan dosen wali. |
| 7 | Mengakhiri proses atau memilih unduh bukti. | Menutup proses pengajuan atau menjalankan SIA-UC03 jika dipilih. |

**Alur Alternatif/Pengecualian**

| Kode | Kondisi | Respons Sistem |
|---|---|---|
| A1 | Data pengajuan tidak lengkap. | Menampilkan informasi kesalahan dan meminta mahasiswa melengkapi data. Pengajuan belum berhasil tersimpan. |
| A2 | Prasyarat mata kuliah tidak terpenuhi. | Menampilkan hasil validasi gagal. Pengajuan belum berhasil tersimpan. |
| A3 | Jadwal mata kuliah berbenturan. | Menampilkan informasi benturan jadwal. Pengajuan belum berhasil tersimpan. |
| A4 | Mahasiswa tidak memilih unduh bukti. | Pengajuan tetap berhasil tersimpan tanpa menjalankan SIA-UC03. |

### B. SIA-UC02 — Validasi KRS

| Elemen | Deskripsi |
|---|---|
| ID dan Nama | SIA-UC02 — Validasi KRS |
| Sumber Kebutuhan | SIA-R04 |
| Tujuan | Memastikan pengajuan KRS memenuhi ketentuan validasi. |
| Aktor Utama | Tidak ada aktor yang memulai secara langsung; use case dipanggil oleh SIA-UC01. |
| Aktor Pendukung | Tidak ada. |
| Pemicu | SIA-UC01 meminta sistem memvalidasi pengajuan KRS. |
| Prasyarat | Pengajuan telah dikirim; data mata kuliah, prasyarat, dan jadwal tersedia. |
| Pascakondisi Berhasil | Sistem menyatakan validasi berhasil sehingga pengajuan dapat disimpan oleh SIA-UC01. |
| Pascakondisi Gagal | Sistem memberikan hasil validasi gagal dan pengajuan belum berhasil tersimpan. |
| Relasi | SIA-UC01 `«include»` SIA-UC02. |

**Alur Utama**

| Langkah | Tindakan Pemanggil | Respons Sistem |
|---|---|---|
| 1 | SIA-UC01 meminta validasi. | Menerima data pengajuan KRS. |
| 2 | — | Memeriksa kelengkapan data pengajuan. |
| 3 | — | Memeriksa prasyarat mata kuliah yang dipilih. |
| 4 | — | Memeriksa benturan jadwal mata kuliah. |
| 5 | — | Jika seluruh pemeriksaan berhasil, mengembalikan hasil validasi berhasil kepada SIA-UC01. |

**Alur Alternatif/Pengecualian**

| Kode | Kondisi | Respons Sistem |
|---|---|---|
| A1 | Data tidak lengkap. | Mengembalikan hasil validasi gagal beserta informasi data yang belum lengkap. |
| A2 | Prasyarat tidak terpenuhi. | Mengembalikan hasil validasi gagal beserta informasi prasyarat yang tidak terpenuhi. |
| A3 | Jadwal berbenturan. | Mengembalikan hasil validasi gagal beserta informasi benturan jadwal. |

### C. SIA-UC03 — Unduh Bukti Pengajuan KRS

| Elemen | Deskripsi |
|---|---|
| ID dan Nama | SIA-UC03 — Unduh bukti pengajuan KRS |
| Sumber Kebutuhan | SIA-R05 |
| Tujuan | Mahasiswa memperoleh bukti pengajuan KRS. |
| Aktor Utama | Mahasiswa |
| Aktor Pendukung | Tidak ada. |
| Pemicu | Mahasiswa memilih opsi unduh bukti pada konfirmasi pengajuan. |
| Prasyarat | Pengajuan KRS berhasil tersimpan dan konfirmasi pengajuan tersedia. |
| Pascakondisi Berhasil | Bukti pengajuan tersedia untuk diunduh mahasiswa. |
| Pascakondisi Gagal | Pengajuan tetap tersimpan; kegagalan unduh tidak membatalkan pengajuan. |
| Relasi | SIA-UC03 `«extend»` SIA-UC01. |
| Extension Point | Bukti pengajuan tersedia. |
| Kondisi Extend | Mahasiswa memilih unduh bukti. |

**Alur Utama**

| Langkah | Tindakan Mahasiswa | Respons Sistem |
|---|---|---|
| 1 | Melihat konfirmasi pengajuan KRS. | Menampilkan informasi pengajuan yang berhasil disimpan. |
| 2 | Memilih opsi unduh bukti. | Menyiapkan bukti berdasarkan data pengajuan. |
| 3 | Memulai pengunduhan. | Menyediakan berkas bukti pengajuan untuk diunduh. |
| 4 | Menerima berkas. | Menyelesaikan proses penyediaan bukti. |

**Alur Alternatif/Pengecualian**

| Kode | Kondisi | Respons Sistem |
|---|---|---|
| A1 | Mahasiswa tidak memilih unduh bukti. | SIA-UC03 tidak dijalankan dan SIA-UC01 tetap berhasil. |
| A2 | Bukti tidak dapat disiapkan. | Menampilkan informasi bahwa bukti belum dapat diunduh. Pengajuan tetap tersimpan. |

### D. SIA-UC04 — Proses Keputusan KRS

| Elemen | Deskripsi |
|---|---|
| ID dan Nama | SIA-UC04 — Proses keputusan KRS |
| Sumber Kebutuhan | SIA-R06 |
| Tujuan | Menetapkan persetujuan atau penolakan KRS beserta catatan keputusan. |
| Aktor Utama | Dosen wali |
| Aktor Pendukung | Tidak ada yang ditentukan dalam skenario. |
| Pemicu | Dosen wali memilih pengajuan KRS untuk diproses. |
| Prasyarat | Dosen wali telah terautentikasi dan pengajuan KRS tersedia untuk diproses. |
| Pascakondisi Berhasil | Keputusan persetujuan atau penolakan beserta catatan keputusan tersimpan. |
| Pascakondisi Gagal | Keputusan belum berhasil ditetapkan dan pengajuan tidak dianggap telah diputuskan. |

**Alur Utama**

| Langkah | Tindakan Dosen Wali | Respons Sistem |
|---|---|---|
| 1 | Membuka fungsi pemrosesan keputusan KRS. | Menampilkan daftar pengajuan yang dapat diproses. |
| 2 | Memilih pengajuan KRS. | Menampilkan informasi pengajuan. |
| 3 | Memeriksa pengajuan. | Menyediakan informasi pengajuan untuk ditinjau. |
| 4 | Memilih persetujuan atau penolakan. | Menerima pilihan keputusan. |
| 5 | Memasukkan catatan keputusan. | Memeriksa kelengkapan keputusan dan catatan. |
| 6 | Mengonfirmasi keputusan. | Menyimpan keputusan beserta catatannya. |
| 7 | Melihat hasil pemrosesan. | Menampilkan hasil keputusan yang telah tersimpan. |

**Alur Alternatif/Pengecualian**

| Kode | Kondisi | Respons Sistem |
|---|---|---|
| A1 | Pengajuan tidak ditemukan. | Menampilkan informasi bahwa pengajuan tidak tersedia dan keputusan belum diproses. |
| A2 | Keputusan atau catatan belum lengkap. | Meminta dosen wali melengkapi data sebelum menyimpan. |
| A3 | Penyimpanan keputusan gagal. | Menampilkan informasi kegagalan; keputusan belum dianggap berhasil ditetapkan. |

**Langkah 6**

## Langkah 7 — Uji Konsistensi

Pengujian konsistensi dilakukan untuk memastikan bahwa use case diagram dan use case description memberikan hasil yang sesuai pada tiga situasi pengajuan KRS.

### Tabel Pengujian Konsistensi

| No. | Situasi Pengujian | Hasil yang Diharapkan | Konsistensi Diagram dan Deskripsi |
|---|---|---|---|
| 1 | Validasi berhasil dan mahasiswa tidak mengunduh bukti. | Sistem menyimpan pengajuan KRS dengan nomor pengajuan dan status Menunggu persetujuan dosen wali. Pengajuan tetap berhasil meskipun mahasiswa tidak mengunduh bukti. | Konsisten. Relasi `«include»` memastikan validasi dilakukan, sedangkan `«extend»` bersifat opsional. |
| 2 | Validasi gagal. | Sistem menampilkan informasi kegagalan validasi dan pengajuan KRS tidak berhasil tersimpan. | Konsisten. Use case Validasi KRS menjadi bagian dari Ajukan KRS. Jika validasi gagal, pengajuan tidak dilanjutkan sebagai pengajuan yang berhasil tersimpan. |
| 3 | Validasi berhasil dan mahasiswa memilih mengunduh bukti. | Sistem menyimpan pengajuan KRS dengan status Menunggu persetujuan dosen wali, kemudian menyediakan bukti pengajuan untuk diunduh mahasiswa. | Konsisten. Relasi `«include»` menjalankan validasi, sedangkan relasi `«extend»` menjalankan pengunduhan bukti jika mahasiswa memilihnya. |

### Analisis Hasil Pengujian

Berdasarkan ketiga situasi pengujian, diagram use case dan use case description menunjukkan hasil yang konsisten dengan skenario tugas Sistem Informasi Akademik. Relasi `«include»` pada Ajukan KRS dan Validasi KRS menunjukkan bahwa validasi merupakan bagian wajib dari proses pengajuan. Sementara itu, relasi `«extend»` pada Unduh Bukti Pengajuan KRS menunjukkan bahwa pengunduhan bukti hanya dilakukan apabila mahasiswa memilihnya.

Apabila validasi gagal, pengajuan belum berhasil tersimpan. Apabila validasi berhasil, pengajuan tersimpan dengan status Menunggu persetujuan dosen wali, baik mahasiswa mengunduh bukti maupun tidak.

### Kesimpulan

Hasil pengujian menunjukkan bahwa diagram use case dan use case description konsisten untuk ketiga situasi yang diuji. Pengajuan KRS tetap mengikuti hasil validasi, sedangkan pengunduhan bukti merupakan fungsi tambahan yang tidak menentukan keberhasilan pengajuan. Dengan demikian, rancangan telah sesuai dengan skenario dan ketentuan pada Jobsheet Praktikum Pertemuan 3.