# Logo rasmi StarHub — batch 1 + batch 3 (SG)

Logo rasmi daripada CDN poster StarHub — `poster.starhubgo.com/Linear_Channels2/`.

## Sumber dan cara proses

Sumber penuh ialah PNG **1920x1080** dengan logo dalam saluran alfa. Setiap fail
diproses: **potong ikut alfa** (buang kanvas kosong), kemudian **skala tinggi 80px**
dan letak di tengah kanvas 190x80 lutsinar — selaras sel logo lain dalam koleksi.

⚠ `?w=N` pada URL sumber membuang saluran alfa (latar jadi pepejal), jadi ia
**tidak** boleh dipakai terus sebagai logo. Ambil PNG penuh, potong sendiri.

## Kenapa folder sendiri

Sebelum ini logo StarHub dicampur dalam `channels/` bersama logo provider lain,
dan 33 nama daripada batch ini **bertindih** nama fail sedia ada yang dipakai
entri Astro (`hits_hd.png`, `cnn_hd.png`, `ktv_hd.png` …). Menimpa fail itu akan
tukar logo saluran Astro. Namespace `channels/starhub/` mengelak semua itu.

## Liputan

| | |
|---|---|
| Saluran `tvg-id="*.starhub"` | 108 entri → 107 rekod (batch 1) |
| Saluran MediaCorp gerbang `starhubtv/go` (`tvg-id` MEWATCH) | 5 entri → **5 rekod (batch 3)** |
| **Fail PNG** | **111** (112 rekod; `222.starhub` bawa 2 nama) |
| Tiada logo rasmi | 1 — `998.starhub` ("Test 998") |

### Batch 3 — saluran MediaCorp (2026-09-25)

Lima saluran StarHub SG yang memakai gerbang `starhubtv/go` tetapi `tvg-id`
**MEWATCH**: Channel 8 HD, Channel U HD, Suria HD, Vasantham HD, Channel News
Asia HD. Batch 1 tidak menutup mereka kerana gerbangnya `tvg-id` berakhir
`.starhub`.

Sumbernya dahulu **repo GitHub pihak ketiga** — `raw.githubusercontent.com/FlyinDVB/star/main/`
(341x192). Poster rasmi StarHub `103`–`107` (1920x1080) memberi kualiti lebih
tinggi, reka bentuk sama.

⚠ `998.starhub` dipetakan ke aliran `sg_mediacorp_ch5_dash` (sama seperti Channel 5);
logo asalnya `Linear_channnes/falseNE` **404** dalam playlist hidup.

## `_peta.json`

⚠ **Kunci BUKAN sentiasa `tvg-id`.**

| Entri | Kunci | Sebab |
|---|---|---|
| Batch 1 | `tvg-id` | normal |
| `222.starhub` | `tvg-id\|nama` | `tvg-id` itu membawa **DUA** saluran (Hub Premier 2 4K + (HD)) — satu kunci akan menelan satu |
| Batch 3 | **slug gerbang** | `tvg-id` mereka **MEWATCH** (`2.mewatch`–`6.mewatch`); berkunci tvg-id akan berlanggar dgn logo mewatch |

⚠ `222.starhub` — **satu poster sahaja** (`222`). Kedua-dua entri memang berkongsi
imej yang sama (CDN StarHub dan mapping DS01 kedua-duanya begitu). Kunci berasingan
kekal supaya maklumat dua saluran tidak hilang.

Peta `tvg-id` → fail, dengan `num` (nombor poster sumber), `logo` (saiz selepas
potong) dan `md5`. Dipakai untuk menjana semula `data/starhub_logo.json`
dalam repo `astro-rnd`.
