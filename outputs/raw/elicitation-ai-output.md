# Requirements Elicitation: Student Task Management System

## 1. Teknik Elisitasi yang Digunakan
- **Wawancara Terstruktur**: Digunakan untuk berdiskusi secara mendalam dengan perwakilan dosen, mahasiswa, dan administrator kampus guna memahami tantangan operasional dan harapan mereka terhadap sistem baru.
- **Analisis Dokumen**: Mengkaji dokumen awal studi kasus ([CASE.md](file:///C:/Users/User/.gemini/antigravity/scratch/se-ai-requirements/CASE.md)), catatan kebutuhan stakeholder ([inputs/stakeholder-notes.md](file:///C:/Users/User/.gemini/antigravity/scratch/se-ai-requirements/inputs/stakeholder-notes.md)), serta draf asumsi proyek ([inputs/assumptions.md](file:///C:/Users/User/.gemini/antigravity/scratch/se-ai-requirements/inputs/assumptions.md)).

## 2. Panduan Pertanyaan Wawancara
### A. Untuk Dosen
1. Bagaimana cara Anda memberikan umpan balik dan nilai kepada mahasiswa saat ini?
2. Berapa banyak rata-rata tugas yang Anda buat untuk setiap mata kuliah dalam satu semester?
3. [SIMULATED] Bagaimana cara pembuatan tugas yang Anda harapkan agar efisien di sistem baru?
4. [SIMULATED] Pemberitahuan/notifikasi apa saja yang Anda perlukan terkait status pengumpulan mahasiswa?
5. [SIMULATED] Bagaimana kebijakan penutupan tugas setelah tenggat waktu berakhir?

### B. Untuk Mahasiswa
1. Apa kesulitan terbesar yang Anda hadapi dalam memantau dan mengumpulkan tugas kuliah saat ini?
2. Format file apa saja yang biasa Anda kumpulkan untuk tugas perkuliahan?
3. [SIMULATED] Bagaimana Anda ingin diingatkan tentang tenggat waktu tugas yang mendekat?
4. [SIMULATED] Bukti atau tanda terima seperti apa yang Anda butuhkan setelah mengunggah tugas?
5. [SIMULATED] Perangkat apa yang paling sering Anda gunakan untuk mengakses informasi perkuliahan?

### C. Untuk Administrator
1. Bagaimana proses pengelolaan data dosen, mahasiswa, dan mata kuliah saat ini?
2. [SIMULATED] Bagaimana kemudahan konfigurasi sistem yang Anda butuhkan tanpa harus mengubah kode program?
3. [SIMULATED] Tindakan pengguna apa saja yang perlu dilacak demi menjaga integritas data?

### D. Untuk Institusi/Manajemen Kampus
1. [SIMULATED] Apa standar keamanan data akademik yang wajib dipenuhi oleh aplikasi ini?
2. [SIMULATED] Laporan evaluasi seperti apa yang Anda harapkan untuk menunjang audit mutu pembelajaran?
3. [SIMULATED] Berapa batas minimum toleransi keandalan (uptime) sistem yang diperbolehkan?

## 3. Catatan Temuan Wawancara (Disimulasikan)
### A. Jawaban Dosen (Perwakilan: Dr. Andrew)
- **Umpan balik saat ini**: Biasanya saya menulis catatan di kertas tugas mahasiswa, atau mengirimkan email satu per satu. Sangat tidak praktis. Saya ingin bisa mengetikkan umpan balik langsung di samping nilai mahasiswa di aplikasi. (Sumber: [inputs/interview-answers.md](file:///C:/Users/User/.gemini/antigravity/scratch/se-ai-requirements/inputs/interview-answers.md))
- **Volume tugas**: Sekitar 4 hingga 6 tugas per mata kuliah. (Sumber: [inputs/interview-answers.md](file:///C:/Users/User/.gemini/antigravity/scratch/se-ai-requirements/inputs/interview-answers.md))
- **Proses pembuatan tugas**: [SIMULATED] Saya ingin proses pembuatan tugas yang cepat tanpa melalui terlalu banyak klik di antarmuka sistem. (Sumber: [inputs/stakeholder-notes.md](file:///C:/Users/User/.gemini/antigravity/scratch/se-ai-requirements/inputs/stakeholder-notes.md))
- **Notifikasi**: [SIMULATED] Saya memerlukan notifikasi pemberitahuan ketika ada mahasiswa yang terlambat mengumpulkan tugas melewati tenggat. (Sumber: [inputs/stakeholder-notes.md](file:///C:/Users/User/.gemini/antigravity/scratch/se-ai-requirements/inputs/stakeholder-notes.md))
- **Penutupan tugas**: [SIMULATED] Sistem harus secara otomatis menutup penerimaan tugas setelah tenggat waktu berakhir agar adil. (Sumber: [inputs/stakeholder-notes.md](file:///C:/Users/User/.gemini/antigravity/scratch/se-ai-requirements/inputs/stakeholder-notes.md))

### B. Jawaban Mahasiswa (Perwakilan: Budi)
- **Kesulitan melacak tugas**: Sering lupa kapan tepatnya deadline karena harus cek di grup chat yang tertumpuk. Saya butuh halaman khusus yang menampilkan seluruh daftar tugas yang belum dikerjakan beserta sisa harinya. (Sumber: [inputs/interview-answers.md](file:///C:/Users/User/.gemini/antigravity/scratch/se-ai-requirements/inputs/interview-answers.md))
- **Format file pengumpulan**: Sebagian besar PDF dan berkas ZIP untuk tugas pemrograman. (Sumber: [inputs/interview-answers.md](file:///C:/Users/User/.gemini/antigravity/scratch/se-ai-requirements/inputs/interview-answers.md))
- **Pengingat tenggat waktu**: [SIMULATED] Saya menginginkan adanya pengingat (reminder) otomatis sebelum tenggat waktu tugas berakhir agar saya tidak terlambat. (Sumber: [inputs/stakeholder-notes.md](file:///C:/Users/User/.gemini/antigravity/scratch/se-ai-requirements/inputs/stakeholder-notes.md))
- **Tanda terima digital**: [SIMULATED] Saya membutuhkan bukti tanda terima digital setelah berhasil mengunggah file untuk menghindari hilangnya data pengumpulan. (Sumber: [inputs/stakeholder-notes.md](file:///C:/Users/User/.gemini/antigravity/scratch/se-ai-requirements/inputs/stakeholder-notes.md))
- **Akses perangkat**: [SIMULATED] Antarmuka aplikasi harus ramah pengguna dan responsif saat diakses lewat handphone. (Sumber: [inputs/stakeholder-notes.md](file:///C:/Users/User/.gemini/antigravity/scratch/se-ai-requirements/inputs/stakeholder-notes.md))

### C. Jawaban Administrator (Perwakilan: Ibu Sari)
- **Pengelolaan data saat ini**: Kami memasukkan data secara manual lewat sistem terpisah. Kami sangat terbantu jika sistem baru ini nanti bisa melakukan sinkronisasi data atau mengizinkan impor massal lewat format CSV [ASSUMPTION]. (Sumber: [inputs/interview-answers.md](file:///C:/Users/User/.gemini/antigravity/scratch/se-ai-requirements/inputs/interview-answers.md))
- **Konfigurasi sistem**: [SIMULATED] Sistem harus mudah dikonfigurasi tanpa harus mengubah kode program oleh staf administrasi non-teknis. (Sumber: [inputs/stakeholder-notes.md](file:///C:/Users/User/.gemini/antigravity/scratch/se-ai-requirements/inputs/stakeholder-notes.md))
- **Integritas data**: [SIMULATED] Kami sangat membutuhkan log aktivitas yang mencatat siapa yang mengunggah file atau mengubah nilai untuk keperluan audit integritas data. (Sumber: [inputs/stakeholder-notes.md](file:///C:/Users/User/.gemini/antigravity/scratch/se-ai-requirements/inputs/stakeholder-notes.md))

### D. Jawaban Institusi/Manajemen Kampus (Disimulasikan)
- **Keamanan data**: [SIMULATED] Sistem wajib menerapkan standar keamanan data akademik kampus yang kokoh untuk melindungi data nilai dan kerahasiaan berkas mahasiswa.
- **Laporan evaluasi**: [SIMULATED] Kami memerlukan laporan ringkas rekap aktivitas tugas perkuliahan untuk melakukan audit mutu dan evaluasi berkala proses pembelajaran.
- **Keandalan sistem**: [SIMULATED] Keandalan (uptime) sistem harus tinggi guna mencegah kegagalan sistem saat puncak pengumpulan tugas mahasiswa di akhir masa tenggat.

## 4. Kebutuhan Eksplisit dan Implisit per Stakeholder
### A. Kebutuhan Dosen
- **Eksplisit**:
  - Dosen dapat membuat tugas secara cepat [ASSUMPTION].
  - Dosen dapat menetapkan tenggat waktu (deadline) tugas.
  - Dosen dapat memberikan nilai secara digital di sistem.
  - Dosen dapat memberikan umpan balik secara digital di samping nilai mahasiswa.
  - Dosen dapat menerima notifikasi otomatis jika ada mahasiswa yang terlambat mengumpulkan tugas [ASSUMPTION].
  - Sistem menutup penerimaan tugas secara otomatis setelah tenggat waktu berakhir [ASSUMPTION].
- **Implisit**:
  - Sistem harus menyediakan penanda status keterlambatan (late flag) otomatis pada tugas yang dikumpulkan melewati deadline.
  - Sistem harus menyediakan tombol aksi penyerahan nilai yang bersifat final dan langsung memicu notifikasi pembaruan ke mahasiswa.

### B. Kebutuhan Mahasiswa
- **Eksplisit**:
  - Mahasiswa dapat melihat tugas aktif beserta sisa hari deadline di halaman khusus.
  - Mahasiswa dapat mengunggah file tugas dengan format PDF dan ZIP.
  - Mahasiswa dapat memantau status tugas mereka.
  - Mahasiswa dapat memantau deadline tugas.
  - Mahasiswa menerima pengingat otomatis sebelum deadline berakhir [ASSUMPTION].
  - Mahasiswa menerima bukti tanda terima digital setelah berhasil mengunggah file [ASSUMPTION].
  - Antarmuka harus dapat diakses dengan baik lewat perangkat mobile [ASSUMPTION].
- **Implisit**:
  - Sistem harus melakukan validasi format file saat proses unggah untuk memblokir ekstensi di luar `.pdf` dan `.zip`.
  - Sistem harus membatasi ukuran file agar tidak melebihi kapasitas memori server yang dialokasikan.

### C. Kebutuhan Administrator
- **Eksplisit**:
  - Administrator dapat mengelola data pengguna (dosen, mahasiswa, admin) secara digital.
  - Administrator dapat mengelola data mata kuliah secara digital.
  - Administrator dapat mengelola konfigurasi sistem secara digital.
  - Administrator dapat mengimpor data massal melalui berkas format CSV [ASSUMPTION].
  - Administrator dapat mengubah konfigurasi sistem tanpa mengubah kode program [ASSUMPTION].
  - Administrator memiliki akses ke log aktivitas sistem untuk melacak aktivitas pengunggahan berkas atau pengubahan nilai demi integritas data [ASSUMPTION].
- **Implisit**:
  - Sistem harus memvalidasi data CSV sebelum diimpor dan menampilkan daftar baris data yang gagal diproses akibat tidak valid.
  - Log aktivitas harus tersimpan secara kronologis, tidak dapat diedit atau dihapus oleh siapa pun (read-only audit trail).

### D. Kebutuhan Institusi/Manajemen Kampus
- **Eksplisit**:
  - Sistem harus memenuhi standar keamanan data akademik yang berlaku [ASSUMPTION].
  - Sistem dapat menghasilkan laporan akademik aktivitas tugas untuk evaluasi kualitas proses pembelajaran [ASSUMPTION].
  - Sistem memiliki keandalan (uptime) tinggi agar tidak mengganggu proses pembelajaran [ASSUMPTION].
- **Implisit**:
  - Sistem harus menggunakan protokol HTTPS terenkripsi untuk mencegah intersepsi nilai akademik mahasiswa.
  - Sistem harus membatasi akses database nilai agar hanya dapat diakses melalui antarmuka aplikasi terotorisasi.

## 5. Pertanyaan Lanjutan (Open Questions)
- [OPEN QUESTION] Platform apa yang akan digunakan — berbasis web (browser), aplikasi mobile native, atau keduanya (hybrid)?
- [OPEN QUESTION] Apa metrik terukur yang ditetapkan untuk setiap kriteria kualitas non-fungsional (batas waktu respons, persentase uptime, standar enkripsi, kapasitas penyimpanan maksimal)?
- [OPEN QUESTION] Apa format laporan akademik yang diharapkan oleh administrator dan manajemen kampus (format ekspor, periode pelaporan, jenis data yang ditampilkan)?
- [OPEN QUESTION] Berapa batas ukuran file maksimal yang diizinkan untuk setiap pengumpulan tugas mahasiswa?
- [OPEN QUESTION] Format nilai apa yang digunakan — angka (0–100), huruf (A–E), atau keduanya?
- [OPEN QUESTION] Apakah sistem harus terintegrasi dengan database akademik kampus yang sudah ada (misalnya SSO atau sistem akademik lama)?
- [OPEN QUESTION] Bagaimana mekanisme pendaftaran pengguna secara detail — apakah sinkronisasi otomatis dengan sistem kampus atau impor massal CSV secara manual?
