# NO BATIDÃO

Team wall interaktif: badge lanyard yang bisa di-flip, ditarik, dan digeser. Dibuat dengan Next.js, TypeScript, Tailwind CSS, dan komponen shadcn.

Mau ikut mengedit? Baca [CONTRIBUTING.md](./CONTRIBUTING.md) untuk panduan clone, edit data tim, ganti foto, dan alur Git.

## Menjalankan proyek

Prasyarat: **Node.js 20+** dan npm.

```bash
npm install
npm run dev
```

Buka <http://localhost:3000>.

Perintah lain:

```bash
npm run build      # build produksi
npm start          # jalankan hasil build
npm run typecheck  # cek TypeScript
```

## Struktur penting

```
app/
  page.tsx                        # halaman utama (render demo)
  globals.css                     # token warna & tema shadcn
components/
  ui/team-lanyard-rail.tsx        # komponen lanyard (jangan diubah kecuali perlu)
  team-lanyard-rail-demo.tsx      # DATA TIM — edit di sini
public/
  team/                           # foto anggota
```

## Mengedit anggota tim

Semua data ada di `components/team-lanyard-rail-demo.tsx` pada array `LANYARD_DEMO_TEAM`.
Setiap anggota punya bentuk:

```tsx
{
  id: "Fathir",                 // unik, dipakai sebagai key React
  name: "Fathir Izzakky",       // nama di badge
  role: "Founder Batidao",      // jabatan
  team: "CEO",                  // baris kecil di bawah role
  tone: 1,                      // warna 1–5 (lihat --chart-1..5 di globals.css)
  image: "/team/fathir.jpg",       // path foto di folder public
  bio: "…",                     // teks di balik badge
  tags: ["CHAMBER", "Zeroks"],  // chip di balik badge (maks. 3 tampil)
  links: [                      // link kontak di balik badge (maks. 3 tampil)
    { label: "Email", href: "#" },
    { label: "Portfolio", href: "#" },
  ],
}
```

Catatan:
- `id` harus unik untuk setiap anggota.
- `image` diawali `/team/...` karena folder `public/team` dipetakan ke URL `/team`.
- Nama file foto tidak harus sama dengan `id`.
- Maksimal 3 `tags` dan 3 `links` yang dirender.

## Mengganti foto

Taruh foto di `public/team/`, lalu samakan nilai `image` dengan nama file tersebut.

- Rasio **1:1 (persegi)**, minimal 400×400 px.
- Wajah di tengah frame karena foto dipotong bulat.
- Nama file disarankan huruf kecil tanpa spasi, misalnya `fathir.jpg`.
- Kalau foto belum ada, komponen otomatis menampilkan siluet abu-abu.

## Kustomisasi tampilan

- Warna badge memakai token `--chart-1` sampai `--chart-5` di `app/globals.css`.
- Judul, eyebrow, caption, dan tombol CTA diatur lewat props di `TeamLanyardRailDemo`.
- Komponen mendukung mode terkontrol (`active`, `flipped`), autoplay, dan label bahasa lewat props `labels`.

## Dokumentasi

- [Panduan kontribusi](./CONTRIBUTING.md)
- [RAB deployment](./docs/RAB.md) · [versi Excel](./docs/RAB-NO-BATIDAO.xlsx)
- [Panduan foto tim](./public/team/README.md)

## Tech stack

- Next.js 16 (App Router)
- React 19
- TypeScript
- Tailwind CSS v4
- shadcn/ui (base-nova)
