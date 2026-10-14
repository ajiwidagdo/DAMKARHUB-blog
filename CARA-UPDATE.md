# CARA UPDATE BLOG DAMKARHUB

Blog: Hugo + GitHub Pages — setiap push ke branch `main` otomatis di-build & deploy (±1–2 menit).

## Tambah artikel baru

1. Buat file markdown baru di `content/artikel/`, contoh `content/artikel/judul-artikel.md`:

```markdown
---
title: "Judul Artikel"
date: 2026-10-15T08:00:00+07:00
draft: false
tags: ["Edukasi"]
summary: "Satu kalimat ringkasan artikel."
---

Isi artikel di sini (Markdown)...
```

2. Commit & push:

```bash
cd ~/workspace/blog-damkarhub
git add content/artikel/judul-artikel.md
git commit -m "artikel baru: judul artikel"
git push origin main
```

3. GitHub Actions otomatis build + deploy. Cek status di tab **Actions** repo.

## Edit / hapus artikel

- Edit file `.md`-nya → commit → push. Sama seperti di atas.
- Hapus: `git rm content/artikel/nama-file.md` → commit → push.

## Struktur penting

- `content/artikel/` — semua artikel
- `content/tentang/_index.md` — halaman Tentang
- `hugo.yaml` — konfigurasi (judul, menu, bahasa)
- `assets/css/extended/damkar.css` — aksen warna merah api
- `themes/PaperMod/` — theme (jangan diedit langsung; override via `layouts/` bila perlu)

## Setup awal (sudah dilakukan 14 Okt 2026)

- [x] Hugo v0.168.0 extended
- [x] Theme PaperMod
- [x] 4 artikel + halaman Tentang
- [x] Workflow GitHub Actions (`.github/workflows/hugo.yaml`)
- [ ] **FOLLOW-UP: repo `ajiwidagdo/damkarhub-blog` belum dibuat** — PAT tidak punya izin create repo. Mas Bos: buat repo **public** bernama `damkarhub-blog` di github.com/new (tanpa README/license), lalu beri tahu Santuy untuk push + aktifkan Pages. Atau berikan PAT dengan izin pembuatan repo.
- [ ] Push source ke `main` (setelah repo dibuat)
- [ ] Aktifkan Pages: Settings → Pages → Source: **GitHub Actions**
