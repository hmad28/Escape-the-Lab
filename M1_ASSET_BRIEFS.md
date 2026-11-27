# Escape the Lab · Brief Produksi Aset M1

Brief ini bisa langsung dibagikan ke Fathan, Al, dan Fachry. Tujuannya menghasilkan model 3D awal untuk prototipe Facility 07 satu zona, dengan sumber yang bisa Hammad edit dan uji di Roblox Studio. Pembagian pemilik ada di [Team Assignment](TEAM_ASSIGNMENT.md). Spesifikasi gameplay dan visual berasal dari [GDD v0.3](ESCAPE_THE_LAB_GDD.md), [Asset Catalog](ASSET_CATALOG.md), [Art Direction](ART_DIRECTION.md), dan [Map Blueprint](MAP_BLUEPRINT.md).

## Urutan pengerjaan

| Orang | Kirim untuk tes impor pertama | Kerjakan setelah Hammad menyetujui contoh |
|---|---|---|
| **Fathan Dzaki** | CHR-02 · Subject Zero, satu blockout karakter | CHR-03 · Mini-Mutant |
| **Al Ghifary** | ENV-11 · Kit dinding Red, tiga modul | ENV-12 · Lantai/plafon. ENV-13 · Pilar/cover |
| **Fachry** | OBJ-01 · Satu Keycard Red | OBJ-07 · Infection Tube. OBJ-05 · Gate evakuasi |
| **Hammad** | Uji tiga paket impor pada place privat dan beri satu daftar revisi per paket | Finalisasi visual, rig, animasi, collision, prompt, tag, anchor, script, layout dan integrasi |

## Standar bersama

- **Gaya** · Industrial sci-fi stylized. Dahulukan bentuk besar dan siluet jelas. Palet dasar charcoal `#101719`, steel `#28363A`, dan concrete `#667477`. Red memakai `#EF4444` dengan segitiga, gate memakai amber `#FBBF24` dan panah keluar. Pakai maksimal beberapa material sederhana untuk blockout. Detail kecil menyusul setelah contoh lolos impor.
- **Dimensi** · Ukuran `lebar × tinggi × kedalaman` untuk objek tegak, kecuali jika baris menyebut urutan lain. Ukuran dalam studs adalah target akhir di Studio. Cantumkan satuan di editor dan pakai satu penggaris atau objek referensi yang sama untuk tiap paket. Hammad mengunci konversi skala FBX setelah impor pertama. Pakai panah `FRONT` pada preview agar arah bisa diperiksa.
- **File 3D** · Beri nama bagian dengan fungsi yang jelas. Gunakan mesh yang bisa diedit, cek face normal dari luar, dan hindari permukaan coplanar yang saling menimpa. Boleh pakai modifier pada sumber. Pastikan hasil ekspor berisi geometri yang dimaksud. Di file ekspor, keluarkan lampu, kamera, avatar referensi, penggaris, dan teks anotasi. Simpan bagian bergerak dan kaca sebagai objek terpisah.
- **Preview** · Pakai pencahayaan netral. Tampilkan bentuk dasar, satu arah kamera bermain, dan pembanding ukuran bila dimensi penting. Preview state cukup dibuat dengan menduplikasi pose atau posisi di file sumber.
- **Bahan referensi** · Gunakan karya sendiri atau sumber berizin. Jika mengimpor material, tekstur, atau mesh pihak ketiga, sertakan pembuat, tautan, dan izin penggunaan. Catat juga bagian karya yang diambil.

## Fathan Dzaki · Karakter anomali

### CHR-02 · Subject Zero

