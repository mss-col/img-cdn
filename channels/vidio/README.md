# channels/vidio/ — logo rasmi Vidio (batch 2)

57 logo saluran Vidio, dibuang latar + dipotong alfa, kanvas **190x80** (sama
seperti `channels/starhub/` dan `channels/mewatch/`).

## Kenapa folder sendiri

57 nama fail ini bertindih nama fail dalam `channels/` yang mungkin dipakai
saluran lain. Namespace sendiri = **sifar fail sedia ada ditimpa**, dan jelas
dari mana ia datang.

## Sumber — ⚠ JANGAN guna medan `logo`

API Vidio memberi DUA medan imej:

| Medan | Bentuk | Guna? |
|---|---|---|
| `logo` | thumbnail promosi **16:9** (830x466 / 640x360) | ❌ foto/banner, bukan logo |
| `square_image` | imej segi empat **1:1** (160–2835 px) | ✅ logo saluran sebenar |

`square_image` ialah logo saluran bersih (SCTV, INDOSIAR, RCTI, TRANS 7 …).
Medan `logo` ialah gambar promosi penuh — 64/71 daripadanya "sibuk" (bukan
logo). Playlist sebelum ini menggunakan medan `logo`, jadi ia memaparkan gambar
promosi sebagai `tvg-logo`.

⚠ **57/71 sahaja** ada `square_image`. 14 yang tiada semuanya kategori `event`
(Asian Games, tenis ATP, Champions Fight, Citra Plus) — halaman Vidio mereka
hanya menyediakan thumbnail 16:9. Tidak ditemui sumber segi empat; dikecualikan.

## Proses

1. Ambil `square_image` dari `data/vidio_mapping_worker.json` (repo `vidio-rnd`).
2. Potong ikut **alfa**; kalau tiada alfa berguna, potong ikut **beza lawan warna
   sudut** (banyak logo Vidio latar penuh, bukan lutsinar).
3. Skala ke kanvas 190x80, pusatkan.

Skrip semak: `~/.hermes/skills/media/astro-rnd/scripts/semak_logo_vidio.py`
(sahkan URL img-cdn hidup + md5 + provenance `square_image`).
