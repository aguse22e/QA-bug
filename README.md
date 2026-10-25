# Sistem QA dan Bug Aplikasi

Aplikasi web statis untuk pengujian QA manual & otomatis, checklist, laporan per sesi, dan Agen AI — dalam **satu file `index.html`**, tanpa server dan tanpa dependensi eksternal.

**Demo online (GitHub Pages):** https://aguse22e.github.io/QA-bug/

## Fitur

- **Ringkasan** — total proyek, kasus uji, sesi, bug terbuka, pass-rate keseluruhan, dan daftar bug terbaru.
- **Proyek** — tambah/edit/hapus proyek dengan nama, deskripsi, alamat website online (misal `https://tokoku.com`, skema boleh kosong) dan alamat website lokal (misal `http://localhost:3000`), tampil sebagai link yang bisa diklik di kartu proyek.
- **Kasus Uji** — tambah/edit/hapus, pilih proyek, jenis Manual atau Otomatis, modul, judul, preconditions, langkah-langkah, hasil yang diharapkan, dan referensi skrip untuk kasus otomatis.
- **Sesi & Checklist** — buat sesi dari proyek + pilih kasus uji, pilih lingkungan online/lokal (diisi dari alamat website proyek), jalankan checklist per item dengan status Lolos / Gagal / Terblokir / Dilewati, catatan, dan durasi. Item yang Gagal bisa langsung dibuat bug.
- **Bug** — tracker dengan status Terbuka → Dikerjakan → Diperbaiki → Terverifikasi → Ditutup, lengkap dengan judul, proyek, modul, tingkat keparahan, deskripsi, dan langkah reproduksi.
- **Laporan per sesi** — ring pass-rate, breakdown per modul, daftar bug sesi, kesimpulan kesiapan rilis, dan tombol unduh laporan sebagai `.txt`.
- **Agen AI** — akun Agen QA-1 (@agen-qa), peran Analis program & perbaikan bug otomatis. Bisa diaktifkan/dijeda, mode offline / online / gabungan, target semua proyek atau satu proyek. Analisis offline menghitung health score, ringkasan berbahasa Indonesia, dan rekomendasi dari data tersimpan. Mode online hanya cek read-only alamat website proyek. Agen ini **tidak mengedit kode langsung**.
- **Roadmap** — Roadmap Pengujian QA Manual dengan 8 fase berurutan, tiap fase berisi tujuan, estimasi waktu, langkah-langkah, checklist yang bisa dicentang (progress tersimpan), output, dan tips; plus tabel 8 jenis pengujian manual, Entry/Exit Criteria, dan kesalahan umum pemula.

## Cara Pakai

### Online (GitHub Pages)

Buka https://aguse22e.github.io/QA-bug/ di browser.

### Lokal (double-click)

1. Unduh/clone repo ini.
2. Buka file `index.html` dengan double-click di browser — tidak butuh server.
3. Mulai dari tab **Proyek**, lalu **Kasus Uji**, **Sesi & Checklist**, dan **Bug**.

## Penyimpanan Data

Semua data tersimpan di **localStorage browser masing-masing pengguna** (key: `qa-bug-app-v1`). Data tidak dikirim ke server mana pun, dan tidak terbawa antar browser/perangkat. Aplikasi mulai dari keadaan kosong, tanpa data contoh. Ada tombol "Hapus Semua Data" di tab Ringkasan.

## Catatan Teknis

- Satu file statis: HTML + CSS + JavaScript dalam `index.html`, tanpa CDN, font eksternal, path absolut, atau backend.
- Berfungsi di `file://` maupun di GitHub Pages (HTTPS).
- Cek online Agen AI bersifat read-only dan menangani kegagalan fetch (misalnya karena CORS) tanpa merusak aplikasi; bug tidak otomatis ditandai Diperbaiki.
