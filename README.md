# Sakura Event

Sistem informasi utang usaha dan reimbursement karyawan untuk Sakura Event Organizer.

## Struktur

- `frontend/index.html`, `style.css`, `script.js`: antarmuka web desktop.
- `frontend/api.js`: penghubung frontend ke API backend.
- `backend/app.js`: server Express dan API Supabase.
- `backend/database.sql`: ERD PostgreSQL Supabase dengan tepat 3 entitas.

## Menjalankan

Pastikan Node.js sudah terpasang, kemudian jalankan dari folder proyek:

```powershell
npm.cmd install --no-save --no-package-lock express @supabase/supabase-js
node backend/app.js
```

Buka `http://localhost:3000`. Jalankan isi `backend/database.sql` di Supabase SQL Editor jika tabel belum tersedia.

Folder `node_modules` tidak disertakan di GitHub. Dependency dapat dipasang kembali menggunakan perintah di atas; proyek ini tidak menggunakan `package.json`.

## GitHub Pages

Di repository GitHub, buka **Settings → Pages**. Pilih **Deploy from a branch**, pilih branch `main` dan folder `/(root)`, lalu simpan. File root `index.html` akan meneruskan pengunjung ke `frontend/index.html`.

GitHub Pages hanya menjalankan frontend statis, bukan Express. Karena itu halaman Pages memakai Supabase JS dan publishable key langsung dari browser. Publishable key memang dirancang untuk frontend; keamanan data harus diatur melalui Row Level Security (RLS) di Supabase. Jangan masukkan service-role key ke file frontend.

Setelah mengubah file, lakukan commit dan push ke branch yang dipilih pada pengaturan Pages, lalu tunggu deployment selesai di tab **Actions**.
