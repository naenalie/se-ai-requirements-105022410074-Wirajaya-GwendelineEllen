# Negotiation and Prioritization: Student Task Management System

## 1. Analisis Konflik Stakeholder dan Resolusi

- **Konflik 1 — Kapasitas File (Dosen vs Administrator)**
  - **Konflik**: Dosen menginginkan kapasitas file tugas tanpa batas agar mahasiswa bebas mengumpulkan file berukuran besar, sementara Administrator memiliki keterbatasan kapasitas penyimpanan server kampus.
  - **Resolusi**: Menetapkan batas ukuran file maksimal 50 MB per pengumpulan sebagai default. Nilai ini dapat dikonfigurasi ulang oleh Administrator melalui panel admin jika kebutuhan berubah (sesuai FR-03 dan FR-10).

- **Konflik 2 — Resubmit Berkas (Mahasiswa vs Dosen)**
  - **Konflik**: Mahasiswa menginginkan kemampuan resubmit berkas berkali-kali, sementara Dosen menginginkan hanya satu versi pengumpulan akhir yang dinilai untuk menghindari kebingungan.
  - **Resolusi**: Resubmit diizinkan selama masih sebelum tenggat waktu berakhir, namun hanya versi pengumpulan terakhir yang diperlakukan sebagai berkas resmi untuk penilaian (sesuai BR-02).

---

## 2. Ketergantungan Kebutuhan (Requirement Dependencies)

- **FR-04** bergantung pada **FR-03**: Notifikasi tanda terima hanya dapat dikirim setelah berkas berhasil diunggah.
- **FR-05** bergantung pada **FR-01**: Pengingat otomatis hanya dapat dihitung setelah tenggat waktu tugas didefinisikan saat pembuatan.
- **FR-06** bergantung pada **FR-01**: Penutupan otomatis menggunakan data tenggat waktu dari pembuatan tugas.
- **FR-07** bergantung pada **FR-03**: Dosen hanya dapat menilai setelah Mahasiswa mengunggah berkas.
- **FR-08** bergantung pada **FR-07**: Nilai hanya dapat ditampilkan kepada Mahasiswa setelah Dosen selesai memberikan penilaian.
- **FR-09** bergantung pada **FR-10** (tidak langsung): Setiap aksi impor massal harus tercatat di log aktivitas demi integritas data.

---

## 3. Prioritisasi MoSCoW

### A. Must Have
- **FR-01**: Pembuatan tugas adalah inti dari sistem; tanpa fitur ini sistem tidak memiliki fungsi apapun.
- **FR-02**: Dashboard tugas adalah titik masuk utama Mahasiswa; tanpa tampilan daftar tugas sistem tidak berguna bagi pengguna.
- **FR-03**: Pengumpulan berkas adalah fungsi bisnis utama; sistem gagal memenuhi tujuannya tanpa fitur ini.
- **FR-06**: Penutupan otomatis memastikan integritas tenggat waktu; tanpa ini dosen harus menutup penerimaan secara manual yang tidak efisien dan rawan kelalaian.
- **FR-07**: Penilaian adalah output akhir dari siklus tugas; tanpa ini proses Requirements Engineering utama tidak selesai.

### B. Should Have
- **FR-04**: Bukti tanda terima meningkatkan kepercayaan Mahasiswa, namun sistem masih dapat berjalan fungsional tanpanya.
- **FR-05**: Pengingat otomatis sangat dibutuhkan Mahasiswa berdasarkan hasil elisitasi, namun ketiadaannya tidak menghentikan fungsi inti sistem.
- **FR-08**: Tampilan nilai di sistem sangat diinginkan Mahasiswa, namun Dosen masih dapat menyampaikan nilai melalui cara lain sementara fitur ini dikembangkan.
- **FR-10**: Log aktivitas penting untuk keamanan dan audit integritas data, namun tidak menghalangi operasional utama jika belum tersedia.

### C. Could Have
- **FR-09**: Impor CSV mempercepat proses onboarding pengguna, tetapi Administrator masih dapat membuat akun satu per satu secara manual sebagai alternatif sementara.

### D. Won't Have (for this release)
- Fitur chat/komunikasi langsung antar-pengguna (sudah ditetapkan Out-of-Scope pada Inception).
- Integrasi dengan LMS eksternal pihak ketiga (sudah ditetapkan Out-of-Scope pada Inception).
- Fitur deteksi plagiarisme otomatis pada berkas tugas.

---

## 4. Analisis Trade-off dan Justifikasi Keputusan

- **Trade-off 1 — Keamanan vs Performa**
  - Penerapan enkripsi HTTPS/TLS wajib (NFR-03) dan hashing bcrypt untuk kata sandi meningkatkan keamanan namun menambah beban komputasi.
  - **Keputusan**: Keamanan diprioritaskan karena data yang ditangani adalah data akademik sensitif (nilai, identitas mahasiswa). Overhead komputasi dari TLS modern dianggap tidak signifikan pada infrastruktur server kampus yang wajar.

- **Trade-off 2 — Pembatasan Format File vs Fleksibilitas**
  - Membatasi format hanya PDF dan ZIP (BR-01) mengurangi fleksibilitas, namun memudahkan pengelolaan dan mengurangi risiko file berbahaya diunggah ke server.
  - **Keputusan**: Pembatasan format dipertahankan untuk rilis pertama. Penambahan format lain (misal .docx, .xlsx) dapat dipertimbangkan pada iterasi berikutnya berdasarkan umpan balik pengguna nyata.

- **Trade-off 3 — Fitur Lengkap vs Waktu Pengembangan**
  - Memasukkan semua FR sebagai Must Have akan mempercepat pengiriman nilai kepada pengguna, namun meningkatkan kompleksitas dan risiko kegagalan pada rilis pertama.
  - **Keputusan**: Hanya 5 FR inti (FR-01, FR-02, FR-03, FR-06, FR-07) yang dikategorikan Must Have untuk memastikan MVP (Minimum Viable Product) dapat dirilis tepat waktu tanpa mengorbankan fungsi bisnis utama.
