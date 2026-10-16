# PriceBrush — Backend

PriceBrush adalah web app (PWA, mobile-first) untuk painter & decorator di UK: jelaskan pekerjaan pakai suara atau teks, AI menyusun quote per item yang bisa diedit, kirim lewat WhatsApp atau PDF, lalu ubah jadi invoice dengan satu tap.

**Status:** tahap perencanaan. Belum ada kode.

## Ringkasan PRD

| | |
| --- | --- |
| Target user | Painter & decorator solo/berdua di UK |
| Solusi inti | Voice/teks → AI quote (bisa diedit) → link/PDF via WhatsApp → invoice satu tap |
| Target bisnis | Pembayaran pertama sebelum 31 Des 2026 |
| Harga | Free (5 dokumen/bulan) · Pro £9/bulan atau £79/tahun · Founding Member £49 seumur hidup |

## Tanggung jawab backend

**MVP (mulai 1 Nov 2026):**

- Proxy AI: audio → transkrip (Groq Whisper) → quote terstruktur (LLM). Kunci API tidak pernah ada di frontend.
- Webhook Polar: aktifkan/nonaktifkan paket Pro dalam ≤ 1 menit.
- Batas paket Free: 5 dokumen per bulan kalender.
- Link quote publik: token acak panjang, bisa dicabut; endpoint "Accept quote" (P1).
- Export CSV & hapus akun (UK GDPR).

**Q1 2027:**

- Backend Go untuk sinkronisasi dan fitur Making Tax Digital (HMRC API, fraud prevention headers). HMRC sedang menunda pendaftaran software MTD baru; kriteria baru diperkirakan awal 2027.

## Keputusan

- **15 Okt 2026:** MVP pakai **Cloudflare Workers (TypeScript)**, package manager pnpm. Backend Go ditambahkan di repo ini mulai Q1 2027.

## Rencana stack ($0)

Cloudflare Workers · Supabase (Postgres + auth) · Groq Whisper (STT) · LLM murah via API · Polar (merchant of record, urus VAT UK).

## Dokumen

- PRD lengkap: `price-brush-frontend/docs/PRD.md`
- Diagram alur & mock-up: `price-brush-frontend/docs/assets/`
