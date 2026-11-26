---
description: Cari dan verifikasi jurnal publikasi untuk manuskrip Anda
argument-hint: [path manuskrip atau judul/topik]
---

Gunakan skill `jurnal-pro` dari plugin ini untuk menjalankan alur pencarian dan verifikasi jurnal.

Argumen dari pengguna: $ARGUMENTS

- Jika argumen kosong, atau belum cukup untuk pencarian, masuk ke tahap INTAKE dan tampilkan formulir dari `onboarding-and-defaults.md` secara utuh dalam satu respons.
- Jika argumen berupa path berkas, baca berkas itu sebagai manuskrip lalu masuk ke tahap EXECUTE.
- Jika argumen berupa judul atau topik, masuk ke EXECUTE hanya bila abstrak atau ringkasan yang substansial tersedia. Jika tidak, masuk ke INTAKE.
