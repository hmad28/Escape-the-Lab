# ESCAPE THE LAB (ETL)

> **Master Game Design Document + Technical Design Document**  
> Roblox • Asymmetrical Survival Horror • Multiplayer  
> **Tagline:** Escape together. Or become the threat.

| Metadata | Keterangan |
|---|---|
| Judul | Escape the Lab (ETL) |
| Versi dokumen | v0.3 — Spesifikasi pre-production |
| Tanggal | 28 November 2026 |
| Konsep awal | Fathan Dzaki (berdasarkan GDD yang dibagikan) |
| Inisiatif kolaborasi | Komunitas Hammad Studio (usulan) |
| Target platform | Roblox, PC & Mobile |
| Genre | Asymmetrical Survival, Infection, Horror-lite |
| Target pemain MVP | Ronde 5–6 pemain, 1 Subject Zero melawan 4–5 Scientists. Latihan opsional untuk 1–2 peserta selama menunggu. |
| Status | Pre-production; belum diimplementasikan / diuji |

**Cara membaca dokumen.** **[BASE]** menandai inti dari penjelasan Fathan di WhatsApp 27 November 2026. **[PROPOSAL]** menandai detail tim. Roster 5–6 diambil dari contoh Fathan. Jumlah kartu, format latihan dan angka timer adalah baseline prototipe.

## Daftar isi

