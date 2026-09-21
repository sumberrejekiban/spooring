# Panduan Landing Page — Paket Spooring & Balancing
### Sumber Rejeki Ban Solo

Isi folder ini:
- `index.html`  → halaman landing page (nama sudah `index.html` supaya langsung jalan di GitHub Pages)
- `og-image.png` → gambar preview saat link di-share ke WhatsApp / Facebook
- `PANDUAN.md`  → file ini

---

## LANGKAH 1 — Isi ID Tracking (WAJIB sebelum publish)
Buka `index.html` dengan Notepad / VS Code, cari lalu ganti:

| Cari teks ini            | Ganti dengan                          | Muncul |
|--------------------------|---------------------------------------|--------|
| `G-XXXXXXXXXX`           | GA4 Measurement ID Bapak (mis. `G-AB12CD34`) | 2x |
| `000000000000000`        | Meta/Facebook Pixel ID Bapak          | 3x |

- GA4 ID: Google Analytics → Admin → Data Streams → salin "Measurement ID".
- Meta Pixel ID: Meta Events Manager → pilih Pixel → salin ID (angka panjang).

> Kalau belum punya, halaman tetap jalan normal — cuma datanya belum kekumpul.

---

## LANGKAH 2 — (Opsional) Ubah harga / cabang
Semua ada di bagian bawah `index.html` di dalam `<script>`:

- **Harga paket** → cari `const PACKAGES` — ubah `harga`, `hargaLama`, isi paket, dll.
- **Data cabang** → cari `const BRANCHES` — ubah alamat, telepon, link Maps.
- **Nomor WhatsApp** → cari `const WA_NOMOR` (sekarang `628111513989`).
  Format: 62 di depan, tanpa 0, tanpa spasi/strip.

Simpan file setelah edit.

---

## LANGKAH 3 — Upload ke GitHub Pages
1. Buat repository baru di GitHub, mis. `spooring`.
2. Upload **ketiga file** (`index.html`, `og-image.png`, `PANDUAN.md`) ke repo.
3. Settings → Pages → Source: `Deploy from a branch` → Branch: `main` / folder `/root` → Save.
4. Tunggu 1–2 menit. Alamat jadi: `https://NAMAUSER.github.io/spooring/`

---

## LANGKAH 4 — Perbaiki preview share (og:image)
Supaya thumbnail muncul cakep di WhatsApp & Facebook, buka `index.html`,
cari 2 baris ini lalu isi dengan URL LENGKAP GitHub Pages Bapak:

```
<meta property="og:url"   content="">
<meta property="og:image" content="og-image.png">
```
ganti jadi (contoh):
```
<meta property="og:url"   content="https://NAMAUSER.github.io/spooring/">
<meta property="og:image" content="https://NAMAUSER.github.io/spooring/og-image.png">
```
Juga baris `twitter:image`. WhatsApp/Facebook butuh URL penuh, bukan `og-image.png` saja.

Tes preview: https://developers.facebook.com/tools/debug/  (tempel URL → Scrape Again)

---

## LANGKAH 5 — Set Conversion untuk Iklan
Tombol WhatsApp & Telepon sudah otomatis kirim event:
- Klik **WhatsApp** → event **`Lead`** (Meta) / **`generate_lead`** (GA4)
- Klik **Telepon** → event **`Contact`** (Meta) / **`contact`** (GA4)

**Meta Ads:** Events Manager → jadikan `Lead` sebagai *conversion event* → pakai sebagai tujuan iklan.
**Google Ads:** import conversion dari GA4 event `generate_lead`.

---

## Cek cepat sebelum iklan jalan
- [ ] GA4 & Pixel ID sudah diganti
- [ ] Buka halaman di HP → tombol WA membuka chat dengan pesan booking terisi
- [ ] Link Maps tiap cabang benar
- [ ] og:url & og:image sudah URL penuh, preview WA sudah muncul
- [ ] Harga paket sudah sesuai

Ada yang perlu diubah, tinggal kabari — bisa saya sesuaikan.
