# UndanganKu — Undangan Digital Pernikahan

Platform undangan digital pernikahan elegan dengan 3 tema premium, builder interaktif, dan integrasi Telegram bot untuk manajemen order.

## Fitur

- **3 Tema Premium** — Royal Classic, Sunset Bloom, Adat Jawa
- **Foto Couple di Cover** — Pembeli bisa unggah foto untuk halaman depan undangan (dikompres otomatis di browser)
- **Builder Interaktif** — Form 3 langkah untuk buat undangan tanpa coding
- **RSVP & Ucapan** — Tamu konfirmasi kehadiran + kirim ucapan langsung
- **Countdown** — Hitung mundur otomatis ke hari H
- **Amplop Digital** — Nomor rekening tampil rapi + tombol salin
- **Musik Background** — Auto-play saat undangan dibuka
- **Google Maps** — Link lokasi akad & resepsi
- **Preview Real-time** — Lihat hasil undangan sebelum memesan
- **Order via Telegram Bot** — Notifikasi otomatis ke owner

## Struktur File

```
undanganku-web/
├── index.html          # Landing page / homepage
├── builder.html        # Builder form (5 steps)
├── undangan-render.html # Router — redirect ke tema berdasarkan data
├── tema-royal.html     # Tema: Royal Classic (midnight sapphire, platinum, mewah)
├── tema-bloom.html     # Tema: Sunset Bloom (warm, peach, romantic)
├── tema-jawa.html      # Tema: Adat Jawa (maroon, klasik, tradisional)
├── favicon.svg         # SVG favicon
├── music/
│   └── romantic.mp3    # Background music default
└── README.md
```

## Cara Deploy

1. **Vercel / Netlify** — Push ke GitHub, connect repo, deploy otomatis (static site).
2. **Manual** — Upload semua file ke hosting static (tidak perlu server/backend).

## Backend (Cloudflare Worker)

Aplikasi ini terhubung ke Telegram Bot API di:
```
https://telegram-bot.daksara-dev.workers.dev
```

Endpoint yang digunakan:
- `POST /orders/new` — Buat order baru
- `GET /orders/status/:id` — Cek status pembayaran
- `GET /orders/data/:id` — Ambil data undangan
- `GET /u/:id` — Render undangan langsung (static HTML)
- `POST /orders/rsvp/:id` — Kirim RSVP
- `GET /orders/rsvp/:id` — Ambil daftar RSVP

## Harga

| Paket | Harga | Durasi | Fitur |
|-------|-------|--------|-------|
| Lengkap | Rp 5.000 (harga perilisan, anchor Rp 249.000) | 3 bulan | Semua fitur, termasuk foto couple di cover |

Harga flat dalam Rupiah — tidak ada lagi harga live mengikuti kurs dolar.

## Tech Stack

- HTML/CSS/JS murni (vanilla, tanpa framework)
- Google Fonts (Cormorant Garamond, Allura, Cinzel, Caveat, Playfair Display, Inter)
- Cloudflare Workers (backend API)
- Telegram Bot (notifikasi order)

## Lisensi

Hak Cipta Daksara. All rights reserved.
