# Siap CPNS · Latihan SKD

Aplikasi latihan SKD CPNS (TWK, TIU, TKP) dalam satu berkas HTML, tanpa build. Bisa dipasang di HP (PWA) dan tetap jalan offline setelah dibuka sekali.

## Fitur
- Latihan per subtes/topik dengan pembahasan langsung
- Simulasi SKD: 110 soal, 100 menit, penilaian resmi (TWK/TIU 5-0, TKP 1-5) dan cek passing grade (65 / 80 / 166)
- Progres: akurasi per subtes dan topik, riwayat, soal yang perlu diulang
- Info CPNS 2026: status seleksi, format SKD, materi, strategi
- Cadangan data (ekspor/impor JSON), mode gelap

## Mengisi bank soal
Isi array `BANK_REAL` di `index.html`. Selama kosong, aplikasi memakai 12 soal contoh. Skema satu soal ada di komentar di atas `BANK_REAL`.

## Publikasi (GitHub Pages)
Unggah semua isi folder ke repositori, lalu Settings → Pages → Deploy from a branch → `main` / root.
Setiap kali `index.html` berubah, naikkan angka versi di `sw.js` (`const V='cpns-v1'`).


## Versi 3
- Beranda dengan estimasi skor, rekomendasi cerdas, target harian, streak.
- Belajar: 15 materi + trik cepat + jebakan + contoh interaktif; kartu hafalan (Leitner).
- Pembahasan, trik, dan tautan materi tampil setelah tiap soal; waktu per soal; simpan soal (bintang); buku kesalahan.
- Panduan: akademik, mental (napas 4-4-6, cek diri), rencana 4 minggu/7 hari, daftar Hari-H, info CPNS.
- Progres: tren simulasi, prioritas belajar, pencapaian.

## Versi 3.1
- Panduan → Kurikulum: tugas harian adaptif (4 fase), target jelas, tercentang otomatis.
- Panduan → Analisis: radar kekuatan, jarak ke batas lolos, kelebihan, minus, strategi, akurasi per topik, kecepatan, tren, konsistensi.

## Versi 3.2
- Tata letak lebar penuh (multi-kolom di desktop), tema dipindah ke sidebar.
- Tab baru di Panduan: Program (6 program), Strategi, Rumus, Seleksi (alur, syarat, dokumen, FAQ); tab Tips di Belajar.
- Latihan: paket latihan, peta topik, soal per tahun; Progres: cakupan bank soal.

## Versi 3.3
- Pembahasan rinci: alasan kunci, analisis tiap opsi, dan playbook cara menghadapi soal serupa (31 jenis soal).

## Versi 4 (rombak UI + materi rinci)
- Navigasi baru: Beranda, Belajar, Latihan, Tes, Program, Progres, Panduan (di HP: bar bawah 6 menu, sisanya di "Lainnya").
- Belajar: 22 materi dengan ringkasan, langkah menjawab, trik kunci, cara menghafal, contoh berlangkah, jebakan, dan soal coba sendiri.
- Pembahasan soal: pola deret dan rumus numerik dijelaskan langkah demi langkah (hanya tampil bila cocok dengan kunci), materi TWK terkait, aturan logika, dan analisis tiap opsi.
- Setelah mengubah file, naikkan versi cache di `sw.js`.

## Versi 4.1 — Soal tambahan format terbaru
- +243 soal orisinal (bank sekarang 1.601): deret kotak/selang-seling/huruf/tiga angka (90), numerik cerita (92), TWK (32), logika & analogi (19), TKP (17 dengan skor 1–5).
- Bukan soal asli SKD 2026 (belum ada yang dirilis resmi); dibuat mengikuti pola dan format terbaru. Soal numerik/deret jawabannya diverifikasi kode; TWK/TKP ditulis manual — mohon dicek bila ragu.
- Soal "own": penjelasan langkah demi langkah + analisis tiap opsi; angka dalam kotak tampil sebagai kotak.

## Versi 4.2 — Program lebih jelas
- Tab Program: kartu "Posisi kamu" (Hari X dari N, sisa hari, deretan hari: ✓ tuntas / merah terlewat / biru hari ini).
- Tab baru "Jadwal lengkap": semua hari lengkap dengan tanggal, fase, target, dan daftar tugas per hari (ketuk untuk membuka).
- "Hari-hari berikutnya": 7 hari ke depan dengan rincian tugas.

