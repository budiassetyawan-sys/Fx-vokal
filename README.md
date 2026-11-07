# Mixer Vokal Satu Channel (Android native, latensi rendah)

Kotlin + C++ (Oboe/AAudio). Rantai: input > gain > low cut > noise gate > EQ 5 band > de-esser
> kompresor > reverb + echo > limiter > output. Mendukung soundcard USB class-compliant.

## Build APK tanpa Android Studio (GitHub Actions)
1. Buat akun GitHub (gratis) lalu buat repository baru (publik atau privat).
2. Unggah ISI folder ini ke repository, termasuk folder tersembunyi `.github`.
   Jika folder `.github` tidak ikut terunggah: Add file > Create new file, ketik nama
   `.github/workflows/build.yml`, lalu tempel isi file `build.yml` dari ZIP.
3. Buka tab Actions > workflow "Build APK". Jika belum jalan, klik Run workflow.
4. Tunggu sekitar 5-10 menit sampai centang hijau. Buka run tersebut, bagian Artifacts,
   unduh `mixer-vokal-apk` (berisi app-debug.apk).
5. Pindahkan APK ke HP, izinkan "Instal aplikasi tidak dikenal", lalu pasang.
6. Jika build gagal, salin 30-50 baris terakhir log yang merah dan kirim ke Claude.

## Pemakaian
1. Colok soundcard USB (pakai kabel OTG jika perlu), lalu buka aplikasi. Perangkat USB dipilih otomatis.
2. Tekan "Mulai live" dan izinkan mikrofon.
3. Pakai headphone yang tersambung ke soundcard atau jack, bukan speaker, agar tidak berdengung.
4. Atur Buffer: mulai dari 1x burst, naikkan jika terdengar putus-putus (lihat angka xrun dan underrun).
5. Latensi terendah umumnya dengan kabel (bukan Bluetooth), output exclusive, dan low-latency "ya".

## Catatan
- Layar dijaga tetap menyala. Jika aplikasi dipindah ke latar belakang, Android bisa membisukan mikrofon.
- APK ini ditandatangani dengan kunci debug (cukup untuk dipakai sendiri).
