# Bug Report #03

**Title:** Notifikasi "Login berhasil" tetap muncul walau login gagal karena timeout server

**Environment:** Windows 11, Chrome v127

**Steps to Reproduce:**
1. Matikan/lambatkan koneksi internet sesaat sebelum klik "Masuk"
2. Klik "Masuk" dengan kredensial valid saat koneksi lambat
3. Tunggu hingga request timeout

**Expected Result:** Muncul pesan error "Koneksi bermasalah, coba lagi" — user tetap di halaman login

**Actual Result:** Notifikasi toast "Login berhasil" sempat muncul sekilas, padahal user tidak benar-benar masuk ke dashboard

**Severity:** Medium (membingungkan user, bukan kehilangan data)

**Priority:** Medium

**Attachment:** [screen recording]
