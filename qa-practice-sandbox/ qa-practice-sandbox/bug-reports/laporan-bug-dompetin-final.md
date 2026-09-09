# Laporan Bug — Dompetin QA Practice (Blind Test)

Ditemukan melalui manual testing & exploratory testing mandiri terhadap sandbox Dompetin v1.5, dibandingkan dengan dokumen Spesifikasi Produk yang disediakan (tanpa kisi-kisi area bug).

## Bug #01

**Title:** Transfer dana melebihi batas maksimum tetap diproses

**Environment:** Web, Chrome

**Fitur:** Transfer Dana

**Steps to Reproduce:**
1. Buka fitur Transfer Dana
2. Isi nominal di atas Rp50.000.000 (batas maksimum sesuai spesifikasi)
3. Konfirmasi dengan PIN

**Expected Result:** Sistem menolak dengan pesan error nominal melebihi batas maksimum

**Actual Result:** Transfer berhasil diproses

**Severity:** Critical

**Priority:** Urgent

---

## Bug #02

**Title:** Top up saldo melebihi batas maksimum tetap diproses

**Environment:** Web, Chrome

**Fitur:** Top Up

**Steps to Reproduce:**
1. Buka fitur Top Up
2. Isi nominal di atas Rp5.000.000 (batas maksimum sesuai spesifikasi)
3. Klik proses

**Expected Result:** Sistem menolak dengan pesan error nominal melebihi batas maksimum

**Actual Result:** Top up berhasil diproses

**Severity:** Critical

**Priority:** Urgent

**Catatan:** Jenis bug ini sama persis dengan Bug #01 (validasi batas maksimum nominal tidak berfungsi) — severity disamakan karena keduanya menyangkut risiko finansial langsung.

---

## Bug #03

**Title:** Tombol pilihan cepat nominal menggantikan nilai input, bukan menambahkannya

**Environment:** Web, Chrome

**Fitur:** Top Up

**Steps to Reproduce:**
1. Buka fitur Top Up
2. Isi nominal secara manual (contoh: Rp20.000)
3. Klik salah satu tombol pilihan cepat, misal "+Rp50.000"

**Expected Result:** Nominal pada field bertambah menjadi akumulasi dari input manual + nilai tombol cepat (Rp70.000)

**Actual Result:** Nominal pada field tergantikan sepenuhnya oleh nilai tombol cepat saja (Rp50.000), input manual sebelumnya hilang

**Severity:** Medium

**Priority:** Medium

---

## Bug #04

**Title:** Kode kupon dengan spasi di depan/belakang ditolak meski kodenya valid

**Environment:** Web, Chrome

**Fitur:** Top Up

**Steps to Reproduce:**
1. Buka fitur Top Up
2. Masukkan kode kupon aktif dengan tambahan spasi di depan atau belakang (contoh: " HEMAT20")
3. Klik "Terapkan Kupon"

**Expected Result:** Sistem tetap memproses kupon dengan benar (trim spasi otomatis sebelum validasi)

**Actual Result:** Sistem menolak dan menampilkan pesan "Kode kupon tidak valid"

**Severity:** Medium

**Priority:** Medium

---

## Bug #05

**Title:** Permintaan kirim ulang OTP tidak memiliki batas/cooldown

**Environment:** Web, Chrome

**Fitur:** Verifikasi OTP (Registrasi)

**Steps to Reproduce:**
1. Buka fitur Registrasi, lanjut ke halaman verifikasi OTP
2. Klik tombol "Kirim ulang OTP" berkali-kali secara berurutan

**Expected Result:** Sistem membatasi jumlah/frekuensi permintaan kirim ulang OTP sesuai spesifikasi (mencegah penyalahgunaan)

**Actual Result:** Permintaan kirim ulang berhasil diproses berkali-kali tanpa batasan

**Severity:** High

**Priority:** Urgent

---

## Bug #06

**Title:** Kode OTP yang sudah kedaluwarsa tetap dapat digunakan untuk verifikasi

**Environment:** Web, Chrome

**Fitur:** Verifikasi OTP (Registrasi)

**Steps to Reproduce:**
1. Buka fitur Registrasi, lanjut ke halaman verifikasi OTP
2. Tunggu hingga timer OTP mencapai 00:00 (lebih dari 5 menit)
3. Masukkan kode OTP yang benar

**Expected Result:** Sistem menolak dengan pesan kode OTP telah kedaluwarsa

**Actual Result:** Kode OTP tetap diterima dan verifikasi berhasil

**Severity:** High

**Priority:** High

---

## Bug #07

**Title:** Registrasi berhasil meski email tidak mengandung karakter "@"

**Environment:** Web, Chrome

**Fitur:** Registrasi

**Steps to Reproduce:**
1. Buka fitur Registrasi
2. Isi field email tanpa karakter "@" (contoh: "usertest.com")
3. Lengkapi field lain dan submit

**Expected Result:** Sistem menolak dengan pesan format email tidak valid

**Actual Result:** Registrasi berhasil diproses

**Severity:** High

**Priority:** High

---

## Bug #08

**Title:** Registrasi berhasil meski password hanya berisi angka (tanpa huruf)

