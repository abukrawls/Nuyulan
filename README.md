# Data Nuyulan

Aplikasi pencatatan jumlah paket nuyulan harian — minimalis, cepat, dan datanya tersimpan permanen di perangkat/browser pengguna.

## Fitur

- Pencatatan tanggal & jumlah paket, dengan nomor urut otomatis
- Daftar data berbentuk kartu, terurut dari tanggal terlama ke terbaru
- Edit dan hapus data (dengan konfirmasi)
- Ringkasan Total Data & Total Paket, dihitung otomatis
- Export laporan ke gambar PNG (siap dibagikan/dicetak)
- Mode terang & gelap
- Validasi input (paket wajib diisi, harus bilangan bulat positif)

## Menjalankan secara lokal

Ini adalah aplikasi **single-file** (`index.html`) tanpa proses build. Cukup buka filenya langsung di browser, atau jalankan server statis sederhana:

```bash
# opsi 1: buka langsung
open index.html          # macOS
start index.html         # Windows

# opsi 2: pakai server lokal (disarankan agar semua fitur browser berjalan normal)
python3 -m http.server 8000
# lalu buka http://localhost:8000 di browser
```

## Deploy ke GitHub Pages

1. Buat repository baru di GitHub, lalu upload/push isi folder ini.
2. Masuk ke **Settings → Pages**.
3. Pada **Source**, pilih branch `main` dan folder `/ (root)`.
4. Simpan — situs akan tersedia beberapa saat kemudian di `https://<username>.github.io/<nama-repo>/`.

## Catatan penyimpanan data

Data disimpan secara persisten di lingkungan tempat aplikasi ini dijalankan (melalui API penyimpanan bawaan pada halaman). Jika di-deploy ke hosting statis biasa (mis. GitHub Pages) di luar lingkungan tersebut, sesuaikan bagian penyimpanan data (`window.storage`) pada `index.html` dengan mekanisme penyimpanan yang tersedia di platform tujuan (misalnya IndexedDB, backend API, dsb.), karena `window.storage` khusus untuk lingkungan Artifact ini dan tidak tersedia di browser biasa.

## Struktur

```
data-nuyulan/
├── index.html      # seluruh aplikasi (markup, gaya, dan logika)
└── README.md
```
