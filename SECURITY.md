🛡️ Kebijakan Keamanan & Integritas Sistem Ujian (Security Policy)
Dokumen ini menjelaskan mekanisme perlindungan keamanan, integritas pelaksanaan evaluasi daring, serta prosedur penanganan kendala teknis pada Portal Ujian Informatika Kelas VII.
🔒 Mekanisme Keamanan yang Diterapkan
1. Perlindungan Integritas Sesi Ujian (Client-Side Monitoring)
•	Deteksi Perpindahan Tab & Aplikasi (visibilitychange): Sistem memantau status visibilitas halaman secara real-time. Apabila siswa meminimalkan browser, menekan tombol Home, atau berpindah ke aplikasi lain, sistem langsung memicu peringatan dan memuat ulang formulir.
•	Deteksi Kehilangan Fokus Layar (window.blur): Mencegah penggunaan fitur layar terbagi (split-screen) atau jendela mengambang (floating window) untuk membuka catatan maupun mesin pencari selama ujian berlangsung.
•	Penghapusan Draf Jawaban Otomatis: Dikombinasikan dengan pengaturan Disable Autosave pada Google Formulir, setiap kali halaman dimuat ulang akibat pelanggaran fokus layar, pilihan jawaban yang belum dikirimkan akan dikosongkan kembali.
2. Autentikasi & Pembatasan Akses Peserta
•	Verifikasi Email Tunggal: Formulir mewajibkan pengumpulan alamat email terverifikasi dan membatasi pengisian hanya 1 kali per akun Google (Limit to 1 response).
•	Kontrol Waktu & Pengiriman Otomatis: Pengelolaan waktu 120 menit dijalankan di sisi layanan Form Presenter + Timer untuk mencegah manipulasi jam perangkat oleh peserta, serta memastikan jawaban langsung terkirim (Auto-Submit) saat waktu habis.
3. Perlindungan Kunci Jawaban & Data Nilai
•	Tidak Ada Kunci Jawaban di Kode Sumber: File index.html di repositori publik GitHub hanya memuat bingkai antarmuka (wrapper) dan skrip pengawas layar. Seluruh butir soal, kunci jawaban, dan perekaman skor tersimpan aman di server Google Formulir yang terproteksi akun guru.
•	Pembatasan Tinjauan Pasca-Ujian: Setelah mengirimkan jawaban, siswa hanya dapat melihat skor akhir total tanpa menampilkan kunci jawaban benar/salah guna mencegah kebocoran soal kepada peserta sesi berikutnya.
⚠️ Batasan Teknis & Mitigasi Risiko
Potensi Risiko	Mitigasi / Tindakan Pencegahan
Siswa membuka tautan Google Form asli secara langsung	Jangan pernah membagikan tautan asli docs.google.com/forms/... kepada siswa. Bagikan hanya tautan GitHub Pages yang membungkus tautan dari Form Presenter.
Notifikasi pop-up mengganggu layar HP siswa	Instruksikan siswa untuk mengaktifkan mode Jangan Ganggu (Do Not Disturb) sebelum memulai ujian agar notifikasi pesan masuk tidak memicu deteksi window.blur.
Koneksi internet terputus sesaat	Pastikan siswa berada di area dengan sinyal stabil sebelum memulai tes, karena pemuatan ulang halaman membutuhkan koneksi internet untuk memuat kembali formulir.
📩 Pelaporan Celah Keamanan atau Kendala Teknis
Apabila guru, pengawas, atau siswa menemukan celah keamanan, gangguan teknis pada pemuatan iframe, atau ketidaksesuaian perilaku sistem selama simulasi maupun pelaksanaan ujian:
1.	Jangan menyebarkan detail celah keamanan secara publik.
2.	Laporkan langsung kepada Guru Mata Pelajaran Informatika atau Admin Teknis Ujian Sekolah dengan menyertakan:
o	Jenis perangkat dan browser yang digunakan (contoh: Android / Google Chrome).
o	Tangkapan layar (screenshot) pesan kesalahan yang muncul.
o	Waktu kejadian kendala teknis.
