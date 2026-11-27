# Escape the Lab · Katalog Aset Produksi

Katalog ini menurunkan [GDD dan TDD v0.2](ESCAPE_THE_LAB_GDD.md) menjadi brief untuk map builder, 3D artist, animator, UI, VFX, dan audio. Ukuran dan durasi yang diberi sebagai target awal boleh disetel setelah uji Studio. Jumlah pada tabel adalah model unik atau set yang harus dibuat. Jumlah penempatan di map ditulis terpisah untuk prefab yang dipakai ulang.

| Tahap | Paket yang harus bisa diuji |
|---|---|
| **M1 · P0** | Lobby, hub, Red Sector, arena latihan dan ronde pendek, satu gate, satu pintu, satu genset, satu kartu Red, tiga tabung publik, tiga spawn Scientist, satu spawn Subject Zero. Pakai bentuk sederhana dengan siluet, ukuran, collision, UI dan feedback yang sudah representatif. |
| **M2 · P0** | Tambah Blue dan Green, dua pintu, dua genset, dua kartu warna, tiga tabung, tiga spawn Scientist, enam mulut vent, visual Lockdown, dan landmark tiap zona. |
| **P1** | Polish lingkungan, suara, animasi, pencahayaan, identitas visual, onboarding dan progression sesuai GDD. |
| **P2** | Kandidat post-MVP. Buat konsep setelah fitur pemiliknya disetujui. |

## 1. Panduan visual dan skala

- **Facility 07** adalah laboratorium bawah tanah dengan bentuk industrial stylized. Siluet besar, panel baja, kabel, pipa dan alat berat memberi konteks. Horornya muncul dari ruang, suara, dan perubahan lampu. Mutasi memakai siluet dan perubahan material tanpa gore.
- **Material dasar** charcoal `#101719`, steel `#28363A`, concrete `#667477`. Red `#EF4444` dengan segitiga, Blue `#60A5FA` dengan persegi, Green `#4ADE80` dengan lingkaran. Evakuasi amber `#FBBF24` dengan simbol exit. Pakai teks dan bentuk di samping warna, termasuk pada kartu, pintu, genset dan HUD.
- **Patokan blockout** hub diameter ±60 studs, map penuh ±280 × 280, lorong utama 12–16, samping 8–12, ruang genset ±24 × 24, tinggi ruang 12–18. Mulai dari grid 4 studs untuk kit. Uji jarak dengan avatar dan kamera third-person selama sprint. Jalur hub ke genset ditargetkan 8–15 detik lari normal.
- **Prefab interaktif** punya root dan pivot tetap, collision sederhana, anchor untuk prompt/VFX/audio bila diperlukan, dan model visual yang bisa diganti tanpa mengganti kontrak. Untuk pintu dan gate, ukur ruang bebas ketika terbuka serta posisi collision saat tertutup. Simpan sumber yang bisa diedit bersama file siap impor.

## 2. Lingkungan dan arsitektur

