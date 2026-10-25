
### 1. Tujuan

Katalog use case kumulatif ini berisi daftar fungsi Sistem Informasi Akademik (SIA) dari Pertemuan 2, Pertemuan 3, dan Pertemuan 4. Katalog digunakan sebagai acuan untuk menyusun diagram use case kumulatif.

### 2. Daftar Use Case

| ID Use Case | Nama Use Case | Keterangan |
|---|---|---|
| SIA-UC01 | Lihat Jadwal Kuliah | Use case dari Pertemuan 2 untuk melihat jadwal kuliah. |
| SIA-UC02 | Kelola Jadwal Kuliah | Use case dari Pertemuan 2 untuk mengelola jadwal kuliah. |
| SIA-UC03 | Ajukan KRS | Use case dari Pertemuan 3 untuk mengajukan Kartu Rencana Studi (KRS). |
| SIA-UC04 | Validasi KRS | Use case dari Pertemuan 3 untuk memvalidasi pengajuan KRS. |
| SIA-UC05 | Unduh Bukti Pengajuan KRS | Use case dari Pertemuan 3 untuk mengunduh bukti pengajuan KRS. |
| SIA-UC06 | Proses Keputusan KRS | Use case dari Pertemuan 3 untuk memproses keputusan terhadap pengajuan KRS. |
| SIA-UC07 | Lihat Kalender Akademik | Use case baru dari Pertemuan 4 untuk melihat kalender akademik. |
| SIA-UC08 | Input Nilai Mata Kuliah | Use case baru dari Pertemuan 4 untuk menginput nilai mata kuliah yang diampu dosen. |
| SIA-UC09 | Lihat KHS | Use case baru dari Pertemuan 4 untuk melihat Kartu Hasil Studi pada semester yang nilainya telah dipublikasikan. |
| SIA-UC10 | Kelola Data Mahasiswa | Use case umum untuk mengelola data mahasiswa. |
| SIA-UC11 | Tambah Data Mahasiswa | Use case khusus untuk menambahkan data mahasiswa. |
| SIA-UC12 | Ubah Data Mahasiswa | Use case khusus untuk mengubah data mahasiswa. |
| SIA-UC13 | Hapus Data Mahasiswa | Use case khusus untuk menghapus data mahasiswa. |

### 3. Daftar Aktor

| Aktor | Keterangan |
|---|---|
| Civitas Akademika | Aktor umum yang memiliki fungsi bersama dalam kegiatan akademik. |
| Mahasiswa | Aktor khusus yang mewarisi fungsi Civitas Akademika. |
| Dosen | Aktor khusus yang mewarisi fungsi Civitas Akademika. |
| Admin Akademik | Aktor yang mengelola data mahasiswa dan fungsi administrasi akademik sesuai kebutuhan sistem. |
| Dosen Wali | Aktor dari pemodelan Pertemuan 3 yang tetap dipertahankan sesuai diagram sebelumnya. |



### 4. Generalization Aktor

Mahasiswa dan Dosen merupakan aktor khusus dari Civitas Akademika. Keduanya mewarisi fungsi yang dimiliki aktor umum tersebut.

Fungsi Lihat Kalender Akademik dihubungkan dengan aktor Civitas Akademika sehingga fungsi tersebut dapat diwarisi oleh Mahasiswa dan Dosen.

#### 4.1 Hierarki Aktor

| Aktor Umum | Aktor Khusus | Hubungan |
|---|---|---|
| Civitas Akademika | Mahasiswa | Mahasiswa merupakan spesialisasi dari Civitas Akademika. |
| Civitas Akademika | Dosen | Dosen merupakan spesialisasi dari Civitas Akademika. |

#### 4.2 Fungsi yang Diwarisi

Mahasiswa dan Dosen mewarisi fungsi Lihat Kalender Akademik dari aktor Civitas Akademika. Dengan demikian, kedua aktor dapat melihat kalender akademik tanpa perlu dibuatkan asosiasi langsung masing-masing ke use case tersebut.

