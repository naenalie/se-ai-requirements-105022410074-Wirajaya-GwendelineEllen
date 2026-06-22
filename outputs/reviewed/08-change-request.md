# Change Request: Integrasi Deteksi Plagiarisme Berkas Tugas

## 1. Deskripsi Perubahan

Penambahan fitur deteksi plagiarisme otomatis yang memeriksa kemiripan konten berkas tugas yang dikumpulkan Mahasiswa terhadap:
- Berkas yang dikumpulkan oleh mahasiswa lain pada tugas yang sama (intra-class comparison).
- Database dokumen akademik publik yang tersedia (opsional, jika layanan eksternal tersedia).

Setelah berkas diunggah, sistem secara otomatis menjalankan pemeriksaan plagiarisme dan menghasilkan laporan persentase kemiripan yang dapat dilihat oleh Dosen sebelum memberikan penilaian.

---

## 2. Alasan Perubahan (Rationale)

Integritas akademik adalah nilai inti institusi. Saat ini tidak ada mekanisme otomatis untuk mendeteksi kemiripan berkas tugas antar-mahasiswa. Dosen bergantung pada pemeriksaan manual yang tidak efisien dan tidak konsisten. Penambahan fitur ini akan:
- Mencegah tindakan plagiarisme sebelum nilai diberikan.
- Memberikan data objektif kepada Dosen sebagai dasar keputusan penilaian.
- Meningkatkan kepercayaan institusi terhadap integritas proses akademik.

---

## 3. Kebutuhan yang Terdampak (Affected Requirements)

- **FR-03**: Alur unggah berkas harus dimodifikasi — setelah berkas diunggah, sistem perlu memicu proses pemeriksaan plagiarisme sebelum status pengumpulan dinyatakan selesai. Ini menambah langkah asinkron dalam alur FR-03.
- **FR-07**: Halaman penilaian Dosen harus diperluas untuk menampilkan laporan persentase kemiripan di samping berkas tugas yang akan dinilai.
- **FR-08**: Halaman hasil penilaian Mahasiswa dapat ditambahkan indikator apakah pengumpulannya telah melewati pemeriksaan plagiarisme.
- **NFR-01**: Waktu respons proses unggah berkas berpotensi meningkat karena analisis plagiarisme membutuhkan waktu komputasi tambahan. Batas waktu respons 3 detik pada NFR-01 mungkin tidak lagi dapat dipenuhi jika pemeriksaan dilakukan secara sinkron.
- **NFR-02**: Jika sistem mengandalkan layanan deteksi plagiarisme eksternal (API pihak ketiga), ketersediaan (uptime) sistem akan bergantung pada SLA penyedia layanan eksternal tersebut, yang berpotensi menurunkan uptime efektif di bawah 99,5%.

---

## 4. Analisis Dampak (Impact Analysis)

- **Dampak Fungsional**: Alur pengumpulan tugas berubah dari satu langkah (unggah → selesai) menjadi dua langkah (unggah → analisis plagiarisme → selesai). Dosen mendapatkan laporan kemiripan tambahan pada antarmuka penilaian. Diperlukan FR baru: "FR-11: Sistem harus menghasilkan laporan persentase kemiripan berkas tugas antar-mahasiswa dalam satu kelas setelah tenggat waktu berakhir."

- **Dampak Kualitas (Non-Fungsional)**:
  - *Performa*: Proses analisis plagiarisme dapat memperlambat konfirmasi pengumpulan. Solusi: jalankan analisis secara asinkron (background job) sehingga Mahasiswa langsung mendapat tanda terima, sementara laporan plagiarisme dihasilkan terpisah dalam rentang waktu tertentu (misalnya 10–30 menit setelah tenggat).
  - *Keamanan*: Berkas tugas Mahasiswa tidak boleh dikirim ke layanan pihak ketiga tanpa anonimisasi atau enkripsi tambahan untuk melindungi privasi data akademik.
  - *Keandalan*: Ketergantungan pada layanan eksternal menambah titik kegagalan. Sistem harus memiliki mekanisme fallback jika layanan eksternal tidak tersedia.

- **Dampak Prioritas MoSCoW**: Fitur ini termasuk kategori **Could Have** — berguna secara signifikan untuk integritas akademik, namun tidak menghalangi fungsi inti sistem (pengumpulan dan penilaian) jika belum tersedia.

---

## 5. Keputusan dan Justifikasi

- **Keputusan**: **Ditangguhkan (Deferred)**

- **Justifikasi**: Fitur ini memiliki nilai bisnis yang jelas namun kompleksitas implementasi yang cukup tinggi — terutama terkait dampak terhadap NFR-01 (performa) dan NFR-02 (ketersediaan) serta kebutuhan pertimbangan privasi data Mahasiswa. Penerapan yang terburu-buru berisiko merusak pengalaman pengguna pada fitur inti yang sudah ada. Fitur ini dimasukkan ke dalam backlog prioritas tinggi untuk diimplementasikan pada **rilis berikutnya (v2.0)** setelah sistem inti berjalan stabil dan setelah dilakukan kajian teknis mendalam terhadap pilihan implementasi (algoritma in-house vs. API eksternal).