| ID · aset | Tahap · jumlah | Brief pembuatan dan cek |
|---|---|---|
| ENV-01 · Lobby briefing | M1 · 1 area | Ruang aman di luar arena. Mulai ±28 × 24 studs, meja briefing, papan status, dan tempat berkumpul yang menampung tujuh avatar. Sediakan titik spawn lobby terpisah dari spawn ronde. Uji kamera dekat dinding dan peralihan ke arena. |
| ENV-02 · Central Hub | M1 · 1 area | Ruang melingkar ±60 studs. Pilar dan meja keamanan memecah line of sight, tiga bukaan cabang memberi orientasi, jalur ke gate terbaca dari pintu masuk. Siapkan penutup fisik yang bisa dipasang pada cabang Blue dan Green untuk profil satu zona. |
| ENV-03 · Koridor publik dan alcove tabung | M1/M2 · 1 jaringan | Hubungkan lorong Red, Blue dan Green sebelum pintu akses. Pakai belokan, dua cabang menuju tiap tabung, dan cover di dekat titik keputusan. T1–T2 di koridor Red, T3 di tepi hub, T4 di pendekatan Blue, T5–T6 di pendekatan Green. Uji rute saat semua pintu terkunci. |
| ENV-04 · Alcove spawn Scientist | M1/M2 · 3 → 6 titik | Tempatkan S1–S6 tersebar di area hub yang aman. Pakai signage, lampu rendah dan cover belakang. Sediakan ruang untuk avatar muncul dan bergerak tanpa bertabrakan. Jauhkan dari T3 dan escape trigger. |
| ENV-05 · Security annex Subject Zero | M1 · 1 ruang | Ruang spawn terpisah dengan kisi atau pintu servis dan jalur langsung menuju hub. Sediakan ruang framing untuk siluet Subject Zero saat role reveal. Geometri tetap aman selama head start dan bebas hambatan saat killer dilepas. |
| ENV-06 · Red Research & Security | M1 · 1 zona | Ruang riset, ruang keamanan dan power room Red. Rak dan meja membentuk satu loop pengejaran. Aksen amber-merah dan segitiga di pintu. Tempatkan genset di ujung zona dengan ruang untuk dua pemain berinteraksi dan jalur mundur yang jelas. |
| ENV-07 · Blue Cryo & Control | M2 · 1 zona | Cryo storage dan ruang kontrol dengan mesin pendingin, panel buram, dan aksen biru-persegi. Cover lebih rapat daripada Red, tetap sisakan loop dan orientasi ke genset. Gunakan embun tipis pada permukaan atau VFX lokal. |
| ENV-08 · Green Containment | M2 · 1 zona | Ruang containment dan specimen dengan aksen hijau-lingkaran, pipa overhead, dan jendela observasi. Buat loop melewati dua landmark berbeda supaya pemain bisa memberi arahan lokasi. Tempatkan genset di power room. |
| ENV-09 · Pendekatan evakuasi | M1 · 1 area | Buat dua pendekatan dari sisi berbeda dengan cover yang memutus pandangan. Jalur menyatu di sekitar gate dan mengarah ke volume escape. Uji apakah satu killer bisa menutup semua jalur, lalu ulangi pada M2 dengan beberapa mutant. |
| ENV-10 · Interior ventilasi | M2 · 1 kit, 3 pasangan | Modul lurus, siku, panel kisi, kipas dan lampu servis redup. Rute RB, RG dan BG masing-masing punya dua mulut yang jelas. Jika transit dipresentasikan sebagai adegan pendek, buat framing yang bisa dipakai ulang dan akhir yang menunjukkan pemain sudah tiba di zona tujuan. |
| ENV-11 · Kit dinding | M1 · 1 kit | Panel tertutup, panel jendela, sudut dalam/luar, ujung, dan frame pintu. Pakai lebar kelipatan 4 studs dan sambungan flush. Satu potongan panjang, satu pendek dan sudut cukup untuk blockout. Tambahkan detail panel di P1. |
| ENV-12 · Kit lantai dan plafon | M1 · 1 kit | Pelat datar, kisi, sambungan, garis tepi, ramp ringan, plafon panel dan akses servis. Buat collision lantai rata dan bebas sambungan yang menyangkut avatar. Plafon menjaga kamera third-person tetap nyaman. |
| ENV-13 · Kit struktur dan cover | M1 · 1 kit | Pilar, balok, penghalang rendah, sekat tinggi, railing dan penutup cabang. Mulai dengan cover tinggi ±7 studs dan tes terhadap garis pandang actual avatar. Pakai bentuk sederhana supaya pembacaan ruang konsisten saat sprint. |
| ENV-14 · Lighting rig Facility 07 | M1 dasar · P1 polish | Susun lampu overhead, lampu servis, lampu zona dan indikator darurat. Jalur publik dan titik interaksi tetap terbaca pada HP. Simpan setup default dan kondisi gelap untuk uji, dengan visual yang tetap terbaca saat efek kedip dikurangi. |

## 3. Prefab gameplay dan props

