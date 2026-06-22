# Refleksi Pengalaman: AI-Assisted Requirements Engineering

Dalam tugas mata kuliah Rekayasa Perangkat Lunak ini, saya telah mempraktikkan proses Requirements Engineering menggunakan pendekatan berbantuan AI (*AI-Assisted Requirements Engineering*). Seluruh proses mulai dari tahap *Project Inception*, *Elicitation*, *Specification*, *Prioritization*, hingga *Validation and Change Management* dilakukan secara iteratif dengan bimbingan dan instruksi terstruktur pada masing-masing file `SKILL.md`. Berikut adalah refleksi pribadi saya mengenai pengalaman ini, yang saya susun untuk menjawab lima pertanyaan kunci evaluasi.

---

## 1. Bagian yang Paling Baik Dikerjakan oleh AI
Berdasarkan pengalaman saya, AI menunjukkan performa yang sangat kuat dalam aspek **konsistensi struktural dan kecepatan pembuatan draf awal**. Ketika saya memberikan instruksi yang terinci, AI mampu menghasilkan draf dokumen yang sangat rapi dan lengkap secara struktural (seperti memetakan tujuan bisnis, daftar stakeholder, batasan ruang lingkup, serta log asumsi dan pertanyaan terbuka) dalam hitungan detik. Kecepatan ini sangat membantu saya melewati fase "memulai dari nol" yang biasanya memakan banyak waktu.

Selain itu, AI sangat disiplin dalam memelihara penomoran ID unik (seperti `FR-01`, `US-01`, `AC-01.1`) secara konsisten di seluruh dokumen. AI juga mampu mengidentifikasi kebutuhan implisit yang logis yang terlewat oleh pembaca manusia—misalnya, mendeteksi bahwa impor data via CSV memerlukan validasi format kolom dan pelaporan baris yang gagal secara detail demi menjaga aspek *data integrity*.

---

## 2. Kesalahan atau Asumsi yang Paling Sering Dibuat oleh AI
Kesalahan terbesar dan paling konsisten yang saya temukan pada AI adalah **kecenderungannya untuk melakukan halusinasi halus dan menggunakan bahasa kualitatif yang ambigu**. Pada draf mentah spesifikasi kebutuhan, AI berulang kali menggunakan kata-kata subjektif seperti "sistem harus merespons dengan cepat," "antarmuka harus mudah digunakan," atau "proses enkripsi harus aman." Hal ini melanggar prinsip dasar bahwa Kebutuhan Non-Fungsional (NFR) wajib terukur (*measurable*).

Selain itu, AI sering kali membuat asumsi tersembunyi tanpa menandainya dan menyajikannya seolah-olah itu adalah fakta. Sebagai contoh, ketika ditanya tentang alur notifikasi tugas, AI langsung berasumsi bahwa sistem akan mengirimkannya melalui email dan notifikasi *in-app*, padahal media transmisi notifikasi tersebut masih berstatus pertanyaan terbuka (`[OPEN QUESTION]`) yang belum disepakati oleh stakeholder. AI juga cenderung terlalu optimis pada tahap validasi mandiri, di mana ia menilai hampir seluruh kebutuhan sebagai "lengkap" (*complete*) dan "dapat diuji" (*testable*) tanpa melakukan tinjauan kritis yang mendalam.

---

## 3. Pengaruh Perubahan pada SKILL.md Terhadap Kualitas Output
Modifikasi instruksi di dalam file `SKILL.md` (seperti memperketat aturan anti-halusinasi, melarang penggunaan kata kualitatif tertentu seperti *fast*, *easy*, atau *secure*, serta mewajibkan format penulisan Acceptance Criteria dengan gaya *Given-When-Then*) terbukti **secara drastis meningkatkan kualitas draf yang dihasilkan**. 

Dengan membatasi ruang gerak AI melalui aturan yang ketat, AI dipaksa untuk berhenti mengarang detail teknis yang tidak ada di dokumen masukan awal. Ketika AI menemukan celah informasi, ia tidak lagi mencoba menebak jawabannya, melainkan dengan patuh memasukkannya ke dalam tabel `[OPEN QUESTION]`. Penambahan contoh positif dan contoh negatif (anti-patterns) di dalam panduan skill juga memandu AI menghasilkan Acceptance Criteria yang jauh lebih terukur dan siap diuji oleh tim pengembang perangkat lunak.

---

## 4. Pentingnya Human Review (Tinjauan Manusia)
Meskipun AI dibekali dengan alur kerja (*workflow*) yang ketat dan pemeriksaan kualitas (*quality checks*) otomatis, **tinjauan manusia (human review) tetap mutlak diperlukan dan tidak dapat digantikan**. Hal ini disebabkan karena AI tidak memiliki pemahaman kontekstual yang mendalam tentang dinamika organisasi kampus nyata dan regulasi akademik.

AI beroperasi berdasarkan pola probabilitas teks, bukan pemahaman nilai bisnis yang sesungguhnya. Keputusan prioritas MoSCoW (misalnya mengapa impor CSV dikategorikan sebagai *Could Have* sedangkan pembuatan tugas dosen adalah *Must Have*) melibatkan penilaian subjektif atas keterbatasan anggaran, tenggat waktu proyek, dan kesiapan operasional staf kampus. Manusia sebagai *Requirements Engineer* harus berperan sebagai filter kritis untuk mengoreksi asumsi-asumsi salah dari AI, menegosiasikan konflik antar-stakeholder, serta memastikan bahwa dokumen spesifikasi kebutuhan benar-benar dapat diimplementasikan secara realistis di dunia nyata.

---

## 5. Peran Traceability dalam Menjaga Konsistensi Artefak
Penerapan *Requirements Traceability Matrix* (RTM) sangat membantu saya dalam **menjaga konsistensi dan integritas data di seluruh siklus rekayasa kebutuhan**. Dengan menghubungkan setiap Kebutuhan Fungsional (FR) kembali ke stakeholder pengusulnya, dan melacaknya ke depan ke cerita pengguna (User Story), kriteria penerimaan (Acceptance Criteria), serta prioritas MoSCoW, saya dapat memastikan tidak ada kebutuhan yang "yatim piatu" (*orphan requirement*).

Traceability menjamin bahwa setiap fitur yang akan dibangun oleh developer memang memiliki dasar bisnis yang disepakati oleh stakeholder pada tahap awal, dan setiap kebutuhan fungsional memiliki kriteria penerimaan yang jelas untuk diuji oleh tim QA. Ketika terjadi permintaan perubahan (*Change Request*), matriks keterlacakan ini juga menjadi alat utama bagi saya untuk melakukan *Impact Analysis* secara instan, guna mengetahui dokumen dan modul mana saja yang akan terpengaruh jika suatu kebutuhan diubah atau dihapus.
