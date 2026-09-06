# WebToAPK — Deploy Guide

Convert website ke APK Android gratis via PWABuilder API.

## Struktur File

```
/
├── index.html       ← Aplikasi utama (semua dalam 1 file)
├── manifest.json    ← PWA manifest untuk app ini sendiri
├── netlify.toml     ← Konfigurasi Netlify
└── README.md
```

## Cara Deploy ke Netlify

### Opsi 1: Drag & Drop (termudah)
1. Buka [netlify.com/drop](https://app.netlify.com/drop)
2. Drag folder ini ke halaman
3. Selesai! URL langsung aktif

### Opsi 2: GitHub + Netlify (auto-deploy)
1. Upload folder ini ke GitHub repo baru
2. Buka [netlify.com](https://netlify.com) → New site from Git
3. Pilih repo → Deploy site
4. Setiap push ke GitHub otomatis deploy ulang

### Opsi 3: Netlify CLI
```bash
npm install -g netlify-cli
netlify deploy --prod --dir .
```

## Cara Pakai App

1. Buka URL Netlify kamu
2. Isi URL website yang mau dikonversi
3. Isi nama app, package name (format: com.nama.app)
4. Upload icon (opsional), pilih warna tema & splash
5. Klik **Build APK Sekarang**
6. Download atau buka PWABuilder untuk finalisasi

## Catatan

- Website harus HTTPS agar TWA bisa bekerja
- Package name format: `com.namaapp.sesuatu` (huruf kecil semua)
- PWABuilder API kadang memerlukan website yang sudah punya manifest.json
- Jika build otomatis gagal, app otomatis redirect ke PWABuilder dengan URL sudah terisi

## Teknologi

- **Frontend**: Pure HTML/CSS/JS (single file)
- **Build engine**: PWABuilder API (Microsoft, gratis)
- **Output**: Android APK via TWA (Trusted Web Activity)
- **Deploy**: Netlify (gratis tier cukup)