## Versi 4.3 — Sinkronisasi antar perangkat
Memakai metode yang sama dengan PAPs Siap 500 (Supabase, tabel `paps_sync`, kode sinkron). Tombol "Sinkron" di pojok kanan atas (semua layar), Progres → Data & sinkron, atau Lainnya → Sinkronisasi: ketik kode sinkron (min. 6 karakter), lalu ketik kode yang sama di perangkat lain. Data dipisahkan dari PAPs otomatis (id `cpns:<kode>`). Sinkron otomatis 2 detik setelah perubahan, saat app dibuka, dan tiap ±45 detik; bila dua perangkat sama-sama berubah, data digabung.

## Versi 4.4 — Perbaikan kualitas
- Soal: dipulihkan teks bacaan/informasi yang hilang (12+ soal TWK & logika), rumus yang rusak direkonstruksi (7 soal), 10 soal yang tidak dapat dipulihkan disembunyikan (bank kini 1.591). ID soal tidak berubah, progres aman.
- Rumus tampil seperti formula (pecahan bertumpuk, akar, pangkat) pada soal TIU, pembahasan, dan materi.
- Pengerjaan soal: opsi di bawah soal, panel "Daftar soal dan selesai" di kanan (desktop).
- Pembahasan: materi/cara mengingat hanya tampil bila sesuai kunci; analisis opsi lebih spesifik (kemungkinan kesalahan pada soal hitungan).
- Riwayat: sesi dan semua soal yang pernah dikerjakan dapat dibuka kembali (jawaban + pembahasan) tanpa mengubah progres.
- Belajar → Hafalan: teknik menghafal ditulis ulang dengan langkah dan contoh nyata.
- Nomor sumber soal ditampilkan agar mudah dilaporkan bila ada yang janggal.

## Versi 4.6 — Cek ulang menyeluruh (soal, opsi, kunci, rumus)
- Seluruh TIU dan TWK dibaca satu per satu; TKP: semua soal tanpa pembahasan dibaca dan 357 soal berpembahasan dicocokkan dengan skornya.
- 21 kunci jawaban yang salah di naskah sumber dikoreksi (mis. TWK: bom atom Hiroshima–Nagasaki, MA vs MK, Hari Kesaktian Pancasila 1 Oktober, asas ius sanguinis, Maklumat 14 November 1945; TIU: 3 soal hitungan) dan pembahasannya ditulis ulang. 23 soal TKP dinilai ulang skornya karena skor sumber bertentangan dengan logikanya atau dengan soal kembarannya.
- Soal yang tidak dapat dipulihkan disembunyikan (soal tanpa kunci yang sahih, soal bergabung, kunci bertentangan dengan premis). Bank aktif: 1.544 soal (TWK 494 · TIU 495 · TKP 555). ID tidak berubah, jadi progres, riwayat, dan sinkron tetap aman.
- Opsi yang rusak diperbaiki: teks soal lain yang menempel di opsi dipotong, opsi kembar diganti, ±215 salah ketik pada soal hasil PDF dibetulkan (mis. "dibwjudkan", "persenjetaan", "Postdam"). Soal buatan sendiri tidak disentuh.
- 13 pembahasan TIU lain (silogisme, hitungan waktu, persen, pola) ditulis ulang bertahap; pecahan dengan koefisien huruf (mis. 2y/3) kini ikut ditulis atas-bawah.
- Analisis tiap opsi pada TWK/TKP tidak lagi memakai kalimat hitungan; untuk soal "kecuali/bukan" kalimatnya disesuaikan.
- Cache offline naik ke cpns-v10.
- Catatan jujur: skor TKP dan beberapa kunci TWK dari PDF sumber bersifat penilaian; yang terlihat bertentangan sudah saya putuskan sendiri dan ditandai di atas, tetapi sisanya mengikuti naskah sumber.

