# Logo rasmi StarHub (batch 1)

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
| Saluran `tvg-id="*.starhub"` | 107 |
| Logo rasmi diperoleh | **106** |
| Tiada logo rasmi | 1 — `998.starhub` ("Test 998") |

⚠ `998.starhub` dipetakan ke aliran `sg_mediacorp_ch5_dash` (sama seperti Channel 5);
logo asalnya `Linear_channnes/falseNE` **404** dalam playlist hidup.

## `_peta.json`

Peta `tvg-id` → fail, dengan `num` (nombor poster sumber), `logo` (saiz selepas
potong) dan `md5`. Dipakai untuk menjana semula `data/starhub_logo.json`
dalam repo `astro-rnd`.
