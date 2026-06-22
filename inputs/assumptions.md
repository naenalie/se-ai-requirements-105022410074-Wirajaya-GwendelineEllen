# Daftar Asumsi Proyek (Project Assumptions)

Dokumen ini mendokumentasikan semua asumsi awal yang dibuat selama proses Requirements Engineering untuk Student Task Management System.

## Asumsi Operasional
- **[ASSUMPTION]** Seluruh mahasiswa, dosen, dan administrator memiliki akses internet yang stabil untuk mengakses sistem kampus ini secara daring.
- **[ASSUMPTION]** Identitas pengguna (SSO/Kredensial Kampus) sudah dikelola secara terpusat oleh server kampus, sehingga sistem ini hanya perlu mengintegrasikannya.
- **[ASSUMPTION]** Kuota penyimpanan server kampus mencukupi untuk menampung file tugas seluruh mahasiswa selama minimal satu tahun ajaran berjalan.

## Asumsi Fungsional
- **[ASSUMPTION]** Administrator adalah satu-satunya peran yang berwenang untuk membuat akun dosen baru dan mendaftarkan mata kuliah baru ke dalam sistem.
- **[ASSUMPTION]** Sistem tidak perlu mengimplementasikan fitur ruang obrolan (chat) langsung antar-pengguna, karena koordinasi dapat dilakukan melalui platform komunikasi eksternal.