| ID · aset | Tahap · jumlah | Brief pembuatan dan cek |
|---|---|---|
| OBJ-01 · Keycard | M1/M2 · 1 model, 3 varian | Kartu polimer dengan sudut terpotong, label R/B/G dan simbol zona yang terbaca dari atas. Mulai ±1,2 × 0,8 × 0,1 studs, dengan highlight pickup yang tetap terlihat pada latar gelap. Tampilkan state tersedia dan sudah diambil. M1 memuat Red. |
| OBJ-02 · Keycard spawn marker | M1/M2 · 3 → 9 penempatan | Marker editor tanpa visual in-game. Tag `KeycardSpawn`, atribut `SpawnId` dan `Color`. Tiga titik publik per warna, seperti di meja, rak terbuka, dan panel lorong. Jangan tumpang tindih antarwarna atau terhalang pintu zona. |
| OBJ-03 · Pintu zona dan scanner | M1/M2 · 1 prefab, 3 varian | Pintu geser baja, lampu status, scanner samping dan logo zona. Bukaan awal ±8 × 10 studs. Buat state terkunci, siap dibuka, membuka, terbuka dan Lockdown (M2). Root bertag `ZoneDoor` dengan `ZoneId`. Scanner dapat memakai mesh yang sama pada semua warna. |
| OBJ-04 · Genset | M1/M2 · 1 prefab, 3 penempatan | Unit ±5 × 3 × 4 studs dengan blok mesin, kabel, panel meter dan titik servis. State mati, diperbaiki, dan aktif. Buat dua posisi penolong dan anchor untuk audio serta indikator. Tag `Generator`, `ZoneId`, `ObjectiveId`. Model sama dengan decal zona berbeda. |
| OBJ-05 · Gate evakuasi | M1 · 1 prefab | Shutter baja dengan lampu amber, panah exit dan indikator hubungan genset. Bukaan awal ±10–12 × 10 studs. Siapkan terkunci, transisi buka 5 detik dan terbuka. Tag `EvacuationGate` dengan `GateId`. Uji area gerak daun pintu saat dilewati. |
| OBJ-06 · Escape trigger | M1 · 1 volume | Volume editor tanpa visual yang menutup celah gate di sisi aman. Tag `EscapeTrigger` dan gunakan `GateId` yang sama dengan gate. QA memastikan trigger bisa dilewati dari seluruh lebar bukaan dan tidak bisa tersentuh dari alcove atau sudut dinding. |
| OBJ-07 · Infection Tube | M1/M2 · 1 prefab, 3 → 6 penempatan | Pod vertikal transparan sebagian, diameter awal ±4 studs, tinggi ±9. Base stabil, pengunci dan panel rescue menghadap jalur publik. State kosong, terisi, rescue berlangsung, release dan mutasi. Anchor korban, panel dan titik keluar aman untuk Scientist atau Mutant. Tag `InfectionTube`, `TubeId` dan `AreaId`. Uji siluet korban dari kedua pendekatan. |
| OBJ-08 · Vent entrance dan hatch | M2 · 1 prefab, 6 penempatan | Kisi di dinding dengan garis aliran udara dan ikon vent. Anchor prompt, titik masuk/keluar dan ruang bebas avatar. Buat idle, sedang masuk dan selama cooldown. Tag `VentEntrance`, `VentId`, `ZoneId`, `LinkedVentId`. Uji tiga pasangan dua arah dan akses saat zona terkunci. |
| OBJ-09 · Penanda spawn arena | M1/M2 · 4 → 7 marker | Marker editor dengan panah arah dan clearance kamera. Tag `ScientistSpawn` untuk S1–S6 dan `KillerSpawn` untuk annex, masing-masing dengan `SpawnId`. Uji posisi muncul dan arah pandang berbeda untuk setiap titik. |
| OBJ-10 · Marker latihan | M1 · 1 set | Anchor penunjuk untuk kartu, pintu, tabung, genset dan gate. Gunakan ulang titik prefab yang sudah ada. Penanda berganti setelah aksi sah dan hilang ketika pemain keluar dari latihan. |
| PROP-01 · Meja riset dan troli | M1 · 2 model | Meja baja berpanel dan troli beroda dengan 1–2 perkakas besar. Pakai meja sebagai cover dan permukaan kartu. Permukaan bersih untuk prompt, collision sederhana, roda boleh menyatu pada mesh. |
| PROP-02 · Rak, locker dan crate | M1 · 3 model | Rak terbuka, locker tinggi, crate tumpuk. Pakai campuran siluet untuk cover, penanda lorong dan penempatan kartu. Buat collision per volume besar dan cek celah yang memang dapat dilalui. |
| PROP-03 · Papan zona dan rambu | M1/M2 · 1 set | Rambu nama area, panah arah, Restricted, Power dan Exit. Sertakan huruf serta bentuk zona. Buat ukuran pintu dan koridor, dengan kontras yang masih terbaca dari arah pemain mendekat. |
| PROP-04 · Lampu dan alarm | M1/M2 · 3 model | Batang overhead, lampu dinding, beacon darurat. Housing gelap dengan diffuser terang. Gunakan bahan emissive sebagai dasar dan lampu lokal seperlunya. Beacon mempunyai idle dan alarm. |
| PROP-05 · Pipa, kabel dan duct dinding | M1/P1 · 1 kit | Segmen lurus, siku, junction, klem dan kabel gantung untuk dressing. Posisikan di luar rute kamera atau kaki avatar. Pakai cross-section dan material bersama. |
| PROP-06 · Terminal keamanan | M1/P1 · 2 model | Meja monitor hub dan terminal dinding Red dengan layout status sederhana. Bentuk besar memberi landmark. Gunakan visual statis untuk M1 dan tambah layar rusak atau animasi ringan di P1. |
| PROP-07 · Cryo tank dan kontrol | M2/P1 · 2 model | Tangki dingin tertutup dengan gauge biru dan panel kontrol, diberi simbol persegi. Siluet horizontal atau badan buram membedakannya dari Infection Tube yang berisi pemain. |
| PROP-08 · Specimen dan containment | M2/P1 · 2 model | Canister tertutup dengan siluet spesimen abstrak, dan frame jendela observasi tebal. Label hijau-lingkaran. Atur ukuran detail agar mudah dibedakan dari tabung rescue saat berlari. |
| PROP-09 · Lab clutter | P1 · 1 set | Clipboard, kartu identitas dekoratif, beaker, sampel tertutup, kabel gulung dan kertas. Pakai kelompok kecil pada meja/rak. Hindari icon glow yang menyerupai kartu interaktif. |
| PROP-10 · Decal dan material | M1/P1 · 1 set | Pelat baja, beton, karet, kaca buram, garis hazard, nomor fasilitas dan noda pelapukan ringan. Siapkan swatch agar level builder memakai material yang sama. Uji tekstur pada skala map dan layar HP. |

