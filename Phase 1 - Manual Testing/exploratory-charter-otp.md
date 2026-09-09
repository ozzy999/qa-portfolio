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
| 1 | Permintaan kirim ulang OTP tidak memiliki batas/cooldown — bisa diklik berkali-kali tanpa jeda | Bug |
| 2 | Kode OTP yang sudah kedaluwarsa (setelah timer 5 menit habis) tetap dapat digunakan untuk verifikasi | Bug |
| 3 | Kode OTP yang benar tetap diverifikasi dengan sukses selama masih dalam batas waktu | Sesuai ekspektasi |

## Catatan
Exploratory testing tidak menggantikan scripted test case — charter ini melengkapi test case yang sudah dibuat sebelumnya dengan menjelajahi kombinasi kondisi yang tidak selalu terpikirkan saat menulis test case formal.
