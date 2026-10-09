# Cara bina APK hanya dengan telefon Android

Kaedah ini menggunakan GitHub Actions untuk membina projek di cloud. Anda tidak perlu memasang Android Studio atau mempunyai PC.

## Perkara penting
- Projek ini ialah prototaip demo. Harga, bias, entry, SL dan TP masih data simulasi.
- APK yang dibina ialah debug APK untuk ujian/pemasangan sendiri, bukan aplikasi Play Store yang ditandatangani untuk edaran.
- Anda perlukan sambungan internet dan akaun GitHub.
- Jangan masukkan API key peribadi ke dalam kod atau repositori.

## Langkah

1. Muat turun dan ekstrak `GlobalFxBiasAndroid-starter.zip` menggunakan aplikasi Files/Files by Google.
2. Dalam Chrome, buka https://github.com dan log masuk atau cipta akaun.
3. Cipta repositori baharu bernama `GlobalFxBiasAndroid`. Untuk cara paling mudah, pilih **Public** (kod prototaip ini tiada rahsia). Jika mahu Private, pastikan akaun/pelan membenarkan Actions.
4. Dalam repositori, pilih **Add file → Upload files**.
5. Muat naik kandungan folder `GlobalFxBiasAndroid` yang telah diekstrak, bukan fail ZIP itu sendiri. Pastikan `app`, `build.gradle.kts`, `settings.gradle.kts`, `gradle.properties`, dan folder tersembunyi `.github/workflows/build-apk.yml` dimasukkan. Jika telefon tidak memaparkan folder `.github`, gunakan pilihan “show hidden files” dalam pengurus fail atau tambah fail workflow melalui laman GitHub.
6. Commit/upload ke branch `main`.
7. Buka tab **Actions** dalam repositori. Pilih workflow **Build Android APK**. Jika ia belum berjalan secara automatik, tekan **Run workflow → Run workflow**.
8. Tunggu sehingga job hijau (sukses). Buka run yang berjaya, pergi ke bahagian **Artifacts**, kemudian muat turun `GlobalFxBias-debug-apk`.
9. Ekstrak fail artifact ZIP yang dimuat turun. Di dalamnya terdapat `app-debug.apk`.
10. Tekan APK untuk memasang. Android mungkin meminta anda membenarkan pemasangan daripada sumber itu untuk aplikasi pelayar atau Files. Benarkan hanya jika anda yakin fail itu datang daripada build repositori anda sendiri.

## Jika gagal
- Buka run Actions yang merah dan semak log langkah `Build debug APK`.
- Jika Gradle/SDK atau plugin tidak serasi, salin mesej ralat terakhir dan minta bantuan untuk membetulkan projek.
- Jika `.github/workflows/build-apk.yml` tidak dimuat naik, Actions tidak akan nampak workflow.
- Artifak disimpan selama 7 hari dalam konfigurasi ini; muat turun APK sebelum tamat tempoh.

## Sebelum data live
Aplikasi ini belum disambungkan kepada harga pasaran, berita atau kalendar ekonomi secara langsung. API perlu ditambah kemudian, sebaiknya melalui backend HTTPS. Jangan gunakan signal demo untuk membuat keputusan kewangan.
