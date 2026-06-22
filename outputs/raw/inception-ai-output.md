# Project Inception: Student Task Management System

## 1. Ringkasan Masalah Bisnis
Masalah bisnis spesifik yang mendasari kebutuhan sistem ini tidak dijelaskan dalam studi kasus [OPEN QUESTION]. Namun, diasumsikan bahwa sistem administrasi tugas sebelumnya masih berjalan secara manual, tidak terintegrasi, atau kurang efisien [ASSUMPTION].

Hal ini diasumsikan menyulitkan pemantauan tenggat waktu, pengumpulan berkas tugas oleh mahasiswa, proses penilaian oleh dosen, serta pembuatan laporan secara terpusat [ASSUMPTION].

## 2. Pemisahan Masalah dan Solusi
- **Masalah Bisnis**: Ketiadaan sistem terpusat yang efisien untuk mengelola tugas perkuliahan, pengumpulan berkas, proses penilaian, pemantauan tenggat waktu, dan pelaporan secara terpusat [ASSUMPTION].
- **Solusi yang Diusulkan**: Mengembangkan Student Task Management System yang digunakan oleh dosen, mahasiswa, dan administrator untuk mengelola tugas perkuliahan, pengumpulan tugas, penilaian, tenggat waktu, dan pelaporan secara terpusat dengan memperhatikan aspek usability, security, performance, reliability, dan data integrity.

## 3. Tujuan Bisnis (Business Goals)
1. Mengimplementasikan fitur bagi dosen untuk membuat tugas, menetapkan tenggat waktu, serta memberikan nilai dan umpan balik secara digital.
2. Menyediakan antarmuka bagi mahasiswa untuk melihat tugas, mengunggah berkas pengumpulan, dan memantau status serta tenggat waktu tugas mereka.
3. Menyediakan modul manajemen bagi administrator untuk mengelola data pengguna, mata kuliah, dan konfigurasi sistem.
4. Menjamin keandalan dan keamanan data akademik dengan memenuhi kriteria usability, security, performance, reliability, dan data integrity yang terukur [ASSUMPTION].
5. [ASSUMPTION] Meningkatkan efisiensi waktu dosen dalam melakukan penilaian tugas perkuliahan.

## 4. Analisis Stakeholder dan Kebutuhannya
### Stakeholder Primer
- **Dosen**: Membutuhkan kemampuan membuat tugas, menetapkan deadline, dan memberikan nilai serta umpan balik.
- **Mahasiswa**: Membutuhkan kemampuan melihat tugas, mengumpulkan file, dan memantau status serta deadline.
- **Administrator**: Membutuhkan kemampuan mengelola pengguna, mata kuliah, dan konfigurasi sistem.

### Stakeholder Sekunder
- **Institusi/Manajemen Kampus**: Mengharapkan sistem membantu meningkatkan integritas data akademik dan efisiensi operasional pengelolaan tugas [ASSUMPTION].

## 5. Ruang Lingkup (Scope Boundaries)
- **In-Scope**:
  - Fitur dosen: pembuatan tugas, penetapan deadline, penilaian, dan pemberian umpan balik.
  - Fitur mahasiswa: melihat tugas, pengumpulan file tugas, pemantauan status tugas, dan pemantauan deadline tugas.
  - Fitur administrator: pengelolaan pengguna, pengelolaan mata kuliah, dan pengelolaan konfigurasi sistem.
  - Aspek kualitas sistem: usability, security, performance, reliability, dan data integrity.
- **Out-of-Scope**:
  - [ASSUMPTION] Integrasi otomatis dengan sistem pembayaran atau sistem keuangan kampus.
  - [ASSUMPTION] Fitur tatap muka kelas digital (video conference) atau ruang diskusi kelompok secara langsung.
  - [ASSUMPTION] Modul manajemen jadwal perkuliahan terperinci di luar administrasi data mata kuliah dasar.

## 6. Asumsi dan Batasan
- **Asumsi**:
  - [ASSUMPTION] Aplikasi ini diharapkan dapat memusatkan dan mempermudah interaksi akademik terkait tugas di lingkungan kampus.
  - [ASSUMPTION] Sistem administrasi tugas sebelumnya masih berjalan secara manual, tidak terintegrasi, atau kurang efisien, sehingga menyulitkan pemantauan tenggat waktu, pengumpulan berkas, proses penilaian, serta pembuatan laporan secara terpusat.
  - [ASSUMPTION] Pengguna (dosen, mahasiswa, administrator) memiliki perangkat yang memadai dan akses internet untuk mengoperasikan sistem.
- **Batasan (Constraints)**:
  - Peran pengguna dibatasi hanya untuk dosen, mahasiswa, dan administrator.
  - Sistem harus memperhatikan usability, security, performance, reliability, dan data integrity. Namun, indikator pencapaian atau metrik spesifik untuk kriteria tersebut tidak disebutkan [OPEN QUESTION].
  - Fokus aplikasi dibatasi hanya pada pengelolaan tugas perkuliahan, pengumpulan, penilaian, tenggat waktu, dan pelaporan.

## 7. Pertanyaan Terbuka (Open Questions)
- [OPEN QUESTION] Detail teknis mengenai platform yang digunakan (misalnya web atau mobile) dan arsitektur integrasi sistem belum ditentukan dalam studi kasus.
- [OPEN QUESTION] Masalah bisnis spesifik yang mendasari kebutuhan sistem ini tidak dijelaskan dalam studi kasus.
- [OPEN QUESTION] Indikator pencapaian atau metrik spesifik untuk usability, security, performance, reliability, dan data integrity tidak disebutkan.
- [OPEN QUESTION] Format, jenis data, dan visualisasi laporan (pelaporan) yang harus dihasilkan oleh sistem tidak dijelaskan.
- [OPEN QUESTION] Tidak disebutkan sistem operasi target, bahasa pemrograman, database, framework, atau batasan infrastruktur yang harus digunakan.
- [OPEN QUESTION] Tidak didefinisikan batas ukuran file maksimal atau jenis/ekstensi file yang diizinkan untuk dikumpulkan oleh mahasiswa.
- [OPEN QUESTION] Bentuk nilai (angka/huruf) dan format umpan balik dari dosen (apakah teks biasa atau berkas file) tidak dijelaskan.
- [OPEN QUESTION] Tidak ada informasi apakah sistem harus terintegrasi dengan database mahasiswa/akademik kampus yang sudah ada (misalnya SSO atau sistem administrasi lain).
- [OPEN QUESTION] Mekanisme pendaftaran pengguna (apakah diimpor oleh admin, sinkronisasi otomatis, atau registrasi mandiri) tidak dijelaskan.
