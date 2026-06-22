# Requirements Traceability Matrix: Student Task Management System

Matriks ini menghubungkan sumber stakeholder → hasil elisitasi → spesifikasi kebutuhan → user stories → acceptance criteria → prioritas MoSCoW.

---

## Matriks Keterlacakan (Traceability Matrix)

| Stakeholder | Sumber Elisitasi | ID Kebutuhan | Deskripsi Ringkas | US ID | AC ID | Prioritas MoSCoW | UC Terkait |
|---|---|---|---|---|---|---|---|
| Dosen | interview-answers.md | FR-01 | Membuat tugas dengan judul, deskripsi, tenggat, bobot | US-01 | AC-01.1, AC-01.2 | Must Have | UC-01 |
| Mahasiswa | interview-answers.md | FR-02 | Dashboard daftar tugas aktif + status pengumpulan | US-02 | AC-02.1, AC-02.2 | Must Have | UC-04 |
| Mahasiswa | interview-answers.md, stakeholder-notes.md | FR-03 | Unggah berkas PDF/ZIP, batas ukuran dari admin | US-03 | AC-03.1, AC-03.2 | Must Have | UC-05 |
| Mahasiswa | stakeholder-notes.md | FR-04 | Bukti tanda terima digital setelah unggah berhasil | US-03 | AC-03.1 | Should Have | UC-05 |
| Mahasiswa | stakeholder-notes.md | FR-05 | Notifikasi pengingat otomatis H-3 dan H-1 | US-04 | AC-04.1, AC-04.2 | Should Have | UC-06 |
| Dosen | stakeholder-notes.md | FR-06 | Penutupan otomatis penerimaan setelah tenggat | — | — | Must Have | UC-01 |
| Dosen | interview-answers.md | FR-07 | Beri nilai (0–100) dan umpan balik teks | US-05 | AC-05.1, AC-05.2 | Must Have | UC-03 |
| Mahasiswa | interview-answers.md | FR-08 | Tampilkan nilai dan umpan balik di halaman tugas | — | — | Should Have | UC-07 |
| Administrator | interview-answers.md | FR-09 | Impor data pengguna massal via CSV + validasi | US-06 | AC-06.1, AC-06.2 | Could Have | UC-09 |
| Administrator | stakeholder-notes.md | FR-10 | Log aktivitas (identitas, tindakan, timestamp, objek) | US-07 | AC-07.1, AC-07.2 | Should Have | UC-10 |
| Institusi/Kampus | CASE.md | NFR-01 | Halaman dashboard dimuat < 3 detik pada 10 Mbps | — | — | Must Have | — |
| Institusi/Kampus | CASE.md | NFR-02 | Uptime ≥ 99,5% per bulan (≤ 3j 39m downtime) | — | — | Must Have | — |
| Institusi/Kampus | CASE.md | NFR-03 | HTTPS TLS 1.2+, password hash bcrypt cost ≥ 10 | — | — | Must Have | — |
| Mahasiswa | stakeholder-notes.md | NFR-04 | Antarmuka responsif mulai 360px, Chrome/FF/Safari n-1 | — | — | Should Have | — |
| Dosen | stakeholder-notes.md | BR-01 | Hanya format PDF dan ZIP yang diterima | US-03 | AC-03.2 | Must Have | UC-05 |
| Mahasiswa | CASE.md | BR-02 | Satu pengumpulan aktif per mahasiswa per tugas | — | — | Must Have | UC-05 |

---

## Legenda

| Simbol | Arti |
|---|---|
| FR-XX | Functional Requirement |
| NFR-XX | Non-Functional Requirement |
| BR-XX | Business Rule |
| US-XX | User Story |
| AC-XX.Y | Acceptance Criteria (nomor US . nomor AC) |
| UC-XX | Use Case |

---

## Ringkasan Keterlacakan

| Kategori | Jumlah |
|---|---|
| Functional Requirements (FR) | 10 |
| Non-Functional Requirements (NFR) | 4 |
| Business Rules (BR) | 2 |
| User Stories (US) | 7 |
| Use Cases (UC) | 10 |
| Acceptance Criteria (AC) total | 14 |

Seluruh kebutuhan dapat ditelusuri ke minimal satu sumber stakeholder dan satu dokumen elisitasi. Tidak ada kebutuhan yang berdiri sendiri tanpa justifikasi dari stakeholder.
