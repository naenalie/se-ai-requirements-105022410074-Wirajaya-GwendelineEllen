# Project Inception: Student Task Management System

## 1. Ringkasan Masalah Bisnis

Pengelolaan tugas perkuliahan di lingkungan kampus saat ini masih berlangsung secara terpisah-pisah dan tidak terstandarisasi. Dosen menyampaikan tugas melalui berbagai saluran informal seperti grup percakapan atau email, sementara pengumpulan berkas tugas dilakukan tanpa sistem yang terintegrasi. Kondisi ini mengakibatkan dosen kesulitan memantau status pengumpulan secara terpusat, mahasiswa sering melewatkan tenggat waktu karena tidak adanya sistem pengingat yang terstruktur, dan proses penilaian berlangsung lambat karena tidak ada mekanisme umpan balik yang efisien.

Selain itu, administrator tidak memiliki visibilitas yang memadai atas data aktivitas akademik terkait tugas, sehingga pembuatan laporan dan audit data menjadi tidak dapat diandalkan. Ketidakterpaduan sistem yang ada meningkatkan risiko kesalahan data, kehilangan berkas, dan inefisiensi operasional yang berdampak pada kualitas proses pembelajaran.

---

## 2. Pemisahan Masalah dan Solusi

- **Masalah Bisnis**: Proses pengelolaan tugas perkuliahan yang tidak terintegrasi menyebabkan inefisiensi dalam distribusi tugas, pengumpulan berkas, penilaian, pemantauan tenggat waktu, dan pelaporan akademik. Tidak adanya sistem terpusat membuat dosen, mahasiswa, dan administrator bekerja dengan cara dan platform yang berbeda-beda, meningkatkan risiko miskomunikasi dan kehilangan data.

- **Solusi yang Diusulkan**: Mengembangkan sistem manajemen tugas perkuliahan berbasis aplikasi digital yang menyatukan seluruh aktivitas terkait tugas — mulai dari pembuatan dan distribusi tugas, pengumpulan berkas, penilaian dan umpan balik, hingga pelaporan dan audit — dalam satu platform terintegrasi yang dapat diakses oleh seluruh pemangku kepentingan.

---

## 3. Tujuan Bisnis (Business Goals)

1. **Sentralisasi Pengelolaan Tugas**: Memusatkan seluruh proses terkait tugas perkuliahan (distribusi, pengumpulan, penilaian, dan pelaporan) dalam satu sistem yang dapat diakses oleh semua pihak yang berwenang.
2. **Peningkatan Efisiensi Waktu**: Mengurangi waktu yang dibutuhkan dosen untuk membuat, mendistribusikan, dan menilai tugas, serta mengurangi waktu mahasiswa dalam mencari informasi tugas.
3. **Minimalisasi Kesalahan dan Kehilangan Data**: Menghilangkan risiko kehilangan berkas tugas, duplikasi data, dan kesalahan pencatatan nilai yang terjadi dalam proses manual.
4. **Pemantauan Tenggat Waktu yang Andal**: Memastikan notifikasi dan pengingat tepat waktu kepada mahasiswa sebelum tenggat waktu dan kepada dosen saat terjadi keterlambatan.
5. **Pelaporan Akademik yang Terstandarisasi**: Menyediakan kemampuan bagi administrator untuk menghasilkan laporan aktivitas tugas yang akurat sebagai dasar pengambilan keputusan manajerial.

---

## 4. Analisis Stakeholder dan Kebutuhannya

### Stakeholder Primer

- **Dosen**: Membutuhkan antarmuka untuk membuat tugas secara cepat dengan penetapan tenggat waktu, melihat status pengumpulan setiap mahasiswa secara real-time, memberikan nilai dan umpan balik tekstual langsung di sistem, serta mendapatkan notifikasi otomatis ketika ada mahasiswa yang terlambat mengumpulkan tugas.

- **Mahasiswa**: Membutuhkan halaman dashboard yang menampilkan daftar seluruh tugas aktif beserta sisa waktu tenggat secara jelas, kemampuan mengunggah berkas tugas dalam format PDF dan ZIP, penerimaan bukti tanda terima digital setelah berhasil mengunggah, notifikasi/pengingat otomatis sebelum tenggat waktu berakhir, serta antarmuka yang dapat diakses dengan baik melalui perangkat mobile.