## Versi 4.5 — Pembahasan ditulis ulang
- 134 pembahasan yang rusak akibat ekstraksi PDF (pecahan/pangkat/tabel terurai menjadi deretan angka) ditulis ulang menjadi langkah bernomor ("Langkah 1 — … Jawaban: X") dengan pecahan atas-bawah. Semua hasil hitung diperiksa terhadap kunci jawaban.
- Soal yang teksnya cacat diperbaiki (pecahan/pangkat hilang, soal cerita yang kontradiktif, opsi yang salah cetak) dan diberi catatan di pembahasan bila naskah asli janggal.
- 11 soal tambahan disembunyikan karena kunci/gambar/soalnya tidak dapat dipulihkan (logika duduk melingkar 2 soal, soal dengan kunci yang bertentangan dengan soalnya, dsb.). Bank kini 1.580 (soal "pernyataan berikut" tanpa pernyataannya ikut disembunyikan; 8 pembahasan hitungan tambahan dirapikan). ID soal tidak berubah; progres, riwayat, dan sinkron aman.
- Analisis tiap opsi pada soal hitungan kini menyebut hasil yang benar vs opsi itu.

## Versi 4.7 — Soal figural (gambar)
- Bank bertambah 77 soal figural bergambar (tahun 2026), sehingga bank aktif menjadi 1.621 soal (TWK 494 · TIU 572 · TKP 555). ID soal lama tidak berubah; progres, riwayat, dan sinkron aman.
- Empat jenis: **deret gambar** (23 soal: rotasi, pergeseran, siklus, sisi/jumlah bertambah, kotak terisi, cermin bergantian, jarum jam), **ketidaksamaan** (20: putar vs cermin, sisi titik, jumlah, warna/bentuk sepusat, simetri), **analogi gambar** (18: rotasi, cermin, warna dibalik, jumlah/sisi bertambah, luar–dalam bertukar, bergeser, dua perubahan sekaligus), **matriks 3×3** (16: kotak latin, jumlah titik, operasi gabung/beda/kurang, rotasi baris-kolom).
- Terintegrasi seperti tipe soal lain: opsi berupa gambar (A–E), pembahasan bernomor dengan atribut J-P-A-W-B, alasan tiap opsi salah, kartu "Materi yang diuji" dan "Cara mengingat", trik cepat, "Cara menghadapi soal serupa", empat materi baru (deret, ketidaksamaan, analogi, matriks) lengkap dengan langkah, trik kunci, contoh, dan "Coba sendiri" bergambar, kartu hafalan "Aturan figural", latihan per topik, statistik/akurasi per topik, rekomendasi materi, buku kesalahan, tinjauan, dan simulasi.
- Simulasi memuat paling banyak 6 soal figural (dari 35 TIU) dan tes diagnostik 1, agar komposisinya mirip ujian.
- Kurikulum: tugas figural ditambahkan pada rencana 4 minggu dan mode kilat 7 hari; program remedial TIU menyebut figural.
- Perbaikan lain: teks "Trik cepat" dan "Cara menghadapi soal serupa" yang memuat huruf tebal sebelumnya tampil dengan tanda `<b>` mentah; kini tampil benar.
- Cache offline naik ke cpns-v11.
- Catatan jujur: semua soal figural adalah soal orisinal buatan sendiri (gambar dibangkitkan dengan kode), bukan soal resmi BKN. Kunci ditentukan oleh aturan pembangkitnya dan setiap opsi dipastikan tidak kembar secara visual; saya memeriksa tampilan contoh tiap pola, tetapi belum diuji oleh orang lain. Matriks 3×3 adalah tipe klasik yang umum di bimbel; kisi-kisi SKD terbaru terutama menyebut deret, ketidaksamaan, dan analogi.

