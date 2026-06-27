# AR Card — Syafrizal Amri Fajar
> WebAR Business Card · AR.js + A-Frame · Tugas Week 12

---

## Struktur Folder

```
ar-card/
├── index.html          ← AR scene utama (file ini)
├── marker.patt         ← ⚠️ HARUS kamu generate sendiri (lihat langkah 1)
├── marker.png          ← Gambar marker untuk dicetak/ditampilkan
├── README.md
└── assets/
    └── website.jpg     ← ⚠️ Screenshot syzaf.dev kamu (lihat langkah 2)
```

---

## Langkah Setup (Wajib Sebelum Demo)

### Langkah 1 — Generate Marker dari Kartu Nama

1. Buka: https://ar-js-org.github.io/AR.js/three.js/examples/marker-training/examples/generator.html
2. Upload foto `syafrizal_amri_fajar.png` (kartu nama kamu)
3. Download `marker.patt` → simpan di root folder (sejajar `index.html`)
4. Screenshot preview markernya → simpan sebagai `marker.png`

**Tips marker yang bagus:**
- Crop bagian dengan kontras tinggi (teks hitam di background terang)
- Hindari bagian yang terlalu simetris
- Jarak optimal saat demo: 20–50 cm

---

### Langkah 2 — Screenshot syzaf.dev

1. Buka browser → pergi ke https://syzaf.dev
2. Screenshot halaman utama (ukuran 1280×720px ideal)
3. Simpan sebagai `assets/website.jpg`

---

### Langkah 3 — Jalankan via HTTPS

**WAJIB HTTPS** — kamera tidak bisa diakses dari HTTP biasa atau file:///

**Opsi A: Vercel (Rekomendasi, paling mudah)**
```bash
npx vercel --prod
```

**Opsi B: GitHub Pages**
```bash
git init
git add .
git commit -m "AR Card Syafrizal"
gh repo create ar-card --public --push
# Lalu aktifkan Pages di Settings → Pages → Deploy from main
```

**Opsi C: ngrok (untuk test lokal)**
```bash
npx serve .
# Di terminal lain:
npx ngrok http 3000
# Buka URL https dari ngrok di HP
```

---

### Langkah 4 — Test Demo

1. Buka URL HTTPS dari HP (bukan laptop)
2. Tap "Mulai AR" → izinkan akses kamera
3. Siapkan `marker.png` di layar lain / print
4. Arahkan kamera ke marker → AR muncul!
5. **Tatap titik merah/emas selama 1.5 detik** → info muncul

---

## Fitur AR Card

| Fitur | Detail |
|-------|--------|
| Marker custom | Pattern dari kartu nama `syafrizal_amri_fajar.png` |
| Website preview | Screenshot syzaf.dev muncul sebagai panel 3D |
| Nama & title | Floating text di atas panel |
| 3 Hotspot gaze | About · Projects · Contact |
| Gaze navigation | Tatap 1.5 detik = klik (sesuai Week 11 & 12) |
| Info panel | Muncul di HUD saat hotspot diklik |
| Animasi ring | Dua cincin berputar berlawanan arah |
| Particle dots | 3 titik melayang dekoratif |
| Smooth tracking | Marker smooth mode aktif |

---

## Warna Brand (Guci-inspired palette)

| Nama | Hex |
|------|-----|
| Guci Red | `#C41E1E` |
| Dark Maroon | `#1C0A0A` |
| Warm Gold | `#C8A97A` |
| Cream | `#F9F3EA` |
| Dark Brown | `#3D2B1F` |

---

## Troubleshooting

| Masalah | Solusi |
|---------|--------|
| Kamera tidak muncul | Pastikan HTTPS, bukan HTTP atau file:/// |
| AR tidak muncul | Cek `marker.patt` sudah ada di root folder |
| Website preview hitam | Pastikan `assets/website.jpg` sudah ada |
| Teks tidak muncul | CDN A-Frame font perlu internet, pastikan koneksi aktif |
| Marker susah terdeteksi | Pastikan pencahayaan cukup, jarak 20–50 cm |
