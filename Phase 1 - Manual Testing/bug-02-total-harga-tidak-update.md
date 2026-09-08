# Bug Report #02

**Title:** Harga total tidak update saat quantity produk diubah lewat tombol "+" secara cepat berulang

**Environment:** iOS 17, Safari, App versi web

**Steps to Reproduce:**
1. Buka halaman keranjang belanja
2. Klik tombol "+" pada quantity produk sebanyak 5x dengan cepat (< 1 detik antar klik)

**Expected Result:** Quantity dan total harga bertambah sesuai jumlah klik

**Actual Result:** Quantity bertambah, tapi total harga di bagian bawah tidak ikut update (masih harga lama) sampai halaman di-refresh

**Severity:** High (user bisa salah paham soal total bayar)

**Priority:** High

**Attachment:** [video singkat merekam bug]
