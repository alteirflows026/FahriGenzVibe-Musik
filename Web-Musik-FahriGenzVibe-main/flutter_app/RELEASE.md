# Rilis Aplikasi Flutter (Android & iOS)

Panduan singkat untuk membangun dan merilis aplikasi Flutter (`flutter_app`).

Persiapan umum:
- Pastikan Flutter SDK dan toolchain terpasang dan up-to-date.
- Jalankan `flutter doctor` untuk memastikan environment bersih.
- Perbarui `version` di `pubspec.yaml` sesuai versi rilis.

Android (build release APK / AAB):

1. Siapkan signing (recommended): Buat `key.jks` dan tambahkan konfigurasi signing ke `android/app/build.gradle` dan `~/.gradle/gradle.properties`.

2. Build APK (debug / release):

```bash
cd flutter_app
flutter build apk --release
# atau build app bundle (AAB) untuk Play Store
flutter build appbundle --release
```

3. File output:
- APK: `build/app/outputs/flutter-apk/app-release.apk`
- AAB: `build/app/outputs/bundle/release/app-release.aab`

Catatan jaringan: jika aplikasi butuh akses ke server lokal (mis. Flask dev server di host), pada emulator Android gunakan `10.0.2.2` sebagai `serverBase` di `lib/main.dart`. Untuk perangkat fisik, gunakan IP LAN dari mesin host (mis. `http://192.168.1.100:8000`).

iOS (build release):

1. Buka `ios/Runner.xcworkspace` di Xcode.
2. Pilih target signing (Team) dan provisioning profile.
3. Pilih `Generic iOS Device` dan pilih `Product → Archive` untuk membuat archive.
4. Upload ke App Store Connect lewat Xcode Organizer.

Atau perintah CLI (butuh macOS):

```bash
cd flutter_app
flutter build ios --release
```

Pengujian & CI:
- Disarankan menggunakan GitHub Actions atau Codemagic untuk membangun artifact release otomatis.

Tip distribusi internal:
- Untuk Android: kirimkan APK langsung ke tester.
- Untuk iOS: gunakan TestFlight via App Store Connect.