## Versi 4.8 — +553 soal HOTS bergaya SKD 2026
- Bank bertambah 553 soal tahun 2026, sehingga bank aktif menjadi **2.174 soal** (TWK 596 · TIU 933 · TKP 645). Penambahan bersifat tambah-saja: ID soal lama tidak berubah, jadi progres, riwayat, dan sinkron tetap aman (diuji dengan memuat progres dari versi 4.7).
- **TIU +361**: numerik 193 (deret berlapis, soal cerita bertingkat, persen/rasio/umur/jarak/kerja/campuran, perbandingan kuantitatif P-Q, kalender), logika analitis 65 (silogisme, premis bersyarat, penjadwalan/penempatan dengan banyak syarat), analogi dan padanan kata 68, verbal analitis 35 (sinonim/antonim, urutan kalimat, simpulan dan asumsi bacaan).
- **TWK +102**: pilar negara 20, nasionalisme 20, integritas 20, bela negara 20, bahasa Indonesia 22. Berpola penalaran/kasus (bukan hafalan murni) sesuai kisi-kisi 2026.
- **TKP +90** (15 per aspek: pelayanan publik, jejaring kerja, sosial budaya, TIK, profesionalisme, anti radikalisme): skor 1–5, jawaban terbaik tersebar merata dan tidak selalu opsi terpanjang. Pembahasan menjelaskan alasan setiap opsi beserta skornya.
- Semua soal baru memuat pembahasan bernomor, alasan tiap opsi salah, dan label sumber "Soal orisinal Siap CPNS · HOTS 2026". Soal tahun 2026 diprioritaskan dalam latihan acak dan simulasi (±44% dari soal simulasi).
- Pemeriksaan: angka kunci pada 163 soal hitungan dicocokkan dengan langkah pembahasan dan sampel soal hitungan dihitung ulang manual; soal kalender dicocokkan dengan kalender asli; seluruh 65 soal logika (penjadwalan, tempat duduk, silogisme, premis bersyarat) dihitung ulang dengan program terpisah (penelusuran semua susunan, tabel kebenaran, model diagram Venn) dan kuncinya cocok serta unik; sampel soal TWK, verbal, dan analogi dibaca ulang satu per satu. Tampilan semua soal baru diuji di desktop dan HP tanpa galat.
- Cache offline naik ke cpns-v12.
- Catatan jujur: ini **bukan** soal asli atau bocoran SKD 2026 dan **bukan** salinan soal bimbel/YouTuber (mis. Al Faiz, dokter Franz); semuanya ditulis orisinal mengikuti kisi-kisi dan format resmi 2026 (110 soal, 100 menit; TWK 30, TIU 35, TKP 45). Soal TWK dan TKP ditulis manual dan belum diuji orang lain — mohon dilaporkan bila ada yang janggal. Soal dari pihak lain dapat ditambahkan bila kamu memiliki berkasnya (PDF atau foto) dan berhak memakainya.

## Versi 4.9 — Campuran soal: terbaru lebih banyak, tetap bercampur
- Latihan (per topik, paket, latihan cepat, diagnostik, drill topik) dan Tes (mini-test, simulasi 110 soal) kini memakai komposisi tahun yang pasti: **±60% soal 2026, ±28% soal 2023, ±12% soal 2019**, urutannya diacak. Sebelumnya hanya pembobotan acak yang menaikkan porsi 2026 sedikit di atas porsinya di bank (±44% di simulasi); sekarang ±60% (sekitar 66 dari 110 soal).
- Bila satu topik tidak punya soal pada salah satu tahun, jatahnya dibagi ke tahun lain secara proporsional dan soal terbaru tetap didahulukan. Paket "Soal tahun YYYY" tetap hanya berisi tahun itu. "Ulangi yang salah" dan buku kesalahan tidak diubah.
- Batas soal figural (maksimal 6 per simulasi) tetap berlaku tanpa mengubah komposisi tahun.
- Rasio dapat diubah di satu tempat: konstanta `YMIX` di `index.html` (mis. `[0.70,0.20,0.10]`). Lapisan tahun mengikuti urutan tahun di bank (sekarang 2026 / 2023 / 2019).
- Pada topik yang soal 2026-nya masih sedikit (mis. TKP dan TWK), soal terbaru akan lebih sering berulang; makin banyak soal baru ditambahkan, makin bervariasi.
- Tab Tes dan Latihan menampilkan catatan komposisi. Progres dan data tersimpan tidak berubah. Cache offline naik ke cpns-v13.

