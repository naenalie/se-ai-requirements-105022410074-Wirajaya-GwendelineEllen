# Requirements Validation and Change Management Report: Student Task Management System

## 1. Hasil Evaluasi Kebutuhan (Minimal 5 FR)
| ID FR | Deskripsi Kebutuhan | Clarity | Completeness | Consistency | Feasibility | Testability | Traceability | Evaluasi / Tindakan Korektif |
|---|---|---|---|---|---|---|---|---|
| **FR-01** | Dosen membuat tugas baru (judul, deskripsi, tenggat waktu, bobot nilai, lampiran). | Ya | Ya | Ya | Ya | Ya | Ya | Kebutuhan tertulis dengan jelas dan siap dijadikan baseline. |
| **FR-03** | Mahasiswa mengunggah berkas tugas dalam format PDF/ZIP dengan ukuran maksimal yang dikonfigurasi Administrator. | Ya | Tidak | Ya | Ya | Ya | Ya | Batas ukuran berkas default (misalnya 50 MB [ASSUMPTION]) belum ditulis secara eksplisit di FR-03. Perlu ditambahkan spesifikasi batas default. |
| **FR-05** | Sistem mengirimkan notifikasi pengingat otomatis pada H-3 dan H-1 sebelum deadline. | Ya | Ya | Ya | Ya | Ya | Ya | Kebutuhan sudah jelas, namun saluran notifikasi (email, in-app, atau keduanya) perlu diklarifikasi untuk pengujian [OPEN QUESTION]. |
| **FR-07** | Dosen memberikan nilai numerik (0–100) dan umpan balik tekstual pada berkas tugas mahasiswa. | Ya | Ya | Ya | Ya | Ya | Ya | Kebutuhan tertulis dengan jelas, terukur, dan siap dijadikan baseline. |
| **FR-09** | Administrator mengimpor data pengguna secara massal menggunakan file CSV. | Ya | Ya | Ya | Ya | Ya | Ya | Kebutuhan lengkap. Format kolom CSV wajib (NIM/NIDN, Nama, Email, Peran [ASSUMPTION]) sebaiknya didokumentasikan di lampiran terpisah. |
| **FR-10** | Sistem mencatat log aktivitas (identitas, tindakan, timestamp, ID objek) yang hanya diakses Administrator. | Ya | Tidak | Ya | Ya | Ya | Ya | Durasi penyimpanan (retention period) log aktivitas sistem belum ditentukan [OPEN QUESTION]. Perlu penambahan aturan batas waktu penyimpanan log. |

## 2. Kesimpulan Baseline Kebutuhan
Secara umum, spesifikasi kebutuhan fungsional (FR) telah memenuhi standar kualitas. Namun, terdapat kekurangan kelengkapan (completeness) minor pada **FR-03** (batas ukuran file default) dan **FR-10** (durasi penyimpanan log aktivitas) yang harus diperbaiki sebelum disepakati sebagai baseline kebutuhan resmi [ASSUMPTION].

---

## 3. Change Request: Integrasi Deteksi Plagiarisme Berkas Tugas
### A. Deskripsi Perubahan
Penambahan fitur pemindaian plagiarisme otomatis untuk berkas tugas mahasiswa (PDF/ZIP) setelah diunggah ke sistem. Sistem akan mendeteksi kemiripan kata antar-mahasiswa di dalam satu kelas yang sama (intra-class comparison) [ASSUMPTION] dan menghasilkan skor persentase kemiripan yang dapat dilihat oleh Dosen pada panel penilaian.

### B. Alasan Perubahan (Rationale)
Mencegah tindakan kecurangan akademik (plagiarisme) secara sistematis dan objektif, menggantikan proses pemeriksaan manual oleh dosen yang tidak efisien [ASSUMPTION].

### C. Kebutuhan yang Terdampak (Affected Requirements)
- **FR-03**: Alur pengunggahan tugas bertambah panjang karena harus memicu proses pemeriksaan plagiarisme.
- **FR-07**: Panel penilaian dosen harus diubah untuk menampilkan skor persentase kemiripan di samping detail tugas.
- **NFR-01 (Performa)**: Waktu respons pengunggahan berpotensi melambat karena proses analisis membutuhkan resource komputasi tambahan [ASSUMPTION].
- **NFR-02 (Keandalan)**: Ketergantungan pada API deteksi eksternal (jika digunakan) berpotensi menurunkan uptime jika penyedia API eksternal mengalami gangguan [ASSUMPTION][OPEN QUESTION].

### D. Analisis Dampak (Impact Analysis)
- **Dampak Fungsional**: Mengubah alur kerja tugas menjadi asinkron (unggah berkas -> jalankan *background job* pemeriksaan -> tampilkan status siap dinilai). Muncul kebutuhan baru (FR-11) untuk menampilkan detail laporan plagiarisme.
- **Dampak Kualitas (Non-Fungsional)**: Potensi peningkatan beban CPU server jika pemrosesan dilakukan di server lokal. Dari sisi keamanan, berkas mahasiswa harus dianonimkan terlebih dahulu jika dikirim ke API eksternal untuk perlindungan data pribadi [ASSUMPTION].
- **Dampak Prioritas MoSCoW**: Fitur ini dikategorikan sebagai **Could Have** karena bukan prasyarat fungsionalitas pengumpulan dan penilaian dasar.

### E. Keputusan dan Justifikasi
- **Keputusan**: **Ditangguhkan (Deferred)**.
- **Justifikasi**: Fitur ini sangat bermanfaat namun memerlukan analisis keamanan data pribadi yang lebih mendalam [ASSUMPTION], serta berisiko menurunkan performa sistem jika dipaksakan masuk pada rilis pertama. Pengembangan ditunda hingga rilis besar berikutnya (v2.0) [ASSUMPTION] untuk memberikan waktu pengujian performa algoritma.
