# channels/vidio/ — logo rasmi Vidio (batch 2)

57 logo saluran Vidio, dibuang latar + dipotong alfa.

⚠⚠ **KANVAS 190x110, bukan 190x80** (2026-09-25).

47 daripada 57 logo ini ialah **CAKERA** (seni bulat dari sumber Vidio sendiri,
liputan 78-79%). Pada kanvas 190x80 nisbah 2.375 lebih lebar daripada sel app
(**195x111**, nisbah 1.76 yang diukur pada tangkapan skrin), jadi app
memperkecilkannya: cakera 80px muncul sebagai **82px** sahaja.

Pada kanvas **190x110** (nisbah 1.727), app guna tinggi penuh → cakera muncul
**111px** — had maksimum sel 16:9, dan kini SAMA tinggi dengan imej event 16:9.

| | 190x80 | 190x110 |
|---|---|---|
| Cakera di app | 82px | **111px (+35%)** |
| Wordmark di app | tidak berubah | **tidak berubah (fail sama)** |

⚠ 10 saluran BUKAN cakera (nama memanjang / kad putih) **tidak disentuh langsung**
— failnya bait-identik. Hanya 47 cakera dijana semula, dan ia diambil dari seni
SUMBER penuh (240-2835px), bukan dibesarkan dari fail 80px (itu jadi kabur).

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
3. Skala ke kanvas **190x110**, pusatkan.
   - **Cakera** (segi empat sama, sudut kotak lutsinar, liputan 68-88%): isi
     tinggi penuh (110px).
   - **Bukan cakera**: biarkan fail sedia ada — jangan jana semula (pemangkasan
     latar putih mudah rosak).
   - ⚠ Elak bbox alfa **mentah** (gagal bila cakera menyentuh tepi saiz rendah).

Skrip semak: `~/.hermes/skills/media/astro-rnd/scripts/semak_logo_vidio.py`
(sahkan URL img-cdn hidup + md5 + provenance `square_image`).
