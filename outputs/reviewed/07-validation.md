# Requirements Validation Report: Student Task Management System

## 1. Hasil Evaluasi Kebutuhan (Minimal 5 FR)

| ID FR | Deskripsi Kebutuhan | Clarity | Completeness | Consistency | Feasibility | Testability | Traceability | Evaluasi / Tindakan Korektif |
|---|---|---|---|---|---|---|---|---|
| FR-01 | Dosen membuat tugas baru: judul, deskripsi, tenggat waktu (tanggal+jam), bobot nilai (0–100%), lampiran opsional | Ya | Ya | Ya | Ya | Ya | Ya | Kebutuhan sudah lengkap, terukur, dan konsisten. Siap dijadikan baseline. |
| FR-03 | Mahasiswa unggah berkas PDF atau ZIP dengan batas ukuran yang dikonfigurasi Administrator | Ya | **Tidak** | Ya | Ya | Ya | Ya | **Koreksi**: Batas ukuran default tidak tercantum dalam FR-03. Ditambahkan klausa: "dengan ukuran default maksimal 50 MB per file". Perlu diperbarui di dokumen 03-requirements.md. |
| FR-05 | Sistem mengirim notifikasi pengingat otomatis pada H-3 dan H-1 sebelum tenggat waktu | Ya | **Tidak** | Ya | Ya | Ya | Ya | **Koreksi**: Saluran notifikasi (email, in-app, atau keduanya) tidak dispesifikasi dalam FR. Ditambahkan: "melalui email DAN notifikasi in-app". Perlu diperbarui di dokumen 03-requirements.md. |
| FR-07 | Dosen memberikan nilai numerik (0–100) dan umpan balik tekstual pada pengumpulan Mahasiswa | Ya | Ya | Ya | Ya | Ya | Ya | Kebutuhan sudah jelas dan terukur. Siap dijadikan baseline. |
| FR-09 | Administrator mengimpor data pengguna massal via CSV dengan validasi format dan laporan baris gagal | Ya | **Tidak** | Ya | Ya | Ya | Ya | **Koreksi**: Format kolom CSV yang wajib (NIM/NIDN, Nama, Email, Peran) tidak didefinisikan dalam FR. Perlu ditambahkan atau dirujuk ke dokumen teknis terlampir. |
| FR-10 | Sistem mencatat log aktivitas: identitas pengguna, jenis tindakan, timestamp, ID objek; hanya dapat diakses Administrator | Ya | **Tidak** | Ya | Ya | Ya | Ya | **Koreksi**: Kebijakan retensi log (berapa lama disimpan) tidak didefinisikan. Ditambahkan: "Log disimpan minimal selama 1 tahun ajaran aktif sebelum diarsipkan." |

---

## 2. Kesimpulan Baseline Kebutuhan

Evaluasi menemukan **4 dari 6 kebutuhan yang ditinjau memerlukan perbaikan minor** terkait kelengkapan spesifikasi (Completeness), khususnya pada:
- **FR-03**: Nilai default batas ukuran file belum tercantum.
- **FR-05**: Saluran notifikasi belum dispesifikasi.
- **FR-09**: Format kolom CSV wajib belum didefinisikan.
- **FR-10**: Kebijakan retensi log belum ditetapkan.

Perbaikan telah didokumentasikan pada kolom Evaluasi di atas. Setelah revisi tersebut diaplikasikan ke `03-requirements.md`, dokumen spesifikasi kebutuhan **dinyatakan siap dijadikan baseline** untuk tahap implementasi. Tidak ditemukan inkonsistensi atau kontradiksi antar-kebutuhan yang bersifat fundamental.
