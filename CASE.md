# Student Task Management System - Case Description

## 1. Project Overview
Student Task Management System adalah sebuah aplikasi kampus yang dirancang untuk digunakan oleh dosen, mahasiswa, dan administrator dalam mengelola tugas perkuliahan, pengumpulan tugas, penilaian, tenggat waktu, dan pelaporan. Aplikasi ini diharapkan dapat memusatkan dan mempermudah interaksi akademik terkait tugas di lingkungan kampus [ASSUMPTION].

Sistem ini memiliki fungsionalitas yang terbagi berdasarkan hak akses pengguna dan diwajibkan untuk memperhatikan aspek-aspek kualitas sistem seperti usability (kegunaan), security (keamanan), performance (kinerja), reliability (keandalan), dan data integrity (integritas data). Namun, detail teknis mengenai platform yang digunakan (misalnya web atau mobile) dan arsitektur integrasi sistem belum ditentukan dalam studi kasus [OPEN QUESTION].

## 2. Business Problem
Masalah bisnis spesifik yang mendasari kebutuhan sistem ini tidak dijelaskan dalam studi kasus [OPEN QUESTION]. Namun, diasumsikan bahwa sistem administrasi tugas sebelumnya masih berjalan secara manual, tidak terintegrasi, atau kurang efisien, sehingga menyulitkan pemantauan tenggat waktu, pengumpulan berkas, proses penilaian, serta pembuatan laporan secara terpusat [ASSUMPTION].

## 3. Project Goals
1. Mengimplementasikan fitur bagi dosen untuk membuat tugas, menetapkan tenggat waktu, serta memberikan nilai dan umpan balik secara digital.
2. Menyediakan antarmuka bagi mahasiswa untuk melihat tugas, mengunggah berkas pengumpulan, dan memantau status serta tenggat waktu tugas mereka.
3. Menyediakan modul manajemen bagi administrator untuk mengelola data pengguna, mata kuliah, dan konfigurasi sistem.
4. Menjamin keandalan dan keamanan data akademik dengan memenuhi kriteria usability, security, performance, reliability, dan data integrity yang terukur [ASSUMPTION].
5. [ASSUMPTION] Meningkatkan efisiensi waktu dosen dalam melakukan penilaian tugas perkuliahan.

## 4. Known Constraints
- **Peran Pengguna**: Sistem hanya ditujukan untuk tiga kategori pengguna, yaitu dosen, mahasiswa, dan administrator.
- **Kualitas Non-Fungsional**: Sistem wajib memenuhi kriteria usability, security, performance, reliability, dan data integrity. Namun, indikator pencapaian atau metrik spesifik untuk kriteria tersebut tidak disebutkan [OPEN QUESTION].
- **Fokus Aplikasi**: Aplikasi dibatasi hanya pada pengelolaan tugas perkuliahan, pengumpulan, penilaian, tenggat waktu, dan pelaporan.

## 5. Information Boundaries (Informasi yang Tidak Diberikan)
Beberapa informasi penting yang tidak disediakan dalam studi kasus meliputi:
- **Metrik Kualitas Non-Fungsional** [OPEN QUESTION]: Tidak ada spesifikasi teknis atau metrik terukur untuk usability (seperti standar desain), security (seperti enkripsi atau autentikasi), performance (seperti response time), reliability (seperti uptime), dan data integrity (seperti backup).
- **Mekanisme Pelaporan (Reporting)** [OPEN QUESTION]: Format, jenis data, dan visualisasi laporan yang harus dihasilkan oleh sistem tidak dijelaskan.
- **Batasan Teknis dan Platform** [OPEN QUESTION]: Tidak disebutkan sistem operasi target, bahasa pemrograman, database, framework, atau batasan infrastruktur yang harus digunakan.
- **Format File Tugas** [OPEN QUESTION]: Tidak didefinisikan batas ukuran file maksimal atau ekstensi file yang diizinkan untuk dikumpulkan oleh mahasiswa.
- **Mekanisme Umpan Balik dan Penilaian** [OPEN QUESTION]: Bentuk nilai (angka/huruf) dan format umpan balik dari dosen (apakah teks biasa atau unggahan file) tidak dijelaskan.
- **Integrasi Sistem** [OPEN QUESTION]: Tidak ada informasi apakah sistem harus terintegrasi dengan database mahasiswa/akademik kampus yang sudah ada (misalnya SSO atau sistem administrasi lain).
- **Manajemen Pengguna** [OPEN QUESTION]: Mekanisme pendaftaran pengguna (apakah diimpor oleh admin, sinkronisasi otomatis, atau registrasi mandiri) tidak dijelaskan.
