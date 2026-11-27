# Escape the Lab · Art Direction

Standar visual Facility 07 untuk map builder, character artist, UI, animator dan VFX. Brief model per ID ada di [katalog aset](ASSET_CATALOG.md). Referensi desain dan lembar review per aset ada di [Visual Asset Bible](VISUAL_ASSET_BIBLE.md).

## Bahasa visual

| Area / sistem | Bentuk dominan | Material, cahaya dan cue |
|---|---|---|
| Lobby | Bingkai horizontal, meja briefing, panel besar | Baja netral, cahaya stabil, status siap terbaca dari tempat berkumpul. |
| Central Hub | Ring, pilar berulang, pendekatan gate dari dua sisi | Beton dan steel. Cahaya putih kehijauan untuk orientasi, amber khusus evakuasi. |
| Red Sector | Segitiga, rak riset, panel keamanan | Merah `#EF4444` sebagai aksen, dengan amber pada alat lokal. |
| Blue Sector | Persegi, kontrol dan mesin pendingin | Biru `#60A5FA`, kaca buram, embun lokal tipis. |
| Green Sector | Lingkaran, pipa dan jendela containment | Hijau `#4ADE80`, specimen tertutup dan siluet sederhana. |
| Vent | Panel memanjang, kisi, panah aliran | Baja gelap, titik lampu servis yang menandai entrance dan exit. |
| Evakuasi | Bingkai lebar, panah keluar, lampu tepi | Amber `#FBBF24` dan simbol exit. Indikator state tetap terlihat pada mode reduced effects. |

Bahan dasar charcoal `#101719`, steel `#28363A`, concrete `#667477`, teks HUD `#E5E7EB`. Hex dipakai sebagai target authoring. Nilai akhir dievaluasi dalam pencahayaan Studio dan di HP. Ikon, huruf dan state menguatkan warna zona. Pakai panel besar, bentuk modular, tekstur sederhana dan detail yang tetap terbaca selama sprint.

## Role dan bahasa interaksi

- **Scientist** memakai proporsi avatar standar dengan bentuk jas lab pendek atau jumpsuit dan badge. Fokus keterbacaan ada di tangan saat interaksi, pose sprint dari belakang, dan wajah atau siluet dari luar tabung.
- **Subject Zero** terbaca dari bahu asimetris, lengan capture dominan, dan harness containment. Pose meraih memperlihatkan momen capture. Aksesori Lockdown pada M2 punya gesture terpisah.
- **Mini-Mutant** bertubuh lebih kecil, condong dan memiliki sisa kostum Scientist. Swipe pendek dan cue slow terlihat berbeda dari capture. Mutasi memakai kabut singkat dan perubahan siluet.
- **Objek interaktif** memakai bentuk khas dan satu titik fokus. Kartu punya bentuk terpotong, Scanner punya simbol zona, genset punya meter, tabung menampilkan siluet, dan gate punya arah keluar. Tampilkan disabled, aktif, proses dan hasil sesuai prefab.
- **UI** memprioritaskan ancaman dekat, action, timer infeksi dan objective aktif. Ikon utama punya teks atau bentuk yang masih jelas saat warna disamarkan. Sisakan area joystick, kamera, serta safe area perangkat.
- **Audio** melengkapi tanda visual menurut [katalog audio](ASSET_CATALOG.md#8-audio). Genset, tabung, gate, dan Lockdown punya cue yang dapat dibedakan saat ambience aktif.

## Review art

1. **Blockout** memperlihatkan bentuk, skala, route, collision dan framing kamera dari posisi bermain.
2. **Style proof** memakai satu koridor Red yang memuat signage, panel, cover, objective, satu Scientist dan Subject Zero. Simpan frame biasa, gelap, dan reduced effects untuk acuan Blue serta Green.
3. **Review aset** memakai tampak sumber, capture di Studio dari jarak interaksi dan jarak koridor, serta preview HP untuk aset kritis. Periksa objek dari spawn, saat dikejar dan tanpa suara.
4. **Integrasi** memeriksa clipping, collision, kontras, flashing/shake, beban partikel dan beberapa sumber cahaya aktif. Uji pada perangkat target sebelum mengunci material final. Catat pembuat, sumber dan izin setiap referensi atau aset impor.
