# RAB Deployment — NO BATIDÃO

**Rencana Anggaran Biaya (RAB) Deployment Website Tim**

| | |
| --- | --- |
| Proyek | Website profil tim **NO BATIDÃO** (Next.js 16 + TypeScript + Tailwind CSS) |
| Repositori | https://github.com/bilhaqschrodinger/BATIDAO |
| Lingkup | Deployment produksi, domain, SSL, monitoring, dan pemeliharaan 1 tahun |
| Versi / Tanggal | v1.0 — 12 November 2026 |
| Penyusun | Tim NO BATIDÃO |
| Status | Draf untuk persetujuan |

---

## 1. Ringkasan

Website ini adalah **situs statis** (tidak ada database, login, atau API berbayar). Semua halaman di-*pre-render* saat build, sehingga kebutuhan infrastruktur sangat minim.

Karena itu, biaya deployment dapat ditekan menjadi **Rp 0** bila memakai subdomain gratis, atau **± Rp 200.000–250.000 per tahun** bila memakai domain sendiri. Biaya besar (Vercel Pro) **baru diperlukan jika situs bersifat komersial** atau butuh fitur tim.

| Skenario | Biaya Tahun 1 | Biaya Tahun Berikutnya | Total 3 Tahun |
| --- | ---: | ---: | ---: |
| **A. Gratis** | Rp 0 | Rp 0 | Rp 0 |
| **B. Rekomendasi** (domain .com + Vercel Hobby) | Rp 149.000 | Rp 220.000 | Rp 589.000 |
| **C. Profesional/Komersial** (Vercel Pro) | Rp 4.517.000 | Rp 4.588.000 | Rp 13.693.000 |

> **Rekomendasi: Skenario B.** Cukup domain sendiri + hosting gratis, total rata-rata **± Rp 196.000/tahun** atau **± Rp 1.400 per anggota per bulan** (12 anggota).

---

## 2. Asumsi dan Dasar Perhitungan

1. **Kurs:** US$1 = **Rp 18.200** (dibulatkan ke atas dari kurs tengah BI 12 Nov 2026: Rp 18.154).
2. **Hosting:** Vercel Hobby (gratis) sesuai untuk proyek **non-komersial/personal**. Jika situs memuat iklan, penjualan, atau aktivitas komersial, wajib Vercel Pro.
3. **Domain:** harga promo tahun pertama; tahun berikutnya memakai harga perpanjangan normal.
4. **Tenaga kerja:** dikerjakan internal tim, sehingga **tidak dihitung sebagai pengeluaran kas**. Nilai waktunya dicantumkan terpisah sebagai *opportunity cost*.
5. **Pajak:** harga belum termasuk PPN/pajak yang berlaku (bila dikenakan penyedia layanan digital luar negeri).
6. **Harga dapat berubah** — verifikasi ulang saat pembelian.

### Perbandingan ekstensi domain (per tahun)

| Ekstensi | Registrasi Tahun 1 | Perpanjangan | Syarat | Catatan |
| --- | ---: | ---: | --- | --- |
| `.com` | ± Rp 149.000 | ± Rp 201.000–232.000 | — | Paling profesional dan mudah diingat |
| `.id` | ± Rp 219.000 | ± Rp 219.000 | KTP | Identitas lokal |
| `.my.id` | ± Rp 9.900 | ± Rp 25.000 | — | Termurah, cocok bila anggaran nol |
| `.web.id` | ± Rp 50.000 | ± Rp 50.000 | — | Alternatif murah |
| `.co.id` | ± Rp 270.000–300.000 | sama | KTP + NIB | Untuk badan usaha, **tidak disarankan** untuk tim komunitas |

---

## 3. Rincian Biaya Awal (One-Time)

