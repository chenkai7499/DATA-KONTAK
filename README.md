# Aplikasi Pencarian Kontak (Google Spreadsheet)

Aplikasi web sederhana dan cepat untuk mencari data dari 2 sheet:
- `DB1`
- `DB2`

## Fitur

1. **Single search**
   - Cari berdasarkan **ID** atau **nomor kontak**.
2. **Bulk search**
   - Input banyak ID/nomor kontak sekaligus via textarea.
   - Pemisah input didukung:
     - Enter/newline
     - Spasi
     - Koma
3. **Output hasil**
   - ID
   - nomor kontak
   - kode kontak
   - asal sheet (`DB1` / `DB2`)
4. **Tombol**
   - `Cari`
   - `Clear / Reset`

## Aturan Pencarian

- ID: **exact match** ke kolom ID.
- Nomor kontak: **exact match** ke kolom nomor kontak setelah normalisasi angka (hapus semua selain digit).
- Auto-detect: jika token mengandung huruf `a-z`, token dianggap **ID**; token angka murni dianggap **nomor kontak**.
- Bulk input campuran ID + nomor kontak didukung dalam satu pencarian.
- Hasil gabungan akan dihapus duplikatnya.

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


## Optimasi performa

- Saat load data, aplikasi membangun index `Map` untuk ID dan nomor kontak normalisasi.
- Proses search memakai lookup map (`O(1)` rata-rata), bukan scan seluruh dataset setiap pencarian.
- Bulk search memproses token input saja, lalu menggabungkan hasil tanpa duplikat.
