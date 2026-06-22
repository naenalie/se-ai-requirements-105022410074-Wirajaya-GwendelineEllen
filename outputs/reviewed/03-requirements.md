# Requirements Specification: Student Task Management System

## 1. Functional Requirements (FR)

- **FR-01**: Sistem harus memungkinkan Dosen untuk membuat tugas baru yang mencakup judul, deskripsi, tenggat waktu (tanggal dan jam), bobot nilai (persentase 0–100), dan lampiran file opsional.
- **FR-02**: Sistem harus menampilkan halaman dashboard kepada Mahasiswa yang memuat daftar seluruh tugas aktif beserta nama mata kuliah, judul tugas, tenggat waktu, dan status pengumpulan (Belum Dikumpulkan / Sudah Dikumpulkan / Terlambat).
- **FR-03**: Sistem harus memungkinkan Mahasiswa untuk mengunggah berkas tugas dalam format PDF atau ZIP dengan ukuran maksimal yang dapat dikonfigurasi oleh Administrator melalui panel admin.
- **FR-04**: Sistem harus mengirimkan bukti tanda terima digital kepada Mahasiswa berupa notifikasi in-app yang mengkonfirmasi pengumpulan tugas berhasil diterima, disertai timestamp penerimaan.
- **FR-05**: Sistem harus secara otomatis mengirimkan notifikasi pengingat kepada Mahasiswa pada H-3 dan H-1 sebelum tenggat waktu tugas berakhir melalui email dan/atau notifikasi in-app.
- **FR-06**: Sistem harus secara otomatis menutup penerimaan berkas tugas tepat saat tenggat waktu berakhir, kecuali Dosen secara eksplisit mengaktifkan perpanjangan tenggat waktu untuk mahasiswa tertentu.
- **FR-07**: Sistem harus memungkinkan Dosen untuk memberikan nilai numerik (0–100) dan umpan balik tekstual pada berkas tugas yang telah dikumpulkan oleh masing-masing Mahasiswa.
- **FR-08**: Sistem harus menampilkan nilai dan umpan balik yang telah diberikan Dosen kepada Mahasiswa yang bersangkutan di halaman detail tugas, hanya setelah penilaian selesai dilakukan oleh Dosen.
- **FR-09**: Sistem harus memungkinkan Administrator untuk mengimpor data pengguna (dosen dan mahasiswa) secara massal menggunakan file berformat CSV, disertai validasi format dan laporan baris yang gagal diimpor.
- **FR-10**: Sistem harus mencatat log aktivitas yang memuat minimal: identitas pengguna, jenis tindakan (unggah, ubah nilai, hapus, konfigurasi), timestamp, dan ID objek yang terdampak. Log ini hanya dapat diakses oleh Administrator.

---

## 2. Non-Functional Requirements (NFR)

- **NFR-01**: Waktu respons halaman dashboard dan halaman daftar tugas harus dimuat sepenuhnya dalam waktu kurang dari 3 detik pada koneksi internet dengan kecepatan minimal 10 Mbps, diukur dari awal permintaan HTTP hingga konten pertama terlihat (First Contentful Paint).
- **NFR-02**: Sistem harus memiliki ketersediaan layanan (uptime) minimal 99,5% dalam satu bulan kalender, setara dengan toleransi downtime tidak lebih dari 3 jam 39 menit per bulan, diukur melalui monitoring ping setiap 5 menit.
- **NFR-03**: Seluruh transmisi data antara klien dan server wajib dienkripsi menggunakan protokol HTTPS dengan TLS versi 1.2 atau lebih baru. Kata sandi pengguna harus disimpan dalam bentuk hash menggunakan algoritma bcrypt dengan cost factor minimal 10.
- **NFR-04**: Antarmuka pengguna sistem harus dapat diakses dan berfungsi dengan benar pada resolusi layar mulai dari 360px lebar (mobile), serta mendukung browser Chrome, Firefox, dan Safari pada versi terbaru dan versi sebelumnya (n-1).

---

## 3. Business Rules (BR)

- **BR-01**: Sistem hanya menerima pengumpulan berkas tugas dalam format PDF atau ZIP. Berkas dengan ekstensi lain akan ditolak secara otomatis oleh sistem, dan Mahasiswa akan diberitahu tentang format file yang diizinkan melalui pesan error yang jelas.
- **BR-02**: Satu Mahasiswa hanya diperbolehkan memiliki satu pengumpulan aktif per tugas. Jika Mahasiswa mengunggah berkas baru sebelum tenggat waktu berakhir, berkas lama akan digantikan oleh berkas baru dan sistem menyimpan versi terakhir sebagai pengumpulan resmi yang akan dinilai Dosen.
