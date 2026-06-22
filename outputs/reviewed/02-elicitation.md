# Requirements Elicitation: Student Task Management System

## 1. Teknik Elisitasi yang Digunakan

- **Wawancara Terstruktur**: Dipilih karena sistem ini melibatkan tiga kelompok stakeholder dengan peran yang berbeda (dosen, mahasiswa, administrator). Wawancara terstruktur memungkinkan penggalian kebutuhan mendalam dari masing-masing peran melalui pertanyaan yang disiapkan terlebih dahulu.

- **Analisis Dokumen**: Digunakan untuk meninjau catatan awal stakeholder (`inputs/stakeholder-notes.md`), jawaban wawancara awal (`inputs/interview-answers.md`), dan dokumen deskripsi kasus (`CASE.md`). Teknik ini efisien untuk mengekstrak kebutuhan yang sudah pernah diungkapkan tanpa perlu mengadakan sesi wawancara berulang.

---

## 2. Panduan Pertanyaan Wawancara

### A. Untuk Dosen

1. Bagaimana proses Anda saat ini dalam mendistribusikan tugas kepada mahasiswa?
2. Informasi apa saja yang ingin Anda cantumkan saat membuat tugas baru (deskripsi, tenggat waktu, bobot nilai, lampiran)?
3. Bagaimana Anda memantau siapa saja yang sudah dan belum mengumpulkan tugas?
4. Bagaimana cara Anda memberikan nilai dan umpan balik saat ini, dan apa kelemahannya?
5. Notifikasi apa saja yang Anda butuhkan dari sistem?
6. Apakah Anda perlu kemampuan memperpanjang tenggat waktu untuk mahasiswa tertentu secara individual?

### B. Untuk Mahasiswa

1. Bagaimana Anda saat ini mengetahui informasi tugas dari dosen?
2. Apa kesulitan terbesar Anda dalam proses pengumpulan tugas saat ini?
3. Format file apa saja yang biasanya Anda kumpulkan sebagai tugas?
4. Apakah Anda membutuhkan konfirmasi bahwa tugas Anda berhasil diterima sistem?
5. Pengingat seperti apa yang Anda harapkan dari sistem (H-1, H-3, atau sesuai preferensi)?
6. Apakah Anda perlu dapat melihat nilai dan umpan balik dosen langsung di sistem?

### C. Untuk Administrator

1. Bagaimana proses pengelolaan data pengguna dilakukan saat ini?
2. Apakah Anda perlu mengimpor data pengguna secara massal (misal dari file CSV)?
3. Laporan seperti apa yang Anda butuhkan dari sistem?
4. Pengaturan sistem apa yang perlu dapat Anda ubah tanpa bantuan developer?
5. Apakah Anda membutuhkan log aktivitas pengguna untuk keperluan audit?

---

## 3. Catatan Temuan Wawancara

### A. Jawaban Dosen (Perwakilan: Dr. Andrew)

- **Proses distribusi tugas**: Biasanya melalui grup WhatsApp atau email massal — tidak efisien karena ada mahasiswa yang mengaku tidak menerima informasi.
- **Cara umpan balik**: *"Biasanya saya menulis catatan di kertas tugas mahasiswa, atau mengirimkan email satu per satu. Sangat tidak praktis. Saya ingin bisa mengetikkan umpan balik langsung di samping nilai mahasiswa di aplikasi."* (Sumber: `interview-answers.md`)
- **Jumlah tugas per semester**: *"Sekitar 4 hingga 6 tugas per mata kuliah."* (Sumber: `interview-answers.md`)
- **Kebutuhan notifikasi**: [SIMULATED] Dosen menginginkan notifikasi email atau in-app ketika ada mahasiswa yang belum mengumpulkan tugas pada H-1 tenggat waktu.
- **Perpanjangan tenggat**: [SIMULATED] Dosen menginginkan kemampuan memperpanjang tenggat waktu untuk mahasiswa tertentu tanpa mengubah tenggat global seluruh kelas.

### B. Jawaban Mahasiswa (Perwakilan: Budi)

- **Cara mengetahui tugas**: *"Sering lupa kapan tepatnya deadline karena harus cek di grup chat yang tertumpuk. Saya butuh halaman khusus yang menampilkan seluruh daftar tugas yang belum dikerjakan beserta sisa harinya."* (Sumber: `interview-answers.md`)
- **Format file**: *"Sebagian besar PDF dan berkas ZIP untuk tugas pemrograman."* (Sumber: `interview-answers.md`)
- **Konfirmasi pengumpulan**: [SIMULATED] Mahasiswa sangat membutuhkan bukti tanda terima digital berupa notifikasi atau halaman konfirmasi setelah berhasil mengunggah.
- **Preferensi pengingat**: [SIMULATED] Pengingat otomatis H-3 dan H-1 sebelum tenggat waktu dianggap paling ideal.
- **Akses nilai**: [SIMULATED] Mahasiswa ingin melihat nilai dan umpan balik dosen langsung di halaman detail tugas, bukan melalui email terpisah.