- **Administrator**: Membutuhkan modul pengelolaan pengguna dan mata kuliah yang dapat dikonfigurasi tanpa perlu mengubah kode program, log aktivitas sistem yang mencatat setiap tindakan pengunggahan dan perubahan nilai untuk keperluan audit integritas data, serta kemampuan impor data pengguna secara massal melalui format CSV.

### Stakeholder Sekunder

- **Institusi/Manajemen Kampus**: Mengharapkan sistem memenuhi standar keamanan data akademik yang berlaku, menghasilkan laporan yang dapat digunakan untuk evaluasi kualitas proses pembelajaran, serta memiliki keandalan (uptime) tinggi agar tidak mengganggu aktivitas akademik.

---

## 5. Ruang Lingkup (Scope Boundaries)

- **In-Scope**:
  - Pembuatan dan distribusi tugas oleh dosen dengan penetapan tenggat waktu.
  - Pengumpulan berkas tugas oleh mahasiswa melalui sistem dengan batas format file PDF dan ZIP.
  - Pemberian nilai dan umpan balik tekstual oleh dosen melalui sistem.
  - Notifikasi otomatis kepada mahasiswa sebelum tenggat waktu dan kepada dosen saat ada keterlambatan.
  - Pengelolaan akun pengguna (dosen dan mahasiswa) serta data mata kuliah oleh administrator.
  - Log aktivitas sistem untuk keperluan audit integritas data.
  - Penutupan otomatis penerimaan tugas setelah tenggat waktu berakhir.
  - Pembuatan laporan akademik terkait aktivitas tugas.

- **Out-of-Scope**:
  - Fitur ruang obrolan (chat) langsung antar-pengguna di dalam sistem.
  - Integrasi dengan platform e-learning atau LMS eksternal pihak ketiga (Moodle, Google Classroom, dll.).
  - Fitur ujian atau kuis online.
  - Sistem pembayaran atau administrasi keuangan kampus.
  - Fitur pembuatan dan pengelolaan jadwal perkuliahan.

---

## 6. Asumsi dan Batasan

- **Asumsi**:
  - [ASSUMPTION] Seluruh pengguna (dosen, mahasiswa, dan administrator) memiliki akses internet yang stabil untuk menggunakan sistem ini secara daring.
  - [ASSUMPTION] Identitas pengguna (SSO/Kredensial Kampus) dikelola secara terpusat oleh server kampus, sehingga sistem hanya perlu melakukan integrasi autentikasi.
  - [ASSUMPTION] Kuota penyimpanan server kampus mencukupi untuk menampung seluruh berkas tugas mahasiswa selama minimal satu tahun ajaran.
  - [ASSUMPTION] Administrator adalah satu-satunya peran yang berwenang untuk membuat akun dosen baru dan mendaftarkan mata kuliah baru ke dalam sistem.
  - [ASSUMPTION] Sistem tidak diwajibkan menyediakan fitur komunikasi langsung antar-pengguna karena sudah tersedia platform komunikasi eksternal di kampus.

- **Batasan (Constraints)**:
  - Sistem hanya ditujukan untuk tiga peran pengguna: dosen, mahasiswa, dan administrator.
  - Sistem wajib memenuhi kriteria kualitas: usability, security, performance, reliability, dan data integrity.
  - Fokus fungsional sistem terbatas pada pengelolaan tugas, pengumpulan, penilaian, tenggat waktu, dan pelaporan.

---

## 7. Pertanyaan Terbuka (Open Questions)

- [OPEN QUESTION] Platform apa yang akan digunakan — berbasis web (browser), aplikasi mobile native, atau keduanya (hybrid)?
- [OPEN QUESTION] Apa metrik terukur yang ditetapkan untuk setiap kriteria kualitas non-fungsional (batas waktu respons, persentase uptime, standar enkripsi, kapasitas penyimpanan maksimal)?
- [OPEN QUESTION] Apa format laporan akademik yang diharapkan oleh administrator (format ekspor, periode pelaporan, jenis data yang ditampilkan)?
- [OPEN QUESTION] Berapa batas ukuran file maksimal yang diizinkan untuk setiap pengumpulan tugas mahasiswa?
- [OPEN QUESTION] Format nilai apa yang digunakan — angka (0–100), huruf (A–E), atau keduanya?
- [OPEN QUESTION] Apakah sistem harus terintegrasi dengan database akademik kampus yang sudah ada, dan melalui mekanisme apa?
- [OPEN QUESTION] Bagaimana mekanisme pendaftaran pengguna — impor massal oleh administrator, sinkronisasi otomatis, atau pendaftaran mandiri?
