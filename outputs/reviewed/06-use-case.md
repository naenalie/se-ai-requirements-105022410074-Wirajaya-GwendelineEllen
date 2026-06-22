# Use Case Description: Student Task Management System

> Diagram file: [use-case-diagram.drawio](../../diagrams/use-case-diagram.drawio)

**Aktor yang Terlibat**: Dosen, Mahasiswa, Administrator
**Jumlah Use Case**: 10 (UC-01 s.d. UC-10)

---

## UC-01: Membuat Tugas Baru
- **Aktor**: Dosen
- **Prekondisi**: Dosen telah login ke sistem dan memiliki minimal satu mata kuliah aktif.
- **Alur Utama**:
  1. Dosen memilih menu "Buat Tugas Baru".
  2. Sistem menampilkan formulir dengan kolom: judul, deskripsi, tenggat waktu, bobot nilai, dan lampiran opsional.
  3. Dosen mengisi semua kolom wajib dan menekan "Simpan".
  4. Sistem menyimpan tugas dan menampilkannya di dashboard mahasiswa yang terdaftar pada mata kuliah tersebut.
- **Pascakondisi**: Tugas baru tersimpan di sistem dan terlihat oleh mahasiswa di mata kuliah terkait.
- **Relasi**: —
- **FR terkait**: FR-01

---

## UC-02: Memantau Status Pengumpulan
- **Aktor**: Dosen
- **Prekondisi**: Dosen telah membuat minimal satu tugas.
- **Alur Utama**:
  1. Dosen membuka halaman detail tugas.
  2. Sistem menampilkan daftar nama mahasiswa beserta status pengumpulan masing-masing (Belum / Sudah / Terlambat).
  3. Dosen dapat memfilter tampilan berdasarkan status pengumpulan.
- **Pascakondisi**: Dosen mengetahui siapa yang sudah dan belum mengumpulkan.
- **FR terkait**: FR-02 (implisit dari perspektif Dosen)

---

## UC-03: Memberikan Nilai dan Umpan Balik
- **Aktor**: Dosen
- **Prekondisi**: Mahasiswa telah mengumpulkan berkas tugas.
- **Alur Utama**:
  1. Dosen membuka halaman detail pengumpulan seorang Mahasiswa.
  2. Sistem menampilkan berkas yang diunggah beserta form penilaian.
  3. Dosen memasukkan nilai (0–100) dan umpan balik teks, lalu menekan "Simpan Nilai".
  4. Sistem menyimpan penilaian dan menandai pengumpulan sebagai "Dinilai".
- **Pascakondisi**: Nilai tersimpan dan Mahasiswa dapat melihatnya di halaman detail tugas.
- **FR terkait**: FR-07, FR-08

---

## UC-04: Melihat Daftar Tugas (Dashboard)
- **Aktor**: Mahasiswa
- **Prekondisi**: Mahasiswa telah login ke sistem.
- **Alur Utama**:
  1. Mahasiswa mengakses halaman utama (dashboard).
  2. Sistem menampilkan daftar tugas aktif diurutkan berdasarkan tenggat waktu terdekat, beserta status pengumpulan.
- **Pascakondisi**: Mahasiswa mengetahui semua tugas aktif dan prioritas mana yang harus diselesaikan.
- **Relasi**: `<<extend>>` UC-06 (sistem dapat menampilkan pengingat)
- **FR terkait**: FR-02

---

## UC-05: Mengumpulkan Berkas Tugas
- **Aktor**: Mahasiswa
- **Prekondisi**: Mahasiswa telah login dan tugas masih dalam tenggat waktu aktif.
- **Alur Utama**:
  1. Mahasiswa membuka halaman detail tugas dan memilih "Kumpulkan Tugas".
  2. Sistem menampilkan form unggah berkas.
  3. Mahasiswa memilih file PDF atau ZIP dari perangkat dan menekan "Unggah".
  4. Sistem memvalidasi format dan ukuran file.
  5. Jika valid, sistem menyimpan berkas dan mengirim notifikasi tanda terima (UC-04 triggered).
