# Panduan Kontribusi

Terima kasih sudah ikut mengerjakan **NO BATIDÃO**. Panduan ini untuk teman-teman yang mau mengedit data tim, mengganti foto, atau mengubah tampilan.

## Prasyarat

- [Git](https://git-scm.com/downloads)
- [Node.js 20+](https://nodejs.org) (sudah termasuk npm)
- Editor, misalnya [VS Code](https://code.visualstudio.com)

## 1. Clone repo

Minta URL repo ke pemilik, lalu:

```bash
git clone https://github.com/USERNAME/no-batidao.git
cd no-batidao
npm install
npm run dev
```

Buka <http://localhost:3000>. Halaman akan otomatis refresh setiap file disimpan.

Perintah lain:

```bash
npm run build      # build produksi
npm start          # jalankan hasil build
npm run typecheck  # cek error TypeScript
```

## 2. Di mana mengedit

| Mau ubah apa | File |
| --- | --- |
| Nama, role, team, bio, tags, links, tone | `components/team-lanyard-rail-demo.tsx` |
| Judul, eyebrow, caption, tombol CTA | `components/team-lanyard-rail-demo.tsx` (bagian `<TeamLanyardRail …>`) |
| Foto anggota | folder `public/team/` |
| Warna badge / tema | `app/globals.css` (`--chart-1` … `--chart-5`) |
| Tampilan komponen lanyard | `components/ui/team-lanyard-rail.tsx` |

### Bentuk data anggota

```tsx
{
  id: "Fathir",                 // unik, jangan disamakan dengan anggota lain
  name: "Fathir Izzakky",
  role: "Founder Batidao",
  team: "CEO",
  tone: 1,                      // 1–5, menentukan warna
  image: "/team/fathir.jpg",       // file di public/team
  bio: "Teks di balik badge",
  tags: ["CHAMBER", "Zeroks"],  // maksimal 3 yang tampil
  links: [                      // maksimal 3 yang tampil
    { label: "Email", href: "#" },
    { label: "Portfolio", href: "#" },
  ],
}
```

Tips:

- `id` harus unik.
- `image` selalu diawali `/team/` karena `public/team` dipetakan ke URL `/team`.
- Nama file foto tidak harus sama dengan `id` — yang penting nilainya cocok.

### Foto

- Taruh file di `public/team/`.
- Rasio **1:1 (persegi)**, minimal 400×400 px, ideal 800×800 px.
- Wajah di tengah frame karena foto dipotong bulat.
- Nama file huruf kecil tanpa spasi, misalnya `fathir.jpg`.
- Kalau foto belum ada, muncul siluet abu-abu (tidak error).

## 3. Alur Git

Selalu tarik perubahan terbaru sebelum mulai:

```bash
git pull
```

Setelah selesai mengedit:

```bash
git add .
git commit -m "update data tim"
git push
```

### Perubahan besar: pakai branch + Pull Request

```bash
git checkout -b update-tim
# ...edit...
git add .
git commit -m "tambah anggota baru"
git push -u origin update-tim
```

Lalu buka Pull Request di GitHub.

## 4. Alternatif tanpa terminal

Bisa juga lewat browser:

1. Buka repo di GitHub → masuk ke file → klik ikon **pensil**.
2. Edit → **Commit changes**.
3. Upload foto: **Add file → Upload files** ke folder `public/team/`.

Cara ini cocok untuk perubahan kecil; untuk mengedit banyak data sekaligus lebih nyaman clone lokal.

## Supaya tidak bentrok

- `git pull` sebelum mulai dan sebelum push.
- Hindari dua orang mengedit baris yang sama bersamaan.
- Jangan commit `node_modules/`, `.next/`, atau file `.env` (sudah di-`.gitignore`).
- Kalau `package.json` berubah, jalankan `npm install` lagi.
- Kompres foto besar (disarankan < 5 MB per file).

## Sebelum push

Pastikan build dan TypeScript lolos:

```bash
npm run typecheck
npm run build
```
