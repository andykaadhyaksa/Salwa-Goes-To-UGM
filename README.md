# PAPs Siap 500 · Fighting For UGM

Aplikasi belajar persiapan tes PAPs UGM (satu berkas HTML, tanpa build). Bisa dipasang di HP sebagai aplikasi (PWA) dan tetap jalan tanpa internet setelah dibuka sekali.

## Cara publikasi di GitHub Pages
1. Buat repositori baru (misal `paps-siap-500`), unggah **semua isi folder ini** (index.html, manifest.webmanifest, sw.js, favicon.ico, folder icons).
2. Settings → Pages → Source: *Deploy from a branch* → Branch: `main`, folder `/ (root)` → Save.
3. Buka `https://USERNAME.github.io/paps-siap-500/` di Chrome HP.
4. Menu ⋮ Chrome → **Instal aplikasi** (atau **Tambahkan ke layar utama**).

## Catatan
- Data belajar tersimpan di browser perangkat (localStorage). Pakai Pengaturan → Cadangan untuk pindah perangkat.
- Setelah memperbarui `index.html`, naikkan angka versi di `sw.js` (`const V='paps-v10'`) agar HP memuat versi baru.
- Pembuatan laporan PDF memuat pustaka dari cdnjs; butuh internet saat pertama kali.

© 2026 Salwa Tsania Nisa, S.K.M.
