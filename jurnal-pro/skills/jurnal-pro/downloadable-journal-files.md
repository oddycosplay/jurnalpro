# Berkas unduhan untuk jurnal final

Berlaku untuk setiap jurnal yang masuk daftar final.

## Yang diunduh

1. **Template resmi**: berkas template yang disediakan jurnal atau penerbit (DOCX, LaTeX dalam ZIP, atau format lain) dari halaman resmi.
2. **Author guidelines dalam Markdown**: isi pedoman penulis dari halaman resmi, dikonversi ke Markdown.

Jika template tidak tersedia secara publik, tulis "Template tidak dipublikasikan" dan sertakan tautan halaman pedoman. Jangan membuat template sendiri, dan jangan memberi nama yang seolah-olah template resmi.

## Langkah

1. **Author guidelines.** Ambil halaman pedoman penulis dengan WebFetch, lalu simpan ke `output/<slug-jurnal>/author-guidelines.md`. Gunakan slug huruf kecil dengan tanda hubung. Awali berkas dengan header:

   ```markdown
   # Author guidelines: <nama jurnal>
   - Sumber: <URL resmi>
   - Tanggal akses: <YYYY-MM-DD>
   - Catatan: Salinan ini dapat tertinggal dari halaman asli. Periksa halaman asli sebelum submit.
   ```

   Isi di bawah header adalah ringkasan Markdown dari halaman tersebut, dalam bahasa aslinya. Jangan menyalin navigasi atau iklan.

2. **Template.** Unduh hanya dari domain jurnal atau penerbit. Periksa jenis dan ukuran berkas sebelum unduh, lalu sebutkan nama berkas, sumber, dan ukurannya di laporan. Simpan ke `output/<slug-jurnal>/template/` dalam folder yang baru dan kosong.
   - Jangan membuka, menjalankan, atau mengekstrak makro.
   - Jika berupa ZIP, ekstrak hanya ke folder baru yang kosong, lalu jangan menjalankan skrip di dalamnya.
   - Jangan mengubah isi template resmi.

3. **Manifes.** Catat setiap berkas beserta sumber, tanggal akses, dan SHA-256-nya di `output/<slug-jurnal>/MANIFEST.md`. Hitung hash dengan alat yang tersedia, misalnya `Get-FileHash` di PowerShell.

4. **Kirim ke pengguna.** Gunakan SendUserFile untuk setiap berkas agar tersedia pada respons yang sama. Jika alat itu tidak tersedia, cantumkan path relatif setiap berkas di bagian "Berkas terlampir" pada laporan.
