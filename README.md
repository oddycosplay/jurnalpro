# 📚 Jurnal Pro

[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-0.1.0-blue.svg)](jurnal-pro/.claude-plugin/plugin.json)
[![Claude Code Plugin](https://img.shields.io/badge/Claude%20Code-plugin-orange.svg)](jurnal-pro/)
[![Last commit](https://img.shields.io/github/last-commit/oddycosplay/jurnalpro)](https://github.com/oddycosplay/jurnalpro/commits/main)
[![Issues](https://img.shields.io/github/issues/oddycosplay/jurnalpro)](https://github.com/oddycosplay/jurnalpro/issues)
[![Stars](https://img.shields.io/github/stars/oddycosplay/jurnalpro?style=social)](https://github.com/oddycosplay/jurnalpro)

Jurnal Pro membantu peneliti menemukan dan memverifikasi jurnal publikasi yang tepat untuk manuskrip mereka. Alat ini menyusun daftar kandidat dari artikel yang mirip, memeriksa status indeks, biaya, scope, dan waktu proses dari sumber resmi, lalu menyajikan rekomendasi dalam tiga tingkat: **Ambisius**, **Realistis**, dan **Aman**.

Repositori ini berisi dua paket dengan isi yang sama:

| Folder | Untuk | Cara pakai |
| --- | --- | --- |
| 🧩 [`jurnal-pro/`](jurnal-pro/) | Claude Code | Plugin: perintah `/jurnal-pro` dan skill otomatis |
| 💬 [`jurnal-pro-portable/`](jurnal-pro-portable/) | ChatGPT, Gemini, Claude.ai, dan AI lain | Instruksi dan berkas pengetahuan yang ditempel atau diunggah |

## ✨ Fitur

- **Dua tahap kerja.** INTAKE menampilkan formulir lengkap jika data belum cukup. EXECUTE mengekstrak informasi yang sudah ada, menerapkan default, dan hanya bertanya bila benar-benar diperlukan.
- **Analisis manuskrip.** Bidang, kontribusi, metode, jenis artikel, dan referensi inti diekstrak dari naskah atau abstrak.
- **Verifikasi berbasis sumber resmi.** Status indeks diperiksa di Scopus Sources, Clarivate Master Journal List, DOAJ, dan portal SINTA. ISSN diperiksa di ISSN Portal.
- **Gerbang kelayakan wajib.** Jurnal yang tidak aktif, tidak konsisten identitasnya, atau menunjukkan tanda predator dikeluarkan, dan alasannya dicatat.
- **Biaya dan waktu yang jelas.** APC wajib, biaya hybrid opsional, biaya submission, dan waiver dibedakan. Waktu resmi dibandingkan dengan waktu empiris dari artikel terbaru.
- **Laporan dengan tautan dan tanggal akses.** Setiap klaim dinamis disertai sumber dan tanggal akses. Metrik selalu disertai tahunnya.
- **Unduhan untuk jurnal final.** Template resmi dan author guidelines dalam Markdown (khusus plugin).

## ⚙️ Instalasi

### Claude Code (plugin)

**Pasang dari marketplace (disarankan):**

1. Di Claude Code, tambahkan marketplace:
   ```
   /plugin marketplace add oddycosplay/jurnalpro
   ```
2. Pasang plugin dari marketplace tersebut:
   ```
   /plugin install jurnal-pro@oddycosplay-jurnalpro
   ```
3. Jalankan `/jurnal-pro`, opsional dengan path manuskrip atau topik.

Untuk memperbarui plugin nanti, jalankan `/plugin marketplace update oddycosplay-jurnalpro`.

**Uji lokal (untuk pengembang):** arahkan Claude Code ke folder plugin:

```powershell
claude --plugin-dir "path\ke\jurnalpro\jurnal-pro"
```

Setelah itu jalankan `/jurnal-pro`, opsional dengan path manuskrip atau topik.

### Claude.ai (chat)

Di Claude.ai, plugin tidak dipasang lewat perintah `claude --plugin-dir`. Ada dua cara:

**Cara A: unggah sebagai skill (disarankan)**

1. Buat berkas ZIP dari folder `jurnal-pro/skills/jurnal-pro/`. Pastikan `SKILL.md` berada di tingkat paling atas di dalam ZIP, dan semua berkas lain di folder itu ikut masuk.
2. Di Claude.ai, buka **Pengaturan** lalu **Kemampuan** (Capabilities), lalu bagian **Skills**, dan pilih unggah skill. Nama menu bisa berbeda tergantung versi aplikasi.
3. Unggah berkas ZIP tersebut. Setelah aktif, ketik `/jurnal-pro` atau minta Claude mencari jurnal untuk manuskrip Anda.

**Cara B: pakai versi portable (tanpa instalasi plugin)**

1. Buat Project baru di Claude.ai.
2. Tempel isi `jurnal-pro-portable/instruksi-sistem.md` ke kolom instruksi Project.
3. Unggah berkas dari `jurnal-pro-portable/knowledge/` ke Project.
4. Aktifkan pencarian web. Verifikasi jurnal bergantung padanya.

### ChatGPT, Gemini, dan AI lain

Ikuti panduan di [`jurnal-pro-portable/README.md`](jurnal-pro-portable/README.md). Singkatnya:

1. Tempel `jurnal-pro-portable/instruksi-sistem.md` ke kolom instruksi (Custom GPT, Gem, atau Project).
2. Unggah berkas dari `jurnal-pro-portable/knowledge/` jika platform mendukung berkas pengetahuan.
3. Aktifkan pencarian web. Verifikasi jurnal bergantung padanya.

## 🚀 Penggunaan

Berikan salah satu dari berikut:

- Berkas manuskrip (PDF, DOCX, atau TXT), atau
- Judul dan abstrak lengkap, atau
- Topik singkat (hasil akan lebih terbatas).

Jika data belum cukup, alat akan menampilkan formulir untuk diisi. Isian yang kosong memakai default: 5 rekomendasi, bahasa jurnal sesuai naskah, Scopus atau Web of Science diutamakan, dan DOAJ sebagai pelengkap.

## 🗂️ Struktur repositori

```
jurnal-pro/                           Plugin Claude Code
├── .claude-plugin/plugin.json
├── commands/jurnal-pro.md
└── skills/jurnal-pro/
    ├── SKILL.md                       Alur kerja utama (INTAKE dan EXECUTE)
    ├── onboarding-and-defaults.md     Formulir dan default
    ├── verification-and-scoring.md    Gerbang, penilaian, dan tanda bahaya
    ├── downloadable-journal-files.md  Unduhan template dan author guidelines
    ├── output-contract.md             Format laporan final
    └── portable-system-prompt.md      Versi instruksi tunggal
jurnal-pro-portable/                  Paket untuk AI chat
├── instruksi-sistem.md
├── knowledge/                         Salinan berkas skill
└── README.md
```

## ⚠️ Batasan

- Hasil bergantung pada sumber web yang tersedia saat pencarian. Status indeks, biaya, dan kebijakan dapat berubah, jadi periksa kembali di situs resmi jurnal sebelum submit.
- Alat ini tidak menjamin penerimaan atau waktu publikasi. Skor hanya alat bantu.
- Naskah hanya dikirim ke satu jurnal pada satu waktu.
- Di AI chat, unduhan template tidak tersimpan otomatis ke komputer. Pengguna mengunduhnya sendiri dari tautan yang diberikan.

## 🤝 Dukungan

- **Laporkan bug atau usulkan fitur** dengan membuka [issue baru](https://github.com/oddycosplay/jurnalpro/issues/new). Sertakan langkah untuk mengulangi masalah dan versi yang Anda pakai.
- **Pertanyaan penggunaan** juga bisa diajukan lewat issue dengan judul yang jelas.
- Jika paket ini membantu, **beri bintang ⭐** pada repositori. Itu membantu orang lain menemukannya.

## ❤️ Donasi

Jika Jurnal Pro membantu pekerjaan Anda, dukungan Anda membantu pengembangannya:

- ☕ **GitHub Sponsors:** [github.com/sponsors/oddycosplay](https://github.com/sponsors/oddycosplay)

## 👤 Pembuat

**oddycosplay**, pembuat dan pengelola proyek ini.
[github.com/oddycosplay](https://github.com/oddycosplay)

## 📄 Lisensi

Proyek ini dilisensikan di bawah [MIT License](LICENSE).
