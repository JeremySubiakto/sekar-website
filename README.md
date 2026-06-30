# Sekar — Website

Landing page satu halaman untuk **Sekar**, layanan pendamping pemakaman di Solo.
Situs statis murni: HTML + CSS + sedikit JS, dua font Google (Cormorant Garamond + Inter), tanpa proses build.

**Dwibahasa (ID / EN).** Ada tombol bahasa di navbar. Default Bahasa Indonesia; pilihan
tersimpan di browser (localStorage). Seluruh teks ada di satu kamus di dalam `<script>` pada
`index.html` (objek `I18N`) — ubah di situ untuk menyunting salinan teks. Tanpa JavaScript,
halaman tetap tampil penuh dalam Bahasa Indonesia.

## Struktur

```
sekar/
├─ index.html        # halaman utama
├─ styles.css        # seluruh gaya (dipisah dari HTML)
├─ assets/
│  ├─ favicon.svg / favicon.png   # mark melati (ikon browser)
│  ├─ apple-touch-icon.png        # ikon iOS (180×180)
│  ├─ icon-512.png                # ikon PWA (512×512)
│  ├─ logo.png / footer-logo.png  # mark melati untuk navbar & footer
│  ├─ lockup-dark.svg / -dark-en.svg     # lockup "Sekar" untuk latar gelap (hero) — ID/EN
│  ├─ lockup-light.svg / -light-en.svg   # lockup "Sekar" untuk latar terang (tentang) — ID/EN
│  └─ og-image.png                # gambar share WhatsApp/Facebook (1200×630)
├─ netlify.toml      # konfigurasi deploy Netlify
├─ vercel.json       # konfigurasi deploy Vercel
├─ robots.txt
└─ sitemap.xml
```

## Pratinjau lokal

Dari dalam folder `sekar/`:

```bash
npx serve .
# atau
python -m http.server 8000
```

Lalu buka alamat yang ditampilkan (mis. `http://localhost:8000`).

## ⚠️ Sebelum dipublikasikan — wajib diganti

1. **Nomor WhatsApp & telepon.** Saat ini masih placeholder `6287771111177` (tampil `+62 877-7111-1177`).
   Cara termudah: cari-ganti **semua** `6287771111177` → nomor asli, dan `+62 877-7111-1177`
   → nomor tampil, di `index.html`. (Tautan WhatsApp dibangun dari satu konstanta `WA_NUMBER`
   di dalam `<script>`; sisanya adalah cadangan tanpa-JS + nomor yang ditampilkan di footer.)
   Format `wa.me`: kode negara tanpa `+` dan tanpa `0` depan, contoh `62812xxxxxxx`.
2. **Domain.** Ganti `https://sekarfuneral.com` dengan domain asli di: `index.html` (canonical + Open Graph),
   `robots.txt`, dan `sitemap.xml`. Tanpa domain yang benar, gambar preview WhatsApp tidak muncul.
3. **Harga paket** (`index.html`): Rp 17,5 jt / Rp 32 jt / Rp 45 jt — sesuaikan jika berubah.
4. **Alamat & jam** di footer, bila ingin lebih spesifik.

## Deploy (pilih satu)

### Netlify — paling cepat
- Buka **app.netlify.com → Add new site → Deploy manually**, seret folder `sekar/` ke area drop. Selesai.
- Atau via CLI: `npm i -g netlify-cli` lalu `netlify deploy --prod` dari dalam folder.

### Vercel
```bash
npm i -g vercel
vercel        # ikuti prompt, lalu `vercel --prod`
```

### GitHub Pages
Push isi folder ke sebuah repo, aktifkan **Settings → Pages → branch `main` / root**.

### Domain
Beli `sekarfuneral.com` atau `sekar.id`, lalu arahkan DNS-nya ke Netlify/Vercel
(ikuti panduan domain di dashboard masing-masing). Setelah domain aktif, ulangi langkah **#2** di atas.