| No | Komponen | Spesifikasi | Qty | Satuan | Harga Satuan | Jumlah | Keterangan |
| ---: | --- | --- | ---: | --- | ---: | ---: | --- |
| 1 | Registrasi domain `.com` | 1 tahun pertama (harga promo) | 1 | tahun | Rp 149.000 | **Rp 149.000** | Wajib bila ingin domain sendiri |
| 2 | Setup deployment | Import repo, build, domain, SSL, redirect | 4 | jam | Rp 0 | **Rp 0** | Dikerjakan internal |
| 3 | Setup DNS & email forwarding | Cloudflare DNS + Email Routing | 1 | paket | Rp 0 | **Rp 0** | Gratis |
| 4 | Aset visual (opsional) | OG image, favicon, banner | 1 | paket | Rp 250.000 | **Rp 250.000** | Bisa dikerjakan internal |
| 5 | Jasa setup (opsional, jika outsourcing) | Deploy + domain + QA | 1 | paket | Rp 750.000 | **Rp 750.000** | Alternatif bila tidak dikerjakan sendiri |
| | **Total wajib (internal)** | | | | | **Rp 149.000** | Tanpa item opsional |
| | **Total dengan aset visual** | | | | | **Rp 399.000** | |
| | **Total dengan outsourcing** | | | | | **Rp 899.000** | |

---

## 4. Biaya Berulang Tahunan

### Skenario A — Gratis (Rp 0/tahun)

| No | Komponen | Spesifikasi | Qty | Harga Satuan | Jumlah |
| ---: | --- | --- | ---: | ---: | ---: |
| 1 | Hosting Vercel Hobby | 100 GB transfer, 1 juta request/bulan | 1 | Rp 0 | Rp 0 |
| 2 | Subdomain `*.vercel.app` | URL bawaan Vercel | 1 | Rp 0 | Rp 0 |
| 3 | SSL/TLS | Otomatis Let's Encrypt | 1 | Rp 0 | Rp 0 |
| 4 | Repository GitHub Free | Repo publik + CI/CD otomatis | 1 | Rp 0 | Rp 0 |
| 5 | Monitoring dasar | Vercel Analytics + UptimeRobot gratis | 1 | Rp 0 | Rp 0 |
| | **Total** | | | | **Rp 0** |

**Kelebihan:** tanpa biaya sama sekali.
**Kekurangan:** URL kurang profesional, tidak ada email `@batidao`, dan Hobby hanya untuk non-komersial.

### Skenario B — Rekomendasi (domain sendiri, hosting gratis)

| No | Komponen | Spesifikasi | Qty | Harga Satuan | Jumlah |
| ---: | --- | --- | ---: | ---: | ---: |
| 1 | Perpanjangan domain `.com` | Otomatis (auto-renew) | 1 tahun | Rp 220.000 | **Rp 220.000** |
| 2 | Hosting Vercel Hobby | 100 GB transfer/bulan | 1 | Rp 0 | Rp 0 |
| 3 | SSL/TLS | Otomatis | 1 | Rp 0 | Rp 0 |
| 4 | DNS & email forwarding | Cloudflare (gratis) | 1 | Rp 0 | Rp 0 |
| 5 | GitHub Free | Repo + auto deploy tiap push | 1 | Rp 0 | Rp 0 |
| 6 | Monitoring | UptimeRobot, Vercel Analytics | 1 | Rp 0 | Rp 0 |
| | **Total tahun berikutnya** | | | | **Rp 220.000** |
| | **Total tahun pertama** (domain promo) | | | | **Rp 149.000** |

*Estimasi perpanjangan memakai harga tengah `.com` (Rp 201.000–232.000).*

### Skenario C — Profesional/Komersial

| No | Komponen | Spesifikasi | Qty | Harga Satuan | Jumlah |
| ---: | --- | --- | ---: | ---: | ---: |
| 1 | Perpanjangan domain `.com` | Auto-renew | 1 tahun | Rp 220.000 | Rp 220.000 |
| 2 | Vercel Pro | US$20/bln/seat × Rp 18.200 × 12 | 1 tahun | Rp 364.000/bln | **Rp 4.368.000** |
| 3 | Email Google Workspace (opsional) | 2 akun × US$7,2/bln × 12 | 2 akun | Rp 131.000/bln | Rp 3.144.000 |
| 4 | SSL, DNS, monitoring | Termasuk paket | 1 | Rp 0 | Rp 0 |
| | **Total tanpa email** | | | | **Rp 4.588.000** |
| | **Total dengan email** | | | | **Rp 7.732.000** |

