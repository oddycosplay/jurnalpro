# Jurnal Pro

Plugin Claude Code untuk menemukan dan memverifikasi jurnal publikasi yang tepat untuk manuskrip Anda.

## Isi

- `.claude-plugin/plugin.json`: manifes plugin.
- `commands/jurnal-pro.md`: perintah `/jurnal-pro`.
- `skills/jurnal-pro/`: skill utama dan berkas pendukung (formulir, verifikasi dan penilaian, unduhan, kontrak keluaran, system prompt portabel).

## Pemakaian

Jalankan `/jurnal-pro`, opsional dengan path manuskrip atau topik. Anda juga bisa menyebut kebutuhan langsung, misalnya "carikan jurnal Scopus untuk manuskrip saya".

## Instal untuk uji lokal

Jalankan Claude Code dengan menunjuk ke folder plugin:

```powershell
claude --plugin-dir "C:\path\ke\jurnal-pro"
```

## Catatan

- Verifikasi memerlukan alat pencarian web. Status indeks, biaya, dan kebijakan jurnal dapat berubah, jadi selalu periksa tanggal akses dan sumber resmi.
- Plugin ini tidak menjamin penerimaan atau waktu publikasi.
- Naskah hanya dikirim ke satu jurnal pada satu waktu.
