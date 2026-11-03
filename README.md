# Toko Bahagia — Frontend Vercel

Tampilan toko & admin di Vercel. Data, keamanan, harga, dan QRIS tetap diproses
oleh Google Apps Script (backend) yang alamatnya ada di `config.js`.

| File | Isi |
|---|---|
| `index.html` | Toko pembeli → `https://toko-bahagia.vercel.app/` |
| `admin.html` | Panel admin → `https://toko-bahagia.vercel.app/admin` |
| `config.js` | Alamat Web App Apps Script (`.../exec`) |
| `vercel.json` | URL bersih + header keamanan (CSP, anti-iframe, HSTS) |
| `robots.txt` | Halaman admin tidak diindeks mesin pencari |

## Bila deployment Apps Script berganti URL
Edit `config.js` → ganti nilai `api` dengan URL `/exec` yang baru → commit. Vercel otomatis deploy ulang.

## Catatan keamanan
- Tidak ada kunci rahasia di repo ini. Semua validasi ada di server Apps Script.
- Sesi admin disimpan di sessionStorage (hilang saat tab ditutup).