## Versi 4.10 — Hari terlewat bisa dikerjakan + dua perbaikan tugas harian
- **Hari "Terlewat" kini bisa dikerjakan.** Ketuk angka merah di grid Jadwal (atau tombol Kerjakan di kartu hari itu, atau kartu baru "Hari terlewat" di Tugas hari ini) untuk membuka daftar tugas hari tersebut lengkap dengan tombol Mulai: soal per subtes, topik terlemah, ulangi soal salah, kartu hafalan, baca materi, simulasi, diagnostik, dan ceklis manual. Begitu semua tugasnya selesai, hari itu otomatis berstatus **Tuntas**.
- **Perhitungannya per hari, tidak dobel.** Soal yang dikerjakan dari daftar hari terlewat dicatat untuk hari itu, bukan untuk tugas hari ini. Aktivitas nyata tetap utuh di tempat lain: riwayat sesi (judulnya berawalan "Hari 2 ·"), statistik per soal, streak, dan grafik harian. Aktivitas yang memang terjadi pada tanggal hari terlewat itu (misalnya sudah 6 dari 10 soal) ikut dihitung.
- Daftar tugas hari terlewat dikunci saat pertama dibuka, jadi target dan materinya tidak berubah-ubah selagi kamu mengerjakan.
- **Perbaikan 1, tugas "Baca materi".** Sebelumnya setelah materi hari itu dibaca, tugasnya pindah ke materi berikutnya dan kembali 0/1, sehingga hari hampir mustahil tuntas (harus membaca semua materi satu per satu). Sekarang materi tiap tanggal dikunci dan tercentang begitu dibaca.
- **Perbaikan 2, tugas "soal topik terlemah"** (fase Penguatan dan Intensif, mulai Hari 9 pada program 28 hari). Sebelumnya topik terlemah berganti setelah dilatih sehingga targetnya ikut pindah. Sekarang topiknya dikunci per tanggal.
- Data tersimpan tidak diubah. Tiga kolom opsional baru (`cmk` ledger, `cpin` daftar tugas terkunci, `cfix` pilihan materi/topik per tanggal) dibuat kosong bila belum ada, ikut cadangan dan sinkron antar perangkat (digabung seperti `cdone`), dan dikosongkan saat program dimulai ulang atau diatur ulang.
- Cache offline naik ke cpns-v14.

## Versi 4.11 — +132 soal "pola tabel angka" (format baru TIU 2026)
- Format baru yang dilaporkan muncul di TIU SKD 2026: tabel angka dengan satu sel bertanda tanya. Bank bertambah **132 soal** (total 2.306; TIU 1.065), kategori Numerik, tahun 2026, dengan enam ragam pola: aturan per baris 3 kolom (46 soal, termasuk yang tanda tanyanya di Kolom 1 atau 2), 4 kolom (16), tabel X–Y dan "suku ke–nilai" (26), aturan per kolom 3×3 (16), dua kolom dengan pola masing-masing (12), dan deret yang mengalir di dalam tabel 3×3 (16).
- Soal-soal ini **orisinal** (bukan salinan soal bimbel atau soal resmi). Ragam polanya mengikuti contoh yang beredar di internet; jumlah contoh terbuka yang lengkap dengan tabelnya masih sedikit.
- Tiap soal punya pembahasan per baris, trik cepat, dan alasan untuk setiap opsi salah. Kunci diperiksa ulang secara terpisah langsung dari tabel yang tampil, dan soal yang aturannya bisa ditafsirkan ganda dibuang saat pembuatan.
- Tabel tampil di atas teks soal (kolom `svg` berisi `<table class="qtb">`, penanda `tp:'tabel'`). Chip baru di Latihan: "Pola tabel angka · 15". Soal tabel juga ikut tercampur di latihan Numerik, paket TIU, dan simulasi (rata-rata 3–4 soal per simulasi).
- Soal lama dan ID-nya tidak berubah; progres aman. Cache offline naik ke cpns-v15.

## Versi 4.12 — +154 soal pola tabel lagi (total 286) dan tata letak baru
- Soal pola tabel angka kini **286** (bank total 2.460; TIU 1.219). Tambahan 154 soal memuat tiga tata letak baru: **tabel X–Y–Z** (26), **tabel mendatar** baris X dan baris Y (11), dan **matriks dengan sifat baris** (26): jumlah tiap baris tetap, hasil kali tiap baris tetap, bilangan tengah = jumlah, hasil kali, atau rata-rata dua sisinya, kolom terakhir = rata-rata. Sisanya ragam lama dengan angka dan aturan baru, lebih banyak yang tanda tanyanya di Kolom 1 atau 2.
- Daftar tata letak mengikuti yang disebut sumber bimbel untuk format 2026: matriks, baris, kolom, tabel X–Y, tabel X–Y–Z, dan suku ke–nilai. Semua soal tetap orisinal dan kuncinya diverifikasi terpisah dari tabel yang tampil.
- Simulasi: soal tabel dibatasi **maksimal 6 per simulasi** (seperti soal figural) supaya TIU tidak didominasi satu jenis soal.
- Soal lama dan ID tidak berubah. Cache offline naik ke cpns-v16.

