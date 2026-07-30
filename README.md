# Data Nuyulan

Aplikasi pencatatan data buyer & COD nuyulan — minimalis, cepat, dan datanya tersimpan permanen di perangkat/browser pengguna.

## Fitur

- Pencatatan nama buyer & jumlah COD, dengan nomor urut otomatis
- Daftar data berbentuk kartu, terurut sesuai urutan input
- Edit dan hapus data (dengan konfirmasi)
- Ringkasan Total Buyer & Total COD, dihitung otomatis dan diformat Rupiah
- Export laporan ke gambar PNG bergaya struk pembayaran (No, Nama Buyer, COD, Total), siap dibagikan/dicetak
- Mode terang & gelap
- Validasi input (nama buyer wajib diisi, COD wajib angka bulat ≥ 0)

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

Data disimpan secara permanen di **IndexedDB** milik browser pengguna — tetap ada walau halaman di-refresh, browser ditutup, atau HP di-restart. Data ini tersimpan per perangkat/per browser (tidak otomatis sinkron antar perangkat berbeda) dan tidak butuh server atau koneksi internet setelah halaman pertama kali dimuat.

## Struktur

```
data-nuyulan/
├── index.html      # seluruh aplikasi (markup, gaya, dan logika)
└── README.md
```
