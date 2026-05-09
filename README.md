# Aplikasi Pencarian Kontak (Google Spreadsheet)

Aplikasi web sederhana untuk mencari data berdasarkan **nomor kontak** dari 2 sheet Google Spreadsheet:
- `DB1`
- `DB2`

Output yang ditampilkan:
- ID
- nomor kontak
- kode kontak
- asal sheet (`DB1` / `DB2`)

## Cara pakai

1. Buka file `index.html`.
2. Ganti nilai:

```js
const SPREADSHEET_ID = "GANTI_DENGAN_SPREADSHEET_ID";
```

3. Pastikan spreadsheet bisa diakses publik (minimal _viewer_).
4. Jalankan lokal (contoh):

```bash
python3 -m http.server 8080
```

5. Buka `http://localhost:8080`.

## Catatan

- Pencarian dilakukan berdasarkan kolom **nomor kontak** (Kolom B).
- DB2 yang terus bertambah akan ikut terbaca saat halaman direfresh.
