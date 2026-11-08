

| No. | Temuan | Perbaikan yang Diperlukan | Alasan |
|---|---|---|---|
| 1 | Terdapat decision node kedua yang tidak memiliki keterangan setelah proses pemeriksaan kelengkapan nilai. | Periksa kembali fungsi simbol tersebut dan ubah menjadi merge node apabila digunakan untuk menggabungkan alur. | Decision node digunakan untuk percabangan kondisi, sedangkan merge node digunakan untuk menggabungkan alur alternatif. |
| 2 | Alur aktivitas melengkapi nilai mata kuliah belum kembali ke proses pemeriksaan kelengkapan nilai. | Hubungkan kembali aktivitas melengkapi nilai ke decision node pemeriksaan kelengkapan nilai. | Sistem perlu melakukan pemeriksaan ulang setelah dosen melengkapi nilai yang belum tersedia. |
| 3 | Decision node pemeriksaan kelengkapan nilai belum ditempatkan pada swimlane Sistem. | Pindahkan decision node ke dalam swimlane Sistem. | Pemeriksaan kelengkapan nilai merupakan tanggung jawab sistem. |
| 4 | Aktivitas penerbitan KHS dan pengiriman pemberitahuan menggunakan percabangan paralel, tetapi hubungan penggabungannya belum jelas. | Perjelas penggunaan fork dan join pada kedua aktivitas tersebut. | Fork membagi aktivitas menjadi proses paralel, sedangkan join menyinkronkan kembali proses tersebut. |
| 5 | Identitas atau judul diagram belum ditampilkan secara jelas. | Tambahkan judul **Activity Diagram Sistem Informasi Akademik (SIA)**. | Judul diperlukan untuk menunjukkan sistem yang sedang dimodelkan. |
| 6 | Hubungan alur dari sistem menuju aktivitas mahasiswa melihat KHS perlu diperjelas. | Pastikan aktivitas mahasiswa melihat KHS dilakukan setelah sistem menerbitkan KHS pada portal akademik. | Hal ini memastikan urutan aktivitas sesuai dengan proses bisnis yang dimodelkan. |

