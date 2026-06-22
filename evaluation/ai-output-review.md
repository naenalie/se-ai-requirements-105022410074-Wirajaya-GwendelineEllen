# AI Output Review

## Skill
Requirements Elaboration and Specification

## AI Output File
outputs/raw/requirements-ai-output.md

## Problems Found
1. **Tidak Ada Pemisahan Dokumen**: Dokumen mentah (`outputs/raw/requirements-ai-output.md`) menyatukan spesifikasi formal (FR, NFR, BR) dan representasi lincah (User Stories & Acceptance Criteria) dalam satu file tunggal. Hal ini melanggar workflow Rule #8 dari `SKILL.md` yang mewajibkan pemisahan dokumen.
2. **Ketiadaan Metrik Pengukuran pada NFR**:
   - **NFR-01**: Waktu respons halaman utama disebutkan "< 3 detik" tetapi tidak mencantumkan parameter awal dan akhir pengukuran (bagaimana cara mengukurnya secara objektif).
   - **NFR-02**: Ketersediaan uptime "99.5%" tidak mencantumkan metode atau alat pemantauan ketersediaan tersebut.
3. **Kata/Frasa Ambigu**:
   - **NFR-04**: Menggunakan frasa "versi terbaru minus 1" yang tidak baku dan membingungkan untuk penentuan pengujian lintas browser.
4. **Parameter Fungsional Tidak Lengkap (Incompleteness)**:
   - **FR-03**: Administrator dapat mengonfigurasi batas ukuran berkas, tetapi tidak disebutkan antarmuka/tempat konfigurasi tersebut.
   - **FR-04**: Menyebutkan pengiriman bukti tanda terima via "email" padahal status integrasi email/SSO masih merupakan status terbuka (`[OPEN QUESTION]`).
   - **FR-05**: Menyebutkan pengiriman notifikasi pengingat otomatis tanpa merinci saluran/media pengirimannya.
   - **FR-08**: Menampilkan nilai dan umpan balik dosen di halaman tugas mahasiswa tanpa membatasi kondisi bahwa nilai hanya boleh tampil setelah dosen selesai menilai seluruhnya.
5. **Kebijakan Aturan Bisnis Kurang Jelas**:
   - **BR-01**: Mahasiswa diberitahu tentang penolakan format file tetapi tidak dijelaskan medium penyampaian penolakannya.
   - **BR-02**: Menyebutkan "versi terakhir sebagai pengumpulan resmi" tanpa mempertegas status kelayakan penilaian untuk dosen.

## Student Corrections
1. **Pemisahan File Spesifikasi**:
   - **Koreksi**: Memindahkan seluruh bagian User Stories dan Acceptance Criteria ke dokumen terpisah yaitu [04-user-stories.md](file:///C:/Users/User/.gemini/antigravity/scratch/se-ai-requirements/outputs/reviewed/04-user-stories.md). File [03-requirements.md](file:///C:/Users/User/.gemini/antigravity/scratch/se-ai-requirements/outputs/reviewed/03-requirements.md) hanya difokuskan untuk spesifikasi formal FR, NFR, dan BR.
   - **Alasan**: Mengikuti ketentuan workflow pemisahan dokumen agar artifacts tetap bersih, fokus, dan mudah dibaca oleh developer maupun tim tester.
2. **Kuantifikasi Metrik Pengukuran NFR**:
   - **Koreksi**: 
     - **NFR-01**: Menambahkan keterangan pengukuran: `"diukur dari awal permintaan HTTP hingga konten pertama terlihat (First Contentful Paint)"`.
     - **NFR-02**: Menambahkan metode monitoring: `"diukur melalui monitoring ping setiap 5 menit"`.
   - **Alasan**: Agar tim QA dapat membuat skenario load testing dan monitoring ketersediaan layanan secara objektif dan terukur sesuai standar industri.
3. **Klarifikasi Browser Target**:
   - **Koreksi**:
     - **NFR-04**: Mengubah `"versi terbaru minus 1"` menjadi `"pada versi terbaru dan versi sebelumnya (n-1)"`.
     - **Alasan**: Menghilangkan ambiguitas istilah kualitatif agar vendor pengembang mengetahui browser mana saja yang harus lolos uji kompatibilitas.
4. **Penyempurnaan Kelengkapan Fungsional (FR & BR)**:
   - **Koreksi**:
     - **FR-03**: Menambahkan detail tempat konfigurasi: `"melalui panel admin"`.
     - **FR-04**: Menghapus `"dan/atau email"` dan menyisakan `"berupa notifikasi in-app"` karena email masih didefinisikan sebagai `[OPEN QUESTION]`.
     - **FR-05**: Menambahkan detail saluran pengiriman: `"melalui email dan/atau notifikasi in-app"`.
     - **FR-08**: Menambahkan kondisi penampilan nilai: `"hanya setelah penilaian selesai dilakukan oleh Dosen"`.
     - **BR-01**: Menambahkan media pemberitahuan penolakan: `"melalui pesan error yang jelas"`.
     - **BR-02**: Menambahkan detail batas waktu dan status penilaian: `"sebelum tenggat waktu berakhir"` dan `"pengumpulan resmi yang akan dinilai Dosen"`.
   - **Alasan**: Mencegah celah pemahaman fungsionalitas sistem (misalnya kebocoran nilai sebelum dosen siap mempublikasikan, atau kebingungan mahasiswa saat file ditolak sistem).

## Final Output
outputs/reviewed/03-requirements.md
