# Requirements Validation Report: Student Task Management System
*(Raw AI Output — belum dikoreksi oleh mahasiswa)*

---

## 1. Hasil Evaluasi Kebutuhan (Minimal 5 FR)

| ID FR | Deskripsi Kebutuhan | Clarity | Completeness | Consistency | Feasibility | Testability | Traceability | Evaluasi / Tindakan Korektif |
|---|---|---|---|---|---|---|---|---|
| FR-01 | Dosen membuat tugas (judul, deskripsi, tenggat, bobot, lampiran) | Ya | Ya | Ya | Ya | Ya | Ya | Kebutuhan sudah lengkap dan terukur. Siap dijadikan baseline. |
| FR-03 | Mahasiswa unggah berkas PDF/ZIP dengan batas ukuran dari admin | Ya | Tidak | Ya | Ya | Ya | Ya | Batas ukuran file (50 MB) belum secara eksplisit tercantum dalam FR-03. Perlu ditambahkan nilai default ke dalam deskripsi FR. |
| FR-05 | Notifikasi pengingat H-3 dan H-1 otomatis | Ya | Ya | Ya | Ya | Ya | Ya | Kebutuhan sudah jelas. Perlu klarifikasi saluran notifikasi (email saja atau juga in-app) agar dapat diuji lebih spesifik. |
| FR-07 | Dosen beri nilai 0-100 dan umpan balik teks | Ya | Ya | Ya | Ya | Ya | Ya | Kebutuhan sudah jelas dan terukur. Siap dijadikan baseline. |
| FR-09 | Admin impor pengguna massal via CSV dengan validasi | Ya | Ya | Ya | Ya | Ya | Ya | Kebutuhan sudah lengkap. Format kolom CSV wajib (NIM/NIDN, Nama, Email, Peran) perlu didokumentasikan dalam lampiran teknis terpisah. |
| FR-10 | Log aktivitas: identitas, tindakan, timestamp, ID objek | Ya | Tidak | Ya | Ya | Ya | Ya | Retention period (berapa lama log disimpan) belum didefinisikan. Perlu ditambahkan spesifikasi retensi log minimal. |

---

## 2. Kesimpulan Baseline Kebutuhan

Sebagian besar kebutuhan fungsional sudah memenuhi kriteria kualitas dasar. Terdapat dua kebutuhan (FR-03 dan FR-10) yang memerlukan perbaikan minor sebelum dijadikan baseline resmi:
- FR-03 perlu mencantumkan nilai default ukuran file secara eksplisit.
- FR-10 perlu mendefinisikan kebijakan retensi log aktivitas.

Setelah dua perbaikan tersebut dilakukan, dokumen spesifikasi kebutuhan dinyatakan siap dijadikan baseline untuk tahap implementasi.
