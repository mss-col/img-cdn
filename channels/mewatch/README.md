# Logo saluran Mewatch (Mediacorp SG)

Logo rasmi bagi 26 saluran Mewatch yang dipakai dalam playlist OTT-1V2 dan
ABG-OTT-V2.

## Kenapa folder sendiri

Koleksi utama `channels/` sudah ada 377 fail. Folder ini diasingkan supaya:

- **sifar tindih** — tidak menyentuh fail sedia ada (termasuk `cna_sg.png`,
  `live_5_sg.png`, `live_6_sg.png`, `live_2_sg.png` yang masih dipakai di
  tempat lain, dan **berbentuk segi empat** — gaya lama yang salah)
- **sifar konflik cache** — nama fail baharu, jadi tepi jsDelivr tidak boleh
  menghidangkan imej lama (lihat nota cache di bawah)
- **jelas asalnya** — jelas apa itu dan dari mana datangnya

## Sumber

Medan `images.logo` daripada halaman saluran:

```
https://www.mewatch.sg/channels/<eid>
```

⚠ **Bukan** medan `images.square` (1024x1024, karya tile app) — itulah yang
menyebabkan 23/26 saluran salah sebelum ini.

⚠ Grid `https://www.mewatch.sg/channel-guide` **bukan** sumber penuh: ia hanya
menyenaraikan 24 saluran dan berubah ikut acara (Asian Games, FIFA U20, SPL).
11 daripada 26 saluran kita tiada di situ.

Ambil semula bila hulu tukar logo: `astro-rnd` →
`~/.hermes/skills/media/astro-rnd/scripts/semak_logo_mewatch.py`

## Nota cache jsDelivr

`cache-control: public, max-age=604800, s-maxage=43200`

Edge cache **12 jam**. Menindih nama fail yang ada bermakna perubahan **tidak
kelihatan** sehingga 12 jam — sebab itu folder ini guna nama baharu, bukan
menulis ganti di `channels/` rata.

## Senarai

| Fail | Saluran |
|---|---|
| `channel-5.png` | Channel 5 |
| `channel-8.png` | Channel 8 |
| `channel-u.png` | Channel U |
| `cna.png` | CNA |
| `suria.png` | Suria |
| `vasantham.png` | Vasantham |
| `live-1.png` | LIVE 1 |
| `live-2.png` | LIVE 2 |
| `live-5.png` | LIVE 5 |
| `live-6.png` | LIVE 6 |
| `fifa.png` | FIFA+ |
| `w-sport.png` | W-Sport |
| `trace-sport-stars.png` | TRACE Sport Stars |
| `masterchef.png` | MasterChef |
| `deal-or-no-deal.png` | Deal or No Deal |
| `fear-factor.png` | Fear Factor |
| `river-monsters.png` | River Monsters |
| `drama-hebat.png` | Drama Hebat |
| `filem-mantap.png` | Filem Mantap |
| `vijay-takkar.png` | Vijay Takkar |
| `kartoon-channel.png` | Kartoon Channel! |
| `tg-junior.png` | TG Junior |
| `action-hollywood-movies.png` | Action Hollywood Movies |
| `that-s-70s.png` | That's 70s |
| `that-s-80s.png` | That's 80s |
| `that-s-rock.png` | That's Rock |

Semua 1000x260 (nisbah 3.85:1) kecuali `cna.png` 500x259 — nisbah hampir sama.
