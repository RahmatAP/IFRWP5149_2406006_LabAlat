# Deskripsi Use Case Sistem Informasi Akademik (SIA)
## Praktikum Pertemuan 4

### 1. SIA-UC08 — Input Nilai Mata Kuliah

| Elemen | Deskripsi |
|---|---|
| ID Use Case | SIA-UC08 |
| Nama Use Case | Input Nilai Mata Kuliah |
| Aktor Utama | Dosen |
| Tujuan | Memasukkan nilai mahasiswa untuk mata kuliah yang diampu oleh dosen. |
| Pemicu | Dosen memilih fungsi input nilai mata kuliah. |
| Prasyarat | Dosen telah terautentikasi, memiliki hak akses, dan merupakan dosen pengampu mata kuliah yang dipilih. |
| Pascakondisi Berhasil | Nilai mahasiswa yang valid tersimpan sebagai nilai yang belum dipublikasikan, sesuai aturan publikasi nilai dalam sistem. |
| Pascakondisi Gagal | Nilai tidak valid atau akses tidak memenuhi syarat ditolak dan tidak disimpan sebagai hasil input yang berhasil. |
| Collaboration | SIA-CO01 — Input Nilai Mata Kuliah |

#### Alur Utama

1. Dosen membuka fungsi Input Nilai Mata Kuliah.
2. Sistem memeriksa hak akses dosen terhadap mata kuliah yang dipilih.
3. Sistem menampilkan daftar mahasiswa pada mata kuliah tersebut.
4. Dosen memasukkan nilai mahasiswa sesuai rentang nilai yang sah.
5. Dosen mengirimkan data nilai.
6. Sistem memvalidasi nilai yang dimasukkan.
7. Sistem menyimpan nilai yang valid.
8. Sistem menampilkan konfirmasi bahwa nilai berhasil disimpan.

#### Alur Alternatif

**A1 — Dosen bukan pengampu mata kuliah**

1. Dosen memilih mata kuliah yang tidak diampunya.
2. Sistem menolak akses input nilai.
3. Sistem tidak menyimpan perubahan nilai.

**A2 — Nilai berada di luar rentang yang sah**

1. Dosen memasukkan nilai di luar rentang yang sah.
2. Sistem menolak nilai tersebut.
3. Sistem menampilkan pesan kesalahan agar dosen memperbaiki nilai.
4. Nilai yang tidak valid tidak disimpan.

### 2. SIA-UC09 — Lihat KHS

| Elemen | Deskripsi |
|---|---|
| ID Use Case | SIA-UC09 |
| Nama Use Case | Lihat KHS |
| Aktor Utama | Mahasiswa |
| Tujuan | Melihat Kartu Hasil Studi (KHS) untuk semester yang dipilih. |
| Prasyarat | Mahasiswa telah terautentikasi dan memiliki hak akses untuk melihat KHS miliknya. |
| Alur Ringkas | Mahasiswa memilih semester, sistem mengambil hasil studi yang tersedia, lalu menampilkan KHS. |
| Aturan Penting | KHS hanya menampilkan nilai yang sudah dipublikasikan. Nilai yang belum dipublikasikan tidak ditampilkan. |
| Pascakondisi | KHS untuk semester yang dipilih ditampilkan berdasarkan nilai yang telah dipublikasikan. |
| Collaboration | SIA-CO02 — Lihat KHS |