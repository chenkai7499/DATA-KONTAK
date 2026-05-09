# Aplikasi Pencarian Kontak (Google Spreadsheet)

Aplikasi web sederhana dan cepat untuk mencari data dari 2 sheet:
- `DB1`
- `DB2`

## Fitur

1. **Single search**
   - Cari berdasarkan **ID** atau **nomor kontak**.
2. **Bulk search**
   - Input banyak ID/nomor kontak sekaligus via textarea.
   - Pisahkan tiap data dengan baris baru (newline).
   - Contoh:
     - `12345`
     - `12346`
     - `08123456789`
3. **Auto-detect tipe input**
   - Sistem deteksi otomatis apakah input adalah ID atau nomor kontak.
4. **Output hasil**
   - ID
   - nomor kontak
   - kode kontak
   - asal sheet (`DB1` / `DB2`)
5. **Tombol**
   - `Cari`
   - `Clear / Reset`

## Cara pakai

1. Buka file `index.html`.
2. Ganti nilai berikut dengan Spreadsheet ID Anda:

```js
const SPREADSHEET_ID = "GANTI_DENGAN_SPREADSHEET_ID";
```

3. Pastikan spreadsheet dapat diakses publik (viewer).
4. Jalankan lokal:

```bash
python3 -m http.server 8080
```

5. Buka `http://localhost:8080`.


## Aturan Pencarian

- ID: **exact match** ke kolom ID.
- Nomor kontak: **partial match** ke kolom nomor kontak.
- Bulk input campuran ID + nomor kontak didukung dalam satu pencarian.
