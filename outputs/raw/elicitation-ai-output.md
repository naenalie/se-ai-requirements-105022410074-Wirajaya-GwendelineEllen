# Requirements Elicitation: Student Task Management System
*(Raw AI Output — belum dikoreksi oleh mahasiswa)*

---

## 1. Teknik Elisitasi yang Digunakan

- **Wawancara Terstruktur**: Digunakan karena sistem ini melibatkan tiga kelompok stakeholder dengan peran yang sangat berbeda (dosen, mahasiswa, administrator). Wawancara terstruktur memungkinkan penggalian kebutuhan mendalam dan spesifik dari masing-masing peran melalui pertanyaan yang disiapkan terlebih dahulu, sehingga tidak ada aspek penting yang terlewat.

- **Analisis Dokumen**: Digunakan untuk meninjau catatan awal stakeholder (`inputs/stakeholder-notes.md`), jawaban wawancara awal (`inputs/interview-answers.md`), dan dokumen deskripsi kasus (`CASE.md`). Teknik ini efisien untuk mengekstrak kebutuhan yang sudah pernah diungkapkan sebelumnya tanpa perlu mengadakan sesi wawancara berulang.

---

## 2. Panduan Pertanyaan Wawancara

### A. Untuk Dosen

1. Bagaimana proses Anda saat ini dalam mendistribusikan tugas kepada mahasiswa?
2. Informasi apa saja yang ingin Anda cantumkan saat membuat tugas baru (deskripsi, tenggat waktu, bobot nilai, lampiran)?
3. Bagaimana Anda saat ini memantau siapa saja yang sudah dan belum mengumpulkan tugas?
4. Bagaimana cara Anda memberikan nilai dan umpan balik saat ini, dan apa kelemahannya?
5. Notifikasi apa saja yang Anda butuhkan dari sistem (misalnya: ada yang terlambat, ada yang mengumpulkan ulang)?
6. Apakah Anda perlu kemampuan untuk memperpanjang tenggat waktu untuk mahasiswa tertentu secara individual?

### B. Untuk Mahasiswa

1. Bagaimana Anda saat ini mengetahui informasi tugas yang diberikan dosen?
2. Apa kesulitan terbesar Anda dalam proses pengumpulan tugas saat ini?
3. Format file apa saja yang biasanya Anda kumpulkan sebagai tugas?
4. Apakah Anda membutuhkan konfirmasi bahwa tugas Anda berhasil diterima sistem?
5. Pengingat seperti apa yang Anda harapkan dari sistem (H-1, H-3, atau berdasarkan preferensi)?
6. Apakah Anda perlu bisa melihat nilai dan umpan balik dosen langsung di sistem?

### C. Untuk Administrator

1. Bagaimana proses pengelolaan data pengguna (dosen dan mahasiswa) dilakukan saat ini?
2. Apakah Anda perlu mengimpor data pengguna secara massal (misalnya dari file spreadsheet)?
3. Laporan seperti apa yang Anda butuhkan dari sistem (aktivitas tugas, statistik pengumpulan)?
4. Pengaturan sistem apa saja yang perlu dapat Anda ubah tanpa bantuan developer?
5. Apakah Anda membutuhkan log aktivitas pengguna untuk keperluan audit keamanan?

---

## 3. Catatan Temuan Wawancara

### A. Jawaban Dosen (Perwakilan: Dr. Andrew)

- **Proses distribusi tugas saat ini**: Biasanya mengirim tugas melalui grup WhatsApp atau email massal. Tidak efisien karena sering ada mahasiswa yang mengaku tidak menerima informasi.
- **Cara memberikan umpan balik**: *J: Biasanya saya menulis catatan di kertas tugas mahasiswa, atau mengirimkan email satu per satu. Sangat tidak praktis. Saya ingin bisa mengetikkan umpan balik langsung di samping nilai mahasiswa di aplikasi.* (Sumber: `interview-answers.md`)
- **Jumlah tugas per semester**: *J: Sekitar 4 hingga 6 tugas per mata kuliah.* (Sumber: `interview-answers.md`)
- **Kebutuhan notifikasi**: [SIMULATED] Dosen menginginkan notifikasi email atau in-app ketika ada mahasiswa yang belum mengumpulkan tugas saat tenggat waktu sudah H-1.
- **Perpanjangan tenggat waktu**: [SIMULATED] Dosen menginginkan kemampuan untuk memperpanjang tenggat waktu untuk satu atau beberapa mahasiswa tertentu tanpa harus mengubah tenggat waktu global untuk seluruh kelas.

### B. Jawaban Mahasiswa (Perwakilan: Budi)