## Versi 4.15 — Jebakan umum diperbaiki

- Sebelumnya kotak "Jebakan umum" memakai satu kalimat generik per topik, sehingga sering tidak sesuai soal. Sekarang jebakan hanya tampil bila nyambung dengan soalnya, berurutan dari: jebakan tulisan tangan di pembahasan → soal bertipe BUKAN/KECUALI (diingatkan membaca perintahnya) → opsi pengecoh nyata beserta alasannya dari soal itu → kalimat topik, hanya bila kata kunci soalnya cocok. Untuk TKP: opsi skor 4 yang hampir benar beserta kekurangannya.
- Bila tidak ada yang cocok, kotak jebakan tidak ditampilkan (lebih baik kosong daripada keliru). Bank soal, ID, dan save tidak berubah.

## Versi 4.14 — Tinjau tugas & Bahan belajar harian

- **Tugas yang sudah tercoret tetap bisa dibuka.** Tombol *Tinjau* (soal), *Baca ulang* (materi) atau *Buka* (hafalan) muncul di tugas selesai, di hari ini maupun hari kejar.
- **Hari-hari lalu yang tuntas bisa dibuka kembali** dari garis hari (angka ✓) atau Jadwal lengkap. Tinjauan bersifat baca-saja dan tidak mengubah progres.
- **Bahan belajar hari ini:** ringkasan strategi (cara membaca soal, trik cepat, jebakan, tanpa jawaban) untuk topik yang akan muncul. Latihan subtes hari itu diarahkan ±70% ke topik fokus. Fokus tiap hari berganti dan dikunci per tanggal. Tombol *Bahan belajar* ada di baris Baca materi. Kartu ini tidak dihitung dalam n/N tugas.
- Save lama tetap aman: kunci `siap-cpns-v2` dan ID soal tidak berubah; hanya menambah `cfix[tanggal].sp/.br` di dalam data yang sudah ikut sinkron. Daftar soal tinjauan tersedia untuk 80 sesi terakhir.

## Versi 4.13 — Pembahasan visual untuk semua soal
- Setiap pembahasan (di latihan, tinjauan, dan buku kesalahan) kini tersusun sama: **kotak jawaban hijau → diagram → kotak Trik Cepat / Jebakan Umum → langkah bernomor**. Analisis tiap opsi tetap ada di bawahnya.
- Diagram dipilih otomatis menurut jenis soal (2.460 soal, semuanya mendapat kotak jawaban, kotak trik atau jebakan, dan langkah; 5 soal lama tanpa teks pembahasan hanya mendapat diagram):
  - Pola tabel (286): tabel terisi dengan kolom **Hitungan** per baris, sel jawaban hijau.
  - Deret angka dan huruf (133): **busur operasi** antarsuku (+6, ×2 +3, ...); deret selang-seling memakai busur atas dan bawah; deret 3–4 pola dipisah per baris.
  - Analogi (126): kotak pasangan kiri dan kanan dengan label hubungannya. Sinonim dan antonim (68): kata soal = / ✕ kata jawaban.
  - Logika (113): premis → kesimpulan (implikasi ditulis P → Q), rantai urutan, dan denah susunan duduk.
  - Hitungan dan soal cerita (254): **rantai hitung** dari data sampai jawaban.
  - TKP (645): **peringkat skor** kelima opsi berupa batang 5 sampai 1.
  - TWK (596) dan sisa TIU (162): kartu "yang ditanya → kunci". Soal figural (77) memakai kartu gambar yang sudah ada.
- Diagram dibangun saat tampil dari data soal dan teks pembahasan yang ada; bank soal, ID, dan progres tidak berubah. Kode: blok "VISUAL PEMBAHASAN (v4.13)" (`vzBlock` dipanggil dari `detail()`).
- Perbaikan tampilan: soal lama yang katanya menempel tidak lagi melebar keluar layar. Cache offline naik ke cpns-v17.
