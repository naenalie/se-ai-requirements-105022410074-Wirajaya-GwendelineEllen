# Negotiation and Prioritization: Student Task Management System
*(Raw AI Output — belum dikoreksi oleh mahasiswa)*

---

## 1. Analisis Konflik Stakeholder dan Resolusi

- **Konflik 1**: Dosen menginginkan kapasitas file tugas tanpa batas agar mahasiswa bebas mengumpulkan file berukuran besar (misalnya video atau dataset), sementara Administrator memiliki keterbatasan kapasitas penyimpanan server kampus.
  - **Resolusi**: Menetapkan batas ukuran file maksimal sebesar 50 MB per pengumpulan, yang cukup untuk dokumen PDF dan arsip ZIP akademik standar, dan dapat dikonfigurasi ulang oleh Administrator jika kebutuhan berubah.

- **Konflik 2**: Mahasiswa menginginkan kemampuan resubmit berkas tanpa batas untuk memastikan mereka dapat mengunggah versi terbaik, sementara Dosen menginginkan hanya satu versi pengumpulan akhir yang dinilai untuk menghindari kebingungan dalam proses penilaian.
  - **Resolusi**: Mengizinkan resubmit sebelum tenggat waktu berakhir, namun hanya versi pengumpulan terakhir yang diperlakukan sebagai berkas resmi untuk penilaian (sesuai BR-02).

---

## 2. Ketergantungan Kebutuhan (Requirement Dependencies)

- **FR-04** (bukti tanda terima) bergantung pada **FR-03** (unggah berkas), karena notifikasi konfirmasi hanya dapat dikirim setelah berkas berhasil diunggah.
- **FR-05** (notifikasi pengingat) bergantung pada **FR-01** (pembuatan tugas), karena sistem hanya dapat menghitung dan mengirim pengingat setelah tenggat waktu tugas didefinisikan.
- **FR-07** (pemberian nilai) bergantung pada **FR-03** (pengumpulan berkas), karena Dosen hanya dapat menilai setelah Mahasiswa mengunggah berkas.
- **FR-08** (tampilkan nilai ke mahasiswa) bergantung pada **FR-07** (pemberian nilai), karena nilai hanya dapat ditampilkan setelah Dosen memberikannya.
- **FR-09** (impor CSV) bergantung pada **FR-10** (log aktivitas) secara tidak langsung — setiap aksi impor harus tercatat di log demi integritas data.
- **FR-06** (penutupan otomatis) bergantung pada **FR-01** (pembuatan tugas) karena waktu penutupan diambil dari tenggat waktu yang ditetapkan saat membuat tugas.

---

## 3. Prioritisasi MoSCoW

### A. Must Have
- **FR-01**: Pembuatan tugas adalah inti dari sistem; tanpa fitur ini sistem tidak memiliki fungsi apapun.
- **FR-02**: Dashboard tugas adalah titik masuk utama Mahasiswa; sistem tidak berguna tanpa tampilan daftar tugas.
- **FR-03**: Pengumpulan berkas adalah fungsi bisnis utama; sistem gagal memenuhi tujuannya tanpa fitur ini.
- **FR-07**: Penilaian adalah output akhir dari proses tugas; tanpa ini siklus tugas tidak selesai.
- **FR-06**: Penutupan otomatis memastikan integritas tenggat waktu; tanpa ini dosen harus menutup manual yang tidak efisien.

### B. Should Have
- **FR-04**: Bukti tanda terima meningkatkan kepercayaan mahasiswa terhadap sistem, namun sistem masih bisa berjalan tanpa fitur ini.
- **FR-05**: Pengingat otomatis sangat dibutuhkan mahasiswa, namun tidak menghalangi jalannya sistem jika tidak ada.
- **FR-08**: Tampilan nilai di sistem sangat diinginkan, tetapi dosen bisa menyampaikan nilai melalui cara lain sementara fitur ini dikembangkan.
- **FR-10**: Log aktivitas penting untuk keamanan dan audit, namun tidak menghalangi operasional utama jika belum ada.

### C. Could Have
- **FR-09**: Impor CSV mempercepat onboarding, tetapi Administrator masih dapat membuat akun satu per satu secara manual sebagai alternatif.

### D. Won't Have (for this release)
- Tidak ada FR yang dikategorikan Won't Have karena seluruh FR yang ada masih dalam ruang lingkup minimum sistem yang layak (MVP).

---

## 4. Analisis Trade-off dan Justifikasi Keputusan

- **Trade-off 1**: Keamanan Data vs Kemudahan Akses
  - Penerapan enkripsi HTTPS/TLS wajib (NFR-03) dan hashing bcrypt untuk kata sandi meningkatkan keamanan secara signifikan, namun sedikit menambah beban komputasi server dibandingkan koneksi tanpa enkripsi.
  - **Keputusan**: Keamanan diprioritaskan karena data yang ditangani adalah data akademik sensitif (nilai, identitas mahasiswa). Beban komputasi tambahan dari TLS modern dianggap tidak signifikan pada infrastruktur server kampus yang wajar.

- **Trade-off 2**: Pembatasan Format File vs Fleksibilitas Mahasiswa
  - Membatasi format hanya PDF dan ZIP (BR-01) mengurangi fleksibilitas mahasiswa yang mungkin memiliki tugas dalam format lain (misalnya .docx atau .pptx), namun memudahkan pengelolaan dan mengurangi risiko file berbahaya.
  - **Keputusan**: Pembatasan format dipertahankan untuk rilis pertama. Penambahan format lain (misal .docx, .xlsx) dapat dipertimbangkan pada iterasi berikutnya berdasarkan umpan balik pengguna.
