# Skill Testing & Evaluation Report: Library Reservation System

Laporan ini mengevaluasi reusability dari `skills/01-inception/SKILL.md` dan `skills/03-specification/SKILL.md` menggunakan studi kasus alternatif: **Library Reservation System**.

---

## 1. Studi Kasus Alternatif: Library Reservation System
Sistem reservasi buku perpustakaan kampus yang memungkinkan Mahasiswa mencari dan memesan buku secara online, Pustakawan mengelola inventaris buku dan konfirmasi peminjaman, serta Administrator mengatur konfigurasi sistem dan laporan.

---

## 2. Evaluasi Skill 1: Project Inception (`skills/01-inception/SKILL.md`)

### A. Bagian Skill yang Menghasilkan Output Bagus
- **Analisis Stakeholder**: AI berhasil mengidentifikasi Mahasiswa (Peminjam) dan Pustakawan sebagai stakeholder primer serta Administrator sebagai stakeholder sekunder secara akurat.
- **Tujuan Bisnis**: AI berhasil merumuskan tujuan bisnis yang logis (sentralisasi katalog, reduksi antrean manual, dan pelaporan stok buku).
- **Asumsi dan Pertanyaan Terbuka**: Penandaan tag `[ASSUMPTION]` dan `[OPEN QUESTION]` berfungsi sangat konsisten.

### B. Bagian Skill yang Menghasilkan Output Buruk atau Membingungkan
- **Pemisahan Masalah dan Solusi**: AI sering kali menyelundupkan detail solusi (seperti web browser, notifikasi push) ke dalam bagian "Ringkasan Masalah Bisnis" yang seharusnya bebas dari solusi teknologi.
- **Batas Ruang Lingkup (Scope Boundaries)**: Deskripsi untuk `In-Scope` dan `Out-of-Scope` cenderung terlalu umum (generik) sehingga batasannya kurang tegas.

### C. Saran Perbaikan Skill
- Tambahkan contoh negatif (anti-patterns) pada bagian "Pemisahan Masalah dari Solusi" di `SKILL.md` untuk mempertegas bahwa teknologi solusi tidak boleh disebut di bagian deskripsi masalah.
- Berikan instruksi tambahan agar `Out-of-Scope` secara aktif memuat integrasi atau fitur opsional yang sengaja ditiadakan (misal pembayaran denda keterlambatan).

---

## 3. Evaluasi Skill 3: Requirements Specification (`skills/03-specification/SKILL.md`)

### A. Bagian Skill yang Menghasilkan Output Bagus
- **Kebutuhan Fungsional (FR)**: Struktur penulisan FR dan User Stories sudah sangat baik dan mengikuti ID unik `FR-XX` serta `US-XX` secara konsisten.
- **Struktur User Stories**: Format penulisan cerita pengguna `"As a... I want to... so that..."` konsisten dan relevan dengan peran masing-masing aktor.

### B. Bagian Skill yang Menghasilkan Output Buruk atau Membingungkan
- **Keterukuran Kebutuhan Non-Fungsional (NFR)**: AI secara konsisten menggunakan kata-kata kualitatif/subjektif seperti "aman", "cepat merespons", dan "ramah pengguna" yang melanggar aturan keterukuran NFR.
- **Kriteria Penerimaan (Acceptance Criteria)**: Beberapa kriteria penerimaan ditulis dalam bentuk deskripsi abstrak (tidak dapat diuji secara objektif/not testable) seperti "sistem menampilkan konfirmasi yang ramah".

### C. Saran Perbaikan Skill
- Tambahkan daftar kata terlarang (seperti *fast*, *easy*, *secure*, *user-friendly*) di bagian Rules `SKILL.md` untuk memaksa AI melakukan kuantifikasi metrik.
- Berikan template wajib berformat **Given-When-Then** untuk penulisan Acceptance Criteria agar seluruh skenario pengujian dapat diverifikasi dengan jelas.