## 4. Karakter, senjata fiksi dan perlengkapan

| ID · aset | Tahap · jumlah | Brief pembuatan dan cek |
|---|---|---|
| CHR-01 · Scientist | M1 · 1 baseline avatar | Pakai avatar standar dengan jas lab pendek atau jumpsuit abu-abu, ID badge, dan aksen punggung kecil. Jaga wajah serta tangan tetap terbaca. Uji kompatibilitas rig avatar, sprint, pose interaksi, kamera, dan siluet pemain di tabung. |
| CHR-02 · Subject Zero | M1 · 1 rig | Siluet paling besar. Bahu asimetris, lengan depan dominan, sisa harness containment dan visor pecah bergaya. Charcoal dengan aksen amber atau putih pucat. Buat tampak depan, samping, belakang dan pose capture. Uji bahwa visual lengan dan indikator capture menjelaskan jangkauan gameplay 5 studs. |
| CHR-03 · Mini-Mutant | M1 · 1 rig | Tubuh lebih kecil dari Subject Zero, pose condong, serpihan jas lab atau ID Scientist masih terlihat. Aksen mutasi dibatasi pada tangan dan wajah. Gerak dan siluet membuat penyerang slow mudah dibedakan dari killer utama pada jarak koridor. |
| GEAR-01 · Lengan capture Subject Zero | M1 · terintegrasi ke CHR-02 | Senjata visual bawaan karakter berupa sarung lengan containment yang rusak, dengan tiga bidang tumpul besar dan garis energi tipis. Forearm dan tangan bergerak mengikuti pose grab. Sinkronkan pose, cue audio/VFX, dan hasil capture yang sudah disahkan server. |
| GEAR-02 · Tangan mutasi Mini-Mutant | M1 · terintegrasi ke CHR-03 | Siluet jari bercabang pendek dengan emissive redup untuk cue slow. Buat sweep yang lebih pendek dan ringan daripada grab Subject Zero. Uji bahwa feedback bisa dibedakan dari capture pada layar kecil. |
| GEAR-03 · Modul System Lockdown | M2 · 1 aksesori | Kontrol pergelangan Subject Zero yang terhubung ke HUD pemilihan zona. Panel gelap dengan tiga simbol zona dan pola pulsa saat aktivasi. Buat mount tangan, pose aktivasi, dan feedback ketika pintu sukses terkunci. |
| GEAR-04 · Perkakas servis Scientist | P1 · 1 set opsional | Handheld diagnostik atau tool prop pendek untuk pose repair dan rescue. Rentang warna netral, grip point jelas, tanpa benturan keras dengan panel. Bisa dipakai ulang antar Scientist tanpa mengubah mekanik. |
| GEAR-05 · Gadget Scientist fiksi | P2 · 2 kandidat | Beacon umpan suara dan scanner jejak sebagai contoh gadget nonlethal. Beacon butuh model dunia, ikon deploy dan cue audio. Scanner butuh model tangan, ikon dan tampilan feedback. Keduanya perlu validasi desain gameplay sebelum diproduksi. |
| GEAR-06 · Varian senjata kosmetik | P2 · 2 konsep awal | Varian shell lengan Subject Zero dan pola tangan Mini-Mutant. Buat siluet dengan batas dimensi rig dasar, timing dan keterbacaan yang sama. Gunakan pasangan warna/material yang berbeda dari simbol akses zona. |