| Aspek | Arahan pengerjaan |
|---|---|
| Fungsi di game | Anomali utama, satu per ronde. Scientist perlu mengenalinya dari ujung koridor dan saat siluet terlihat dari belakang. Lengan dominan memperjelas aksi capture. |
| Siluet | Buat kepala dengan visor sederhana, satu bahu lebih tinggi/berat, dan forearm dominan dengan sarung lengan containment. Gunakan dada lebar dan kaki kokoh sebagai bentuk utama. Sebagai starting point, pakai tinggi sekitar 1,15–1,25× avatar Scientist dengan telapak pada garis lantai yang sama. Ini ukuran visual untuk review. |
| Detail | Harness melingkari torso dan punya satu buckle besar. Visor boleh punya satu garis retak stylized. Forearm dominan cukup tiga bidang besar tumpul. Bentuk lab industrial, perubahan tubuh abstrak, dan permukaan tetap bersih dari detail gore. |
| Material | Badan charcoal, harness steel gelap, visor putih pucat atau aksen amber kecil. Sisakan kontras di kepala dan bahu ketika background gelap. Pakai satu pilihan aksen untuk draft pertama. |
| Mesh dan orientasi | Buat kepala, torso/pelvis, lengan, tangan, kaki, dan aksesori sebagai bagian yang jelas untuk rigging. Jaga siku, bahu, pinggul, dan lutut terbaca. Tempatkan titik acuan karakter di tengah antara telapak kaki. Ekspor dalam pose netral simetris pada sendi. Asimetri berasal dari desain. |
| Bukti review | Satu lembar berisi depan, samping, belakang, dan tiga perempat. Sertakan Scientist pembanding serta satu gambar pose meraih. Pose aksi boleh berupa salinan model atau sketsa di atas render. |
| Lolos bila | Hammad bisa mengenali karakter pada gambar gelap dari depan dan belakang, dapat melihat sendi yang akan di-rig, dan bisa memilih lengan capture sebagai bagian yang jelas. Model tidak mengandalkan detail kecil untuk terbaca. |

### CHR-03 · Mini-Mutant

| Aspek | Arahan pengerjaan |
|---|---|
| Fungsi di game | Scientist yang bermutasi bergabung ke tim anomali. Mini-Mutant memberi slow. Gerakan utamanya berupa swipe singkat dan harus mudah dibedakan dari grab Subject Zero. |
| Siluet | Pakai tinggi visual mendekati Scientist dan lebih kecil daripada Subject Zero. Bentuk badan ramping, bahu lebih sempit, dengan gestur condong saat bergerak. Di mesh netral, pertahankan sendi siap di-rig. Tunjukkan pose condong pada preview terpisah. |
| Detail | Sisakan potongan jas lab atau badge yang mengingatkan asal role. Aksen mutasi dibatasi pada tangan dan wajah. Buat bentuk tangan pendek dengan ujung tumpul dan siluet yang mudah dilihat dari samping. |
| Material | Abu-abu pudar pada pakaian, charcoal di tangan, dan satu aksen terang kecil. Tunjukkan visual yang cukup berbeda dari forearm dan visor Subject Zero. |
| Mesh dan bukti | Bagian dasar karakter mengikuti CHR-02. Pisahkan badge atau aksesori besar bila perlu diganti. Kirim tampak depan, samping, belakang, satu pose swipe, serta perbandingan ukuran bersama Scientist dan Subject Zero. |
| Lolos bila | Tiga role bisa dibedakan pada skala yang sama dalam satu gambar koridor. Tangan memberi cue swipe tanpa mendominasi siluet, dan sisa pakaian Scientist masih terlihat. |

## Al Ghifary · Kit lingkungan Hub dan Red

Untuk kit dinding, `lebar` mengikuti jalur dinding, `tinggi` naik dari lantai, dan `tebal` masuk ke belakang sisi yang menghadap pemain. Kunci titik acuan sambungan sebelum membuat panel tambahan. Target di bawah adalah pilihan draft untuk grid 4 studs.

### ENV-11 · Dinding modular Red

| Komponen | Ukuran dan desain | Pivot, sambungan dan tes |
|---|---|---|
| `Wall_Red_Short` | **4 × 12 × 0,5 studs**. Panel tertutup, bagian bawah lebih gelap, satu relief besar opsional. | Pivot di bawah, di ujung kiri saat dilihat dari sisi pemain. Akhiri busur/bevel sebelum bidang sambungan. |
| `Wall_Red_Long` | **8 × 12 × 0,5 studs**. Bahasa bentuk sama. Posisikan garis panel dalam ritme kelipatan 4 studs. | Pivot sama. Dua panel pendek harus sama panjang dengan satu panel panjang. |
| `Wall_Red_Corner` | Sudut dalam **90°**. Dua kaki dengan panjang nominal 4 studs, tinggi dan ketebalan sama dengan panel. Buat dinding bertemu bersih pada satu sudut. | Pivot di titik sudut pada garis lantai. Tandai dua muka yang menerima panel lurus. Preview sudut dari sisi pemain. |

