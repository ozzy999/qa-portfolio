# QA Practice Sandbox — Dompetin Simulator

Sebuah aplikasi fintech simulasi ("Dompetin") yang saya bangun dengan bantuan AI sebagai lingkungan latihan pribadi untuk mempraktikkan manual testing dan exploratory testing pada skenario yang menyerupai fitur nyata (transfer dana, top up saldo, registrasi & verifikasi OTP, ubah PIN, edit profil, riwayat transaksi).

## Konteks

Folder ini **bukan produk/aplikasi yang saya kembangkan sebagai developer** — ini adalah sandbox testing yang dibangun dengan bantuan AI, khusus untuk kebutuhan latihan QA saya. Tujuannya membuat lingkungan yang bisa diuji berulang kali secara bebas, dengan skenario yang relevan ke domain fintech (sesuai target karier saya), tanpa risiko menguji aplikasi produksi sungguhan.

Pengujian dilakukan sebagai **blind test** — saya hanya diberi dokumen spesifikasi produk (requirement tertulis per fitur), tanpa diberi tahu di mana letak bug-nya, persis seperti kondisi kerja QA sungguhan.

## Yang Saya Kerjakan Sendiri

- Melakukan exploratory testing & manual testing terhadap seluruh alur aplikasi
- Membandingkan perilaku sistem dengan dokumen Spesifikasi Produk yang disediakan di dalam sandbox
- Menemukan bug secara mandiri, tanpa diberi tahu area yang bermasalah
- Menulis laporan bug profesional (title, environment, steps to reproduce, expected/actual result, severity, priority)
- Menentukan severity & priority berdasarkan reversibilitas dampak, potensi disalahgunakan, dan skala dampak ke user

Hasil temuan bug ada di folder [`bug-reports/`](./bug-reports).

## Cara Menjalankan

File `dompetin-simulator.html` bisa langsung dibuka di browser apa pun tanpa instalasi:

```bash
# Clone repo, lalu buka file secara langsung di browser
open dompetin-simulator.html
```

Aplikasi mencakup 7 alur utama: Dashboard, Transfer Dana, Top Up Saldo, Registrasi + Verifikasi OTP, Ubah PIN, Edit Profil, dan Riwayat/Cari Transaksi — lengkap dengan dokumen Spesifikasi Produk dan panel pencatat laporan bug bawaan (tersimpan otomatis di sesi browser).

## Tech Stack

HTML, CSS, dan vanilla JavaScript — dipilih agar sandbox bisa dijalankan langsung tanpa build process, fokus waktu saya ke aktivitas testing, bukan setup environment.

## Isi Folder

| File/Folder | Deskripsi |
|---|---|
| `dompetin-simulator.html` | Source code sandbox aplikasi |
| `bug-reports/laporan-bug-dompetin-final.md` | Laporan bug hasil temuan mandiri saya |