> Vercel Pro hanya perlu jika: situs **komersial**, butuh *password protection*, *preview deployment* tim, atau kuota Hobby terlampaui. Untuk website profil komunitas, **tidak diperlukan**.

---

## 5. Rekapitulasi 3 Tahun (TCO)

| Skenario | Tahun 1 | Tahun 2 | Tahun 3 | Subtotal | Kontingensi 10% | **Total** |
| --- | ---: | ---: | ---: | ---: | ---: | ---: |
| A. Gratis | Rp 0 | Rp 0 | Rp 0 | Rp 0 | Rp 0 | **Rp 0** |
| B. Rekomendasi | Rp 149.000 | Rp 220.000 | Rp 220.000 | Rp 589.000 | Rp 59.000 | **Rp 648.000** |
| C. Profesional | Rp 4.517.000 | Rp 4.588.000 | Rp 4.588.000 | Rp 13.693.000 | Rp 1.369.000 | **Rp 15.062.000** |

**Biaya per anggota (12 orang):**

| Skenario | Rata-rata per tahun | Per bulan |
| --- | ---: | ---: |
| A | Rp 0 | Rp 0 |
| B | ± Rp 196.000 | ± Rp 16.400 (≈ Rp 1.400/orang/bulan) |
| C | ± Rp 4.564.000 | ± Rp 380.000 (≈ Rp 31.900/orang/bulan) |

---

## 6. Estimasi Nilai Waktu (Bukan Pengeluaran Kas)

| Aktivitas | Frekuensi | Durasi | Tarif (asumsi) | Nilai per tahun |
| --- | --- | ---: | ---: | ---: |
| Setup awal deployment | Sekali | 4 jam | Rp 50.000/jam | Rp 200.000 |
| Update konten/foto | 2× per bulan (24×/tahun) | 1 jam | Rp 50.000/jam | Rp 1.200.000 |
| Maintenance & monitoring | 1× per bulan (12×/tahun) | 1 jam | Rp 50.000/jam | Rp 600.000 |
| **Total nilai waktu** | | | | **± Rp 2.000.000/tahun** |

Biaya ini **tidak keluar dari kas** selama dikerjakan sendiri oleh anggota tim.

---

## 7. Rencana Kerja Deployment

| Hari | Kegiatan | Output | PIC |
| --- | --- | --- | --- |
| 1 | Finalisasi konten, foto, dan link | Semua data 12 anggota lengkap | Konten |
| 2 | Pembelian domain + setup DNS di Cloudflare | Domain aktif, nameserver mengarah | Teknis |
| 3 | Import repo ke Vercel, set domain, build produksi | Preview deployment berjalan | Teknis |
| 4 | QA: mobile/desktop, foto, link, aksesibilitas | Daftar bug = 0 blocker | QA |
| 5 | UAT internal + perbaikan | Persetujuan tim | Semua |
| 6 | Go-live + aktifkan monitoring & auto-renew | Situs live di domain resmi | Teknis |

**Estimasi total:** 6 hari kerja (± 1 minggu), ± 10–12 jam orang.

---

## 8. Analisis Risiko

