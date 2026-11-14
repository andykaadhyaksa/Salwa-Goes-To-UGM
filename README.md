# PAPs Siap 500 · Fighting For UGM

Aplikasi belajar persiapan tes PAPs UGM (satu berkas HTML, tanpa build). Bisa dipasang di HP sebagai aplikasi (PWA) dan tetap jalan tanpa internet setelah dibuka sekali.

## Cara publikasi di GitHub Pages
1. Buat repositori baru (misal `paps-siap-500`), unggah **semua isi folder ini** (index.html, manifest.webmanifest, sw.js, favicon.ico, folder icons).
2. Settings → Pages → Source: *Deploy from a branch* → Branch: `main`, folder `/ (root)` → Save.
3. Buka `https://USERNAME.github.io/paps-siap-500/` di Chrome HP.
4. Menu ⋮ Chrome → **Instal aplikasi** (atau **Tambahkan ke layar utama**).

## Sinkronisasi antar perangkat (HP, laptop, dst.)
1. Buat proyek gratis di supabase.com → SQL Editor → jalankan:
   ```sql
   create table paps_sync(id text primary key, upd bigint, json text);
   alter table paps_sync enable row level security;
   create policy "paps open" on paps_sync for all to anon using (true) with check (true);
   ```
2. Project Settings → API: salin **Project URL** dan **anon public key**, tempel ke `config.js`, lalu commit.
3. Di aplikasi: Lainnya → Pengaturan → Sinkronisasi → ketik **kode sinkron** (rahasia buatanmu, min. 6 karakter) → Hubungkan.
4. Di perangkat lain buka alamat yang sama, ketik kode yang sama. Salwa dan Andyka bisa memakai kode berbeda bila ingin riwayat terpisah.

## Catatan
- Pembaruan v19 (14 Nov 2026): **pembahasan visual**. Setiap pembahasan kini berisi kotak jawaban hijau, diagram sesuai jenis soal (busur pola deret angka dan huruf, rantai hitung, diagram Venn himpunan, alur diskon bertingkat, kartu P banding Q, padanan dan lawan kata dengan opsi yang dicoret, pasangan analogi, premis ke kesimpulan, denah susunan duduk atau urutan, gambar jawaban untuk Venn, pola gambar, dan klasifikasi), kotak Cara cepat, langkah bernomor, lalu Rumus dan Tips. Hanya tampilan yang berubah: bank soal, ID soal, kunci jawaban, dan data belajar (`asal_paps_v1`) tidak disentuh.
- Pembaruan v15: rumus (pecahan, akar, pangkat) ditulis bertumpuk rapi; setiap pembahasan berisi Langkah pengerjaan, Rumus & konsep, dan Tips & trik; kunci jawaban yang keliru dibetulkan; soal yang ambigu/rusak/duplikat disembunyikan otomatis (tidak muncul di latihan, tetap aman di riwayat). Kunci progres tidak berubah (`asal_paps_v1`).
- Data belajar tersimpan di browser perangkat (localStorage). Pakai Pengaturan → Cadangan untuk pindah perangkat.
- Setelah memperbarui `index.html`, naikkan angka versi di `sw.js` (`const V='paps-v19'`) agar HP memuat versi baru.
- Pembuatan laporan PDF memuat pustaka dari cdnjs; butuh internet saat pertama kali.

© 2026 Salwa Tsania Nisa, S.K.M.
