# UndanganKu — Undangan Digital Pernikahan

Platform undangan digital pernikahan elegan dengan 3 tema premium, builder interaktif, dan integrasi Telegram bot untuk manajemen order.

## Fitur

- **3 Tema Premium** — Royal Classic, Sunset Bloom, Adat Jawa
- **Builder Interaktif** — Form 5 langkah untuk buat undangan tanpa coding
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
- `POST /rsvp` — Kirim RSVP
- `GET /rsvp/:orderId` — Ambil daftar RSVP

## Paket Harga

| Paket | Harga | Durasi | Fitur Tambahan |
|-------|-------|--------|----------------|
| Standard | Rp 29.000 | 3 bulan | Semua fitur dasar |
| Premium | Rp 49.000 | 6 bulan | + Galeri foto, Love Story, revisi 1x |

## Tech Stack

- HTML/CSS/JS murni (vanilla, tanpa framework)
- Google Fonts (Cormorant Garamond, Allura, Cinzel, Caveat, Playfair Display, Inter)
- Cloudflare Workers (backend API)
- Telegram Bot (notifikasi order)

## Lisensi

Hak Cipta Daksara. All rights reserved.
