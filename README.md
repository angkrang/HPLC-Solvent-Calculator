# HPLC Solvent Calculator

Alat sederhana untuk menghitung kebutuhan pelarut (mobile phase) pada HPLC. Berguna untuk menyiapkan volume larutan pelarut dengan komposisi persentase (mis. A/B atau hingga 3 komponen) dalam satuan mL atau L.

## Fitur
- Hitung volume tiap komponen berdasarkan total volume dan persentase komposisi.
- Dukungan untuk 2 atau 3 komponen (A, B, dan opsi C).
- Pilihan satuan output: mL atau L.
- Contoh penggunaan langsung dari browser (single-page web app) atau melalui skrip Python.
- Ekspor hasil ke CSV (opsional di web app).

## Cara Kerja / Rumus
Untuk setiap komponen:
- Volume komponen = Total volume × (Persentase komponen / 100)

Contoh (2 komponen):
- Total = 1000 mL, A = 60%, B = 40%
  - V_A = 1000 × 60/100 = 600 mL
  - V_B = 1000 × 40/100 = 400 mL

## Instalasi & Penggunaan

### Web (recommended — buka di browser)
1. Salin/unduh file `index.html` di repo.
2. Buka `index.html` di browser (double-click atau jalankan via server lokal).
3. Masukkan total volume, pilih satuan (mL/L), masukkan persentase untuk tiap komponen (A, B, C bila perlu).
4. Tekan tombol "Hitung" untuk melihat hasil; tersedia opsi salin/unduh CSV bila disediakan.

Kelebihan: cepat, tanpa instalasi, visual dan mudah dipakai di komputer/laptop.

### Python CLI
Contoh skrip singkat (jika disertakan di repo sebagai `hplc_calculator.py`):

- Jalankan:
  ```
  python hplc_calculator.py --total 1000 --unit mL --A 60 --B 40
  ```

- Output:
  ```
  Total: 1000 mL
  A: 600.0 mL
  B: 400.0 mL
  ```

(Tambahan: skrip dapat ditambahkan argumen untuk komponen C dan opsi simpan ke CSV.)

## Contoh Penghitungan
- Input:
  - Total = 2000 mL
  - A = 10%, B = 90%
- Output:
  - A = 200.0 mL
  - B = 1800.0 mL

- Contoh 3 komponen:
  - Total = 1000 mL, A = 20%, B = 30%, C = 50%
  - A = 200 mL, B = 300 mL, C = 500 mL

Catatan: Pastikan jumlah persentase = 100% (atau terima pembulatan kecil). Alat ini tidak otomatis menormalisasi persentase kecuali fitur tersebut ditambahkan.

## Catatan Keselamatan & Praktis
- Gunakan pelarut sesuai prosedur laboratorium: ventilasi, APD (alat pelindung diri), dan pelabelan yang sesuai.
- Hitung dan timbang pelarut dengan peralatan yang sudah dikalibrasi untuk akurasi.
- Periksa kompatibilitas pelarut dengan kolom HPLC dan sistem.

## Struktur Repo (saran)
- index.html         — single-page web app
- assets/
  - style.css
  - script.js
- hplc_calculator.py — contoh CLI Python
- README.md

## Kontribusi
Kontribusi sangat disambut:
- Perbaikan UI/UX web app
- Menambahkan validasi persentase / normalisasi otomatis
- Dukungan rounding/format angka, penghitungan berat (mg/g) jika diperlukan
- Menambahkan test unit untuk skrip Python

Silakan buat pull request atau buka issue jika ada fitur yang diinginkan.

## Lisensi
MIT — lihat file `LICENSE` untuk detail.