**Batas desain senjata.** MVP memakai capture Subject Zero dan slow Mini-Mutant. Scientist bertahan dengan sprint, jalur dan kerja sama. Perkakas dan varian di atas adalah brief visual. Gadget yang mengubah gameplay masuk P2. [GDD §5 dan §16](ESCAPE_THE_LAB_GDD.md#5-faksi-karakter-dan-balancing)

## 5. Animasi karakter dan objek

| ID · set | Tahap · klip atau state | Brief pembuatan dan cek |
|---|---|---|
| ANM-01 · Lokomosi Scientist | M1 · idle, walk, sprint | Pose siap, langkah normal dan sprint panik yang terbaca dari belakang. Gunakan loop yang halus dan cocok dengan kecepatan in-game serta suara langkah. |
| ANM-02 · Interaksi Scientist | M1 · pickup, scan, repair, rescue | Pickup dan scan singkat. Repair berupa loop yang bisa dihentikan dan dipakai sampai progres selesai. Pose rescue pegang panel selama hold 3 detik. Uji batal saat pemain bergerak dan transisi kembali ke idle. |
| ANM-03 · Scientist di tabung | M1 · captured idle, release | Pose tertahan yang muat di kaca, gerakan napas ringan dan pose keluar. Buat transisi pendek agar pemain bisa kembali bergerak saat server mengizinkan. |
| ANM-04 · Lokomosi Subject Zero | M1 · idle, walk/run, aksen Rush | Idle bahu berat dan langkah yang terbaca di koridor. Sesuaikan frekuensi loop dengan kecepatan setelah genset aktif. Aksen Rush dapat berupa perubahan pose dan cue pendek. |
| ANM-05 · Capture Subject Zero | M1 · 1 aksi | Antisipasi lengan, gerak meraih, lalu recovery. Posisi kontak visual mengikuti jangkauan yang sudah divalidasi. Korban memakai transisi singkat ke tabung, sesuai capture langsung. |
| ANM-06 · Lokomosi Mini-Mutant | M1 · idle, walk/run | Tubuh condong, langkah cepat kecil, bahu berbeda dari Subject Zero. Blend dari mutasi ke gerak normal dengan frame awal yang stabil. |
| ANM-07 · Slow Mini-Mutant | M1 · swipe | Sapuan pendek dengan awal, kontak dan recovery. Jaga gesture ringkas supaya pemain punya cue visual yang konsisten dengan slow dan cooldown. |
| ANM-08 · Transformasi | M1 · 1 transisi | Kabut singkat, pose Scientist berakhir, lalu siluet Mini-Mutant muncul di titik aman. Role HUD berubah setelah transisi gameplay. Cek kamera korban dan pemain yang melihat dari luar tabung. |
| ANM-09 · System Lockdown | M2 · 1 gesture | Subject Zero memutar lengan dan memicu panel pergelangan. Gunakan cue berbeda dari ancang-ancang capture, lalu hubungkan ke feedback pintu sasaran. |
| ANM-10 · Masuk/keluar vent | M2 · 2 klip | Interaksi buka, masuk, lalu keluar menghadap arah yang aman. Sisakan ruang bagi kamera dan pakai titik acuan yang konsisten pada enam mulut vent. |
| ANM-11 · Mekanik prefab | M1/M2 · pintu, gate, pod, hatch | Pintu geser dengan state Lockdown pada M2, gate bergerak selama 5 detik, pod latch buka/tutup, hatch vent. Uji pause, replay dan reset tiap state tanpa tertinggal pada pose antara. |
| ANM-12 · Role reveal dan emote | P1/P2 · 3 role pose, emote opsional | Pose singkat Scientist, Subject Zero dan Mini-Mutant untuk role/reward screen. Emote kosmetik P2 memakai slot terpisah dan menyisakan keterbacaan role. |

## 6. UI, ikon dan identitas visual

| ID · aset | Tahap · jumlah | Brief pembuatan dan cek |
|---|---|---|
| UI-01 · Lobby dan status siap | M1 · 1 layar | Jumlah pemain siap, toggle Siap, opsi mulai solo/co-op dan persetujuan co-op. Buat state menunggu, latihan berlangsung, ronde siap, `Ikut Ronde` dan intermission. Uji transisi 1 → 2 → 3 → 4 pemain. |
| UI-02 · Role reveal dan tutorial | M1 · 1 layout modular | Judul role, tujuan satu kalimat, ikon aksi utama dan langkah berikutnya. Tutorial latihan mengikuti urutan kartu, pintu, tabung co-op, genset, gate. |
| UI-03 · HUD Scientist | M1/M2 · 1 layout responsif | Timer ronde, genset aktif, status kartu/pintu, stamina, marker tabung dan status gate. M1 menampilkan satu zona, M2 menampilkan tiga. Prioritaskan informasi rescue dan objective di layar kecil. |
| UI-04 · HUD Subject Zero | M1/M2 · 1 layout | Jumlah Scientist aktif, tertangkap, kabur dan bermutasi, timer, indikator capture dan bonus Rush. M2 menambah pemilihan zona Lockdown beserta valid, terkunci dan cooldown. |
| UI-05 · HUD Captured | M1 · 1 panel | Countdown infeksi dan tombol ping rescue, dengan location marker yang dibaca teman. Tambahkan hasil rescue, gagal latihan atau berubah jadi mutant sesuai mode. |
| UI-06 · HUD Mini-Mutant | M1 · 1 panel | Ikon tim killer, tombol slow dan cooldown. Feedback kontak berhasil atau sedang kebal memberi pemain status yang jelas. |
| UI-07 · Prompt interaksi | M1/M2 · 1 komponen | Label aksi, binding keyboard atau tombol touch, progres hold dan feedback batal. Pakai untuk kartu, pintu, repair, rescue dan vent. Validasi status terkunci dan saat aktivitas berubah. |
| UI-08 · Kontrol touch | M1/M2 · 1 set | Tombol sprint, interaksi, attack, ping dan skill M2. Ukuran dan posisi mengikuti area aman, dengan state hold, cooldown dan disabled. Uji pakai dua jempol sambil bergerak dan menggeser kamera. |
| UI-09 · Spectator dan Results | M1 · 2 panel | Spectator punya target yang jelas atau pesan menunggu. Results menampilkan individu dan faksi, jumlah escape, rescue, mutasi, genset dan alasan ronde batal. Latihan punya hasil dan pilihan ulang tersendiri. |
| UI-10 · Settings dan aksesibilitas | M1 dasar · P1 polish | Sediakan pengurangan flashing/shake untuk efek yang dipakai dan kontrol audio saat tersedia. Label, ikon dan state tetap terbaca dengan efek suara mati atau warna sulit dibedakan. |
| UI-11 · Icon atlas | M1/M2 · 1 set | Ikon tiga warna/simbol zona, tiga role, kartu, pintu, genset, tabung, rescue ping, stamina, slow, lockdown, vent, gate, waktu dan hasil. Buat state aktif/disabled seperlunya. Tes ukuran icon aktual di perangkat. |
| UI-12 · Logo dan halaman Roblox | P1 · 1 wordmark, 1 icon, 2 thumbnail | Logo mengikuti panel industrial tanpa kehilangan keterbacaan. Thumbnail pertama menunjukkan hub dan Subject Zero, kedua menunjukkan rescue. Simpan master yang dapat di-crop, dengan area penting di tengah. |
| UI-13 · Progression dan shop | P1/P2 · 1 set | P1 mencakup bar XP, badge level dan breakdown results. P2 kandidat shop: grid, detail preview, equip/owned, nameplate dan tab kosmetik. Uji layout dengan nama panjang di HP. |

## 7. VFX dan pencahayaan interaktif

| ID · aset | Tahap · jumlah | Brief pembuatan dan cek |
|---|---|---|
| VFX-01 · Pickup dan objective ping | M1 · 1 set | Outline halus, pulsa pendek saat kartu diambil, marker mengarah ke langkah berikutnya di latihan. Lingkup efek mengikuti pemain yang perlu melihat informasi itu. |
| VFX-02 · Genset mati, repair, aktif | M1 · 3 state | Lampu padam, meter berkedip ringan saat repair, indikator tetap menyala dan burst pendek saat aktif. Partikel kecil lokal dengan varian efek rendah. |
| VFX-03 · Gate dan evakuasi | M1 · 1 set | Lampu amber, arah panah menyala, debu atau uap pendek saat gate membuka, cue escape yang bersih. Cue sinkron dengan state gate dan waktu escape sah. |
| VFX-04 · Capture dan tabung | M1 · 1 set | Aksen swipe, transisi singkat korban, rim light kaca saat terisi dan marker rescue. Pastikan siluet korban masih terlihat dan efek tidak menutup prompt. |
| VFX-05 · Rescue, mutasi dan proteksi | M1 · 1 set | Pulsa putih saat lepas, kabut dan perubahan siluet saat mutasi, outline perlindungan tiga detik setelah rescue. Masing-masing punya bentuk dan ritme yang berbeda. |
| VFX-06 · Rush dan slow | M1 · 1 set | Rush berupa pulsa pada harness saat genset aktif. Slow berupa garis pendek di lantai atau tepi HUD selama efek aktif. Tes dengan beberapa mutant agar efek tidak berlebihan. |
| VFX-07 · Lockdown dan vent | M2 · 1 set | Lockdown memakai segmen tertutup dan countdown pada pintu. Vent memakai puff udara dan cue masuk/keluar. Sediakan bentuk statis untuk mode reduced effects. |
| VFX-08 · Atmosfer per zona | P1 · 3 varian | Red memakai debu ringan, Blue embun lokal, Green kabut tipis di sekitar alat. Jaga rute, simbol, lawan dan prompt tetap terbaca sambil mengejar. |

## 8. Audio

| ID · aset | Tahap · jumlah | Brief pembuatan dan cek |
|---|---|---|
| AUD-01 · Ambience fasilitas | M1/P1 · 1 loop dasar, 3 layer zona | Hum listrik, aliran ventilasi dan gema ruang. M1 pakai loop dasar. P1 tambah karakter Red (relai), Blue (pendingin), Green (pompa). Buat looping tanpa klik dan transisi antararea yang halus. |
| AUD-02 · Langkah tiap role | M1 · 3 bank | Scientist ringan, Subject Zero berat, Mini-Mutant cepat dan tidak teratur. Mulai dengan 3 sampel per role untuk variasi. Cek jarak dengar dan sinkronisasi foot contact. |
| AUD-03 · Keycard dan pintu | M1/M2 · 1 set | Pickup lembut, scan diterima/ditolak, motor geser dan hentakan akhir. Bunyi scanner singkat berbeda dari bunyi hasil interaksi UI. |
| AUD-04 · Genset | M1 · 1 set | Klik repair, loop percobaan starter, bunyi menyala satu kali dan loop mesin aktif. Loop repair berhenti ketika kontribusi batal. |
| AUD-05 · Gate | M1 · 1 set | Peringatan buka, motor ±5 detik, bunyi selesai dan konfirmasi escape. Uji pemisahan volume dari alarm Lockdown. |
| AUD-06 · Capture dan tube | M1 · 1 set | Cue grab, seal pod, ambience pod yang biasa terdengar dekat dan pulse menjelang infeksi. Buat level volume yang terbaca tanpa menutupi arah langkah. |
| AUD-07 · Rescue, mutasi dan slow | M1 · 1 set | Release latch, cue mutasi non-gore, swipe mutant dan tanda slow sukses. Pisahkan cue pemain terdampak dari suara yang didengar sekitar. |
| AUD-08 · Lockdown dan ventilasi | M2 · 1 set | Alarm pendek, pintu mengunci dan terbuka lagi, gesek hatch, udara selama transit dan bunyi exit. Loop vent berhenti ketika pemain keluar atau ronde berakhir. |
| AUD-09 · UI dan hasil | M1/P1 · 1 set | Klik, berhasil/gagal, ping rescue, ronde siap, stinger hasil Scientist/Killer dan hasil latihan. Simpan level relatif konsisten dengan ambience. |
| AUD-10 · Heartbeat dan musik | P1 · 1 set | Dua atau tiga tingkat heartbeat per kedekatan dengan Subject Zero tanpa memberi jarak presisi. Musik lobby dan tension layer opsional dengan jalur volume terpisah. |

## 9. Kandidat aset post-MVP

| ID · aset | Brief saat fitur disetujui |
|---|---|
| P2-01 · Empat class Scientist | Engineer dengan tool pouch, Medic dengan pouch dan ikon medis fiksi, Scout dengan harness ringan, Researcher dengan tablet. Buat masing-masing satu siluet, satu kit ikon, dan animasi kemampuan setelah aturan class tersedia. |
| P2-02 · Minigame genset | Panel modular dengan meter timing, marker sukses/gagal dan audio cue. Preview touch dan keyboard sebelum produksi visual final. |
| P2-03 · CCTV | Kamera kubah, monitor ruang kontrol, indikator feed dan overlay. Tentukan dulu peran gameplay dan siapa yang bisa melihat feed. |
| P2-04 · Blackout dan gas event | Paket indikator neon darurat, material lampu nonaktif, kabut lokal, icon peringatan dan audio event. Uji keterbacaan jalur sepanjang event. |
| P2-05 · Varian mutant | Satu lembar konsep per kemampuan yang disetujui berisi siluet, ukuran relatif, cue ancaman, rig, animasi aksi dan feedback untuk korban. |
| P2-06 · Map tambahan | Brief satu map berisi landmark, kit modular, daftar objective prefab yang dipakai ulang, pencahayaan, audio dan kontrak marker. Tentukan layout setelah data Facility 07 tersedia. |
| P2-07 · Skin, nameplate dan emote | Satu paket kosmetik per role sebagai baseline. Buat render preview, icon inventori, rig/outline yang konsisten dan VFX yang tetap jelas bagi lawan. |
| P2-08 · Lore dan intro | Catatan riset, kartu staf, display interkom dan intro singkat opsional. Buat preview portrait, versi layar kecil, caption dan audio bila ada. |
| P2-09 · UI sosial dan leaderboard | Panel ranking, daftar party dan status antrean lintas server jika fitur tersedia. Buat state kosong, loading dan feedback perubahan anggota. |

## 10. Serah terima dan urutan pembuatan

1. **Blockout dulu.** Kerjakan ENV-01 sampai ENV-06, ENV-09, ENV-11 sampai ENV-13 dan prefab OBJ-01 sampai OBJ-07. Buktikan kartu, tiga tabung dan gate bisa dijangkau lewat rute yang direncanakan.
2. **Pasang karakter dan feedback M1.** Pakai ketiga role, animasi inti, HUD touch, VFX dan audio fungsional. Tes latihan 1–2 pemain, ronde 3–4 pemain, tabung, rescue, mutasi dan akhir ronde sebelum polish.
3. **Tambah zona.** Pasang Blue, Green, tiga tabung tambahan dan enam vent. Uji rute antarzona, Lockdown, dua pendekatan gate dan readability pada kondisi endgame.
4. **Serahkan per ID.** Sertakan sumber editable, ekspor/model Roblox, preview in-context, ukuran studs, pivot, anchor, collision, daftar state/klip, tag dan atribut yang relevan, serta catatan lisensi. Untuk VFX/audio, sertakan pemicu, durasi atau loop, dan keadaan yang menghentikan efek.
5. **Review di Studio.** Uji pada map nyata, PC dan HP. Periksa prompt, siluet, clipping kamera, collision, keterbacaan tanpa mengandalkan warna, dan performa saat beberapa pemain berada di ruang yang sama. Catat pembuat, sumber dan izin sebelum memasukkan aset pihak ketiga.
