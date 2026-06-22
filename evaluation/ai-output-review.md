# AI Output Review: Perbandingan Raw vs Reviewed Output

Dokumen ini mendokumentasikan perbedaan antara output mentah AI (`outputs/raw/`) dan output final yang telah dikoreksi mahasiswa (`outputs/reviewed/`), disertai alasan mengapa setiap koreksi diperlukan.

---

## Skill 1 — Project Inception

| No. | Lokasi dalam Output | Kesalahan AI (Raw) | Koreksi Mahasiswa (Reviewed) | Alasan Koreksi |
|---|---|---|---|---|
| 1 | Bagian 3: Tujuan Bisnis | AI hanya merumuskan 3 tujuan bisnis di raw output | Ditambahkan 2 tujuan bisnis (poin 4 dan 5) | Stakeholder notes menyebut pemantauan tenggat waktu dan pelaporan sebagai kebutuhan eksplisit yang harus tercermin dalam tujuan bisnis |
| 2 | Bagian 6: Asumsi | Raw output tidak mencantumkan asumsi tentang sistem SSO kampus secara eksplisit | Ditambahkan asumsi SSO dari `inputs/assumptions.md` | Informasi ini tersedia di dokumen input dan harus dimasukkan sesuai Rule #2 (semua asumsi harus ditandai) |
| 3 | Bagian 7: Open Questions | Raw output melewatkan pertanyaan tentang format nilai (angka vs huruf) | Ditambahkan sebagai Open Question | Informasi ini disebutkan di CASE.md sebagai informasi yang tidak tersedia dan harus ditandai |

---

## Skill 2 — Requirements Elicitation

| No. | Lokasi dalam Output | Kesalahan AI (Raw) | Koreksi Mahasiswa (Reviewed) | Alasan Koreksi |
|---|---|---|---|---|
| 1 | Bagian 3: Temuan Wawancara | Beberapa jawaban yang bersumber dari `interview-answers.md` tidak dibedakan dari jawaban [SIMULATED] | Semua kutipan langsung dari `interview-answers.md` diberi keterangan sumber "(Sumber: interview-answers.md)" | Rule #2 Skill 2 mewajibkan pemisahan tegas antara jawaban riil dan simulasi |
| 2 | Bagian 4: Kebutuhan Implisit Mahasiswa | Raw output tidak menyebut kebutuhan antarmuka responsif mobile sebagai kebutuhan implisit | Ditambahkan sebagai kebutuhan implisit Mahasiswa | Stakeholder notes secara eksplisit menyebut "antarmuka harus ramah pengguna saat diakses lewat handphone" — ini adalah kebutuhan implisit yang valid |
| 3 | Bagian 5: Open Questions | Raw output hanya mencantumkan 3 open questions | Ditambahkan 2 open questions (tentang resubmit dan revisi nilai) | Kedua topik ini muncul dari analisis kebutuhan implisit tetapi tidak terjawab di dokumen input manapun |

---

## Skill 3 — Requirements Specification

| No. | Lokasi dalam Output | Kesalahan AI (Raw) | Koreksi Mahasiswa (Reviewed) | Alasan Koreksi |
|---|---|---|---|---|
| 1 | NFR-01 (Raw) | "Sistem harus memuat halaman dengan cepat" | Diubah menjadi: "< 3 detik pada koneksi 10 Mbps, diukur dari First Contentful Paint" | Rule #2 Skill 3: Dilarang menggunakan kata "cepat" tanpa metrik terukur |
| 2 | NFR-04 (Raw) | Hanya menyebut "antarmuka responsif di perangkat mobile" tanpa spesifikasi lebar layar atau browser | Ditambahkan: "mulai dari 360px, Chrome/Firefox/Safari versi n-1" | Kriteria harus testable (bisa diverifikasi secara objektif) |
| 3 | FR-04 (Raw) | "Sistem mengirimkan tanda terima melalui email" saja | Diubah menjadi: "notifikasi in-app" (bukan email) karena mekanisme email belum dikonfirmasi di Open Questions | Mekanisme notifikasi adalah Open Question — AI tidak boleh menganggapnya sudah terjawab |
| 4 | User Stories | US-06 tentang admin tidak ada di raw output | Ditambahkan US-06 dan US-07 untuk Administrator | Raw output hanya menghasilkan 5 US (kurang dari minimum 6) — melanggar Rule #4 Skill 3 |

---

## Skill 4 — Prioritization

| No. | Lokasi dalam Output | Kesalahan AI (Raw) | Koreksi Mahasiswa (Reviewed) | Alasan Koreksi |
|---|---|---|---|---|
| 1 | MoSCoW: Must Have | Raw output memasukkan FR-04 (tanda terima) sebagai Must Have | Dipindahkan ke Should Have | FR-04 bukan fungsi bisnis inti yang menghentikan sistem jika tidak ada; sistem tetap beroperasi tanpa tanda terima |
| 2 | Won't Have | Raw output tidak memiliki kategori Won't Have karena semua FR dikategorikan | Ditambahkan kategori Won't Have dengan fitur out-of-scope (chat, LMS eksternal, plagiarisme) | Rule: semua kategori MoSCoW harus ada meskipun berisi item out-of-scope |
| 3 | Trade-off | Raw output hanya menganalisis 2 trade-off | Ditambahkan Trade-off 3 (Fitur Lengkap vs Waktu Pengembangan) | Pertimbangan MVP vs rilis lengkap adalah keputusan negosiasi penting yang harus didokumentasikan |

---

## Skill 5 — Validation & Change

| No. | Lokasi dalam Output | Kesalahan AI (Raw) | Koreksi Mahasiswa (Reviewed) | Alasan Koreksi |
|---|---|---|---|---|
| 1 | Tabel Validasi | Raw output menilai FR-05 sebagai "Completeness: Ya" | Dikoreksi menjadi "Completeness: Tidak" | Saluran notifikasi (email vs in-app) belum dispesifikasi dalam FR-05 — ini adalah kekurangan kelengkapan yang nyata |
| 2 | Change Request: Dampak NFR | Raw output tidak membahas dampak terhadap NFR-02 (uptime) jika menggunakan API plagiarisme eksternal | Ditambahkan analisis dampak terhadap NFR-02 | Ketergantungan pada layanan eksternal secara langsung mempengaruhi ketersediaan sistem dan harus dianalisis |
| 3 | Keputusan Change Request | Raw output merekomendasikan "Disetujui" untuk fitur plagiarisme | Diubah menjadi "Ditangguhkan (Deferred)" | Kompleksitas teknis, dampak terhadap NFR-01 dan privasi data belum dikaji — keputusan terburu-buru tidak tepat |

---

## Pola Kesalahan Umum AI

Berdasarkan review di atas, terdapat pola kesalahan yang berulang dari AI:

1. **Kata Ambigu**: AI sering menggunakan kata seperti "cepat", "baik", atau "mudah" tanpa metrik pada NFR.
2. **Asumsi Tersembunyi**: AI kadang menjawab Open Questions secara implisit tanpa menandainya, seolah informasi sudah tersedia.
3. **Kekurangan Kuantitas Minimum**: AI kadang menghasilkan jumlah item di bawah minimum yang disyaratkan (US, FR).
4. **Penilaian Terlalu Optimistis**: AI cenderung menilai semua kebutuhan sebagai "Ya" pada Quality Check tanpa berpikir kritis.
5. **Ruang Lingkup Tidak Lengkap**: AI kadang tidak mempertimbangkan semua stakeholder secara merata.
