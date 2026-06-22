# Refleksi: AI-Assisted Requirements Engineering

---

## 1. Apa yang AI Lakukan dengan Baik?

AI menunjukkan kemampuan yang kuat dalam beberapa aspek proses requirements engineering:

- **Konsistensi Struktur**: AI selalu menghasilkan output yang mengikuti format yang ditentukan dalam `SKILL.md` — setiap bagian (tujuan bisnis, stakeholder, scope boundaries, asumsi, open questions) hadir secara lengkap tanpa perlu diingatkan berkali-kali.

- **Kecepatan Draft Awal**: AI dapat menghasilkan draft dokumen yang komprehensif (misalnya 10 FR, 4 NFR, 6 User Stories) dalam hitungan detik, yang secara signifikan lebih cepat dibandingkan penyusunan manual dari nol.

- **Identifikasi Kebutuhan Implisit**: AI mampu menyimpulkan kebutuhan implisit yang tidak dinyatakan secara langsung oleh stakeholder — misalnya kebutuhan validasi format CSV saat impor data, atau kebutuhan antarmuka yang mencegah pengumpulan ganda yang tidak disengaja.

- **Pemberian Label Asumsi**: Ketika diinstruksikan melalui Rules dalam SKILL.md, AI secara konsisten menandai asumsi dengan `[ASSUMPTION]` dan pertanyaan terbuka dengan `[OPEN QUESTION]`, membantu mahasiswa mengenali mana yang perlu dikonfirmasi.

---

## 2. Di Mana AI Membuat Kesalahan atau Asumsi yang Salah?

Selama proses pengerjaan, ditemukan beberapa pola kesalahan yang konsisten dari AI:

- **Kata Ambigu pada NFR**: AI berulang kali menggunakan kata-kata seperti "cepat", "aman", atau "ramah pengguna" pada Non-Functional Requirements tanpa menyertakan metrik yang terukur, yang secara langsung melanggar Rule #2 pada Skill 3. Ini adalah kesalahan yang paling sering ditemukan.

- **Penilaian Terlalu Optimistis (Overconfident Validation)**: Pada tahap validasi (Skill 5), AI cenderung menilai hampir semua kebutuhan sebagai memenuhi semua kriteria kualitas. Padahal, beberapa kebutuhan (FR-03, FR-05, FR-09, FR-10) memiliki kekurangan Completeness yang signifikan yang hanya teridentifikasi setelah tinjauan manusia yang kritis.

- **Asumsi Tersembunyi**: AI kadang menjawab Open Questions secara implisit dalam output — misalnya menulis "notifikasi dikirim via email" padahal mekanisme notifikasi masih merupakan Open Question yang belum terjawab. Ini adalah pelanggaran prinsip "Do not invent missing facts."

- **Prioritisasi yang Longgar**: AI tidak selalu konsisten dalam membedakan Must Have (fungsi inti yang menghentikan sistem jika tidak ada) dengan Should Have. Beberapa fungsi yang merupakan "nice to have" dikategorikan terlalu tinggi sebagai Must Have.

---

## 3. Mengapa Peninjauan Manusia Tetap Diperlukan?

Berdasarkan pengalaman mengerjakan tugas ini, peninjauan manusia bukan sekadar formalitas — melainkan komponen yang **tidak dapat dihilangkan** dari proses requirements engineering, karena:

- **AI tidak memiliki konteks domain bisnis yang mendalam**: AI tidak mengetahui kebijakan kampus, budaya akademik, atau konsektrasi regulasi pendidikan yang berlaku. Mahasiswa sebagai reviewer membawa pengetahuan kontekstual ini yang tidak dapat dihasilkan AI dari dokumen input saja.

- **AI tidak bisa "tidak tahu" dengan baik**: AI cenderung mengisi celah informasi dengan asumsi yang tidak ditandai, sedangkan seorang analis kebutuhan yang baik harus tahu kapan harus berhenti dan bertanya kepada stakeholder.

- **Testability membutuhkan pemikiran verifikasi**: Menentukan apakah sebuah kebutuhan dapat diuji (testable) memerlukan kemampuan berpikir tentang skenario pengujian yang konkrit — kemampuan ini lebih dimiliki manusia yang memahami sistem secara holistik.

- **Keputusan negosiasi adalah tanggung jawab manusia**: Prioritisasi MoSCoW dan keputusan change request melibatkan nilai bisnis, batasan sumber daya, dan risiko proyek yang hanya dapat diputuskan oleh manusia yang memahami konteks organisasi.

---

## 4. Bagaimana Skill Ini Bisa Ditingkatkan?

Beberapa peningkatan yang dapat dilakukan pada file `SKILL.md` berdasarkan pengalaman pengerjaan:

- **Skill 1 & 2**: Tambahkan Rule eksplisit: "Jika ada informasi yang berasal langsung dari dokumen input, cantumkan nama file sumbernya dalam format (Sumber: nama-file.md). Jika tidak ada sumber, tandai sebagai [ASSUMPTION] atau [SIMULATED]."

- **Skill 3**: Tambahkan contoh negatif (counter-example) pada bagian Rules — misalnya daftar kata-kata yang TIDAK boleh digunakan: "cepat", "mudah", "aman", "ramah pengguna", "handal" — tanpa disertai metrik terukur.

- **Skill 5**: Tambahkan instruksi pada Workflow: "Sebelum menilai 'Ya' pada kriteria Completeness, periksa apakah ada pertanyaan terbuka (Open Questions) dari tahap sebelumnya yang belum terjawab yang relevan dengan kebutuhan ini."

- **Semua Skill**: Tambahkan **Negative Quality Check** — daftar tanda-tanda bahwa output kemungkinan bermasalah (misalnya: "Jika tidak ada satupun kebutuhan yang dinilai 'Tidak' dalam tabel validasi, kemungkinan besar penilaian tidak kritis — ulangi evaluasi.")

---

## 5. Apa Batasan Terbesar AI dalam Requirements Engineering?

Batasan paling fundamental yang ditemukan selama pengerjaan tugas ini adalah:

**AI tidak dapat menggantikan dialog aktif dengan stakeholder nyata.**

Requirements engineering pada dasarnya adalah proses komunikasi dan negosiasi antar-manusia. AI dapat membantu menyusun pertanyaan wawancara, menganalisis dokumen, dan menghasilkan draft spesifikasi — tetapi AI tidak dapat:
- Membaca bahasa tubuh atau intonasi stakeholder untuk memahami prioritas sebenarnya.
- Mendeteksi ketika stakeholder tidak mengatakan apa yang sebenarnya mereka butuhkan.
- Menegosiasikan konflik kepentingan antara stakeholder dengan mempertimbangkan dinamika organisasi.
- Memverifikasi bahwa kebutuhan yang terdokumentasi benar-benar mencerminkan masalah bisnis yang sebenarnya.

Dengan memahami batasan ini, mahasiswa dapat menggunakan AI secara lebih efektif — bukan sebagai pengganti analis, tetapi sebagai **asisten struktural** yang membantu mengorganisir informasi dan memastikan tidak ada aspek yang terlewat dalam proses requirements engineering.
