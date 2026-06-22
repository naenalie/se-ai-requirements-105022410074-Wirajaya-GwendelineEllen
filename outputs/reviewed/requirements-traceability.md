# Requirements Traceability Matrix: Student Task Management System

Matriks Keterlacakan Kebutuhan (Requirements Traceability Matrix) ini memetakan hubungan keterlacakan dari peran stakeholder dan dokumen sumber elisitasi, hingga ke spesifikasi kebutuhan, cerita pengguna (user stories), kriteria penerimaan (acceptance criteria), dan prioritas MoSCoW.

---

## 1. Matriks Keterlacakan (Traceability Matrix)

| Requirement ID | Stakeholder | Source (ID temuan elicitation) | User Story ID | Acceptance Criteria ID | Priority (MoSCoW) |
|---|---|---|---|---|---|
| **FR-01** | Dosen | 02-elicitation.md Sec 4.A (Eksplisit) / interview-answers.md / stakeholder-notes.md | US-01 | AC-01.1, AC-01.2 | Must Have |
| **FR-02** | Mahasiswa | 02-elicitation.md Sec 4.B (Eksplisit) / interview-answers.md | US-02 | AC-02.1, AC-02.2 | Must Have |
| **FR-03** | Mahasiswa | 02-elicitation.md Sec 4.B (Eksplisit) / interview-answers.md / stakeholder-notes.md | US-03 | AC-03.1, AC-03.2 | Must Have |
| **FR-04** | Mahasiswa | 02-elicitation.md Sec 4.B (Eksplisit) / stakeholder-notes.md | US-03 | AC-03.1 | Should Have |
| **FR-05** | Mahasiswa | 02-elicitation.md Sec 4.B (Eksplisit) / stakeholder-notes.md | US-04 | AC-04.1, AC-04.2 | Should Have |
| **FR-06** | Dosen | 02-elicitation.md Sec 4.A (Implisit) / stakeholder-notes.md | — | — | Must Have |
| **FR-07** | Dosen | 02-elicitation.md Sec 4.A (Eksplisit) / interview-answers.md | US-05 | AC-05.1, AC-05.2 | Must Have |
| **FR-08** | Mahasiswa | 02-elicitation.md Sec 4.B (Implisit) / interview-answers.md | — | — | Should Have |
| **FR-09** | Administrator | 02-elicitation.md Sec 4.C (Eksplisit) / interview-answers.md | US-06 | AC-06.1, AC-06.2 | Could Have |
| **FR-10** | Administrator | 02-elicitation.md Sec 4.C (Eksplisit) / stakeholder-notes.md | US-07 | AC-07.1, AC-07.2 | Should Have |
| **NFR-01** | Institusi/Manajemen Kampus | CASE.md | — | — | Must Have |
| **NFR-02** | Institusi/Manajemen Kampus | CASE.md | — | — | Must Have |
| **NFR-03** | Institusi/Manajemen Kampus | CASE.md | — | — | Must Have |
| **NFR-04** | Mahasiswa | stakeholder-notes.md | — | — | Should Have |
| **BR-01** | Dosen / Mahasiswa | stakeholder-notes.md | US-03 | AC-03.2 | Must Have |
| **BR-02** | Mahasiswa | CASE.md | — | — | Must Have |

---

## 2. Legenda Kode Kebutuhan

| Kode | Kategori | Arti |
|---|---|---|
| **FR-XX** | Functional Requirement | Kebutuhan Fungsional (Perilaku sistem) |
| **NFR-XX** | Non-Functional Requirement | Kebutuhan Non-Fungsional (Kualitas sistem) |
| **BR-XX** | Business Rule | Aturan Bisnis (Kebijakan operasional) |
| **US-XX** | User Story | Cerita Pengguna (Representasi lincah) |
| **AC-XX.Y** | Acceptance Criteria | Kriteria Penerimaan (Nomor User Story . Nomor Kriteria) |
