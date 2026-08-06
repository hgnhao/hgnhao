# Setup — Profile README `hgnhao`

Catatan teknis buat maintain README ini. File ini boleh dihapus kalau nggak perlu.

---

## Status

| Bagian | Status |
|---|---|
| Banner GIF | ✅ `assets/funny-man-gif-funny-man.gif` (498×212) |
| Spotify Recently Played | ✅ sudah diauthorize, render 5 lagu asli |
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

Sudah diauthorize dan sudah jalan.

> ⚠️ **Penting:** parameter `user` diisi **uid Spotify** (`433u3cfkqmvawbehz0k5eyvnm`), **bukan** username `hgnhao`. Awalnya saya isi `hgnhao` dan hasilnya "Spotify authorization needed" — uid-nya kelihatan di halaman generator setelah authorize.

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

## Badge visitor counter

Warna teks badge **tidak bisa diubah**. komarev hardcode `fill="#fff"` buat label maupun angkanya, dan cuma nerima parameter: `username`, `color`, `style`, `label`, `base`, `abbreviated`. Saya cek dua alternatif — shields.io dan hits.sh — dua-duanya juga hardcode `fill="#fff"`.

Jadi kontras diperbaiki dari sisi background: `color=FFE81F` → **`0d1117`**, jadi teks putihnya kebaca jelas dan nyatu sama dark theme.

> Badge **Portfolio** di header punya masalah yang sama (teks putih di atas kuning `FFE81F`). Belum saya ubah karena kamu nggak minta — bilang aja kalau mau dijadiin dark juga.

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