### C. Jawaban Administrator (Perwakilan: Ibu Sari)

- **Pengelolaan data saat ini**: *"Kami memasukkan data secara manual lewat sistem terpisah. Kami sangat terbantu jika sistem baru bisa melakukan sinkronisasi data atau mengizinkan impor massal lewat format CSV."* (Sumber: `interview-answers.md`)
- **Log aktivitas**: [SIMULATED] Administrator membutuhkan log yang mencatat: siapa yang mengunggah file, kapan, siapa yang mengubah nilai, dan kapan perubahan dilakukan.
- **Pengaturan tanpa kode**: [SIMULATED] Administrator ingin mengubah pengaturan (ukuran file maksimal, format file yang diterima, periode pelaporan) melalui panel admin, bukan dengan mengubah konfigurasi server.

---

## 4. Kebutuhan Eksplisit dan Implisit per Stakeholder

### A. Kebutuhan Dosen

- **Eksplisit**:
  - Dosen membutuhkan kemampuan membuat tugas baru dengan deskripsi, tenggat waktu, dan bobot nilai.
  - Dosen membutuhkan fasilitas mengetikkan umpan balik dan nilai langsung di sistem.
  - Dosen membutuhkan notifikasi ketika ada mahasiswa yang terlambat mengumpulkan tugas.

- **Implisit**:
  - Sistem harus menyediakan halaman rekap status pengumpulan per tugas (siapa sudah dan belum mengumpulkan).
  - Sistem harus mendukung perpanjangan tenggat waktu secara individual per mahasiswa.
  - Sistem harus menutup penerimaan tugas secara otomatis setelah tenggat waktu berakhir (kecuali dosen mengaktifkan perpanjangan).

### B. Kebutuhan Mahasiswa

- **Eksplisit**:
  - Mahasiswa membutuhkan dashboard daftar tugas aktif beserta sisa waktu tenggat.
  - Mahasiswa membutuhkan kemampuan mengunggah berkas dalam format PDF dan ZIP.
  - Mahasiswa membutuhkan bukti tanda terima digital setelah pengumpulan berhasil.
  - Mahasiswa membutuhkan pengingat otomatis sebelum tenggat waktu berakhir.

- **Implisit**:
  - Sistem harus menyediakan antarmuka responsif yang dapat diakses melalui perangkat mobile.
  - Sistem harus menampilkan nilai dan umpan balik dosen di halaman detail tugas setelah penilaian selesai.
  - Sistem harus mencegah pengumpulan ganda yang tidak disengaja dengan menampilkan status pengumpulan yang jelas.

### C. Kebutuhan Administrator

- **Eksplisit**:
  - Administrator membutuhkan modul impor data pengguna massal melalui format CSV.
  - Administrator membutuhkan log aktivitas sistem untuk keperluan audit.
  - Administrator membutuhkan panel konfigurasi sistem tanpa perlu mengubah kode program.

- **Implisit**:
  - Sistem harus memvalidasi format CSV saat impor dan memberikan laporan kesalahan jika ada data yang tidak valid.
  - Log aktivitas harus mencatat minimal: waktu, identitas pengguna, jenis tindakan, dan data yang diubah.
  - Panel konfigurasi harus mencakup: ukuran file maksimal, format file yang diterima, dan batas penyimpanan data.

---

## 5. Pertanyaan Lanjutan (Open Questions)

- [OPEN QUESTION] Apakah sistem harus mendukung perpanjangan tenggat waktu individual (per mahasiswa), dan apakah dosen perlu memberikan catatan alasan untuk setiap perpanjangan?
- [OPEN QUESTION] Berapa lama log aktivitas harus disimpan sebelum diarsipkan atau dihapus?
- [OPEN QUESTION] Apakah pengingat otomatis dikirim melalui email, notifikasi in-app, atau keduanya?
- [OPEN QUESTION] Apakah mahasiswa dapat mengumpulkan ulang (resubmit) sebelum tenggat waktu berakhir, dan apakah setiap versi pengumpulan harus disimpan?
- [OPEN QUESTION] Apakah nilai yang sudah diberikan dapat direvisi oleh dosen, dan apakah revisi perlu disetujui oleh administrator?