Gunakan steel atau concrete netral dan satu panel tanda Red kecil. Kirim ketiga modul terpisah dan screenshot rakitan lurus `pendek + pendek` di samping `panjang`, plus satu rakitan L. **Lolos** jika tepi atas, lantai, dan garis sambungan bertemu rapat tanpa celah atau tumpang tindih terlihat. Hammad cek ulang grid dan collision di Studio.

### ENV-12 · Lantai dan plafon

| Komponen | Ukuran dan desain | Pivot dan tes |
|---|---|---|
| `Floor_Panel` | **4 × 4 studs** tapak, tebal ±0,25 studs. Pelat beton atau baja dengan tekstur/garis panel sederhana. Jaga muka atas rata di area jalan. | Pivot salah satu sudut pada permukaan pijak. Kirim preview rakitan 2 × 2 dan pertemuan dengan dinding. |
| `Ceiling_Panel` | **4 × 4 studs** tapak, tebal ±0,25 studs. Muka bawah memakai panel gelap dan bingkai tipis. | Pivot salah satu sudut pada muka bawah. Tunjukkan satu panel di atas dinding tinggi 12 studs pada preview. |

**Lolos** jika ukuran grid konsisten dengan ENV-11, permukaan pijak satu level, material tidak menyamarkan ujung lantai, dan arah panel plafon terbaca. Hammad mengecek clipping kamera dari sudut dan sambungan collision saat sprint.

### ENV-13 · Pilar dan cover

| Komponen | Ukuran dan desain | Pivot dan tes |
|---|---|---|
| `Pillar_Hub` | **2 × 12 × 2 studs**. Inti kuat dengan base tipis dan bentuk simetris sehingga bisa diputar. | Pivot tengah bawah. Preview di hub dan dekat dinding untuk memperlihatkan ruang jalan. |
| `Cover_Red_High` | **4 × 7 × 2 studs**. Sekat atau konsol tinggi dengan footprint sederhana. Pakai massa padat untuk menutup pandangan dari beberapa sudut. | Pivot tengah bawah. Preview dari kedua sisi dengan avatar. Sisakan lintasan di sampingnya saat disusun di lorong. |

**Lolos** jika kedua aset bisa dipindah/dirotasi tanpa menggeser dasar dari lantai dan cover bisa dibaca sebagai penghalang. Tinggi akhir cover ditentukan Hammad setelah tes garis pandang dan kamera.

## Fachry · Prefab interaktif

### OBJ-01 · Keycard Red

| Aspek | Arahan pengerjaan |
|---|---|
| Fungsi | Objek pickup yang membuka gate setelah syarat kartu dipenuhi. M1 memerlukan satu kartu Red. Hammad akan menempatkannya pada tiga kandidat spawn. |
| Dimensi dan bentuk | Tapak **1,2 × 0,8 studs**, tebal **0,1 studs**. Satu sudut terpotong, sisi utama rata, dengan label `R` dan simbol segitiga yang mengisi bagian cukup besar. |
| Material | Badan polimer gelap, panel merah dengan simbol kontras. Buat label agar tetap terbaca dalam grayscale. Bila memakai tekstur, sertakan PNG sumber atau file editable yang memuat label. |
| Pivot dan ekspor | Pivot di tengah bawah kartu, muka berlabel menghadap atas saat kartu diletakkan. Satu mesh cukup. Kirim render tampak atas dan contoh di atas meja Red yang gelap. |
| Lolos bila | Siluet kartu tampak berbeda dari kartu dekorasi, `R` atau segitiga mudah dikenali, dan aset duduk rata di meja saat diimpor. Hammad menambah prompt dan highlight pickup. |

### OBJ-07 · Infection Tube

| Aspek | Arahan pengerjaan |
|---|---|
| Fungsi | Menampung satu korban dan menampilkan posisi rescue. Buat **satu prefab 3D** yang akan Hammad gandakan menjadi T1–T5 di map. Panel rescue dan siluet korban perlu terbaca dari dua pendekatan. |
| Dimensi dan bentuk | Pod vertikal diameter luar awal **±4 studs**, tinggi **±9 studs**. Base stabil, rangka tipis, panel rescue di muka publik, serta bukaan yang menyisakan ruang avatar. Gunakan satu preview berisi avatar pembanding di dalam pod. Perlebar setelah review bila avatar atau pose keluar clipping. |
| Mesh terpisah | `Tube_Base`, `Tube_Frame`, `Tube_Glass`, `Tube_Hatch`, `Tube_RescuePanel`, `Tube_StatusLight`. Kaca atau bagian tembus pandang terpisah dari rangka. Pakai hatch depan dengan jalur buka yang ditunjukkan di preview agar Hammad bisa menentukan animasi. |
| Pivot dan material | Pivot prefab di tengah base pada lantai. Untuk hatch, letakkan pivot pada engsel jika bukaan berputar. Body steel gelap, kaca bening sebagian, panel dan lampu status cukup terang tanpa menutupi korban. |
| Preview state | Tunjukkan kosong/tertutup, berisi dengan avatar, dan hatch terbuka. Tandai perkiraan lokasi tangan penolong di panel, posisi korban, serta titik keluar di lantai. Hammad memasang anchor final dan state rescue/mutasi. |
| Lolos bila | Avatar bisa terlihat dari arah depan dan tiga perempat, panel mudah ditemukan, hatch terpisah saat diimpor, dan posisi keluar punya ruang untuk avatar serta kamera. |

