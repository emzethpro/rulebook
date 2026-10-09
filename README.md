# Rulebook (HTML)

Aplikasi ini berjalan sebagai frontend statis (`index.html`) untuk mengekstrak *voice rulebook* dari kumpulan tweet.

## Provider & model

UI kini mendukung dua provider:

- **Direct API**: kirim request ke base URL chat-completions kompatibel OpenAI
- **OpenRouter**: kirim request ke endpoint OpenRouter dengan header aplikasi opsional

Daftar model default bersifat konfiguratif (string) dan bisa diubah langsung di UI. Nilai awal:

- `gpt-astra-6`
- `opus-5.5`
- `glm-5.3`

> Catatan: identifier model diperlakukan sebagai string konfigurasi, tidak diasumsikan tersedia resmi.

## Penyimpanan konfigurasi

Konfigurasi disimpan via `localStorage` (`rulebook_settings_v2`) untuk:

- provider aktif
- daftar model
- endpoint/base URL
- model terpilih
- opsi OpenRouter dan mock mode

API key **tidak disimpan** kecuali pengguna mencentang opsi **Remember API key in this browser**.

## Keamanan frontend statis

Karena aplikasi berjalan di browser:

- API key tetap bisa terekspos pada perangkat/browser pengguna.
- Jangan gunakan key produksi tanpa pembatasan (scope, quota, rotasi).
- Jangan commit API key ke repository.

## Mock mode

Aktifkan **Mock mode** untuk menguji alur UI tanpa API key dan tanpa request jaringan.

## Manual verification

1. Buka `/home/runner/work/rulebook/rulebook/index.html` di browser.
2. Pastikan pilihan provider hanya **Direct API** dan **OpenRouter**.
3. Verifikasi daftar model awal berisi `gpt-astra-6`, `opus-5.5`, `glm-5.3`.
4. Ubah daftar model, klik **Apply list**, refresh halaman, pastikan tersimpan.
5. Uji validasi:
   - model kosong
   - URL endpoint/base URL tidak valid
   - API key kosong saat mock mode mati
6. Aktifkan mock mode dan jalankan ekstraksi tanpa API key.
7. Nonaktifkan mock mode, isi API key + endpoint valid, jalankan request ke provider.