Asosiasi Lihat Kalender Akademik digambar satu kali dari aktor Civitas Akademika.

#### 4.3 Alasan Pemodelan

Generalization digunakan karena Mahasiswa dan Dosen memiliki fungsi bersama sebagai Civitas Akademika, yaitu melihat kalender akademik. Pemodelan ini menghindari pengulangan asosiasi yang sama pada setiap aktor khusus dan membuat diagram use case lebih ringkas serta mudah dipahami.

### 5. Generalization Use Case

Use case Kelola Data Mahasiswa merupakan use case umum yang memiliki tiga use case khusus, yaitu:

1. **Tambah Data Mahasiswa:** menambahkan data mahasiswa baru.
2. **Ubah Data Mahasiswa:** memperbarui data mahasiswa yang sudah tersimpan.
3. **Hapus Data Mahasiswa:** menghapus data mahasiswa sesuai ketentuan sistem.

Ketiga use case khusus tersebut merupakan bentuk spesialisasi dari Kelola Data Mahasiswa.

#### 5.1 Use Case Umum

| ID | Nama Use Case | Keterangan |
|---|---|---|
| SIA-UC10 | Kelola Data Mahasiswa | Use case umum yang mencakup pengelolaan data mahasiswa oleh Admin Akademik. |

#### 5.2 Use Case Khusus

| ID | Nama Use Case | Perilaku Pembeda |
|---|---|---|
| SIA-UC11 | Tambah Data Mahasiswa | Admin Akademik memasukkan data mahasiswa baru agar data tersebut dapat tercatat dalam sistem. |
| SIA-UC12 | Ubah Data Mahasiswa | Admin Akademik memperbarui data mahasiswa yang sudah tersimpan. |
| SIA-UC13 | Hapus Data Mahasiswa | Admin Akademik menghapus data mahasiswa yang memenuhi ketentuan penghapusan. |

#### 5.3 Hubungan Generalization

SIA-UC11 Tambah Data Mahasiswa, SIA-UC12 Ubah Data Mahasiswa, dan SIA-UC13 Hapus Data Mahasiswa merupakan use case khusus dari SIA-UC10 Kelola Data Mahasiswa.

Generalization digunakan untuk menunjukkan bahwa ketiga tindakan tersebut merupakan bentuk khusus dari pengelolaan data mahasiswa, tetapi masing-masing memiliki perilaku yang berbeda.

Aktor Admin Akademik berasosiasi dengan fungsi Kelola Data Mahasiswa. Perilaku khusus tambah, ubah, dan hapus dijelaskan oleh masing-masing use case spesialisasinya.

### 6. Collaboration

| ID Collaboration | Nama Collaboration | Use Case yang Direalisasikan |
|---|---|---|
| SIA-CO01 | Input Nilai Mata Kuliah | SIA-UC08 — Input Nilai Mata Kuliah |
| SIA-CO02 | Lihat KHS | SIA-UC09 — Lihat KHS |

Collaboration digunakan untuk menunjukkan realisasi use case Input Nilai Mata Kuliah dan Lihat KHS dalam model analisis.

#### 6.1 Daftar Collaboration

| ID Collaboration | Nama Collaboration | Use Case yang Direalisasikan |
|---|---|---|
| SIA-CO01 | Input Nilai Mata Kuliah | SIA-UC08 — Input Nilai Mata Kuliah |
| SIA-CO02 | Lihat KHS | SIA-UC09 — Lihat KHS |

#### 6.2 Penjelasan Collaboration

**SIA-CO01 — Input Nilai Mata Kuliah**

Collaboration ini merealisasikan use case SIA-UC08 Input Nilai Mata Kuliah. Collaboration menunjukkan realisasi fungsi penginputan nilai mata kuliah oleh dosen pengampu.

**SIA-CO02 — Lihat KHS**

Collaboration ini merealisasikan use case SIA-UC09 Lihat KHS. Collaboration menunjukkan realisasi fungsi mahasiswa dalam melihat Kartu Hasil Studi (KHS), yang hanya menampilkan nilai yang telah dipublikasikan.

