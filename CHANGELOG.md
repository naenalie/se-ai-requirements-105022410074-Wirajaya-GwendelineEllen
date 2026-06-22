# CHANGELOG

Semua perubahan pada repositori dan spesifikasi kebutuhan ini dicatat di dokumen ini.

---

## [1.0.0] — 2026-06-22

### Added — Tahap 1: Project Inception
- Pembuatan `outputs/raw/inception-ai-output.md` — raw output AI dari Skill 1
- Pembuatan `outputs/reviewed/01-inception.md` — final inception document setelah koreksi mahasiswa
  - Koreksi: penambahan 2 tujuan bisnis yang terlewat dari raw output
  - Koreksi: penambahan asumsi SSO dari `inputs/assumptions.md` yang tidak dimasukkan AI
  - Koreksi: penambahan open question tentang format nilai

### Added — Tahap 2: Requirements Elicitation
- Pembuatan `outputs/raw/elicitation-ai-output.md` — raw output AI dari Skill 2
- Pembuatan `outputs/reviewed/02-elicitation.md` — final elicitation document setelah koreksi mahasiswa
  - Koreksi: pemisahan jawaban riil (dari interview-answers.md) vs jawaban [SIMULATED]
  - Koreksi: penambahan kebutuhan implisit mobile responsif yang terlewat
  - Koreksi: penambahan 2 open questions (resubmit dan revisi nilai)

### Added — Tahap 3: Requirements Specification
- Pembuatan `outputs/raw/requirements-ai-output.md` — raw output AI dari Skill 3
- Pembuatan `outputs/reviewed/03-requirements.md` — final requirements spec dengan 10 FR, 4 NFR, 2 BR
  - Koreksi: NFR-01 dan NFR-04 yang menggunakan kata ambigu diganti metrik terukur
  - Koreksi: FR-04 diubah dari "email" menjadi "notifikasi in-app" karena mekanisme masih open question
- Pembuatan `outputs/reviewed/04-user-stories.md` — 7 User Stories (US-01 s.d. US-07) + 14 AC
  - Koreksi: penambahan US-06 dan US-07 untuk Administrator (raw output hanya 5 US)

### Added — Tahap 4: Prioritization
- Pembuatan `outputs/raw/prioritization-ai-output.md` — raw output AI dari Skill 4
- Pembuatan `outputs/reviewed/05-prioritization.md` — final prioritization dengan analisis MoSCoW
  - Koreksi: FR-04 dipindah dari Must Have ke Should Have
  - Koreksi: penambahan kategori Won't Have dengan fitur out-of-scope
  - Koreksi: penambahan Trade-off ke-3 (Fitur Lengkap vs Waktu Pengembangan)

### Added — Tahap 5: Validation & Change Management
- Pembuatan `outputs/raw/validation-ai-output.md` — raw output AI dari Skill 5
- Pembuatan `outputs/reviewed/07-validation.md` — tabel validasi 6 FR dengan koreksi kritis
  - Koreksi: penilaian Completeness FR-05 diubah dari Ya menjadi Tidak
- Pembuatan `outputs/reviewed/08-change-request.md` — change request fitur plagiarisme detection
  - Koreksi: keputusan diubah dari Disetujui menjadi Ditangguhkan

### Added — Tahap 6: Diagrams & Traceability
- Pembuatan `diagrams/use-case-diagram.drawio` — diagram use case dengan 3 aktor dan 10 use case
- Pembuatan `outputs/reviewed/06-use-case.md` — deskripsi naratif 10 use case (UC-01 s.d. UC-10)
- Pembuatan `outputs/reviewed/requirements-traceability.md` — matriks keterlacakan lengkap

### Added — Tahap 7: Skill Testing
- Pembuatan `evaluation/skill-test-results.md` — hasil uji reusability Skill 1 dan Skill 3
  - Studi kasus alternatif: Library Reservation System
  - Temuan: 2 koreksi pada Skill 1, 3 koreksi pada Skill 3

### Added — Tahap 8: Evaluation & Reflection
- Pembuatan `evaluation/ai-output-review.md` — perbandingan raw vs reviewed output (15 koreksi total)
- Pembuatan `evaluation/reflection.md` — refleksi 5 pertanyaan tentang batas kemampuan AI

### Modified — Tahap 9: Documentation Update
- Diperbarui `README.md` — penambahan daftar semua output, ringkasan spesifikasi, AI usage, dan refleksi
- Diperbarui `CHANGELOG.md` — dokumentasi seluruh riwayat perubahan repositori

---

## [Unreleased]
- Inisialisasi struktur repositori tugas sesuai dengan petunjuk penugasan.
- Pembuatan berkas `CASE.md`.
- Kerangka kerja awal untuk 5 reusable AI Skills (`SKILL.md`).
- Pembuatan berkas input awal: `inputs/stakeholder-notes.md`, `inputs/interview-answers.md`, `inputs/assumptions.md`.
