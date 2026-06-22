# AI-Assisted Requirements Engineering Assignment

## Student Information
- Name: Wirajaya, Gwendeline Ellen
- Student ID: 105022410074
- Class: [OPEN QUESTION]
- Course: Software Engineering
- Lecturer: Andrew Tanny Liem

## Project
Student Task Management System (STMS)

## Assignment Objective
Repositori ini mendemonstrasikan reusable AI skills untuk menjalankan setiap tahap requirements engineering secara sistematis. Prinsip utama: **AI menghasilkan draft, mahasiswa bertanggung jawab terhadap requirement baseline akhir.**

## Skills
1. [Inception Skill](skills/01-inception/SKILL.md) — Project Inception & Stakeholder Discovery
2. [Elicitation Skill](skills/02-elicitation/SKILL.md) — Requirements Elicitation
3. [Specification Skill](skills/03-specification/SKILL.md) — Requirements Elaboration & Specification
4. [Prioritization Skill](skills/04-prioritization/SKILL.md) — Negotiation & Prioritization
5. [Validation and Change Skill](skills/05-validation-change/SKILL.md) — Requirements Validation & Change Management

## Final Outputs

### Reviewed Outputs (Baseline Final)
- [01-inception.md](outputs/reviewed/01-inception.md)
- [02-elicitation.md](outputs/reviewed/02-elicitation.md)
- [03-requirements.md](outputs/reviewed/03-requirements.md)
- [04-user-stories.md](outputs/reviewed/04-user-stories.md)
- [05-prioritization.md](outputs/reviewed/05-prioritization.md)
- [06-use-case.md](outputs/reviewed/06-use-case.md)
- [07-validation.md](outputs/reviewed/07-validation.md)
- [08-change-request.md](outputs/reviewed/08-change-request.md)
- [requirements-traceability.md](outputs/reviewed/requirements-traceability.md)

### Raw AI Outputs (Draft sebelum dikoreksi)
- [inception-ai-output.md](outputs/raw/inception-ai-output.md)
- [elicitation-ai-output.md](outputs/raw/elicitation-ai-output.md)
- [requirements-ai-output.md](outputs/raw/requirements-ai-output.md)
- [prioritization-ai-output.md](outputs/raw/prioritization-ai-output.md)
- [validation-ai-output.md](outputs/raw/validation-ai-output.md)

### Diagrams
- [use-case-diagram.drawio](diagrams/use-case-diagram.drawio)

### Evaluation
- [skill-test-results.md](evaluation/skill-test-results.md)
- [ai-output-review.md](evaluation/ai-output-review.md)
- [reflection.md](evaluation/reflection.md)

## Ringkasan Spesifikasi Requirements

| Kategori | Jumlah |
|---|---|
| Functional Requirements (FR) | 10 |
| Non-Functional Requirements (NFR) | 4 |
| Business Rules (BR) | 2 |
| User Stories (US) | 7 |
| Use Cases (UC) | 10 |
| Acceptance Criteria (AC) | 14 |

## AI Usage
- AI tool used: Antigravity Coding Assistant
- Model: Claude Sonnet 4.6 (Thinking)
- Date: 2026-06-22
- Skills tested: Skill 1 (Inception), Skill 3 (Specification) — diuji pada studi kasus Library Reservation System
- Major corrections made:
  1. NFR menggunakan kata ambigu → ditambahkan metrik terukur
  2. Asumsi tersembunyi dalam output AI → diidentifikasi dan ditandai eksplisit
  3. Penilaian validasi terlalu optimistis → dikoreksi dengan tinjauan kritis
  4. Jumlah User Stories di bawah minimum → ditambahkan US-06 dan US-07
  5. Keputusan Change Request terburu-buru → diubah dari Disetujui menjadi Ditangguhkan

## Reflection
AI sangat membantu dalam menghasilkan draft awal yang terstruktur dengan cepat, namun secara konsisten membuat kesalahan pada aspek keterukuran NFR, asumsi tersembunyi, dan penilaian validasi yang terlalu optimistis. Peninjauan manusia tetap wajib dilakukan karena AI tidak memiliki konteks domain bisnis yang mendalam, tidak dapat mendeteksi ketidakkonsistenan antar-stakeholder secara tersirat, dan tidak dapat membuat keputusan negosiasi yang mempertimbangkan dinamika organisasi. Skill yang dirancang terbukti **generik dan reusable** — dapat dijalankan pada studi kasus alternatif (Library Reservation System) tanpa modifikasi, namun tetap menghasilkan kesalahan yang memerlukan koreksi mahasiswa.
