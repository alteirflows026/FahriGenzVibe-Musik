# Flutter client for FahriGenzVibe

Simple Flutter app that mencari lagu menggunakan iTunes Search API dan memutar preview audio.

Langkah menjalankan:

1. Pastikan Anda sudah memasang Flutter dan toolchain.
2. Masuk ke folder `flutter_app`:

```bash
cd flutter_app
flutter pub get
flutter run
```

Catatan:
- Aplikasi ini langsung memanggil `https://itunes.apple.com/search` dari klien.
- Jika ingin menggunakan proxy lokal (mis. `app.py`), Anda perlu menyesuaikan endpoint di `lib/main.dart`.
 - Aplikasi ini langsung memanggil `https://itunes.apple.com/search` dari klien.
 - Terdapat fitur Playlist yang dapat disinkronkan dengan backend Flask melalui endpoint `/api/playlists`.
 - Untuk mengakses server lokal dari emulator Android gunakan `serverBase = 'http://10.0.2.2:8000'` di `lib/main.dart`.
 - Untuk menyimpan playlist per-user, buka dialog username (ikon pengguna di pojok kanan atas) dan masukkan nama pengguna. Playlist akan tersimpan terpisah untuk setiap username.
