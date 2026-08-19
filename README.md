# QRIS-SCORE — Showcase

Folder ini berisi halaman showcase yang menampilkan aplikasi QRIS-SCORE
**sungguhan berjalan** (lewat iframe, bukan gambar statis) dalam bingkai
browser (versi Web) dan bingkai ponsel (versi App) sekaligus.

⚠️ **Folder ini HARUS dipublish PALING TERAKHIR**, setelah `qris-score-web`
dan `qris-score-app` sudah live di GitHub Pages — karena halaman ini
menampilkan kedua situs itu lewat iframe.

## Langkah-langkah

1. Publish dulu folder **qris-score-web** dan **qris-score-app** (lihat
   README masing-masing) → catat kedua URL-nya, misalnya:
   - `https://USERNAME.github.io/qris-score-web`
   - `https://USERNAME.github.io/qris-score-app`
2. Buka file `index.html` di folder ini dengan text editor apa saja, cari
   tag `<script>` di bagian paling bawah, lalu edit dua baris ini:
   ```javascript
   const WEB_BASE = "https://USERNAME.github.io/qris-score-web";   // <-- ganti sesuai punyamu
   const APP_BASE = "https://USERNAME.github.io/qris-score-app";   // <-- ganti sesuai punyamu
   ```
   Ganti `USERNAME` dan nama repo dengan punya kamu sendiri. **Jangan pakai
   garis miring `/` di akhir URL.**
3. Simpan file, lalu buat repository baru di GitHub (mis. `qris-score-showcase`),
   push isi folder ini (sama seperti langkah publish di folder lain).
4. Aktifkan GitHub Pages seperti biasa (Settings → Pages → branch `main` → root).
5. Kalau lupa mengedit langkah 2, nanti muncul kotak peringatan kuning
   otomatis di halaman yang mengingatkan kamu.

## Isi folder

```
index.html   ← showcase utama (perlu diedit dulu, lihat langkah 2 di atas)
```

## Kenapa harus diedit manual?

Karena tiga folder ini akan jadi tiga repository GitHub Pages yang **terpisah**
(masing-masing punya URL/domain sendiri), halaman showcase tidak bisa lagi
memakai path relatif (`../qris-score-web/...`) seperti saat semuanya masih
dalam satu folder proyek — makanya perlu diberi tahu URL publik masing-masing
secara eksplisit lewat `WEB_BASE` dan `APP_BASE`.
