# Jurnal Pro: paket portabel

Paket ini dipakai di AI yang tidak menjalankan plugin Claude Code, misalnya ChatGPT dan Gemini. Tidak ada yang "terpasang". Isinya adalah instruksi dan berkas pengetahuan yang Anda tempelkan atau unggah ke AI pilihan Anda.

## Isi paket

- `instruksi-sistem.md`: instruksi utama. Tempel isinya ke kolom instruksi.
- `knowledge/`: alur kerja lengkap dan empat berkas pendukung (formulir, verifikasi dan penilaian, unduhan, format laporan). Unggah sebagai berkas pengetahuan.

## ChatGPT (Custom GPT)

1. Buka **Explore GPTs**, lalu pilih **Create**, dan buka tab **Configure**.
2. Tempel isi `instruksi-sistem.md` ke kolom **Instructions**.
3. Di bagian **Knowledge**, unggah kelima berkas dari folder `knowledge`.
4. Di bagian **Capabilities**, aktifkan **Web Search**. Verifikasi jurnal membutuhkan pencarian web.
5. Simpan. Pilih visibilitas sesuai kebutuhan, misalnya **Only me**.

## Gemini (Gem)

1. Buka **Explore Gems**, lalu pilih **New Gem**.
2. Tempel isi `instruksi-sistem.md` ke kolom instruksi.
3. Unggah berkas dari folder `knowledge` jika fitur unggah berkas tersedia di akun Anda. Jika tidak, tempel `instruksi-sistem.md` saja. Itu sudah berisi alur inti.
4. Pastikan pencarian Google aktif di percakapan.

## Claude.ai (Project) atau AI lain

- **Claude.ai**: buat Project, isi kolom instruksi Project dengan `instruksi-sistem.md`, lalu unggah berkas dari folder `knowledge`.
- **AI lain**: tempel `instruksi-sistem.md` sebagai system prompt atau instruksi kustom. Berikan berkas `knowledge` sebagai lampiran di awal percakapan.

## Cara memakai

Kirim abstrak lengkap, atau unggah manuskrip, lalu isi formulir yang ditampilkan AI. Jika belum punya bahan, ketik `mulai` untuk memunculkan formulir.

## Batasan di AI chat

- AI chat tidak bisa menjalankan perintah atau menyimpan berkas ke komputer Anda. Unduhan template dan author guidelines menjadi tautan yang Anda unduh sendiri.
- Verifikasi bergantung pada pencarian web. Jika pencarian tidak tersedia, AI akan menandai klaim sebagai "Belum diverifikasi".
- Periksa status indeks, biaya, dan pedoman di situs resmi jurnal sebelum submit. Informasi dapat berubah.
- Paket ini tidak menjamin penerimaan atau waktu publikasi.
- Naskah hanya dikirim ke satu jurnal pada satu waktu.

Paket ini dibuat dari plugin `jurnal-pro` v0.1.0.
