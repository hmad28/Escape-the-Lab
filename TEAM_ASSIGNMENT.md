# Escape the Lab · Team Assignment

Pembagian fungsi untuk tim kecil. Nama PIC diisi saat kickoff setelah akses serta kapasitas orangnya disepakati. Satu orang boleh memegang beberapa fungsi. Setiap tiket atau aset punya satu PIC utama.

| Fungsi | PIC nama | Deliverable M1 | Reviewer / serah terima |
|---|---|---|---|
| Lead / Producer | TBD | Owner place/repo, izin, scope, jadwal, triage blocker, keputusan go/no-go | Terima rangkuman QA dan status dependency |
| Game Design | TBD | Aturan GDD, tuning awal capture/rescue/slow dan hasil ronde | Lead dan Gameplay memeriksa dampak teknis |
| Gameplay Engineering | TBD | Match state, objective, capture, rescue, mutasi, gate, practice, validation, cleanup | QA menjalankan kasus server dan multiplayer |
| Map / Environment | TBD | Lobby, hub, Red, routing, tag dan prefab map | Gameplay memeriksa kontrak, QA memeriksa rute |
| Character / Animation | TBD | Tiga role, rig, locomotion, capture, slow, mutasi | Gameplay memeriksa action timing, Art memeriksa siluet |
| UI / Client | TBD | Lobby, practice prompts, HUD role, touch, spectator dan results | QA menguji PC dan HP |
| Art / VFX / Audio | TBD | Style proof Red, signage, material, VFX dan cue gameplay | QA memeriksa readability dan dampak performa |
| QA / Playtest | TBD | Build matrix, sesi 1–4 pemain, bukti, triage dan retest | Lead memutuskan milestone berdasarkan hasil |

## Handoff

| Alur | Yang diserahkan | Kapan reviewer masuk |
|---|---|---|
| Map → Gameplay | Scene blockout, ID/tag, screenshot rute, ukuran dan daftar prefab | Sebelum scripting mengandalkan anchor atau profil |
| Character → Gameplay | Rig, root/pivot, daftar klip dan timing cue | Saat pose capture/slow sudah bisa dipraktikkan |
| Gameplay → UI | State yang boleh ditampilkan, aksi per role, hasil/penolakan | Saat lobby dan role yang sama bisa diuji pada beberapa client |
| Art/Audio → integrator | Sumber, ekspor/model, preview, trigger, loop dan lisensi | Sebelum aset dipakai di scene tes |
| Build → QA | Build/place, daftar perubahan, scope, known issues dan perangkat target | Sebelum sesi multiplayer dijadwalkan |

Isi nama di sini, lalu cantumkan PIC pada [backlog](DEVELOPMENT_BACKLOG.md) atau [tracker aset](ASSET_TRACKER.md) ketika pekerjaan ditarik. Lead mencatat keputusan produk yang mengubah GDD beserta ID tiket terdampak. Reviewer mencatat bukti atau feedback pada tiket/entri terkait agar status bisa dipakai lintas fungsi.