- **Alur Alternatif**: Jika format atau ukuran tidak valid, sistem menampilkan pesan error dan pengumpulan tidak tersimpan.
- **Pascakondisi**: Berkas tersimpan di sistem, status pengumpulan berubah menjadi "Sudah Dikumpulkan".
- **FR terkait**: FR-03, FR-04, BR-01, BR-02

---

## UC-06: Menerima Notifikasi Pengingat
- **Aktor**: Mahasiswa
- **Prekondisi**: Mahasiswa belum mengumpulkan tugas dan tenggat waktu tersisa H-3 atau H-1.
- **Alur Utama**:
  1. Sistem (scheduled job) memeriksa daftar tugas yang belum dikumpulkan setiap hari.
  2. Jika ditemukan Mahasiswa yang belum mengumpulkan pada H-3 atau H-1, sistem mengirim notifikasi email dan/atau in-app.
- **Pascakondisi**: Mahasiswa menerima pengingat dan dapat segera mengumpulkan tugasnya.
- **Relasi**: `<<extend>>` dari UC-04
- **FR terkait**: FR-05

---

## UC-07: Melihat Nilai dan Umpan Balik
- **Aktor**: Mahasiswa
- **Prekondisi**: Dosen telah menyelesaikan penilaian pada pengumpulan Mahasiswa.
- **Alur Utama**:
  1. Mahasiswa membuka halaman detail tugas.
  2. Sistem menampilkan nilai (0–100) dan umpan balik teks yang diberikan Dosen.
- **Pascakondisi**: Mahasiswa mengetahui hasil penilaian dan umpan balik.
- **FR terkait**: FR-08

---

## UC-08: Mengelola Pengguna dan Mata Kuliah
- **Aktor**: Administrator
- **Prekondisi**: Administrator telah login ke panel admin.
- **Alur Utama**:
  1. Administrator mengakses menu manajemen pengguna atau mata kuliah.
  2. Sistem menampilkan daftar pengguna/mata kuliah dengan opsi tambah, ubah, atau nonaktifkan.
  3. Administrator melakukan perubahan dan menekan Simpan.
  4. Sistem memperbarui data dan mencatat perubahan ke log aktivitas.
- **Pascakondisi**: Data pengguna atau mata kuliah diperbarui.
- **Relasi**: `<<include>>` UC-09
- **FR terkait**: FR-09, FR-10

---

## UC-09: Impor Data Pengguna via CSV
- **Aktor**: Administrator
- **Prekondisi**: Administrator memiliki file CSV berformat valid.
- **Alur Utama**:
  1. Administrator memilih menu "Impor Pengguna" dan mengunggah file CSV.
  2. Sistem memvalidasi format kolom (NIM/NIDN, Nama, Email, Peran).
  3. Sistem membuat akun untuk setiap baris valid dan menampilkan ringkasan: "X akun berhasil, Y gagal".
- **Alur Alternatif**: Jika kolom wajib tidak ada, sistem menolak seluruh file dengan pesan error.
- **Pascakondisi**: Akun pengguna baru tersimpan di sistem.
- **Relasi**: `<<include>>` dari UC-08
- **FR terkait**: FR-09

---

## UC-10: Memantau Log Aktivitas
- **Aktor**: Administrator
- **Prekondisi**: Administrator telah login ke panel admin.
- **Alur Utama**:
  1. Administrator membuka menu "Log Aktivitas".
  2. Sistem menampilkan tabel log terurut terbaru terlebih dahulu, berisi: timestamp, nama pengguna, peran, jenis tindakan, dan ID objek.
  3. Administrator dapat memfilter berdasarkan rentang tanggal atau jenis tindakan.
- **Pascakondisi**: Administrator mendapatkan informasi audit aktivitas sistem.
- **FR terkait**: FR-10
