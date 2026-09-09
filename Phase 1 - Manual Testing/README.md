# Fase 1 — Manual Testing Fundamentals

Dokumentasi latihan **test design** (perencanaan pengujian) sebagai bagian dari transisi karier saya ke QA Engineer — mencakup test plan formal, test case dengan prioritas berbasis risk analysis (impact × likelihood), dan exploratory testing charter.

## Konteks

File di folder ini adalah latihan menulis test plan dan test case **dari dokumen requirement/spesifikasi tertulis**, sebelum aplikasinya tersedia untuk dieksekusi langsung — ini praktik umum di dunia kerja nyata, di mana QA sering merancang skenario pengujian berdasarkan requirement/user story sebelum fitur selesai dikembangkan.

Studi kasus disusun menyerupai fitur aplikasi fintech (transfer dana, verifikasi OTP), relevan dengan role QA Engineer yang menjadi target karier saya.

**Untuk bukti eksekusi pengujian nyata dan bug report asli**, lihat folder [`qa-practice-sandbox/`](../qa-practice-sandbox) — di sana saya menguji aplikasi simulasi secara langsung (blind testing, tanpa kisi-kisi) dan menemukan 13 bug valid secara mandiri.

## Isi Folder

| File | Deskripsi |
|---|---|
| `test-plan-transfer-dana.md` | Test plan formal untuk fitur transfer dana |
| `test-cases-transfer-dana.md` | 10 test case dengan priority & alasan risk-based |
| `exploratory-charter-otp.md` | Exploratory testing charter untuk flow OTP |

## Teknik yang Digunakan

- STLC (Software Testing Life Cycle)
- Equivalence Partitioning
- Boundary Value Analysis
- Decision Table Testing
- Risk-Based Test Prioritization (Impact × Likelihood)
- Exploratory Testing (Session-Based Charter)
