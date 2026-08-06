# Setup — Profile README `hgnhao`

Catatan teknis buat maintain README ini. File ini boleh dihapus kalau nggak perlu.

---

## Status

| Bagian | Status |
|---|---|
| Banner GIF | ✅ `assets/funny-man-gif-funny-man.gif` (498×212) |
| Spotify Now Playing | ✅ uid `433u3cfkqmvawbehz0k5eyvnm` — sudah ditest, render "Now playing" |
| Letterboxd Recently Watched | ✅ auto dari RSS `letterboxd.com/hgnhao/rss/` |
| Streak / Activity graph / Skillicons / Badges | ✅ semua 200 OK |
| GitHub Stats card | ⚠️ instance publik lagi 503, lihat bagian bawah |

**Nggak ada placeholder yang tersisa** — tinggal commit & push.

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

## Spotify 🎧

Pakai [kittinan/spotify-github-profile](https://github.com/kittinan/spotify-github-profile). uid kamu sudah terpasang.

Dua hal yang saya ubah dari snippet yang kamu dapat:

- `show_offline=false` → **`true`** — biar pas Spotify lagi mati kartunya nampilin lagu terakhir, bukan kosong/rusak
- `background_color=121212` → **`0d1117`** — nyamain sama background dark mode GitHub, jadi kartunya nyatu

Tema lain yang bisa dicoba di `theme=`: `default` (sekarang), `compact`, `novatorem`, `karaoke`, `natemoo-re`, `blur`.

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

Kalau nggak mau ribet, hapus aja 2 baris `<img>` pertama di section `## 📊 GitHub Stats` — streak & activity graph pakai servis lain yang lagi sehat.
