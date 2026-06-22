# Skill Testing Results: Uji Reusability pada Studi Kasus Alternatif

## Tujuan Pengujian

Membuktikan bahwa skill yang dirancang (`SKILL.md`) bersifat **generik dan reusable** — dapat digunakan pada proyek perangkat lunak yang berbeda tanpa perlu mengubah instruksi di dalam file skill.

Pengujian dilakukan pada **2 skill** menggunakan **studi kasus alternatif**: **Library Reservation System (Sistem Reservasi Perpustakaan)**.

---

## Studi Kasus Alternatif: Library Reservation System

Sistem pemesanan ruang baca dan buku perpustakaan kampus secara digital. Pengguna dapat memesan meja baca, meminjam buku, dan mendapatkan notifikasi jatuh tempo pengembalian. Staf perpustakaan mengelola stok buku dan memproses peminjaman.

**Aktor**: Peminjam (Mahasiswa/Dosen), Staf Perpustakaan, Admin Sistem.

---

## Pengujian Skill 1: Project Inception

### Langkah Pengujian
Skill `01-inception/SKILL.md` dijalankan tanpa modifikasi apapun, hanya mengganti input menjadi deskripsi Library Reservation System.

**Prompt yang digunakan**:
```
Read the Library Reservation System project description and skills/01-inception/SKILL.md.
Execute the skill exactly as written.
Do not invent missing facts. Mark assumptions and open questions explicitly.
```

### Ringkasan Output AI yang Dihasilkan
- **Ringkasan Masalah**: AI berhasil mengidentifikasi masalah bisnis (antrian panjang reservasi manual, data stok buku tidak akurat) tanpa mencampuradukkan dengan solusi teknologi. ✅
- **Stakeholder**: AI mengidentifikasi Peminjam sebagai Stakeholder Primer dan Manajemen Perpustakaan sebagai Stakeholder Sekunder. ✅
- **Tujuan Bisnis**: AI merumuskan 3 tujuan bisnis yang relevan. ✅
- **Asumsi**: AI menandai semua asumsi dengan tag `[ASSUMPTION]`. ✅
- **Open Questions**: AI mengidentifikasi pertanyaan terbuka yang relevan untuk domain perpustakaan. ✅

### Kesalahan AI yang Ditemukan
1. AI memasukkan detail teknis (nama database) ke dalam bagian Ringkasan Masalah — melanggar Rule #4 (pemisahan masalah dari solusi). **Koreksi mahasiswa**: bagian tersebut dipindahkan ke bagian Solusi.
2. AI tidak mencantumkan batasan regulasi terkait privasi data peminjam (data peminjaman buku adalah data pribadi). **Koreksi mahasiswa**: ditambahkan sebagai Constraint baru.

### Kesimpulan Skill 1
✅ **Skill bersifat reusable**. Workflow dan output format dapat diterapkan pada domain berbeda. Dua koreksi ditemukan, menunjukkan bahwa peninjauan manusia tetap diperlukan untuk memastikan kualitas output.

---

## Pengujian Skill 3: Requirements Specification

### Langkah Pengujian
Skill `03-specification/SKILL.md` dijalankan menggunakan output elisitasi Library Reservation System (yang sebelumnya dihasilkan dengan Skill 2).

**Prompt yang digunakan**:
```
Read the Library Reservation System elicitation output and skills/03-specification/SKILL.md.
Execute the skill exactly as written.
Save FR, NFR, BR into 03-requirements.md and User Stories into 04-user-stories.md.
```

### Ringkasan Output AI yang Dihasilkan
- **FR**: AI menghasilkan 9 FR (melampaui minimum 8). ✅
- **NFR**: AI menghasilkan 4 NFR, namun 1 NFR menggunakan kata ambigu ("sistem harus cepat merespons"). ⚠️
- **BR**: AI menghasilkan 2 BR yang relevan. ✅
- **User Stories**: AI menghasilkan 6 US dengan format "As a... I want... so that..." yang benar. ✅
- **Acceptance Criteria**: Seluruh US memiliki minimal 2 AC. ✅

### Kesalahan AI yang Ditemukan
1. **NFR-02 menggunakan kata ambigu**: "Sistem harus merespons dengan cepat" — melanggar Rule #2 (tidak boleh ada kata ambigu tanpa metrik). **Koreksi mahasiswa**: diubah menjadi "Halaman pencarian buku harus merespons dalam waktu kurang dari 2 detik pada koneksi 5 Mbps."
2. **US-04 tidak memiliki role yang jelas**: Format "As a user, I want..." tidak spesifik. **Koreksi mahasiswa**: diubah menjadi "As a Peminjam, I want..."
3. **AC-03.2 tidak bisa diuji (not testable)**: "Sistem harus memberikan konfirmasi yang baik" — tidak ada kriteria spesifik. **Koreksi mahasiswa**: diubah menjadi "Sistem menampilkan pesan konfirmasi berisi nomor reservasi dalam format RES-YYYYMMDD-XXX."

### Kesimpulan Skill 3
✅ **Skill bersifat reusable**. Output dapat dihasilkan pada domain perpustakaan tanpa memodifikasi SKILL.md. Tiga koreksi kritis ditemukan terkait kata ambigu, spesifisitas peran, dan testability — menegaskan pentingnya peninjauan mahasiswa.

---

## Kesimpulan Umum Skill Testing

| Aspek | Skill 1 | Skill 3 |
|---|---|---|
| Dapat dijalankan tanpa modifikasi? | ✅ Ya | ✅ Ya |
| Output mengikuti format yang ditentukan? | ✅ Ya | ✅ Ya |
| Kesalahan AI ditemukan? | ✅ 2 kesalahan | ✅ 3 kesalahan |
| Koreksi mahasiswa diperlukan? | ✅ Ya | ✅ Ya |

**Temuan Utama**: Kedua skill terbukti **generik dan reusable**. Namun, AI secara konsisten membuat kesalahan dalam aspek:
1. Pencampuradukkan masalah dan solusi (Skill 1)
2. Penggunaan kata ambigu pada NFR (Skill 3)
3. Acceptance Criteria yang tidak dapat diuji (Skill 3)

Hal ini mengonfirmasi bahwa **peninjauan manusia adalah komponen wajib** dalam proses requirements engineering berbantuan AI.
