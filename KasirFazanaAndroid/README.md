# Kasir Fazana - Android WebView wrapper

Project Android Studio untuk membungkus aplikasi HTML kasir yang diberikan menjadi aplikasi Android bernama **Kasir Fazana**.

## Build APK

Persyaratan: Android Studio terbaru, JDK 17 atau lebih baru, Android SDK Platform 35, dan koneksi internet pertama kali untuk mengunduh Android Gradle Plugin.

1. Ekstrak ZIP ini.
2. Buka folder `KasirFazanaAndroid` melalui Android Studio.
3. Tunggu Gradle Sync selesai.
4. Pilih **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
5. APK debug akan dibuat di `app/build/outputs/apk/debug/app-debug.apk`.
6. Salin APK ke HP Android dan buka untuk memasang. Jika diminta, izinkan instalasi dari sumber tersebut.

## Catatan fungsi

- HTML asli dipertahankan di `app/src/main/assets/index.html`.
- JavaScript dan penyimpanan lokal WebView diaktifkan.
- Pemilihan screenshot/gambar memakai pemilih file Android.
- Tombol cetak sistem diarahkan ke dialog cetak Android.
- Skema `rawbt:` diteruskan ke aplikasi eksternal. Untuk cetak printer Bluetooth melalui tombol RawBT, pasang aplikasi RawBT dan pasangkan printer dari aplikasi tersebut.
- Tailwind CSS, Google Fonts, dan Tesseract.js masih dimuat dari CDN, sehingga fitur yang memakai pustaka tersebut memerlukan internet.
- Web Bluetooth API pada tombol “Bluetooth Langsung” dapat tidak tersedia di WebView Android; gunakan opsi RawBT untuk printer Bluetooth.

Paket aplikasi: `id.fazana.kasir`  
Versi: `1.0.0`

## Build APK secara online dengan GitHub Actions

Project ini sudah dilengkapi workflow otomatis di `.github/workflows/build-apk.yml`.

1. Ekstrak ZIP project ini di komputer.
2. Buat repository baru di https://github.com/ dan beri nama, misalnya `kasir-fazana-android`.
3. Upload **isi folder `KasirFazanaAndroid`** ke repository (pastikan folder `.github/workflows` ikut ter-upload).
4. Buka tab **Actions** di repository. Jika diminta, pilih **I understand my workflows, go ahead and enable them**.
5. Workflow akan berjalan otomatis setelah file di-push ke branch `main` atau `master`. Bisa juga dijalankan manual melalui **Actions > Build Kasir Fazana APK > Run workflow**.
6. Tunggu sampai proses selesai dengan status hijau **Success**.
7. Buka proses workflow yang berhasil, gulir ke bagian **Artifacts**, lalu unduh `Kasir-Fazana-APK`.
8. Ekstrak file artifact ZIP. Di dalamnya ada `app-debug.apk`; kirim ke HP Android lalu buka untuk memasang.

Jika proses gagal, buka detail job **Build Android APK** dan lihat langkah yang berwarna merah. Artifact hanya tersedia jika proses build berhasil.