### OBJ-05 · Gate evakuasi

| Aspek | Arahan pengerjaan |
|---|---|
| Fungsi | Exit Central Hub. Kartu terakhir yang diperlukan memicu pembukaan. UI dan lampu memberi tahu pemain ke mana harus berlari sebelum trigger escape aktif. |
| Dimensi dan bentuk | Target draft bukaan bersih **12 × 10 studs**. Buat frame tebal, satu shutter yang bergeser ke atas, dan rumah shutter atau ruang gerak di atas bukaan. Tandai posisi terbuka penuh sesuai clearance. |
| Mesh terpisah | `Gate_Frame`, `Gate_Shutter`, `Gate_Indicator`, `Gate_ExitSign`. Rumah shutter boleh menyatu dengan frame. Pisahkan shutter agar seluruh area buka bisa diuji. |
| Pivot dan material | Pivot prefab di tengah ambang pada lantai. Shutter memakai origin yang konsisten dengan arah gerak vertikal. Steel gelap dengan lampu dan panah exit amber. Tempatkan indikator agar terlihat dari dua pendekatan. Satu slot kartu Red cukup untuk M1. |
| Preview state | Kirim tampak depan tertutup, setengah terbuka dan terbuka penuh. Tambahkan satu tampak samping dengan panah gerak serta ukuran bukaan. Hammad mengerjakan gerak 5 detik, tag gate, collision dan escape trigger di sisi aman. |
| Lolos bila | Ukuran bukaan bersih jelas, shutter punya ruang gerak, panah exit terbaca dari dua sisi, dan gate bisa dibuka penuh tanpa menghalangi jalur avatar. |

## Paket yang dikirim

Kirim satu folder per ID. Sumber harus memuat semua mesh yang bisa diedit dan posisi awalnya. Sertakan FBX dan file tekstur jika dipakai. Modul kit diekspor satu per file untuk cek sambungan. Prefab boleh memakai satu FBX selama objek bergerak tetap punya nama dan bisa dipilih sendiri setelah impor.

```text
OBJ-07_InfectionTube_v01/
  OBJ-07_InfectionTube_v01.blend
  OBJ-07_InfectionTube_v01.fbx
  Preview_Front.png
  Preview_Open.png
  Textures/                     (kalau dipakai)
  Handoff.txt
```

Isi `Handoff.txt` dengan ID dan versi, ukuran target dalam studs, satuan sumber, arah depan, posisi pivot, bagian bergerak, hasil yang masih sementara, dan kredit atau lisensi bila relevan. Tambahkan ukuran atau jarak dari titik acuan jika bagian akan ditempatkan ulang. Pakai nama versi `v01`, `v02`, dan seterusnya agar revisi mudah dibandingkan.

## Review Hammad sebelum batch lanjutan

- [ ] Buka source dan impor `.fbx` ke place privat. Cocokkan arah depan, ukuran, pivot, pemisahan komponen dan material dengan preview.
- [ ] Bandingkan Subject Zero dengan avatar Scientist, sambungkan tiga modul dinding, dan letakkan Keycard Red di permukaan gelap dari kamera bermain.
- [ ] Catat konversi ukuran dan aturan ekspor yang berhasil pada tiga contoh. Kirim balik screenshot dan perubahan yang harus dibuat sebelum aset lanjutan dimulai.
- [ ] Setelah revisi diterima, masukkan PIC, versi dan bukti impor ke [Asset Tracker](ASSET_TRACKER.md). Pakai status review atau terintegrasi sesuai hasil di Studio.
