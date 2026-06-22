# Project Inception: Student Task Management System
*(Raw AI Output — belum dikoreksi oleh mahasiswa)*

---

## 1. Ringkasan Masalah Bisnis

Pengelolaan tugas perkuliahan di lingkungan kampus saat ini masih berlangsung secara terpisah-pisah dan tidak terstandarisasi. Dosen menyampaikan tugas melalui berbagai saluran informal seperti grup percakapan atau email, sementara pengumpulan berkas tugas oleh mahasiswa dilakukan secara manual, baik secara fisik maupun melalui platform yang tidak terintegrasi. Kondisi ini mengakibatkan dosen kesulitan memantau status pengumpulan secara terpusat, mahasiswa sering melewatkan tenggat waktu karena tidak adanya sistem pengingat yang terstruktur, dan proses penilaian memerlukan waktu yang lama karena tidak ada mekanisme pemberian umpan balik yang efisien.

Selain itu, administrator kampus tidak memiliki visibilitas yang memadai atas data aktivitas akademik terkait tugas, sehingga pembuatan laporan dan audit data menjadi tidak dapat diandalkan. Ketidakterpaduan sistem yang ada meningkatkan risiko kesalahan data, kehilangan berkas, dan inefisiensi operasional yang berdampak pada kualitas proses pembelajaran secara keseluruhan.

---

## 2. Pemisahan Masalah dan Solusi

- **Masalah Bisnis**: Proses pengelolaan tugas perkuliahan yang tidak terintegrasi menyebabkan inefisiensi dalam distribusi tugas, pengumpulan berkas, proses penilaian, pemantauan tenggat waktu, dan pelaporan akademik. Tidak adanya sistem terpusat membuat seluruh pihak (dosen, mahasiswa, dan administrator) bekerja dengan cara dan platform yang berbeda-beda.

- **Solusi yang Diusulkan**: Mengembangkan sebuah sistem manajemen tugas berbasis aplikasi digital yang menyatukan seluruh aktivitas terkait tugas perkuliahan — mulai dari pembuatan dan distribusi tugas oleh dosen, pengumpulan berkas oleh mahasiswa, proses penilaian dan pemberian umpan balik, hingga pelaporan dan audit oleh administrator — dalam satu platform terintegrasi.

---

## 3. Tujuan Bisnis (Business Goals)

1. **Sentralisasi Pengelolaan Tugas**: Memusatkan seluruh proses terkait tugas perkuliahan dalam satu sistem yang dapat diakses oleh semua pihak yang berwenang.
2. **Peningkatan Efisiensi Waktu**: Mengurangi waktu yang dibutuhkan dosen untuk membuat tugas, mengumpulkan berkas, dan memberikan penilaian.
3. **Minimalisasi Kesalahan dan Kehilangan Data**: Menghilangkan risiko kehilangan berkas tugas, duplikasi data, dan kesalahan pencatatan nilai.
4. **Pemantauan Tenggat Waktu yang Andal**: Memastikan notifikasi dan pengingat tepat waktu terkait tenggat waktu tugas.
5. **Pelaporan Akademik yang Terstandarisasi**: Menyediakan laporan aktivitas tugas yang akurat untuk administrator.

---

## 4. Analisis Stakeholder dan Kebutuhannya

### Stakeholder Primer

- **Dosen**: Membutuhkan antarmuka untuk membuat tugas secara cepat, melihat status pengumpulan real-time, memberikan nilai dan umpan balik tekstual, serta mendapatkan notifikasi keterlambatan mahasiswa.
- **Mahasiswa**: Membutuhkan dashboard daftar tugas dengan sisa tenggat waktu, fasilitas unggah berkas (PDF dan ZIP), bukti tanda terima digital, pengingat otomatis, dan antarmuka yang ramah perangkat mobile.
- **Administrator**: Membutuhkan modul pengelolaan pengguna dan mata kuliah yang dapat dikonfigurasi tanpa coding, log aktivitas untuk audit, dan kemampuan impor data massal via CSV.

### Stakeholder Sekunder

- **Institusi/Manajemen Kampus**: Mengharapkan sistem memenuhi standar keamanan data akademik, menghasilkan laporan evaluasi proses pembelajaran, dan memiliki keandalan (uptime) tinggi.

---

## 5. Ruang Lingkup (Scope Boundaries)

- **In-Scope**:
  - Pembuatan dan distribusi tugas oleh dosen dengan penetapan tenggat waktu.
  - Pengumpulan berkas tugas oleh mahasiswa (format PDF dan ZIP).
  - Pemberian nilai dan umpan balik tekstual oleh dosen.
  - Notifikasi otomatis kepada mahasiswa sebelum tenggat waktu dan kepada dosen saat ada keterlambatan.
  - Pengelolaan akun pengguna dan mata kuliah oleh administrator.
  - Log aktivitas sistem untuk audit integritas data.
  - Penutupan otomatis penerimaan tugas setelah tenggat waktu.
  - Pembuatan laporan akademik aktivitas tugas.

- **Out-of-Scope**:
  - Fitur ruang obrolan (chat) langsung antar-pengguna.
  - Integrasi dengan LMS eksternal pihak ketiga (Moodle, Google Classroom, dll.).
  - Fitur ujian atau kuis online.
  - Sistem pembayaran atau administrasi keuangan kampus.
  - Fitur pembuatan dan pengelolaan jadwal perkuliahan.

---

## 6. Asumsi dan Batasan

- **Asumsi**:
  - [ASSUMPTION] Seluruh pengguna memiliki akses internet yang stabil untuk menggunakan sistem secara daring.
  - [ASSUMPTION] Identitas pengguna dikelola secara terpusat oleh server kampus (SSO).
  - [ASSUMPTION] Kuota penyimpanan server kampus mencukupi untuk berkas tugas selama minimal satu tahun ajaran.
  - [ASSUMPTION] Administrator adalah satu-satunya peran yang berwenang membuat akun dosen baru dan mendaftarkan mata kuliah baru.
  - [ASSUMPTION] Sistem tidak diwajibkan menyediakan fitur komunikasi langsung antar-pengguna.

- **Batasan (Constraints)**:
  - Sistem hanya untuk tiga peran pengguna: dosen, mahasiswa, dan administrator.
  - Sistem wajib memenuhi kriteria: usability, security, performance, reliability, dan data integrity.
  - Fokus fungsional terbatas pada tugas, pengumpulan, penilaian, tenggat waktu, dan pelaporan.

---

## 7. Pertanyaan Terbuka (Open Questions)

- [OPEN QUESTION] Platform apa yang digunakan — web, mobile native, atau hybrid?
- [OPEN QUESTION] Apa metrik terukur untuk setiap kriteria kualitas non-fungsional (waktu respons, uptime, enkripsi, kapasitas)?
- [OPEN QUESTION] Format laporan akademik apa yang diharapkan (format ekspor, periode, jenis data)?
- [OPEN QUESTION] Berapa batas ukuran file maksimal per pengumpulan tugas?
- [OPEN QUESTION] Format nilai apa yang digunakan (angka 0–100, huruf A–E, atau keduanya)?
- [OPEN QUESTION] Apakah sistem harus terintegrasi dengan database akademik kampus yang sudah ada?
- [OPEN QUESTION] Bagaimana mekanisme pendaftaran pengguna (impor CSV, sinkronisasi otomatis, atau mandiri)?
