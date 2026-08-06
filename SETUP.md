# Setup — Profile README `hgnhao`

Catatan teknis buat maintain README ini. File ini boleh dihapus kalau nggak perlu.

---

## Status

| Bagian | Status |
|---|---|
| Banner GIF | ✅ `assets/funny-man-gif-funny-man.gif` (498×212) |
| Spotify Recently Played | ⏳ **butuh authorize sekali** — lihat bagian Spotify |
| Letterboxd Recently Watched | ✅ auto dari RSS `letterboxd.com/hgnhao/rss/` |
| Skillicons / Badges / Typing SVG / Footer | ✅ semua 200 OK |
| GitHub Stats card | ⚠️ instance publik lagi 503, lihat bagian bawah |

---

## Push

```bash
cd "C:\Users\kefas\OneDrive\Documents\Coding\Personal\hgnhao"
git add .
git commit -m "feat: star wars themed profile readme"
git push
```

Repo `hgnhao/hgnhao` harus **public** biar README-nya muncul di halaman profil.

---

## Spotify 🎧 — ADA 1 LANGKAH YANG HARUS KAMU KERJAIN

README sekarang pakai [JeffreyCA/spotify-recently-played-readme](https://github.com/JeffreyCA/spotify-recently-played-readme) — nampilin **5 lagu terakhir** yang kamu putar.

**Kenapa ganti servis:** kartu kittinan yang lama secara teknis nggak bisa nampilin recently played. Label yang dia punya cuma `Now playing on Spotify`, `Currently not playing`, dan `Offline` — semuanya hardcoded di servisnya, nggak ada parameter buat ganti mode.

### Yang harus kamu lakuin

1. Buka **https://spotify-recently-played-readme.vercel.app/**
2. Klik authorize → login pakai akun Spotify `hgnhao` → Agree
3. Selesai. Kartunya langsung jalan, nggak ada uid yang perlu ditempel.

**Sebelum kamu authorize, kartunya nampilin tulisan "Spotify authorization needed".** Ini normal, bukan bug.

Parameter yang ada: `user`, `count` (1–10, sekarang 5), `width` (300–1000, sekarang 600), `unique` (true = skip lagu yang diulang).

### Kalau nggak jalan

Di `README.md` section 🎧 sudah saya siapin blok fallback dalam HTML comment — kartu "Now Playing" kittinan pakai uid kamu (`433u3...`), yang **sudah terverifikasi jalan**. Tinggal hapus blok `<a>` yang aktif, uncomment yang di komentar.

Bedanya: fallback nampilin lagu yang lagi diputar (atau lagu terakhir kalau offline, karena `show_offline=true`), bukan daftar 5 lagu.

---

## Letterboxd 🎬

Servisnya [nikitalpopov/letterboxd-profile](https://github.com/nikitalpopov/letterboxd-profile), baca RSS publik. Nggak ada API key, nggak ada yang expired.

Format lain: `/api/svg/hgnhao` (dipakai sekarang), `/api/png/hgnhao`, `/api/html/hgnhao`.

Syarat: profil Letterboxd harus **public**.

---

## Ganti GIF

GIF sekarang 498×212 (1.7 MB), dirender di `width="500"` — ukuran aslinya, jadi tajam. Kalau ganti GIF yang lebih besar, sesuaikan angka `width` di baris pertama README, atau pakai `width="100%"` kalau GIF-nya lebar (≥800px).

Batas aman ukuran file: **< 5 MB**, di atas itu GitHub sering nolak render.

---

## ⚠️ GitHub Stats card

Instance publik `github-readme-stats.vercel.app` balikin **503 (over quota)** waktu saya tes. Ini normal dan biasanya pulih sendiri — servisnya dipakai jutaan repo.

Kalau kartunya nggak muncul dan kamu mau yang permanen, deploy sendiri (gratis, ~5 menit):

1. Fork https://github.com/anuraghazra/github-readme-stats
2. Import hasil fork ke [vercel.com](https://vercel.com)
3. Tambah env var `PAT_1` = GitHub personal access token (scope `public_repo` cukup)
4. Deploy, lalu replace semua `github-readme-stats.vercel.app` di README jadi domain Vercel kamu

Kalau nggak mau ribet, hapus aja seluruh section `## 📊 GitHub Stats`.

> Catatan: widget streak (current/longest streak) dan contribution graph sudah dihapus atas permintaan, jadi section ini sekarang cuma berisi Stats card + Top Languages — dua-duanya dari servis yang lagi 503 itu. Artinya kalau servisnya nggak pulih, **seluruh** section ini kosong.
