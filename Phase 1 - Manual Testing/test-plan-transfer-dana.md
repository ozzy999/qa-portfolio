## 1. Objective
Memastikan fitur transfer dana berfungsi sesuai requirement dan aman dari risiko finansial sebelum dianggap layak rilis.

## 2. Scope

**In Scope:**
- Form input nominal transfer
- Validasi PIN 6 digit
- Validasi saldo cukup/tidak cukup
- Update saldo setelah transfer berhasil
- Riwayat transaksi setelah transfer

**Out of Scope:**
- Proses tambah rekening tujuan baru
- Notifikasi push/email setelah transfer
- Transfer antar bank (hanya transfer internal pada siklus ini)

## 3. Test Strategy

| Jenis Testing | Alasan |
|---|---|
| Functional | Memastikan alur transfer bekerja sesuai requirement dasar |
| Negative | Memastikan sistem menolak input tidak valid dengan benar |
| Boundary Value | Nominal transfer punya batas min/max yang wajib diverifikasi presisi |
| Integration | Saldo & riwayat transaksi harus konsisten lintas halaman |

## 4. Test Environment & Data

- Environment: Staging / aplikasi latihan
- Akun testing: 1 akun saldo cukup, 1 akun saldo tidak cukup
- Data: Nominal transfer Rp10.000 – Rp50.000.000, PIN 6 digit

## 5. Roles & Responsibilities

- QA: menulis test case, eksekusi, melaporkan bug
- Developer: memperbaiki bug yang dilaporkan

## 6. Timeline

- Test case design: [isi durasi]
- Eksekusi: [isi durasi]

## 7. Exit Criteria

Seluruh test case dengan priority High berstatus Pass, dan tidak ada bug berstatus Critical/High yang masih terbuka.