**Environment:** Web, Chrome

**Fitur:** Registrasi

**Steps to Reproduce:**
1. Buka fitur Registrasi
2. Isi field password hanya dengan angka (contoh: "12345678"), minimal 8 karakter
3. Lengkapi field lain dan submit

**Expected Result:** Sistem menolak dan menampilkan pesan bahwa password harus mengandung kombinasi huruf dan angka

**Actual Result:** Registrasi berhasil diproses meski password hanya berisi angka

**Severity:** High

**Priority:** High

---

## Bug #09

**Title:** Edit profil berhasil meski nomor HP kurang dari jumlah digit yang wajar

**Environment:** Web, Chrome

**Fitur:** Edit Profil

**Steps to Reproduce:**
1. Buka fitur Edit Profil
2. Ubah nomor HP dengan input kurang dari jumlah digit normal (contoh: "123")
3. Simpan perubahan

**Expected Result:** Sistem menolak dengan pesan nomor HP tidak valid

**Actual Result:** Perubahan tersimpan tanpa validasi

**Severity:** Medium

**Priority:** Medium

---

## Bug #10

**Title:** Edit profil berhasil meski seluruh field diisi dengan angka (termasuk nama dan email)

**Environment:** Web, Chrome

**Fitur:** Edit Profil

**Steps to Reproduce:**
1. Buka fitur Edit Profil
2. Isi field nama, email, dan nomor HP seluruhnya dengan angka
3. Simpan perubahan

**Expected Result:** Sistem menolak dengan pesan format data tidak sesuai jenis field

**Actual Result:** Perubahan profil berhasil disimpan

**Severity:** High

**Priority:** Medium

---

## Bug #11

**Title:** Kursor input berpindah/hilang saat mengetik di field Riwayat Transaksi & Cari Transaksi

**Environment:** Web, Chrome

**Fitur:** Riwayat Transaksi / Cari Transaksi

**Steps to Reproduce:**
1. Buka fitur Riwayat Transaksi atau Cari Transaksi
2. Ketik nama transaksi di field pencarian

**Expected Result:** Kursor tetap berada di posisi yang benar selama pengetikan berlangsung

**Actual Result:** Kursor hilang/berpindah setiap kali karakter diketik, mengganggu pengalaman pengetikan

**Severity:** Medium

**Priority:** Medium

**Catatan:** Riwayat Transaksi dan Cari Transaksi mengarah ke layar yang sama, sehingga digabung menjadi satu laporan. Ditemukan lewat eksplorasi mandiri, di luar area yang diarahkan.

---

## Bug #12

**Title:** Field Konfirmasi PIN Baru tidak dicocokkan dengan field PIN Baru sebelum disimpan

**Environment:** Web, Chrome

**Fitur:** Ubah PIN

**Steps to Reproduce:**
1. Buka fitur Ubah PIN
2. Isi PIN Lama dengan benar
3. Isi PIN Baru dan Konfirmasi PIN Baru dengan angka yang berbeda satu sama lain
4. Simpan

**Expected Result:** Sistem menolak dan menampilkan pesan error bahwa PIN baru dan konfirmasi tidak sama

**Actual Result:** Perubahan PIN tetap berhasil diproses meski kedua field tidak cocok

**Severity:** High

**Priority:** High

---

## Bug #13

**Title:** Field PIN menerima karakter huruf, bukan hanya angka

**Environment:** Web, Chrome

**Fitur:** Ubah PIN

**Steps to Reproduce:**
1. Buka fitur Ubah PIN
2. Isi salah satu field PIN dengan karakter huruf (bukan angka)
3. Submit

**Expected Result:** Sistem menolak dengan pesan PIN harus berupa angka

**Actual Result:** Input huruf diterima dan proses ubah PIN tetap berhasil

**Severity:** High

**Priority:** High

**Catatan:** Ditemukan melalui exploratory testing di luar area yang diarahkan.

---

## Catatan / Perlu Klarifikasi ke Product Owner (Bukan Bug Pasti)

### Ubah PIN dengan PIN baru yang sama dengan PIN lama tetap diproses

**Fitur:** Ubah PIN

**Observasi:** Sistem tetap memproses perubahan PIN meski PIN baru yang dimasukkan sama persis dengan PIN lama.

**Kenapa ini bukan bug pasti:** Dokumen Spesifikasi Produk tidak menyebutkan aturan bahwa PIN baru harus berbeda dari PIN lama. Ini perlu dikonfirmasi ke Product Owner sebagai potensi requirement yang belum tercakup, bukan langsung diklaim sebagai penyimpangan dari spesifikasi.

---

## Ringkasan

Total **13 bug valid** ditemukan dari pengujian menyeluruh terhadap seluruh alur aplikasi (Transfer Dana, Top Up, Registrasi, Verifikasi OTP, Ubah PIN, Edit Profil, Riwayat/Cari Transaksi), dibandingkan langsung dengan dokumen Spesifikasi Produk tanpa arahan area bug sebelumnya (blind test). 2 di antaranya (Bug #11 dan #13) ditemukan melalui exploratory testing mandiri di luar area yang diarahkan.