| No | Risiko | Dampak | Kemungkinan | Mitigasi |
| ---: | --- | --- | --- | --- |
| 1 | Domain lupa diperpanjang | Situs tidak bisa diakses | Sedang | Auto-renew + pengingat 30 hari + kartu cadangan |
| 2 | Situs dianggap komersial di Vercel Hobby | Deployment diblokir | Rendah | Tidak ada iklan/monetisasi; upgrade Pro bila perlu |
| 3 | Kuota Hobby (100 GB/bulan) terlampaui | Situs melambat/dibatasi | Rendah | Pantau analytics; upgrade Pro atau pindah Cloudflare Pages |
| 4 | Foto terlalu besar | Load lambat, kuota cepat habis | Sedang | Kompres ke < 300 KB, format WebP, ukuran maks. 800×800 |
| 5 | Kehilangan akses repo/akun | Tidak bisa update | Rendah | 2 admin, 2FA, arsip ZIP berkala |
| 6 | Harga domain/kurs berubah | Estimasi meleset | Sedang | Kontingensi 10%; bayar tahunan di awal |
| 7 | Data anggota salah/kurang | Kualitas konten | Sedang | UAT hari ke-5 sebelum go-live |

---

## 9. Strategi Penghematan

1. **Hosting gratis:** Vercel Hobby (atau Cloudflare Pages/Netlify) — Rp 0.
2. **SSL gratis:** Let's Encrypt otomatis — Rp 0.
3. **DNS & email forwarding gratis:** Cloudflare — Rp 0.
4. **Repo & CI/CD gratis:** GitHub Free — Rp 0.
5. **Monitoring gratis:** UptimeRobot + Vercel Analytics — Rp 0.
6. **Domain murah:** `.my.id` ± Rp 25.000/tahun bila anggaran benar-benar nol.
7. **Aset gratis:** foto Unsplash atau dokumentasi internal; tidak perlu stok berbayar.
8. **Tanpa database/server:** situs statis, tidak ada biaya compute.

---

## 10. Yang Tidak Termasuk dalam RAB

- Iklan/promosi berbayar (Google Ads, Meta Ads).
- Sesi foto profesional dan jasa fotografer.
- Email massal/newsletter berbayar.
- Penulisan konten oleh pihak ketiga.
- Pengembangan fitur baru di luar deployment (mis. CMS, login, database).
- Pajak penghasilan dan administrasi keuangan.

---

## 11. Rekomendasi Akhir

1. Pilih **Skenario B**: domain `.com` + **Vercel Hobby** + Cloudflare DNS.
2. Anggarkan **Rp 250.000 untuk tahun pertama** (domain promo + cadangan).
3. Siapkan **Rp 250.000/tahun** untuk perpanjangan domain.
4. Jangan ambil Vercel Pro selama situs belum komersial.
5. Deploy otomatis dari branch `main` — setiap `git push` langsung tayang.

**Total anggaran yang diajukan: Rp 250.000 (tahun pertama) dan Rp 250.000/tahun (perpanjangan).**

---

## 12. Sumber Harga

| Komponen | Sumber | Tanggal cek |
| --- | --- | --- |
| Vercel Hobby/Pro (US$0 / US$20 per bulan) | vercel.com/pricing | 9–12 Nov 2026 |
| Domain `.com` (registrasi ± Rp 149.000; perpanjangan ± Rp 201.000–232.000) | Domainesia, Rumahweb, Depodomain | Okt–Nov 2026 |
| Domain `.id` (± Rp 219.000), `.my.id` (± Rp 25.000), `.web.id` (± Rp 50.000) | Rumahweb, Domainesia, IDCloudHost | Sep–Nov 2026 |
| Kurs US$1 = Rp 18.154 | Kurs tengah BI, 12 Nov 2026 | 12 Nov 2026 |

---

## 13. Persetujuan

| Peran | Nama | Tanda Tangan | Tanggal |
| --- | --- | --- | --- |
| Ketua / Founder | Fathir Izzakky | | |
| Bendahara | Muhammad Jisrin Syahadata | | |
| PIC Teknis | Bilhaq Zouvary Brahmantya Jatmiko | | |
| PIC Konten | Raydisa Putra ACEMAD | | |

---

*Dokumen ini adalah estimasi. Harga final mengikuti tagihan penyedia layanan pada saat pembelian.*
