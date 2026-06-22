# Negotiation and Prioritization: Student Task Management System

## 1. Analisis Konflik Stakeholder dan Resolusi
- **Konflik 1**: Dosen menginginkan kapasitas penyimpanan file tugas tanpa batas agar mahasiswa bebas mengunggah dokumen berukuran besar, sedangkan Administrator memiliki kapasitas penyimpanan server kampus yang terbatas [ASSUMPTION].
  - **Resolusi**: Administrator menetapkan batas ukuran file maksimal melalui panel admin secara dinamis, dengan batas awal 50 MB per file, yang dinilai mencukupi untuk file dokumen akademik [ASSUMPTION].
- **Konflik 2**: Mahasiswa menginginkan fleksibilitas untuk dapat mengunggah berkas revisi berkali-kali sebelum tenggat waktu berakhir, sedangkan Dosen menginginkan satu berkas final per mahasiswa agar penilaian tidak membingungkan [ASSUMPTION].
  - **Resolusi**: Mengizinkan pengunggahan berkali-kali sebelum deadline, tetapi sistem secara otomatis mengganti berkas lama dengan berkas baru sehingga hanya ada satu berkas aktif yang dinilai (sesuai BR-02).
- **Konflik 3**: Administrator menginginkan kemudahan sinkronisasi data pengguna otomatis dari sistem kampus pusat, sedangkan tim keamanan sistem IT kampus belum memberikan kejelasan akses API [ASSUMPTION][OPEN QUESTION].
  - **Resolusi**: Menyediakan fitur impor massal menggunakan CSV (FR-09) sebagai langkah kompromi sementara sembari menunggu akses integrasi API kampus [ASSUMPTION].

## 2. Ketergantungan Kebutuhan (Requirement Dependencies)
- **FR-04 (Bukti Tanda Terima)** bergantung pada **FR-03 (Unggah Berkas)** karena bukti tanda terima digital hanya dapat dikeluarkan dan dikirim setelah mahasiswa berhasil mengunggah file tugas.
- **FR-05 (Notifikasi Pengingat)** bergantung pada **FR-01 (Pembuatan Tugas)** karena penghitungan waktu H-3 dan H-1 pengingat membutuhkan data tenggat waktu (tanggal dan jam) tugas yang dibuat Dosen.
- **FR-06 (Penutupan Otomatis)** bergantung pada **FR-01 (Pembuatan Tugas)** karena waktu penutupan akses unggahan didasarkan pada data tenggat waktu yang disimpan saat pembuatan tugas.
- **FR-07 (Penilaian oleh Dosen)** bergantung pada **FR-03 (Unggah Berkas)** karena Dosen hanya dapat memasukkan nilai dan umpan balik apabila Mahasiswa telah berhasil mengumpulkan berkas tugasnya.
- **FR-08 (Tampilan Nilai ke Mahasiswa)** bergantung pada **FR-07 (Penilaian oleh Dosen)** karena nilai dan umpan balik tidak dapat ditampilkan di halaman detail tugas mahasiswa sebelum Dosen selesai melakukan input penilaian.
- **FR-09 (Impor Data CSV)** bergantung pada **FR-10 (Log Aktivitas)** secara tidak langsung, karena setiap penambahan pengguna secara massal harus tercatat di log audit demi integritas data akademik [ASSUMPTION].

## 3. Prioritisasi MoSCoW
### A. Must Have
- **FR-01**: Pembuatan tugas oleh Dosen merupakan fungsi inti; tanpa pembuatan tugas, sistem tidak dapat berjalan.
- **FR-02**: Tampilan dashboard tugas aktif merupakan alur kerja utama bagi Mahasiswa untuk mengakses informasi tugas.
- **FR-03**: Pengunggahan berkas tugas dalam format PDF/ZIP oleh Mahasiswa merupakan fungsi pengumpulan utama yang wajib disediakan.
- **FR-06**: Penutupan otomatis pengumpulan tugas setelah tenggat waktu berakhir adalah kebijakan penting untuk menjaga kedisiplinan dan integritas data [ASSUMPTION].
- **FR-07**: Penilaian numerik dan umpan balik oleh Dosen merupakan fungsionalitas inti untuk menutup alur siklus tugas perkuliahan.

### B. Should Have
- **FR-04**: Bukti tanda terima digital sangat penting dikirimkan pasca-pengunggahan tugas guna memastikan aspek data integrity dan memberikan kepastian psikologis kepada mahasiswa [ASSUMPTION], tetapi sistem masih dapat berjalan tanpanya.
- **FR-08**: Tampilan nilai dan umpan balik di halaman tugas Mahasiswa seharusnya diimplementasikan untuk kemudahan akses informasi nilai mahasiswa secara terpusat, meskipun nilai dapat diumumkan secara manual di luar sistem sebagai alternatif sementara [ASSUMPTION].
- **FR-10**: Log aktivitas sistem harus dicatat untuk memenuhi aspek security dan audit integritas data, tetapi secara teknis operasional transaksi tugas dasar masih dapat berjalan jika modul log ini ditunda [ASSUMPTION].

### C. Could Have
- **FR-05**: Pengingat otomatis H-3 dan H-1 sangat membantu mahasiswa untuk usability, namun mahasiswa tetap dapat memantau tenggat waktu secara mandiri melalui dashboard (FR-02) [ASSUMPTION].
- **FR-09**: Impor data massal via CSV membantu Administrator dalam operasional awal kampus, tetapi administrator masih bisa memasukkan data pengguna satu per satu secara manual sebagai fallback [ASSUMPTION].

### D. Won't Have (for this release)
- Tidak ada kebutuhan fungsional (FR) dari `03-requirements.md` yang masuk kategori Won't Have, karena kesepuluh FR tersebut dianggap sebagai ruang lingkup dasar minimum sistem yang layak rilis (MVP) [ASSUMPTION]. Namun, fitur obrolan langsung (chatting) dan integrasi SSO otomatis penuh ditunda untuk rilis saat ini [ASSUMPTION][OPEN QUESTION].

## 4. Analisis Trade-off dan Justifikasi Keputusan
- **Trade-off 1: Keamanan Transmisi Data vs Waktu Respons Muat Halaman**
  - Penggunaan enkripsi HTTPS/TLS 1.2+ wajib (NFR-03) melindungi data nilai akademik, namun sedikit meningkatkan waktu jabat tangan (handshake) SSL/TLS yang dapat memengaruhi performa respons halaman (NFR-01) [ASSUMPTION].
  - **Keputusan**: Mengutamakan keamanan data (security) di atas performa respons. Keamanan transmisi dinilai krusial untuk data akademik kampus, sedangkan latensi tambahan dari TLS 1.2+ modern dianggap minimal dan tidak akan merusak batas 3 detik respons pada koneksi 10 Mbps [ASSUMPTION].
- **Trade-off 2: Pembatasan Format Berkas (PDF/ZIP) vs Fleksibilitas Pengumpulan**
  - Pembatasan format berkas yang ketat (BR-01) membantu Administrator menjaga kebersihan penyimpanan dan keamanan server dari eksekusi file berbahaya, namun membatasi mahasiswa jika memiliki format tugas non-dokumen (misal audio/gambar) [ASSUMPTION].
  - **Keputusan**: Mempertahankan pembatasan format PDF dan ZIP untuk rilis awal demi menjamin aspek security dan data integrity server. Alternatif format file lain dapat direncanakan di iterasi berikutnya setelah infrastruktur pemindaian virus file siap diimplementasikan [ASSUMPTION][OPEN QUESTION].