- **Cara mengetahui informasi tugas**: *J: Sering lupa kapan tepatnya deadline karena harus cek di grup chat yang tertumpuk. Saya butuh halaman khusus yang menampilkan seluruh daftar tugas yang belum dikerjakan beserta sisa harinya.* (Sumber: `interview-answers.md`)
- **Format file yang dikumpulkan**: *J: Sebagian besar PDF dan berkas ZIP untuk tugas pemrograman.* (Sumber: `interview-answers.md`)
- **Konfirmasi pengumpulan**: [SIMULATED] Mahasiswa sangat membutuhkan bukti tanda terima digital berupa notifikasi atau halaman konfirmasi yang dapat di-screenshot sebagai bukti pengumpulan.
- **Preferensi pengingat**: [SIMULATED] Pengingat otomatis 3 hari dan 1 hari sebelum tenggat waktu dianggap ideal oleh mahasiswa.
- **Kebutuhan akses nilai**: [SIMULATED] Mahasiswa ingin dapat melihat nilai dan umpan balik dosen langsung di halaman detail tugas, bukan harus menerima email terpisah.

### C. Jawaban Administrator (Perwakilan: Ibu Sari)

- **Pengelolaan mata kuliah saat ini**: *J: Kami memasukkan data secara manual lewat sistem terpisah. Kami sangat terbantu jika sistem baru ini nanti bisa melakukan sinkronisasi data atau mengizinkan impor massal lewat format CSV.* (Sumber: `interview-answers.md`)
- **Log aktivitas**: [SIMULATED] Administrator membutuhkan log yang mencatat siapa yang mengunggah file, kapan, dari IP mana, serta siapa yang mengubah nilai dan kapan perubahan dilakukan.
- **Pengaturan tanpa kode**: [SIMULATED] Administrator ingin dapat mengubah pengaturan sistem seperti ukuran maksimal file, format file yang diterima, dan periode pelaporan melalui antarmuka panel admin, bukan dengan mengedit konfigurasi server.

---

## 4. Kebutuhan Eksplisit dan Implisit per Stakeholder

### A. Kebutuhan Dosen

- **Eksplisit**:
  - Dosen membutuhkan kemampuan untuk membuat tugas baru dengan deskripsi, tenggat waktu, dan bobot nilai.
  - Dosen membutuhkan fasilitas untuk mengetikkan umpan balik dan nilai langsung di sistem.
  - Dosen membutuhkan notifikasi ketika ada mahasiswa yang terlambat mengumpulkan tugas.

- **Implisit**:
  - Sistem harus menyediakan halaman rekap status pengumpulan per tugas yang menampilkan siapa sudah dan belum mengumpulkan.
  - Sistem harus mendukung kemampuan perpanjangan tenggat waktu secara individual per mahasiswa.
  - Sistem harus menutup penerimaan tugas secara otomatis setelah tenggat waktu berakhir (kecuali dosen mengaktifkan perpanjangan).

### B. Kebutuhan Mahasiswa

- **Eksplisit**:
  - Mahasiswa membutuhkan halaman dashboard yang menampilkan daftar tugas aktif beserta sisa waktu tenggat.
  - Mahasiswa membutuhkan kemampuan mengunggah berkas dalam format PDF dan ZIP.
  - Mahasiswa membutuhkan bukti tanda terima digital setelah pengumpulan berhasil.
  - Mahasiswa membutuhkan pengingat otomatis sebelum tenggat waktu berakhir.

- **Implisit**:
  - Sistem harus menyediakan antarmuka yang responsif dan dapat diakses melalui perangkat mobile.
  - Sistem harus menampilkan nilai dan umpan balik dosen di halaman detail tugas setelah penilaian selesai.
  - Sistem harus mencegah pengumpulan ganda yang tidak disengaja dengan menampilkan status pengumpulan yang jelas.

### C. Kebutuhan Administrator

- **Eksplisit**:
  - Administrator membutuhkan modul impor data pengguna massal melalui format CSV.
  - Administrator membutuhkan log aktivitas sistem untuk keperluan audit.
  - Administrator membutuhkan panel konfigurasi sistem tanpa perlu mengubah kode program.

- **Implisit**:
  - Sistem harus memvalidasi format CSV saat impor data dan memberikan laporan kesalahan yang jelas jika ada data yang tidak valid.
  - Log aktivitas harus menyimpan minimal informasi: waktu, identitas pengguna, jenis tindakan, dan data yang diubah.
  - Panel konfigurasi harus mencakup pengaturan: ukuran file maksimal, format file yang diterima, dan batas waktu penyimpanan data.

---

## 5. Pertanyaan Lanjutan (Open Questions)

- [OPEN QUESTION] Apakah sistem harus mendukung perpanjangan tenggat waktu individual (per mahasiswa), dan jika ya, apakah dosen perlu memberikan alasan/catatan untuk setiap perpanjangan?
- [OPEN QUESTION] Berapa lama log aktivitas harus disimpan oleh sistem sebelum diarsipkan atau dihapus?
- [OPEN QUESTION] Apakah pengingat otomatis dikirim melalui email, notifikasi in-app, atau keduanya?
- [OPEN QUESTION] Apakah mahasiswa dapat mengumpulkan ulang (resubmit) sebelum tenggat waktu berakhir, dan apakah setiap versi pengumpulan harus disimpan?
- [OPEN QUESTION] Apakah nilai yang sudah diberikan oleh dosen dapat direvisi, dan jika ya, apakah revisi tersebut perlu disetujui oleh administrator?
