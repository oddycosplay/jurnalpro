# Jurnal Pro

Jurnal Pro membantu peneliti menemukan dan memverifikasi jurnal publikasi yang tepat untuk manuskrip mereka. Alat ini menyusun daftar kandidat dari artikel yang mirip, memeriksa status indeks, biaya, scope, dan waktu proses dari sumber resmi, lalu menyajikan rekomendasi dalam tiga tingkat: **Ambisius**, **Realistis**, dan **Aman**.

Repositori ini berisi dua paket dengan isi yang sama:

| Folder | Untuk | Cara pakai |
| --- | --- | --- |
| [`jurnal-pro/`](jurnal-pro/) | Claude Code | Plugin: perintah `/jurnal-pro` dan skill otomatis |
| [`jurnal-pro-portable/`](jurnal-pro-portable/) | ChatGPT, Gemini, Claude.ai, dan AI lain | Instruksi dan berkas pengetahuan yang ditempel atau diunggah |

## Fitur

- **Dua tahap kerja.** INTAKE menampilkan formulir lengkap jika data belum cukup. EXECUTE mengekstrak informasi yang sudah ada, menerapkan default, dan hanya bertanya bila benar-benar diperlukan.
- **Analisis manuskrip.** Bidang, kontribusi, metode, jenis artikel, dan referensi inti diekstrak dari naskah atau abstrak.
- **Verifikasi berbasis sumber resmi.** Status indeks diperiksa di Scopus Sources, Clarivate Master Journal List, DOAJ, dan portal SINTA. ISSN diperiksa di ISSN Portal.
- **Gerbang kelayakan wajib.** Jurnal yang tidak aktif, tidak konsisten identitasnya, atau menunjukkan tanda predator dikeluarkan dan alasannya dicatat.
- **Biaya dan waktu yang jelas.** APC wajib, biaya hybrid opsional, biaya submission, dan waiver dibedakan. Waktu resmi dibandingkan dengan waktu empiris dari artikel terbaru.
- **Laporan dengan tautan dan tanggal akses.** Setiap klaim dinamis disertai sumber dan tanggal akses. Metrik selalu disertai tahunnya.
- **Unduhan untuk jurnal final.** Template resmi dan author guidelines dalam Markdown (khusus plugin).

## Instalasi

### Claude Code (plugin)

Untuk uji lokal, arahkan Claude Code ke folder plugin:

```powershell
claude --plugin-dir "path\ke\jurnalpro\jurnal-pro"
```

Setelah itu jalankan `/jurnal-pro`, opsional dengan path manuskrip atau topik.

### ChatGPT, Gemini, dan AI lain

Ikuti panduan di [`jurnal-pro-portable/README.md`](jurnal-pro-portable/README.md). Singkatnya:

1. Tempel `jurnal-pro-portable/instruksi-sistem.md` ke kolom instruksi (Custom GPT, Gem, atau Project).
2. Unggah berkas dari `jurnal-pro-portable/knowledge/` jika platform mendukung berkas pengetahuan.
3. Aktifkan pencarian web. Verifikasi jurnal bergantung padanya.

## Penggunaan

Berikan salah satu dari berikut:

- Berkas manuskrip (PDF, DOCX, atau TXT), atau
- Judul dan abstrak lengkap, atau
- Topik singkat (hasil akan lebih terbatas).

Jika data belum cukup, alat akan menampilkan formulir untuk diisi. Isian yang kosong memakai default: 5 rekomendasi, bahasa jurnal sesuai naskah, Scopus atau Web of Science diutamakan, dan DOAJ sebagai pelengkap.

## Struktur repositori

```
jurnal-pro/                  Plugin Claude Code
├── .claude-plugin/plugin.json
├── commands/jurnal-pro.md
└── skills/jurnal-pro/
    ├── SKILL.md                      Alur kerja utama (INTAKE dan EXECUTE)
    ├── onboarding-and-defaults.md    Formulir dan default
    ├── verification-and-scoring.md    Gerbang, penilaian, dan tanda bahaya
    ├── downloadable-journal-files.md  Unduhan template dan author guidelines
    ├── output-contract.md             Format laporan final
    └── portable-system-prompt.md      Versi instruksi tunggal
jurnal-pro-portable/         Paket untuk AI chat
├── instruksi-sistem.md
├── knowledge/                        Salinan berkas skill
└── README.md
```

## Batasan

- Hasil bergantung pada sumber web yang tersedia pada saat pencarian. Status indeks, biaya, dan kebijakan dapat berubah. Periksa kembali di situs resmi jurnal sebelum submit.
- Alat ini tidak menjamin penerimaan atau waktu publikasi. Skor hanya alat bantu.
- Naskah hanya dikirim ke satu jurnal pada satu waktu.
- Di AI chat, unduhan template tidak tersimpan otomatis ke komputer. Pengguna mengunduhnya sendiri dari tautan yang diberikan.

## Lisensi

Proyek ini dilisensikan di bawah [MIT License](LICENSE).
