# Test Cases — Fitur Transfer Dana

Requirement: Transfer dana ke rekening tujuan. Nominal minimal Rp10.000, maksimal Rp50.000.000 per transaksi. Konfirmasi via PIN 6 digit. Jika saldo tidak cukup, transfer ditolak. Setelah berhasil, saldo berkurang dan transaksi muncul di riwayat.

| ID | Test Case | Teknik | Steps | Expected Result | Priority | Alasan Priority |
|---|---|---|---|---|---|---|
| TC-01 | Transfer berhasil dengan saldo & PIN benar | Equivalence (valid) | 1. Input nominal Rp500.000 2. Input PIN benar 3. Konfirmasi | Transfer berhasil, saldo berkurang | High | Fitur inti, terjadi di setiap transaksi normal |
| TC-02 | Transfer ditolak — nominal Rp9.999 (di bawah minimum) | Boundary | Input nominal Rp9.999, konfirmasi | Ditolak, pesan "Nominal minimum Rp10.000" | High | Celah validasi di titik batas berisiko besar jika lolos |
| TC-03 | Transfer berhasil — nominal Rp10.000 (tepat batas minimum) | Boundary | Input nominal Rp10.000, konfirmasi | Berhasil | High | Titik boundary paling rawan bug off-by-one |
| TC-04 | Transfer berhasil — nominal Rp50.000.000 (tepat batas maksimum) | Boundary | Input nominal Rp50.000.000, konfirmasi | Berhasil | High | Titik boundary maksimum, dampak finansial besar |
| TC-05 | Transfer ditolak — nominal Rp50.000.001 (di atas maksimum) | Boundary | Input nominal Rp50.000.001, konfirmasi | Ditolak, pesan "Nominal maksimum Rp50.000.000" | High | Jika lolos, risiko finansial signifikan |
| TC-06 | Transfer ditolak — saldo tidak cukup | Decision table | Saldo < nominal transfer, konfirmasi | Ditolak, pesan "Saldo tidak cukup" | High | Skenario sangat sering terjadi di penggunaan nyata |
| TC-07 | Transfer ditolak — PIN salah | Equivalence (invalid) | Input PIN salah, konfirmasi | Ditolak, pesan "PIN salah", saldo tidak berkurang | High | Keamanan transaksi, wajib teruji ketat |
| TC-08 | Validasi — PIN kurang dari 6 digit | Boundary | Input PIN 5 digit | Tombol konfirmasi disabled / muncul validasi | Medium | Dampak sedang, biasanya sudah dicegah UI |
| TC-09 | Saldo berkurang sesuai nominal setelah transfer sukses | Functional + data validation | Transfer sukses, cek saldo baru | Saldo baru = saldo lama − nominal | High | Integritas data finansial, wajib akurat |
| TC-10 | Transaksi muncul di riwayat setelah berhasil | Integration | Cek halaman riwayat setelah transfer | Riwayat menampilkan transaksi baru dengan nominal & waktu benar | Medium | Penting untuk transparansi user, dampak tidak langsung ke saldo |

## Catatan Metodologi

Priority ditentukan menggunakan pendekatan **risk-based testing**: Impact (seberapa parah jika gagal) × Likelihood (seberapa sering skenario ini terjadi di dunia nyata). Skenario boundary (TC-02 s/d TC-05) sengaja dipecah menjadi 4 test case terpisah karena bug paling sering muncul tepat di titik batas, bukan di tengah rentang nilai yang valid.
