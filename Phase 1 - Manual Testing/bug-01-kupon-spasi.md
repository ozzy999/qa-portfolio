# Bug Report #01

**Title:** Field kupon menerima spasi di awal input sehingga kode valid ditolak sistem

**Environment:** Android 14, App v3.2.1, koneksi WiFi

**Steps to Reproduce:**
1. Buka halaman checkout
2. Pada field "Kode Kupon", ketik spasi lalu kode kupon valid (contoh: " DISKON10")
3. Klik "Terapkan"

**Expected Result:** Sistem otomatis trim spasi, kupon berhasil diterapkan

**Actual Result:** Muncul pesan "Kode kupon tidak valid" walau kode benar

**Severity:** Medium (mengganggu konversi, tapi ada workaround hapus spasi manual)

**Priority:** Medium

**Attachment:** [screenshot pesan error]
