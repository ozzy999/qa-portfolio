# Exploratory Testing Charter — Flow OTP Registrasi

**Charter:** Jelajahi flow verifikasi OTP pada fitur registrasi akun selama 30 menit, fokus pada interaksi antara waktu expired OTP (5 menit) dan aksi berulang oleh user.

**Durasi:** 30 menit
**Area fokus:** Verifikasi OTP setelah registrasi

## Hal yang Dicoba (Test Ideas)

1. Buka 2 tab/device berbeda, request OTP di keduanya secara bersamaan — cek OTP mana yang tetap valid.
2. Matikan koneksi internet tepat saat submit OTP, lalu nyalakan kembali — cek apakah status verifikasi konsisten.
3. Copy-paste kode OTP dengan tambahan spasi di depan/belakang — cek apakah sistem melakukan trim otomatis.
4. Minta kirim ulang OTP 5x berturut-turut dalam waktu singkat — cek apakah ada rate limiting.
5. Masukkan OTP tepat 1 detik setelah waktu expired (5:01) — cek apakah sistem menolak dengan benar.

## Temuan (diisi setelah eksekusi)

| # | Temuan | Klasifikasi |
|---|---|---|
| 1 | [isi hasil temuan] | Bug / Observasi / Sesuai ekspektasi |
| 2 | [isi hasil temuan] | Bug / Observasi / Sesuai ekspektasi |

## Catatan
Exploratory testing tidak menggantikan scripted test case — charter ini melengkapi test case yang sudah dibuat sebelumnya dengan menjelajahi kombinasi kondisi yang tidak selalu terpikirkan saat menulis test case formal.
