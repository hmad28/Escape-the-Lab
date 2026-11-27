# Escape the Lab · Development Backlog

Gunakan ID kickoff [GDD §16](ESCAPE_THE_LAB_GDD.md#16-roadmap-dan-backlog-mvp). Fungsi yang tercantum memegang tanggung jawab awal. Nama PIC ditetapkan menurut [Team Assignment](TEAM_ASSIGNMENT.md). Bukti acceptance memakai ID pada [Playtest Checklist](PLAYTEST_CHECKLIST.md).

## Urutan kerja

`Ready` berarti dependency dan acceptance jelas. Setelah ditarik oleh PIC, gunakan `In Progress → Review → Playtest → Done`. Catat blocker pada tiket. Untuk PR atau serah terima, lampirkan daftar perubahan, build yang diuji dan bukti acceptance.

| ID | Fase | Pekerjaan | PIC fungsi | Dependency utama | Acceptance / bukti |
|---|---|---|---|---|---|
| ETL-001 | M0 · P0 | Place, repo & izin | Lead | — | Owner, place staging, dan akses tim dicatat. |
| ETL-002 | M1 · P0 | Konfigurasi, state match, reservasi arena | Gameplay | 001 | Pilih mode dan profil, kunci roster, satu arena dan cleanup. QA-01/02/25. |
| ETL-003 | M1 · P0 | Role, spawn dan head start | Gameplay | 002, 004 | Satu Subject Zero pada ronde kompetitif dan spawn valid. QA-02/25. |
| ETL-004 | M1 · P0 | Lobby, hub, Red dan tabung publik | Map | 001 | Profil satu zona lulus validator dan walkthrough. QA-03/16. |
| ETL-005 | M1 · P0 | Keycard dan pintu | Gameplay | 002, 004 | Pickup atomik, akses tim, penolakan sebelum unlock. QA-03/04. |
| ETL-006 | M1 · P0 | Genset dan kontribusi | Gameplay | 002, 004 | Kontribusi hold bisa berhenti dan dilanjutkan. Genset aktif permanen. QA-05/06. |
| ETL-007 | M1 · P0 | Capture dan alokasi tabung | Gameplay | 003, 004 | Hanya capture valid mengisi satu tube. QA-07/16. |
| ETL-008 | M1 · P0 | Rescue dan deadline infeksi | Gameplay | 007 | Hold 3 detik, deadline 45 detik, penentuan hasil sekali dan proteksi. QA-08/09/10/18. |
| ETL-009 | M1 · P0 | Role Mini-Mutant dan slow | Gameplay | 008 | Mutasi sekali, tabung bebas dan slow mengikuti aturan immunity. QA-09/19. |
| ETL-010 | M2 · P0 | Facility 07 tiga zona | Map | 004, M1 lulus | S1–S6, T1–T6, semua tags, gate dan tiga loop. QA-03/06/16/20. |
| ETL-011 | M1/M2 · P0 | Adrenaline Rush, lalu Lockdown | Gameplay | 003, 006. Lockdown juga 010 | M1 +5% per genset. M2 Lockdown 10 detik dan cooldown 45 detik. QA-06/11. |
| ETL-012 | M2 · P0 | Vent dan routing | Gameplay + Map | 005, 010 | Enam mulut, link dua arah dan kedua zona wajib unlocked. QA-11/17. |
| ETL-013 | M1 · P0 | Gate, escape dan results | Gameplay + UI | 002, 006, 009 | Gate delay 5 detik, end-state, timeout dan disconnect konsisten. QA-06/12/14/26. |
| ETL-014 | M1/M2 · P0 | HUD role dan snapshot | UI | 002, 003, 007–009, 013 | UI mengikuti role/status. M2 memuat tiga zona dan Lockdown. QA-15/22. |
| ETL-015 | M1/M2 · P0 | Kontrol mobile | UI | 014 | Semua aksi yang tersedia dapat dimainkan di HP. Ulangi untuk skill dan vent M2. QA-15. |
| ETL-016 | M1/M2 · P0 | Validation, resync dan cleanup | Gameplay + QA | 002, 007, 013, 024 | Payload invalid ditolak, state bersih setelah sesi, resync sesuai mode. QA-02/12/13/18/22/26. |
| ETL-017 | M1/M2 · P0 | Uji camping tabung/gate | Design + Map | 004, 007, 013. Ulangi setelah 010 | Dua pendekatan teruji, temuan dan revisi routing didokumentasikan. QA-16/20. |
| ETL-018 | M3 · P0 | Closed alpha | QA | M2 P0 selesai | Matrix P0 lulus, 10 sesi beruntun bersih dan blocker dicatat. |
| ETL-019 | M4 · P1 | Polish karakter dan environment | Art | ETL-018 | Siluet, kontras, clipping dan performa HP direview. |
| ETL-020 | M4 · P1 | Polish audio dan aksesibilitas | Client + Art | 014, 018 | Cue masih terbaca saat audio/efek dikurangi. |
| ETL-021 | M4 · P1 | XP dan persistence | Gameplay | 013, 016, 018 | Reward idempotent, latihan atau ronde batal tidak diberi XP kompetitif, data lama aman. QA-21/22/23. |
| ETL-022 | M4 · P1 | Telemetry dan balancing | Design + QA | 018 | Pisahkan mode dan roster awal. Catat hasil sebelum/sesudah mutasi pertama. |
| ETL-023 | M5 · P1 | Closed beta dan release checklist | Lead + QA | 018–022 | Release build diperiksa, lisensi aset, performa dan blocker direview. |
| ETL-024 | M1 · P0 | Latihan solo/co-op dan transisi | Gameplay + UI | 002, 004–008, 013–015 | Co-op consent, satu skenario rescue, latihan kembali ke lobby dan clean handoff ke ronde. QA-23/24. |

Dependency memakai tiga digit dari ID ETL. ETL-016 berjalan sejak kontrak dasar tersedia dan lolos akhir setelah latihan siap. Untuk M1, HUD serta kontrol dapat diintegrasikan bersamaan dengan mechanic yang sudah punya state stabil.

## Format tiket

- **Deliverable** dan pemain yang terdampak.
- **Dependency** berupa ID tiket, versi kontrak map, atau ID aset.
- **Acceptance** berupa langkah uji, hasil yang harus terlihat dan perangkat atau roster.
- **Bukti** berupa build, clip, screenshot atau log dan hasil reviewer.