1. [Visi produk](#1-visi-produk)
2. [Game pillars dan target pemain](#2-game-pillars-dan-target-pemain)
3. [Lore dan atmosfer](#3-lore-dan-atmosfer)
4. [Core gameplay loop](#4-core-gameplay-loop)
5. [Faksi, karakter, dan balancing](#5-faksi-karakter-dan-balancing)
6. [Objective dan interaksi](#6-objective-dan-interaksi)
7. [Infection dan rescue system](#7-infection-dan-rescue-system)
8. [Map design blueprint](#8-map-design-blueprint)
9. [Match flow dan edge cases](#9-match-flow-dan-edge-cases)
10. [UI/UX dan kontrol](#10-uiux-dan-kontrol)
11. [Art direction dan audio](#11-art-direction-dan-audio)
12. [Progression dan monetisasi](#12-progression-dan-monetisasi)
13. [Technical Design Document](#13-technical-design-document)
14. [Keamanan, performa, dan QA](#14-keamanan-performa-dan-qa)
15. [Pembagian tim dan workflow](#15-pembagian-tim-dan-workflow)
16. [Roadmap dan backlog MVP](#16-roadmap-dan-backlog-mvp)
17. [Playtest dan success metrics](#17-playtest-dan-success-metrics)
18. [Risiko dan keputusan terbuka](#18-risiko-dan-keputusan-terbuka)
19. [Referensi](#19-referensi)

---

## 1. Visi produk

### 1.1 High concept [BASE]

Scientists terjebak di Facility 07. Satu pemain jadi anomali bernama Subject Zero. Pemain lain mencari kunci yang langsung membuka gate evakuasi. Scientist yang tertangkap bisa diselamatkan sebelum timer habis. Jika gagal diselamatkan, ia menjadi Mini-Mutant dan bergabung ke tim anomali.

### 1.2 Unique selling proposition

**Kekalahan bukan akhir permainan, tetapi awal peran yang baru.**

Pemain yang tertangkap dimasukkan ke Infection Tube. Rekan satu tim dapat menyelamatkannya sebelum waktu habis. Jika gagal, pemain tersebut berubah menjadi Mini-Mutant dan ikut memburu Scientists yang sebelumnya menjadi rekannya.

Dengan begitu, ETL menggabungkan pengejaran, kerja sama, manajemen risiko, dan perubahan faksi secara dinamis. Match yang dimulai sebagai 1 vs 6 dapat berakhir sebagai 5 vs 2 atau bahkan 6 vs 1.

### 1.3 Positioning [PROPOSAL]

- Mudah dipahami dalam satu match, tetapi sulit dikuasai secara taktis.
- Horror yang mengandalkan atmosfer, audio, dan ketegangan, bukan gore.
- Cocok untuk momen lucu, panik, pengkhianatan karena infeksi, serta konten pendek kreator Roblox.
- Prioritaskan pengalaman multiplayer yang stabil dibanding banyak map atau fitur kosmetik pada versi pertama.

## 2. Game pillars dan target pemain

| Pillar | Implementasi |
|---|---|
| **Nobody sits out early** | Scientist yang tertangkap dapat diselamatkan atau melanjutkan sebagai mutant. Pemain yang sudah kabur menjadi spectator hingga match selesai. |
| **Teamwork under pressure** | Pemain harus membagi tugas antara mencari kunci dan menyelamatkan teman. |
| **Escalating threat** | Jumlah mutant bertambah bila korban tidak terselamatkan. |
| **Meaningful counterplay** | Ventilasi, rute alternatif, suara ancaman, dan batas kemampuan mutant memberi kesempatan melawan secara taktis. |
| **Readable chaos** | Warna zona, simbol, HUD, dan audio membantu pemain memahami situasi walau sedang dikejar. |

Target: pemain Roblox yang menyukai survival multiplayer, horror-lite, dan bermain bersama teman. Tidak diperlukan pengetahuan game horror sebelumnya. UI dan kontrol harus dapat digunakan di HP, bukan hanya PC.

## 3. Lore dan atmosfer

**[PROPOSAL]** Fasilitas bawah tanah dengan nama sementara **Facility 07** mengembangkan proyek regenerasi biologis. Eksperimen Subject Zero lepas kendali, sistem listrik utama mati, dan protokol karantina mengunci akses keluar. Scientists yang tersisa harus mengumpulkan kunci darurat untuk membuka jalur keluar.

Identitas Subject Zero dan detail eksperimen dapat disampaikan melalui catatan penelitian, layar rusak, dan pesan interkom. Lore tidak boleh memperlambat gameplay. Gunakan cerita lingkungan daripada cutscene panjang.

- Red Sector: penelitian dan keamanan.
- Blue Sector: cryogenics dan kontrol sistem.
- Green Sector: biohazard dan containment.
- Central Hub: pusat kendali dan evakuasi.

Nama-nama fasilitas ini bersifat sementara.

## 4. Core gameplay loop

### 4.1 Scientist [BASE]

Cari kunci → gate terbuka setelah seluruh kunci terkumpul → kabur. Jika tertangkap, tunggu rescue di Infection Tube. Bila waktunya habis, bergabung ke tim anomali sebagai Mini-Mutant. Pemain yang diselamatkan kembali mencari kunci atau menuju gate yang sudah terbuka.

### 4.2 Subject Zero [BASE]

Patroli, kejar dan tangkap Scientist. Setelah korban masuk tabung, pilih menjaga rute rescue, memotong jalur pencarian, atau menuju gate. Mini-Mutant yang muncul membantu memberi tekanan.

### 4.3 Ketegangan per fase [PROPOSAL]

Awal ronde memberi waktu mencari kunci dan mengenali rute. Setelah capture pertama, Scientist memilih lanjut mencari atau kembali menolong. Saat gate terbuka, dua pendekatan memberi pilihan untuk kabur.

## 5. Faksi, karakter, dan balancing

### 5.1 Scientists

- **[BASE]** Objektif: cari kunci, evakuasi, rescue teman.
- **[PROPOSAL]** Semua Scientist menggunakan kemampuan dasar yang sama pada MVP agar balancing tidak terlalu kompleks.
- Dapat sprint, menggunakan ventilasi, berinteraksi dengan objective dan membantu rescue.
- Tidak mempunyai senjata mematikan. Bertahan dengan pergerakan, koordinasi dan penggunaan layout.

### 5.2 Subject Zero

Satu pemain menjadi anomali. Aksi inti adalah capture langsung dalam jangkauan yang divalidasi server. Kecepatan dasar tetap sepanjang ronde. Ancaman bertambah melalui Mini-Mutant dan posisi.

### 5.3 Mini-Mutant

- **[BASE]** Scientist yang gagal diselamatkan beralih ke tim anomali. **[PROPOSAL]** Mini-Mutant bergerak lebih lambat daripada Subject Zero.
- **[PROPOSAL]** Mini-Mutant tidak memakai ventilasi.
- Untuk mengurangi snowball, mutant tidak bisa menangkap langsung. Serangannya memberi efek slow singkat dan menandai target secara lokal sehingga Subject Zero bisa mendekat. Hanya Subject Zero yang dapat melakukan final capture pada MVP.
- Efek slow tidak menumpuk, dan target yang sama menerima kekebalan singkat dari slow ulang.
- Mutant mengikuti hasil faksi Killer sesuai §9.2.

> Keputusan penting: apakah mutant boleh melakukan capture sendiri? GDD awal hanya menyebut tugas mengejar. Pembatasan di atas adalah usulan konservatif supaya infeksi pertama tidak otomatis menentukan hasil pertandingan.

### 5.4 Tabel parameter awal [PROPOSAL, kecuali bertanda BASE]

| Parameter | Nilai prototipe | Catatan |
|---|---:|---|
| Scientist walk speed | 16 studs/s | Gerakan normal |
| Scientist sprint speed | 22 studs/s | Dibatasi stamina |
| Stamina | 100 | Sprint menghabiskan 20/s; pulih 15/s setelah 1,5 s |
| Subject Zero base speed | 19 studs/s | Tanpa sprint tambahan |
| Mini-Mutant speed | 17,5 studs/s | Selalu di bawah Subject Zero |
| Subject Zero capture range | 5 studs | Jarak dan line-of-sight diverifikasi server |
| Capture cooldown | 3 s | Mulai setelah capture berhasil dicatat |
| Mutant attack range | 4 studs | Perlu dekat |
| Mutant slow | 20% selama 2 s | Kekebalan slow ulang 5 s setelah efek berakhir |
| Mutant attack cooldown | 6 s | Tidak stack |
| Infection timer | 120 s ronde, 45 s latihan co-op | Nilai awal prototipe |
| Rescue hold | 3 s | Nilai awal prototipe |
| Rescue protection | 3 s | Tidak dapat ditangkap ulang; tidak mengerjakan objective |
| Match duration | 10 menit | Termasuk fase evakuasi, dapat berubah saat playtest |

Semua nilai diletakkan dalam konfigurasi, bukan hardcoded pada banyak script. Speed Roblox di atas adalah target prototipe, bukan hasil simulasi fisik atau playtest.

## 6. Objective dan interaksi

### 6.1 Kunci evakuasi

**[BASE]** Scientist mencari kunci untuk membuka jalan keluar. **[PROPOSAL]** Kunci berupa keycard. Latihan dan M1 memakai satu keycard Red. M2 memakai tiga keycard, satu per warna. Server memilih satu dari tiga kandidat publik per warna aktif. Semua zona aktif dapat dimasuki sejak awal.

Server mencatat pickup sekali dan memberi progres ke tim. Kartu tetap tercatat setelah capture, mutasi atau disconnect.

### 6.2 Gate evakuasi

- Kartu terakhir memulai animasi gate 5 detik secara otomatis. Escape trigger baru aktif saat animasi selesai.
- Gate di Central Hub punya dua pendekatan ber-cover. Scientist aktif bisa escape jika melewati trigger sebelum deadline. Hasil individu dan faksi mengikuti §9.2.
- Pada latihan co-op, pickup memicu simulasi capture. Gate mulai membuka setelah rescue latihan berhasil.

## 7. Infection dan rescue system

### 7.1 Capture [BASE + PROPOSAL]

Saat Subject Zero berhasil menangkap Scientist, korban langsung dimasukkan ke Infection Tube. Untuk MVP, gunakan pemindahan yang dilakukan server menuju tabung bebas terdekat, dengan transisi visual singkat. Tidak ada sistem gendong/HP/downed tambahan pada MVP. Ini menyederhanakan networking dan menghindari menunggu animasi panjang.

- Satu tabung menampung satu pemain.
- Pilih tabung valid yang kosong dengan jarak lurus terkecil dari posisi korban, lalu `TubeId` terkecil jika seri. Semua tabung aktif harus bisa dicapai dari hub sebelum kartu pertama diambil. Jika tidak ada tabung valid, tolak capture, pertahankan state korban dan cooldown, lalu log error.
- Server mencatat penempatan korban, status `Captured`, deadline infeksi dan cooldown capture sebagai satu perubahan gameplay. Transisi visual mengikuti perubahan itu.
- Pemain yang tertangkap melihat timer dan dapat menggunakan ping rescue terbatas.
- Scientist aktif mendapatkan indikator lokasi tabung dan sisa waktu korban.
- Timer tetap berjalan jika Subject Zero pindah zona.

### 7.2 Rescue

**[BASE]** Scientist lain bisa membebaskan korban sebelum batas waktu. **[PROPOSAL]** Tahan E atau tombol touch selama 3 detik. Timer awal 120 detik untuk ronde dan 45 detik untuk latihan co-op. Deadline sesi tetap berlaku jika sesi selesai lebih dulu.

**[PROPOSAL]** Rescue batal saat penolong menjauh, tertangkap, atau melepas input. Progres rescue direset saat batal. Jika dua penolong berinteraksi, hanya satu yang dapat menyelesaikan rescue; keduanya tidak mempercepat durasi. Setelah bebas, korban mendapat proteksi capture 3 detik dan tidak bisa mengerjakan objective saat proteksi berlangsung.

### 7.3 Mutation [BASE + PROPOSAL]

Jika waktu habis, server mengubah role korban menjadi Mini-Mutant, melepas tabung, menghapus hak akses Scientist, mengganti HUD dan kemampuan, serta memindahkan pemain ke titik aman sekitar tabung. Pemain tetap berada pada match yang sama. Proses dibuat atomik agar tidak terjadi rescue dan mutation bersamaan.

Aturan tie: rescue sah hanya apabila penyelesaian hold di server terjadi **sebelum** deadline infeksi; jika tepat pada deadline, mutation menang. Jangan gunakan timer lokal sebagai sumber kebenaran.

### 7.4 Anti-camping

- Tabung tersebar di lokasi dengan minimal dua pendekatan dan cover.
- Jangan membuat tabung berada tepat di sebelah titik kunci atau gerbang evakuasi.
- P0 menguji layout dan countdown tetap per mode. Jika pemain masih konsisten gagal mencapai tabung karena camping, eksperimen P1 dapat memperlambat countdown menjadi 50% setelah 8 detik Subject Zero berada dalam radius 12 studs tanpa Scientist aktif lain di radius itu, dengan tambahan maksimum 15 detik per episode capture. Tampilkan efek aktif dan kembali ke laju normal saat kondisi berakhir.

### 7.5 Player state diagram

```mermaid
stateDiagram-v2
    [*] --> Lobby
    Lobby --> Scientist: Role scientist
    Lobby --> SubjectZero: Role killer
    Scientist --> Captured: Valid capture
    Captured --> Scientist: Rescue sebelum deadline
    Captured --> MiniMutant: Infection selesai
    Scientist --> Escaped: Valid escape
    Escaped --> Spectating
    Scientist --> Results: Round berakhir
    Captured --> Results: Round berakhir
    MiniMutant --> Results: Round berakhir
    SubjectZero --> Results: Round berakhir
    Spectating --> Results: Round berakhir
    Results --> Lobby
```

Disconnect adalah transisi terpisah dari setiap state aktif, dijelaskan pada bagian match flow.

## 8. Map design blueprint

### 8.1 Layout

Facility 07 memakai Hub & Spoke sebagai proposal map. Hub menghubungkan Red, Blue, Green dan gate. Cabang yang aktif bisa dimasuki sejak awal. Vent pada map penuh memberi jalur rotasi Scientist.

### 8.2 Top-down schematic

Lihat [Map Blueprint](MAP_BLUEPRINT.md) untuk diagram dan posisi. Red berada di utara, Blue barat daya, Green tenggara. Masing-masing memiliki chase loop dan kandidat kunci. Tabung berada di alcove publik, terpisah dari titik kunci, spawn dan gate.

### 8.3 Ruangan dan landmark

| Area | Ruangan | Tujuan gameplay | Identitas visual |
|---|---|---|---|
| Central Hub | Evacuation, security desk, reception alcoves | Orientasi, spawn Scientists, akses antarzona, evakuasi | Ruang melingkar, pilar, lampu putih/hijau, emergency shutter |
| Red | Research, security | Objective merah, chase loop | Merah, amber, simbol segitiga, rak dan meja riset |
| Blue | Cryo storage, control | Objective biru, cover rapat | Biru, simbol persegi, mesin pendingin, kaca buram |
| Green | Containment, specimen room | Objective hijau, chase loop | Hijau, simbol lingkaran, tabung spesimen, pipa |
| Vent | RB, RG, BG | Rute kabur dan rotasi Scientist | Logam, lampu rendah, suara ventilasi |

### 8.4 Blockout dimensions

| Elemen | Target awal |
|---|---|
| Footprint total | Sekitar 280 × 280 studs; skala dapat berubah |
| Central Hub | Diameter sekitar 60 studs |
| Lorong utama | Lebar 12–16 studs |
| Lorong samping | Lebar 8–12 studs |
| Ruang landmark | Sekitar 24 × 24 studs |
| Tinggi ruang | 12–18 studs |
| Vent | Entrance berinteraksi, terhubung dengan jalur transit khusus |
| Waktu hub ke kandidat kunci terjauh | Target 8–15 detik lari normal tanpa hambatan; ukur pada blockout |
| Waktu rotasi vent antarzona | Target 6–9 detik pada profil tiga zona |

Gunakan `studs` sebagai unit pengukuran Roblox. Target waktu dan dimensi adalah hipotesis, bukan ukuran map referensi.

### 8.5 Routing rules dan spawn

- Setiap zona mempunyai setidaknya satu loop pengejaran. Setiap tabung publik punya dua pendekatan layak dari percabangan publik dengan cover.
- Vent hanya untuk Scientist aktif pada profil penuh. Sambungkan jalur publik antarzona dan letakkan exit di luar gate serta escape trigger.
- MVP vent menggunakan interaksi masuk 1 detik, transit 4–6 detik, lalu server menempatkan pemain di exit. Jangan gunakan teleport seketika untuk menghindari chase yang terlalu mudah. Cooldown vent per pemain 8 detik setelah keluar.
- Sediakan 5 spawn Scientist tersebar di alcove hub yang dapat dicapai tanpa kartu; spawn Subject Zero di security annex terpisah yang punya jalur ke hub. Berikan head start Scientist 12 detik sebelum killer dapat bergerak.
- Kandidat keycard tersebar di area aktif yang bisa dimasuki dari hub sejak awal. Awal match tidak boleh memiliki objective yang mustahil diakses.
- Letakkan cover di sekitar gate agar killer tidak bisa mengawasi semua pendekatan sekaligus. Uji camp di gate dengan 1–3 mutant aktif. Jika terlalu kuat, desain ulang gate menjadi area escape lebih lebar atau dua entrance menuju satu tujuan evakuasi.

### 8.6 Map object contract

Map builder memberi nama/atribut/tag sesuai kontrak yang disepakati programmer. ID stabil antar match, tidak tergantung nama dekorasi.

| Tag | Attributes wajib | Satu zona | Tiga zona |
|---|---|---:|---:|
| `ScientistSpawn` | `SpawnId` | 5 | 5 |
| `KillerSpawn` | `SpawnId` | 1 | 1 |
| `KeycardSpawn` | `SpawnId`, `Color` | 3 | 9 |
| `InfectionTube` | `TubeId`, `AreaId` | 5 | 5 |
| `VentEntrance` | `VentId`, `ZoneId`, `LinkedVentId` | 0 | 6 |
| `EvacuationGate` | `GateId` | 1 | 1 |
| `EscapeTrigger` | `GateId` | 1 | 1 |

Latihan dan M1 memakai profil Red. M2 memakai tiga zona. Keduanya punya S1–S5, T1–T5, spawn Subject Zero dan pasangan gate/trigger. Pada profil Red, cabang Blue dan Green ditutup secara fisik dan T4/T5 berada di alcove hub. Pada profil penuh, T4/T5 berada pada pendekatan publik Blue/Green. Vent hanya terdaftar pada profil penuh. `AreaId` menamai landmark publik di HUD.

Sebelum spawn, validator memeriksa jumlah objek, ID unik per tag, tiga kandidat kartu per warna aktif, `GateId` yang menghubungkan gate dan trigger, serta link vent dua arah. Jika gagal, kembali ke lobby dan log objek bermasalah. QA memastikan kartu, tabung dan rute rescue dapat dicapai dari hub sebelum gate terbuka.

## 9. Match flow dan edge cases

### 9.0 Mode dan transisi pemain

| Pemain siap | Alur |
|---|---|
| 1–4 | Lobby menunggu ronde. Latihan opsional tersedia untuk satu atau dua peserta di Red. |
| 5–6 | Ronde utama, satu Subject Zero melawan 4–5 Scientists. Profil Red pada M1, tiga zona pada M2. Batas awal 10 menit. |

- **Solo** · Ambil kartu dan kabur.
- **Co-op** · Dua pemain setuju memulai latihan. Setelah kartu diambil, server memasukkan pengambil ke tabung satu kali. Rekannya punya 45 detik untuk rescue. Jika berhasil, gate membuka dan keduanya perlu escape. Jika rescue gagal atau salah satu keluar, akhiri latihan dan tawarkan ulang.
- Saat arena kosong dan pemain siap kurang dari lima, satu pemain siap boleh mulai solo atau mengajak satu pemain siap lain. Undangan co-op hanya berlaku untuk pasangan itu. Server menerima satu sesi arena, dan membatalkan undangan lain ketika sesi dimulai atau ambang ronde tercapai. Latihan maksimal 120 detik.
- Pemain baru otomatis siap. Saat lima pemain siap, hentikan start latihan baru. Peserta aktif boleh menyelesaikan latihan atau memilih `Ikut Ronde` untuk keluar lebih cepat. Status siap tetap berlaku kecuali dibatalkan pemain. Intermission mulai setelah arena kosong jika minimal lima masih siap.
- Jika jumlah siap turun di bawah lima saat intermission, kembali ke `Waiting`. Kunci roster 5–6 saat masuk `Preparing`. Jika peserta keluar saat persiapan, reset dan pilih roster ulang. Join setelah roster terkunci menunggu ronde berikutnya. Disconnect di `Active` mengikuti §9.4.
- Server menampung maksimal enam pemain dan satu sesi arena. Latihan punya ID sendiri tanpa perubahan statistik, bobot role atau reward kompetitif.

### 9.1 Round lifecycle [PROPOSAL]

| State | Durasi awal | Perilaku |
|---|---:|---|
| `Waiting` | Dinamis | Di bawah lima pemain siap, latihan tersedia saat arena kosong. Pada 5–6, mulai intermission setelah arena kosong. |
| `Intermission` | 20 s | Pemain siap, server memeriksa map. |
| `Preparing` | 5 s | Reset round, assign roles, spawn, tutorial singkat. |
| `Active` | 600 s | Waktu berjalan sejak awal gameplay termasuk head start. |
| `Results` | 12 s | Tampilkan hasil individu dan faksi, XP jika fitur tersedia. |
| `Cleanup` | Sesingkat mungkin | Bersihkan task, connection, state, map, lalu ke Waiting. |

Evakuasi adalah substate `GateOpen` dalam Active, bukan round baru; timer tetap berjalan. Tidak ada overtime pada MVP. Jika semua Scientist sudah kabur, terinfeksi, atau keluar sebelum waktu habis, selesaikan round lebih awal. Scientist dalam tabung masih dihitung sebagai belum terselesaikan hingga mutasi, rescue, atau round timeout.

### 9.2 Win conditions

Pada ronde kompetitif, server mencatat escape yang sah sebelum deadline. Begitu tercatat, escape tetap berlaku meskipun pemain keluar. Sebelum menerapkan aksi atau disconnect, server memeriksa deadline. Jika sudah tercapai, hasil timeout memakai state terakhir yang sah. Sebelum deadline, evaluasi hasil setelah setiap escape, mutasi, atau disconnect. Selesaikan hasil satu kali dengan aturan berikut.

1. Jika Subject Zero keluar saat `Active`, selesaikan kemenangan Scientist bila escape sudah tercatat. Jika belum, batalkan ronde.
2. Jika tidak ada Scientist aktif atau tertangkap, selesaikan kemenangan Scientist bila sudah ada escape. Tanpa escape, mutasi Scientist terakhir memberi kemenangan Killer, sementara disconnect Scientist terakhir membatalkan ronde. Disconnect Scientist sebelumnya tidak menghalangi kemenangan dari mutasi terakhir. Mutant yang keluar tetap tercatat pernah bermutasi.
3. Jika deadline tiba dengan Scientist aktif atau tertangkap, Scientist menang bila ada escape. Jika tidak, Killer menang. Aksi yang diterima tepat pada deadline atau setelahnya tidak mengubah hasil.

Scientist mendapat kemenangan individu lewat escape. Mini-Mutant mewarisi hasil Killer. Scientist yang belum kabur kalah secara individu meskipun faksinya menang. Ronde berlanjut setelah escape pertama selama masih ada Scientist aktif atau tertangkap dan Subject Zero masih bermain. Results menampilkan outcome, escape, mutasi, rescue, dan kunci terkumpul. Ronde batal tidak memberi reward kompetitif.

### 9.3 Role selection

Pilih killer di server menggunakan bobot yang meningkat untuk pemain yang belum mendapatkan role tersebut. Jangan menjual kesempatan killer pada MVP. Tawarkan opsi preferensi role post-MVP, bukan role yang dipastikan setiap saat.

### 9.4 Edge cases

| Kasus | Penanganan |
|---|---|
| Scientist keluar | Bebaskan slot tabung dan interaksinya; kartu yang sudah diambil tetap milik tim. |
| Captured player disconnect | Kosongkan tabung; tidak melahirkan mutant bot. |
| Mutant keluar | Bersihkan effect, slot, dan koneksi. |
| Subject Zero keluar | Akhiri ronde sesuai §9.2 dan tampilkan alasan hasilnya. |
| Scientist aktif/captured terakhir keluar | Catat disconnect dan evaluasi hasil sesuai §9.2 setelah slot dan interaksinya dibersihkan. |
| Join ketika match aktif | Lobby/spectator tanpa ikut round yang sedang berjalan. |
| Reset character / jatuh keluar map | Role tidak berubah. Server pulihkan ke titik valid sesuai role; cegah reset menjadi cara keluar dari tabung. |
| Rescue vs mutation pada waktu sama | Server memutuskan dari deadline; mutation pada waktu yang sama. |
| Kartu terakhir tercatat hampir bersamaan dengan event lain | Server jadwalkan pembukaan gate satu kali. |
| Dua pemain mengambil kartu sama | Server menandai acquired secara atomik, reward sekali. |
| Timer habis saat escape berlangsung | Hanya escape yang tercatat server sebelum deadline dianggap sah. |

## 10. UI/UX dan kontrol

### 10.1 Screen flow

```text
Launch → Lobby → Intermission → Role Reveal → In-game HUD → Results → Lobby
                                    |              |
                                    |              +-- Captured HUD → Rescue / Mutant HUD
                                    |              +-- Escaped → Spectator HUD
                                    +-- Tutorial ringkas sesuai role
```

### 10.2 Lobby

- Logo ETL, jumlah pemain siap, status ronde berikutnya, tombol `Siap`, dan settings. Saat syarat §9.0 terpenuhi, tampilkan `Mulai Latihan`. Jika ronde siap saat pemain berlatih, tampilkan `Ikut Ronde` tanpa menutup latihan mendadak.
- Gunakan lobby sederhana berbentuk ruang briefing laboratorium.
- Tampilkan status matchmaking lokal, countdown saat cukup pemain, dan informasi role secara jelas.
- Jangan membuat inventory shop, battle pass, atau matchmaking lintas server sebelum game loop terbukti menarik.

### 10.3 Scientist HUD

```text
+-----------------------------------------------------+
| ETL       KEYCARDS    1/3              TIME  06:42   |
|          R: FOUND  B: MISSING  G: MISSING                 |
|                                                     |
|     RESCUE: Green Sector — Scientist 04: 00:27       |
|                                                     |
|                 [ E ] HOLD TO RESCUE              |
|                      █████░░░  62%                  |
|                                                     |
| Stamina ███████░░░                      [SPRINT]    |
+-----------------------------------------------------+
```

Status warna selalu disertai huruf, ikon atau teks. UI tidak boleh mengandalkan merah/hijau saja. Peringatan rescue memakai lokasi zona, ikon tabung, dan countdown. Objective tracker menampilkan tahap keycard → gate terbuka → escape.

### 10.4 Killer HUD

- Timer, jumlah Scientist aktif / captured / escaped / mutant.
- Crosshair/indikator capture jika target berada dalam jangkauan secara perkiraan; keputusan akhir tetap di server.
- Tidak ada wallhack lokasi semua Scientist permanen.

### 10.5 Captured, mutant, dan results

Captured HUD menampilkan `INFECTION IN PROGRESS`, countdown besar, dan aksi ping. Pada ronde kompetitif, HUD menjelaskan mutasi akan memberi peran Mini-Mutant, lalu menampilkan slow dan cooldown setelah berubah. Pada latihan co-op, tampilkan instruksi penolong dan hasil latihan sesuai §9.0. Results ronde memisahkan outcome faksi dan status individu. Pemain kembali ke lobby setelah results dan dapat mengatur status `Siap` untuk sesi berikutnya.

### 10.6 Input mapping [PROPOSAL]

| Action | PC | Mobile |
|---|---|---|
| Move / camera | WASD / mouse | Virtual thumbstick / swipe |
| Sprint | Shift | Tombol sprint toggle |
| Interact / rescue | E / tahan E | Contextual hold button |
| Capture / mutant attack | Klik kiri | Tombol attack |
| Ping rescue | R (captured) | Tombol ping |
| Settings | Escape / menu Roblox + UI custom | Ikon settings |

Gunakan `ProximityPrompt` sebagai dasar tampilan interaksi dunia bila sesuai, dengan UI yang responsif untuk touch dan keyboard. Jika diperlukan custom action, ikat input sesuai perangkat. Hindari tombol menutupi joystick dan area kamera. Uji di HP fisik, bukan hanya emulator Studio.

## 11. Art direction dan audio

### 11.1 Style guide

**Arah visual [PROPOSAL]:** stylized industrial sci-fi horror; bentuk modular, low-to-medium poly, siluet kuat, tekstur sederhana, kontras yang terbaca di layar HP. Ruang gelap tetapi navigasi tetap jelas. Kamera third-person, tanpa jumpscare ekstrem.

| Elemen | Palet / identitas |
|---|---|
| Base | Charcoal `#101719`, steel `#28363A`, concrete `#667477` |
| Red | `#EF4444`, simbol segitiga |
| Blue | `#60A5FA`, simbol persegi |
| Green | `#4ADE80`, simbol lingkaran |
| Evacuation | `#FBBF24`, ikon exit |
| Text/HUD | `#E5E7EB` pada latar gelap |

Gunakan warna sebagai aksen landmark, bukan membanjiri seluruh ruangan. Lampu overhead, pipa, panel pintu, signage, serta lantai modular membangun konsistensi. Efek kedip dan camera shake harus dapat dikurangi/dimatikan.

### 11.2 Asset list minimum

| Prioritas | Asset |
|---|---|
| P0 | Kit modular, gate dan trigger, tiga varian keycard, lima tabung per profil, entrance vent, cover props |
| P0 | Subject Zero rig dan Mini-Mutant rig; idle, walk, run, attack, capture/mutation feedback |
| P0 | Scientist avatar standar dengan animasi interaksi |
| P1 | Emergency light, signage, desk, pipe, rack, monitor, cryo props, specimen props |
| P1 | Logo, role icons, objective icons, UI textures |
| P2 | Skin karakter, lore collectible, cinematic intro, dekorasi tambahan |

Gunakan asset original atau asset dengan lisensi yang mengizinkan penggunaan di Roblox. Catat pembuat, URL, izin, dan file sumber di `ASSET_CREDITS.md`. Jangan menyalin map/karakter dari game lain secara langsung.

### 11.3 Audio plan

- Ambience dasar: mesin, ventilasi, humming listrik.
- Audio landmark: keycard diambil, tabung terkunci/terbuka, dan escape gate.
- Proximity heartbeat untuk Scientist (target P1): intensitas meningkat saat Subject Zero dekat; hindari informasi jarak terlalu presisi.
- Mutasi: alarm dan suara transformasi singkat, tanpa gore.
- Audio UI: pickup, interaksi berhasil/gagal, timer rescue.
- Sediakan volume master/music/SFX, kurangi flashing, dan pastikan objective tetap dapat dipahami tanpa suara.

## 12. Progression dan monetisasi

**[PROPOSAL]** Fokus MVP adalah loop match. Progression disiapkan sebagai P1 setelah fitur inti lulus QA; monetisasi publik post-MVP.

### 12.1 XP dan reward awal

| Aksi | XP usulan |
|---|---:|
| Selesaikan round yang valid | 20 |
| Escape sebagai Scientist | 50 |
| Rescue berhasil | 20 |
| Mengambil satu keycard evakuasi sah | 15 |
| Capture valid oleh Subject Zero | 10 |
| Assist mutant yang berujung capture dalam 5 detik | 10 |
| Menang sebagai faksi killer | 40 |

Server menyimpan ledger reward per match. Batasi rescue berulang pada korban yang sama dan reward capture berulang untuk menghindari boosting. Jangan memberi bonus karena Scientist sengaja terinfeksi. Tampilkan rincian XP di results. Reward hanya dikomit untuk ronde kompetitif yang sah.

### 12.2 Monetisasi kosmetik

- Skin Subject Zero, Mini-Mutant, Scientist outfit, emote, nameplate, serta efek kosmetik yang tidak mengganggu gameplay.
- Tidak menjual speed, capture radius, tambahan stamina, penurunan cooldown, atau keuntungan kompetitif lain.
- Tidak menentukan harga Robux sebelum ada validasi pemain, biaya produksi, dan review aturan platform yang berlaku ketika rilis.
- Revenue share internal tim merupakan perjanjian terpisah dari monetisasi game.

## 13. Technical Design Document

### 13.1 Tech stack dan prinsip

| Layer | Pilihan awal |
|---|---|
| Engine | Roblox Studio |
| Language | Luau, `--!strict` untuk module inti bila memungkinkan |
| Multiplayer | Roblox client-server runtime; server sebagai otoritas gameplay |
| UI | ScreenGui / LocalScript; responsive scale dan safe area |
| Interaksi | ProximityPrompt atau custom action sesuai kebutuhan |
| Map | Models, CollectionService tags, Attributes |
| Persistence | DataStoreService untuk progression P1; tidak diperlukan pada prototype P0 |
| Collaboration | Team Create untuk place/map; Git + Rojo opsional untuk source code |
| Testing | Studio multi-client, private test place, perangkat Android/PC fisik |

MVP memakai satu place dengan lobby dan arena pada server yang sama. `MatchService` memiliki akses eksklusif ke arena mulai dari persiapan hingga cleanup, termasuk saat latihan. Praktik solo, co-op, dan ronde kompetitif berbagi layanan map, interaksi, objective, infection, dan hasil sesuai mode. Pemicu capture latihan dijalankan server dan memakai transisi `Captured` yang sama, tanpa actor Subject Zero atau remote capture khusus.

### 13.2 Arsitektur

```mermaid
flowchart LR
    C[Roblox client: input / UI / effects] -->|Intent| R[Remote router + validation]
    R --> S[Server gameplay services]
    S --> M[Match state / role / objective]
    S --> W[Workspace: map / characters]
    S --> P[DataStore: progression P1]
    M -->|Snapshot + delta| C
    W -->|Roblox replication| C
```

Client bertugas membaca input dan menampilkan feedback, bukan memutuskan role, hadiah, capture, escape, atau objective. Server memeriksa konteks aksi dan mengelola perubahan state. Model ini mengikuti prinsip keamanan client-server Roblox; bukan klaim bahwa fitur engine server-authority khusus telah dikonfigurasi.

### 13.3 Struktur Explorer / source tree

```text
EscapeTheLab/
├── ReplicatedStorage/
│   ├── Shared/
│   │   ├── Config.lua
│   │   ├── Types.lua
│   │   ├── Constants.lua
│   │   └── NetSchema.lua
│   ├── Remotes/
│   │   ├── RequestAction
│   │   ├── ActionResult
│   │   ├── MatchSnapshot
│   │   ├── MatchDelta
│   │   └── PlayEffect
│   └── Assets/
│       └── SharedFX/
├── ServerScriptService/
│   ├── Bootstrap.server.lua
│   └── Services/
│       ├── MatchService.lua
│       ├── RoleService.lua
│       ├── MapService.lua
│       ├── ObjectiveService.lua
│       ├── CombatService.lua
│       ├── InfectionService.lua
│       ├── VentService.lua
│       ├── MovementService.lua
│       ├── ReplicationService.lua
│       ├── SecurityService.lua
│       └── RewardService.lua         # P1
├── ServerStorage/
│   ├── Maps/Facility07/
│   └── CharacterRigs/
├── StarterPlayer/
│   └── StarterPlayerScripts/
│       ├── Bootstrap.client.lua
│       └── Controllers/
│           ├── InputController.lua
│           ├── HUDController.lua
│           ├── InteractionController.lua
│           ├── AudioController.lua
│           └── CameraController.lua
├── StarterGui/
│   ├── LobbyGui/
│   ├── MatchGui/
│   ├── CapturedGui/
│   └── ResultsGui/
├── Workspace/
│   ├── Lobby/
│   └── ActiveMap/                    # generated per round
└── docs/
    ├── ESCAPE_THE_LAB_GDD.md
    └── ASSET_CREDITS.md
```

Ini struktur logis Roblox Explorer, bukan project Rojo yang siap dijalankan. Jika menggunakan Rojo, buat `default.project.json` dan tentukan ownership folder sebelum sync; jangan biarkan source-controlled folder ditimpa edit manual Studio tanpa koordinasi.

### 13.4 Pembagian tanggung jawab module

| Service | Responsibility |
|---|---|
| `MatchService` | Reservasi arena, roster, mode, session ID, deadline, hasil dan cleanup |
| `RoleService` | Assign role, state transition, spawn, permission |
| `MapService` | Load, validate tags, lookup objects, random spawn |
| `ObjectiveService` | Keycard milik tim, pembukaan gate dan escape |
| `CombatService` | Capture attempt, target validation, mutant slow effect |
| `InfectionService` | Tube reservation, countdown, rescue, mutation, anti-camping |
| `VentService` | Vent routing, transit, cooldown, valid exit |
| `MovementService` | Sprint stamina, role speed modifiers, movement anomaly checks |
| `ReplicationService` | Scoped snapshots dan deltas untuk UI |
| `SecurityService` | Schema validation, rate limiting, permission helpers |
| `RewardService` | Ledger XP, persistence, idempotent reward P1 |

`MatchService` mengorkestrasi; module lain tidak mengubah phase match langsung. Hindari circular require dengan dependency injection pada bootstrap atau event internal yang terdokumentasi. Gunakan satu pemilik mutasi untuk setiap jenis state.

### 13.5 State model

Contoh konsep tipe Luau (belum berupa implementasi lengkap):

```luau
export type ZoneId = "Red" | "Blue" | "Green"
export type Role = "Scientist" | "SubjectZero" | "MiniMutant"
export type PlayerStatus = "Lobby" | "Active" | "Captured" | "Escaped" | "Disconnected"
export type MatchPhase = "Waiting" | "Intermission" | "Preparing" | "Active" | "Results" | "Cleanup"
export type SessionMode = "SoloPractice" | "CoopPractice" | "MainRound"

export type PlayerRoundState = {
    userId: number,
    originalRole: Role,
    role: Role,
    status: PlayerStatus,
    tubeId: string?,
    infectionDeadline: number?,
    protectedUntil: number?,
    stamina: number,
    cooldowns: {[string]: number},
}

export type ZoneState = {
    keycardAcquired: boolean,
}

export type RoundState = {
    roundId: string,
    mode: SessionMode,
    activeZones: {ZoneId},
    phase: MatchPhase,
    deadline: number?,
    players: {[number]: PlayerRoundState},
    zones: {[ZoneId]: ZoneState?},
    gateState: "Closed" | "Opening" | "Open",
    gateOpensAt: number?,
    escapedCount: number,
    mutatedCount: number,
}
```

`role` dan `status` dipisah: Scientist yang tertangkap tetap role Scientist sampai mutasi selesai. `originalRole` digunakan untuk statistik dan reward, bukan otorisasi aksi. State penuh hanya tersedia di server; client mendapat subset sesuai role. Semua timestamp aksi dibandingkan terhadap clock server yang konsisten; tampilkan waktu relatif untuk HUD.

### 13.6 Network contract

| Event | Direction | Payload konseptual |
|---|---|---|
| `RequestAction` | C → S | `requestId`, `action`, `roundId?` (wajib untuk aksi arena), `targetId?`, field per aksi bila diperlukan |
| `ActionResult` | S → C | `requestId`, `ok`, `reason?` |
| `MatchSnapshot` | S → C | `roundId`, `revision`, phase, public state, private role state |
| `MatchDelta` | S → C | `roundId`, `revision`, changed fields yang diizinkan |
| `PlayEffect` | S → C | `effectType`, safe target/position sesuai role |

Action enum awal mencakup `SetReady`, `StartPractice`, `LeavePractice`, `PickupKeycard`, `BeginRescue`, `EndRescue`, `Capture`, `MutantAttack`, `EnterVent`, `SetSprint`, `PingRescue`, dan `RequestSnapshot`. `SetReady` dan `SetSprint` memvalidasi boolean `enabled`. `StartPractice` berlaku di lobby, dengan pilihan `Solo` atau `Coop`. Permintaan `Coop` menyertakan ID pasangan. Konfirmasi kedua pemain siap untuk pasangan yang sama diperlukan. `LeavePractice` dan aksi arena memakai `roundId` sesi aktif dan memerlukan keanggotaan yang sah. Prompt native memakai handler server yang sama dengan aksi custom. Pilih satu jalur pengiriman per interaksi.

Rules:

- Server memperoleh identitas actor dari koneksi remote, bukan `userId` kiriman client.
- Target ID wajib terdaftar pada map/round aktif, dengan panjang string dan tipe data yang dibatasi.
- Capture/attack: server mencari karakter target, mengecek role, jarak, line-of-sight, cooldown, protection, dan posisi wajar.
- Rescue hold memakai waktu mulai yang disimpan server. Server memeriksa kelayakan selama hold. `EndRescue` membatalkan hold. Keberhasilan ditentukan oleh server dan dicatat sebelum deadline infeksi.
- Event lama dari round sebelumnya ditolak. Snapshot memiliki revision sehingga UI dapat mengabaikan delta usang dan meminta resync jika dibutuhkan.
- Rate limit per pemain dan jenis aksi; hindari broadcast setiap frame. Jangan replikasi posisi keycard rahasia atau daftar lokasi Scientist ke killer melalui data HUD. Objek Workspace yang direplikasi masih dapat terlihat oleh client yang dimodifikasi; jangan menjanjikan secrecy atau anti-wallhack sempurna.

### 13.7 Capture dan mutation: transaction-like flow

Pseudocode (sengaja belum executable):

```text
tryCapture(actor, target, roundId):
  validate round, role, target status, distance, LOS, cooldown
  find eligible free tube
  if invalid or no tube: reject
  reserve tube, place target, and commit Captured without yielding
  on placement failure: release reservation and reject
  cancel target interactions and reset speed modifiers
  set infection deadline = server now + infectionWindow(mode)
  start capture cooldown and apply movement restriction
  replicate scoped changes and effect

updateCapturedPlayers(dt):
  if current server time >= infection deadline:
     if mode is CoopPractice: finish drill and release tube
     else: atomically transition Captured → Active MiniMutant
           release tube; update abilities and appearance

tryCompleteRescue(rescuer, target):
  validate active hold for >= 3 seconds and eligibility
  if target not Captured or deadline reached: reject
  atomically transition Captured → Active Scientist
  release tube, apply capture protection, replicate
```

Selesaikan perubahan state kritis sebelum operasi yang bisa yield. Semua evaluasi memakai waktu saat perubahan dicatat server. Waktu hold yang sudah cukup hanya membuat rescue layak diproses. Jika baru diproses pada atau setelah deadline infeksi, rescue gagal. Saat deadline ronde tercapai, finalisasi ronde sebelum update infeksi, termasuk jika kedua deadline bertepatan. Jika efek visual atau spawn gagal setelah transisi, pulihkan state yang sah atau batalkan sesi bila integritasnya tidak bisa dipulihkan.

### 13.8 Configuration sketch

```luau
-- Shared/Config.lua — starter values only
return table.freeze({
    MIN_COMPETITIVE_PLAYERS = 5,
    MAX_PLAYERS = 6,
    PRACTICE_SECONDS = 120,
    MAIN_ROUND_SECONDS = 600,
    HEAD_START_SECONDS = 12,
    GATE_OPEN_DELAY_SECONDS = 5,
    INFECTION_SECONDS = 120,
    PRACTICE_INFECTION_SECONDS = 45,
    RESCUE_SECONDS = 3,
    RESCUE_PROTECTION_SECONDS = 3,
    SCIENTIST_WALK_SPEED = 16,
    SCIENTIST_SPRINT_SPEED = 22,
    KILLER_BASE_SPEED = 19,
    MUTANT_SPEED = 17.5,
    CAPTURE_RANGE = 5,
    CAPTURE_COOLDOWN = 3,
})
```

Konfigurasi dapat dibaca client untuk presentasi, dan server menentukan nilai yang berlaku. Lengkapi parameter stamina, vent, attack dan rate limit sesuai milestone yang memakai mekaniknya.

### 13.9 Persistence P1

Simpan hanya progression yang diperlukan. Contoh schema: `schemaVersion`, `xp`, `level`, `matchesPlayed`, `escapes`, `killerWins`, `rescues`, `ownedCosmetics`, `equippedCosmetics`. Jangan menyimpan temporary match state atau informasi pribadi yang tidak relevan.

- Gunakan `DataStoreService` dari server, dengan `pcall`, retry terbatas, backoff, dan `UpdateAsync` untuk perubahan yang perlu aman dari concurrent write.
- Rancang session ownership dan reward ID untuk mencegah duplicate payout, terutama pada reconnect atau retry.
- Jika load gagal, izinkan mode tanpa progression dengan pesan jelas atau tolak akses fitur progression; jangan menimpa profil lama dengan default.
- Simpan saat interval wajar dan saat player keluar; jangan mengandalkan shutdown saja. Gunakan environment test yang tidak menulis data production.

## 14. Keamanan, performa, dan QA

### 14.1 Threat model sederhana

| Abuse | Mitigasi |
|---|---|
| Remote spam | Rate limit, schema check, reject invalid intent |
| Capture dari jauh | Server distance + LOS + target status + cooldown |
| Instant rescue | Server-owned hold timer dan validasi berkala |
| Escape sebelum semua keycard | Server team ownership check |
| Speed / teleport exploit | Server sanity check pergerakan, toleransi latency, pengecualian teleport resmi |
| Reset untuk bebas dari tabung | Server mengembalikan pemain sesuai state |
| Reward duplication | Ledger per round, reward ID, idempotency |
| Malicious free model | Review script, dependency, dan permission sebelum import |

Jangan menghukum pemain hanya dari satu spike posisi yang bisa terjadi karena lag. Log anomali dan gunakan tindakan proporsional. Semua keputusan keamanan perlu diuji dalam kondisi latency yang realistis.

### 14.2 Performance budget awal

- Target minimal 30 FPS pada perangkat mobile kelas menengah yang dipilih tim; target 60 FPS PC pada perangkat uji yang dicatat spesifikasinya.
- Gunakan aset modular dan reuse material/mesh. Batasi partikel, dynamic light, shadow, dan transparansi bertumpuk.
- Pertimbangkan StreamingEnabled jika map membesar; uji spawn, vent exit, camera, dan interaksi saat object belum tersedia di client.
- Server scheduler untuk objective dan infection menggunakan interval terukur (misalnya 0,1–0,2 detik), bukan loop terpisah per objek setiap frame. Gunakan deadline absolut untuk keputusan waktu kritis.
- Bersihkan event connection, timer, model, dan table setiap round. Jalankan soak test minimal 10 round berturut-turut untuk menemukan kebocoran resource.
- Profilkan dengan tooling Studio dan HP fisik; angka FPS adalah target, bukan hasil benchmark.

### 14.3 Acceptance test matrix

| ID | Skenario | Expected result |
|---|---|---|
| QA-01 | 1–4 lalu 5–6 pemain siap | Latihan hanya selama menunggu. Ronde mulai dari 5 dengan satu anomali. |
| QA-02 | Start dan reset 10 round | Tepat 1 Subject Zero; tidak ada state/timer lama bocor |
| QA-03 | Keycard random di 20 seed per profil | Tepat satu kartu per warna aktif. Semua kandidat dapat dijangkau sebelum gate terbuka. |
| QA-04 | 2 Scientist ambil kartu bersamaan | Hanya satu pickup; akses tim tersedia |
| QA-05 | Pengambil keycard disconnect atau bermutasi | Progres kartu tim tetap tercatat. |
| QA-06 | Kartu terakhir di tiap profil, termasuk pickup bersamaan | Satu kartu Red atau tiga kartu map penuh. Gate membuka sekali setelah 5 detik. |
| QA-07 | Capture valid / invalid jarak | Valid masuk tube; invalid tidak mengubah state |
| QA-08 | Rescue hold 3 detik sebelum deadline | Scientist bebas, tube kosong, proteksi 3 detik |
| QA-09 | Infeksi 120 detik pada ronde aktif | Role berubah menjadi mutant satu kali. |
| QA-10 | Rescue diproses sebelum, pada, atau setelah deadline infeksi, termasuk hold yang sudah cukup sebelum tick | Rescue hanya berhasil jika dicatat sebelum deadline. Tepat pada atau sesudahnya, mutation terjadi sekali. |
| QA-11 | Vent profil penuh dicoba oleh setiap role | Hanya Scientist aktif bisa masuk. Profil Red tidak menampilkan vent. |
| QA-12 | Subject Zero keluar sebelum/sesudah escape, Scientist terakhir keluar, mutant keluar, atau Scientist terakhir bermutasi setelah rekan keluar | State bersih. Hasil berturut-turut batal/kemenangan Scientist, batal jika belum ada escape, ronde lanjut jika masih ada Scientist, dan kemenangan Killer jika belum ada escape. |
| QA-13 | Remote action spam / payload salah | Ditolak tanpa mengganggu pemain lain |
| QA-14 | Scientist escape saat gate belum terbuka | Tidak dianggap escape |
| QA-15 | Touch input pada HP | Seluruh objective dan role dapat dimainkan tanpa keyboard |
| QA-16 | Capture sebelum kartu pertama | Penolong punya dua pendekatan publik dari percabangan. |
| QA-17 | Uji enam mulut vent profil penuh | Link dua arah berakhir di jalur publik di luar gate dan trigger. |
| QA-18 | Reset saat captured | Tetap captured dengan timer yang benar |
| QA-19 | Killer slow berulang / beberapa mutant | Slow tidak stack; kekebalan ulang berlaku |
| QA-20 | Gate camp dengan beberapa mutant | Catat apakah masih ada rute lolos; revisi layout jika buntu |
| QA-21 | DataStore load gagal (P1) | Data lama tidak tertimpa default |
| QA-22 | Latency tinggi dan reconnect | UI resync, tidak ada duplicate reward atau role |
| QA-23 | Solo selesai, co-op rescue berhasil/gagal, atau peserta co-op keluar | Progress latihan sesuai mode. Arena bersih setiap kali sesi berakhir. Statistik, XP dan bobot role kompetitif tetap sama. |
| QA-24 | Satu pemain mencoba mulai co-op, kemudian pemain kelima siap saat latihan berjalan dan peserta keluar saat persiapan ronde | Co-op baru mulai saat kedua pemain setuju. Saat pemain kelima siap, latihan baru tertahan. Latihan aktif bisa selesai atau ditinggalkan. Setelah arena kosong hanya satu ronde bisa mulai. Roster yang kehilangan peserta saat Preparing dipilih ulang. |
| QA-25 | Roster terkunci di 5 atau 6 pemain, lalu pemain masuk/keluar selama Active | Profil dan jumlah objective tetap. Pemain baru menunggu ronde berikutnya. |
| QA-26 | Escape sebelum / pada deadline, disconnect setelah deadline sebelum tick berikutnya, dan deadline infeksi bersamaan dengan deadline ronde | Hanya escape sebelum deadline tercatat. Hasil timeout memakai state terakhir yang sudah dicatat. Satu hasil akhir dan satu cleanup. |

## 15. Pembagian tim dan workflow

### 15.1 Struktur tim yang disarankan

Peran bisa dirangkap sesuai jumlah dan skill anggota. Penunjukan berikut masih usulan, bukan assignment yang sudah disetujui.

| Peran | Jumlah ideal | Deliverable |
|---|---:|---|
| Project Lead / Producer | 1 | Prioritas, scope, milestone, review, koordinasi |
| Game Designer | 1 | GDD, balancing, playtest feedback |
| Gameplay Programmer | 1–2 | Match, roles, objective, combat, infection, vent |
| Map Builder / Environment Artist | 1–2 | Blockout, routing, map contract, lighting |
| UI/UX + Client Programmer | 1 | HUD, lobby, mobile input, results |
| Character Artist / Animator | 1 | Rig, animation, transform feedback |
| QA / Community | 1–2 | Test case, bug report, tester recruitment |

Usulan: Hammad Studio mengelola koordinasi dan review engineering; Fathan sebagai pengusul konsep awal berkontribusi pada keputusan gameplay sesuai minat dan kesediaannya. Nama owner tiap pekerjaan ditentukan saat kickoff, bukan otomatis dari dokumen ini.

### 15.2 Collaboration setup

- Buat Roblox group/experience milik entitas yang disepakati tim; tetapkan owner dan permission sebelum kontribusi asset besar.
- Gunakan private development place untuk Team Create. Pisahkan staging/playtest dan production jika diperlukan. Beri akses minimum sesuai jobdesk; hindari berbagi password/token akun.
- Jika tim menggunakan Git + Rojo, buat repo private untuk source dan docs, dengan mapping folder yang jelas. Team Create menjadi area kerja map/asset, sedangkan script di folder terkelola mengikuti Git.
- Branch usulan: `main`, `develop`, `feat/match-service`, `feat/infection-system`, `fix/gate-camping`. Merge setelah review dan test. Hindari dua anggota mengedit source/map object yang sama tanpa koordinasi.
- Task board: Backlog → Ready → In Progress → Review → Playtest → Done.
- Setiap PR atau serah terima map mencantumkan perubahan, langkah test, screenshot/video bila relevan, dan known issues.
- Sync tim singkat 2–3 kali per minggu; catat keputusan balancing di `CHANGELOG.md` atau issue.

### 15.3 Benefit, ownership dan revenue share

Jangan mengasumsikan anggota bekerja gratis atau otomatis menerima persentase kepemilikan tertentu. Sepakati model kolaborasi tertulis sebelum rilis komersial. Untuk anggota yang belum dewasa, perhatikan persetujuan wali dan aturan platform yang relevan sebelum kontrak atau pembayaran.

Hal yang perlu disetujui:

- Siapa pemilik experience, repo, brand, asset dan lisensi penggunaan kontribusi.
- Kompensasi: volunteer learning project, fixed fee, revenue share, atau kombinasi yang transparan.
- Jika revenue share: definisi pendapatan yang dibagi (misalnya penerimaan bersih setelah biaya yang disetujui), periode payout, metode perhitungan, pencatatan, siapa yang mengelola, dan kondisi anggota keluar.
- Kontribusi yang diharapkan, waktu kerja fleksibel, hak credit, portfolio, dan mekanisme dispute.
- Tools yang disediakan tim, penggunaan asset pihak ketiga, serta kebijakan akses dan pencabutan akses.

Tidak ada persentase revenue, komitmen biaya, atau pembagian kepemilikan yang diputuskan dalam dokumen ini.

## 16. Roadmap dan backlog MVP

### 16.1 Prioritas scope

**P0 — wajib sebelum closed alpha:** latihan solo/co-op, lobby/intermission, ronde 5–6 pemain, role assignment, map tiga zona, keycard langsung membuka gate, capture, rescue, mutasi, vent, HUD PC-mobile, cleanup dan private playtest.

**P1 — setelah loop stabil:** visual/audio polish, heartbeat, polish onboarding, XP/level sederhana, telemetry, balancing pass, accessibility settings tambahan, eksperimen timer anti-camping bila layout P0 belum cukup.

**P2 — post-MVP:** classes (Engineer, Medic, Scout, Researcher), minigame genset opsional, System Lockdown dan eksperimen bonus speed, gadget, CCTV, random blackout/gas event, additional mutant types, map tambahan, shop kosmetik, leaderboard, cross-server matchmaking, social features.

Jangan membuka P2 ketika P0 masih mengalami bug blocker. MVP boleh jelek secara visual, tetapi core match tidak boleh rusak.

### 16.2 Milestone estimasi

Durasi di bawah adalah contoh rencana 4–6 minggu part-time, **bukan janji tanggal rilis**. Asumsi: tim kecil dengan beberapa anggota aktif, kemampuan Roblox/Luau dasar, dan komunikasi rutin. Re-estimate setelah task P0 pertama selesai.

| Milestone | Perkiraan | Deliverable / gate |
|---|---|---|
| M0: Kickoff | Minggu 1 awal | Review GDD, repo, owner, role, access, task board |
| M1: Vertical slice | Minggu 1–2 | Profil Red. Latihan 1–2 peserta dan ronde 5–6 pemain memakai satu keycard/gate, capture, rescue, slow, mutasi dan cleanup. |
| M2: Full core loop | Minggu 2–3 | Ronde 5–6 pemain memakai tiga zona, tiga keycard dan vent. Latihan tetap di Red. |
| M3: Closed alpha | Minggu 3–4 | Mobile HUD, semua P0 QA, 10 round tanpa blocker |
| M4: Polish & balance | Minggu 4–5 | Revisi map, art/audio pass, balancing, tutorial, telemetry minimal |
| M5: Release candidate | Minggu 5–6 atau lebih | Closed beta, performance check, asset/license review, release checklist |

Gate M1 sebelum memperluas map mencakup latihan solo dan co-op yang bisa diselesaikan via PC dan touch, semua cabang capture/rescue/mutasi dan hasil ronde yang sah, serta 10 sesi beruntun tanpa slot, timer, atau progres bocor. Uji roster lima dan enam pemain secara terpisah. Catat apakah setidaknya dua jalur menuju tabung dan gate benar-benar dapat dipakai saat dikejar.

### 16.3 Starter backlog untuk GitHub Issues

| ID | Priority | Task | Owner role | Dependency / acceptance |
|---|---|---|---|---|
| ETL-001 | P0 | Setup place, repo, group access | Lead | Owner dan permission disetujui |
| ETL-002 | P0 | Config dan match state | Gameplay | Lifecycle berjalan berulang |
| ETL-003 | P0 | Role selection + spawn | Gameplay | Tepat 1 killer, head start |
| ETL-004 | P0 | Blockout satu zona + tube | Map | Map contract subset valid |
| ETL-005 | P0 | Keycard dan progres tim | Gameplay | Pickup sah, akses tim, jumlah kartu sesuai profil |
| ETL-006 | P0 | Gate membuka dari kartu terakhir | Gameplay | Gate membuka otomatis sekali setelah 5 detik |
| ETL-007 | P0 | Capture dan tube assignment | Gameplay | Valid target, tube reserved |
| ETL-008 | P0 | Rescue dan infection timer | Gameplay | Ronde 120s, latihan 45s, hold 3s, race safe |
| ETL-009 | P0 | Mini-Mutant role dan slow | Gameplay | Mutation atomik, no stacking |
| ETL-010 | P0 | Full map 3 zona | Map | Semua tags, loop, vent positions |
| ETL-011 | P2 | Evaluasi skill tambahan anomali | Design + Gameplay | Uji setelah loop dasar dan balancing |
| ETL-012 | P0 | Vent routing | Gameplay + Map | No keycard bypass |
| ETL-013 | P0 | Gate dan results | Gameplay + UI | Escape, win, timeout |
| ETL-014 | P0 | Scientist/Killer/Captured HUD | UI | Accurate role-scoped state |
| ETL-015 | P0 | Mobile input | UI | Semua aksi tanpa keyboard |
| ETL-016 | P0 | Validation + cleanup | Gameplay + QA | Abuse dan disconnect tests |
| ETL-017 | P0 | Uji camping tabung dan gate | Designer + Map | Rescue tersedia sebelum kartu pertama. Revisi routing bila satu penjaga menutup semua pendekatan. |
| ETL-018 | P0 | Closed alpha test | QA | Matrix P0 lulus, log bug |
| ETL-019 | P1 | Character + environment polish | Art | Siluet, contrast, performance |
| ETL-020 | P1 | Sound dan accessibility | Client + Art | Audio settings, warning readable |
| ETL-021 | P1 | XP dan persistence | Gameplay | Idempotency + load failure test |
| ETL-022 | P1 | Telemetry + balance review | Designer + QA | Data match dapat dievaluasi |
| ETL-023 | P1 | Closed beta + release checklist | Lead + QA | Tidak ada blocker terbuka |
| ETL-024 | P0 | Latihan solo/co-op dan transisi lobby | Gameplay + UI | Latihan memakai loop satu zona, kondisi akhir dan cleanup sesuai §9.0. QA-23 dan QA-24 lulus. Target M1. |

### 16.4 Definition of Done

Task selesai jika acceptance criteria terpenuhi, diuji dengan minimal dua client bila relevan, tidak menimbulkan error baru yang diketahui, direview anggota lain, dokumentasi/config diperbarui, dan merge/publish ke environment pengujian berhasil. Cosmetic polish bukan syarat vertical slice.

## 17. Playtest dan success metrics

### 17.1 Rencana pengujian

1. Internal technical test: jalankan solo, co-op, lalu tambah pemain sampai lima dan enam tanpa restart. Pastikan 3–4 pemain tetap menunggu dan peserta latihan bisa pindah ke ronde. Uji join setelah roster terkunci, rescue dan mutasi.
2. Full lobby test: 6 orang, coba strategi berbeda (rush objective, rescue-heavy, killer camping, vent routing).
3. Closed alpha: undang komunitas, target 15–25 tester, beberapa sesi full lobby; catat perangkat dan feedback.
4. Iterasi: ubah maksimal beberapa parameter balancing utama tiap putaran agar dampaknya bisa dipahami.
5. Closed beta: tester baru tanpa penjelasan verbal; ukur apakah tutorial, objective tracker dan kontrol cukup jelas.

### 17.2 Metrics awal

| Metric | Definisi | Target / hipotesis awal |
|---|---|---|
| Match completion | Round normal selesai / round dimulai | ≥ 90% pada closed alpha |
| Scientist faction win rate | Round normal dengan ≥1 escape / round normal | 40–60%; evaluasi per jumlah pemain |
| Escape rate per Scientist | Jumlah escape / jumlah Scientist awal pada round normal | 30–60% |
| Rescue success | Korban diselamatkan / episode capture yang berakhir rescue atau mutation | 35–65% |
| Median match duration | Median waktu Active ronde kompetitif normal per mode | Target awal 5–10 menit. |
| Penyelesaian latihan | Sesi latihan selesai / sesi latihan dimulai, per mode | Catat selesai, timeout, keluar, pindah ke ronde, dan hasil rescue co-op. Ambil baseline alpha. |
| First objective clarity | Tester baru memahami objective tanpa bantuan | ≥ 80% pada sesi observasi |
| Mobile frame rate | FPS pada HP uji selama chase | ≥ 30 FPS sebagai target awal |
| Critical bug count | Bug yang memblokir core loop | 0 sebelum release |

Target merupakan hipotesis ETL. Laporkan jumlah sampel, disconnect, role, mode, map version, dan distribusi hasil. Pisahkan metrik latihan dari statistik kompetitif. Kelompokkan ronde kompetitif menurut mode dan ukuran roster awal, lalu bandingkan hasil sebelum dan sesudah mutasi pertama. Jangan mengambil kesimpulan balancing dari satu atau dua match.

Telemetry minimum mencatat `practice_started`, `practice_ended`, `round_started`, `keycard_acquired`, `gate_opened`, `player_captured`, `player_rescued`, `player_mutated`, `player_escaped`, `round_ended`, dan `round_cancelled`. Sertakan ID sesi, mode, ukuran roster awal, versi build, waktu berjalan, dan alasan sesi berakhir. Untuk prototipe, log internal cukup. Hindari isi chat dan informasi pribadi yang tidak diperlukan.

### 17.3 Template feedback tester

```text
Build / device:
Role terakhir:
Durasi match:
Bagian paling seru:
Bagian paling membingungkan:
Apakah chase terasa adil? (1–5)
Apakah rescue terasa layak dicoba? (1–5)
Apakah mutant terasa menyenangkan? (1–5 / N/A)
Bug + langkah reproduksi:
Apakah mau main lagi? Kenapa?
```

## 18. Risiko dan keputusan terbuka

| Risiko / keputusan | Rekomendasi awal | Cara verifikasi |
|---|---|---|
| Infection snowball | Mutant hanya slow, capture tetap Subject Zero | Bandingkan win/escape rate setelah infeksi pertama |
| Gate camping | Cover dan beberapa pendekatan ke satu gate | Playtest 1 killer + beberapa mutant di endgame |
| Tube camping | Multiple approaches + bounded timer extension | Uji strategi camp dan rescue |
| Keycard shared vs inventory | Shared team access | Uji disconnect dan pemahaman HUD |
| Capture langsung vs HP/downed | Direct capture untuk MVP | Uji rasa adil, latency dan range |
| Snowball setelah mutasi pertama | Subject Zero punya kecepatan tetap. Mini-Mutant membantu lewat slow. | Bandingkan escape dan keputusan rescue pada roster lima dan enam. |
| Map terlalu kecil/besar | Ukur travel time pada blockout | Uji chase dan rotasi vent |
| Killer terlalu lambat saat awal | Base speed 19, sprint Scientist terbatas | Uji durasi chase dan stamina |
| Camping tetap efektif setelah perubahan layout | Eksperimen timer masuk P1 jika playtest P0 menunjukkan masalah berulang | Uji pemahaman pemain dan kemungkinan memperpanjang infeksi dengan sengaja |
| Scope creep | Freeze P0 sampai vertical slice lulus | Review backlog mingguan |
| Ownership / revenue | Kesepakatan tertulis sebelum rilis | Persetujuan seluruh kontributor |
| Asset dan content maturity | Horror-lite, asset berizin, review aturan rilis | Checklist lisensi dan aturan Roblox saat publish |

### Kickoff checklist

- [ ] Tim menyetujui visi dan batas P0.
- [ ] Review baseline capture langsung, slow mutant, hasil ronde §9.2, dan routing anti-camping P0.
- [ ] Tentukan owner Roblox experience dan repo serta akses anggota.
- [ ] Pilih Team Create saja atau Team Create + Git/Rojo.
- [ ] Assign PIC pekerjaan M1, termasuk gate, UI minimum, kontrol touch, cleanup, dan latihan ETL-024.
- [ ] Bangun blockout satu zona tanpa polish.
- [ ] Buktikan alur latihan ke ronde, capture → tube → rescue/mutasi, dan cleanup pada profil satu zona sebelum membuat seluruh map.
- [ ] Jadwalkan sesi playtest pertama sesuai ketersediaan tim.
- [ ] Catat keputusan kompensasi dan ownership secara transparan.

## 19. Referensi

### Sumber konsep

- Penjelasan Fathan Dzaki melalui WhatsApp, 27 November 2026. Contohnya 5–6 pemain, satu anomali, pemain lain mencari kunci untuk keluar, korban bisa ditolong selama timer fleksibel, lalu pindah tim jika gagal diselamatkan. Facility 07, tabung, keycard berwarna, slow mutant dan angka prototipe adalah pengembangan tim.
- Gambar referensi Central Hub / koridor laboratorium yang disertakan, dengan atribusi tertulis D&M Production. Hak penggunaan aset asli tidak diverifikasi.
- Pengembangan dalam dokumen ini merupakan proposal desain, bukan kutipan mekanik dari game lain atau hasil playtest.

### Dokumentasi teknis resmi Roblox

- [Client-server runtime](https://create.roblox.com/docs/projects/client-server)
- [Securing the client-server boundary](https://create.roblox.com/docs/scripting/security/client-server-boundary)
- [Remote events and callbacks](https://create.roblox.com/docs/scripting/events/remote)
- [Proximity prompts](https://create.roblox.com/docs/ui/proximity-prompts)
- [Cross-platform development](https://create.roblox.com/docs/projects/cross-platform)
- [Collaboration / Team Create](https://create.roblox.com/docs/projects/collaboration)

Dokumentasi di atas menjadi referensi prinsip teknis dan input/collaboration. Detail konfigurasi, kode contoh, arsitektur, dan angka balancing ETL masih perlu implementasi serta verifikasi di Roblox Studio.

---

**End of document — ETL v0.3.**

**Langkah berikutnya** adalah review tim dan uji vertical slice satu zona untuk latihan 1–2 peserta dan ronde 5–6 pemain.
