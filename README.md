# MODUL 2 — Saat Perkataan, Pikiran, dan Perbuatan Harus Selaras

Modul pembelajaran interaktif PUSDIKLAT BAZNAS RI, hasil ekspor HTML5 dari
Articulate Storyline. Repositori ini hanya berisi berkas statis hasil ekspor
tersebut, apa adanya.

## Kenapa dihosting terpisah

Modul interaktif seperti ini berisi JavaScript dalam jumlah besar. Saat
diunggah lewat domain Z-Learning, sebagian berkasnya ditolak oleh pemeriksa
keamanan di depan layanan karena polanya menyerupai muatan berbahaya —
padahal isinya sah. Menghostingnya terpisah menghindari persoalan itu,
sekaligus memberi isolasi yang lebih tegas: modul berjalan di origin sendiri
dan tidak bisa menyentuh sesi peserta di Z-Learning.

## Menjalankan secara lokal

Butuh peladen statis; membuka `story.html` langsung lewat `file://` tidak
bekerja karena peramban memblokir pemuatan antar-berkasnya.

```bash
python3 -m http.server 4100
# lalu buka http://localhost:4100/story.html
```

## Deploy ke Vercel

1. Buat project baru di Vercel, hubungkan ke repositori ini.
2. Framework Preset: **Other**. Build command dan output directory dikosongkan
   — tidak ada yang perlu dibangun.
3. Setelah deploy selesai, salin domainnya.

## Menautkannya di Z-Learning

Pada form materi, pilih tipe **Paket**, lalu tempel alamat hasil deploy pada
kolom *Alamat Paket yang Dihosting Sendiri*.

## Catatan

- Peluncurnya **`story.html`**, bukan `index.html`. `vercel.json` di repositori
  ini mengarahkan alamat akar ke sana, jadi domain polos pun langsung terbuka.
- `analytics-frame.html` di akar **bukan** peluncur. Ia bingkai pelacakan, dan
  membukanya hanya menampilkan halaman kosong.
