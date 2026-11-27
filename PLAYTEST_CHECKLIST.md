# Escape the Lab · Playtest Checklist

Jalankan pada private test place atau Studio multi-client. Ekspektasi mekanik berasal dari [GDD §9 dan §14](ESCAPE_THE_LAB_GDD.md#14-keamanan-performa-dan-qa). Catat setiap ID sebagai `Pass`, `Fail`, `Blocked` atau `N/A` per build dan mode. Kasus dengan beberapa cabang lulus setelah semua cabang yang berlaku diuji.

## Persiapan

- [ ] Isi build/commit, versi map, profil, versi Studio/Roblox, roster awal, nama tester, perangkat, kontrol dan kondisi latency.
- [ ] Siapkan Studio multi-client serta minimal satu HP fisik untuk touch. Pisahkan data test dari production saat menguji progression.
- [ ] Siapkan log waktu server, ID sesi dan catatan per role. Rekam layar pemain yang berinteraksi dan observer bila hasilnya bergantung pada timing.
- [ ] Uji urutan 1 → 2 → 3 → 4 pemain tanpa restart. Pada M2 tambahkan 7 pemain dan akses dua client HP bila tersedia.

## Checklist skenario

| ID | Minimum fase | Langkah dan hasil lulus |
|---|---|---|
| QA-01 | M1 | Coba 1/2/3/4 pemain siap. Solo, co-op, ronde pendek dan baseline empat pemain dipilih sesuai aturan. M1 memakai satu zona. |
| QA-02 | M1 | Jalankan 10 ronde berturut-turut. Masing-masing punya satu Subject Zero dan state, timer, tabung, progres serta event lama bersih setelah sesi. |
| QA-03 | M1/M2 | Ulangi 20 seed per profil. Satu kartu muncul per warna aktif dan semua kandidat bisa diraih sebelum unlock. |
| QA-04 | M1 | Dua Scientist mengambil satu kartu bersamaan. Server mencatat satu pickup dan memberi akses tim. |
| QA-05 | M1 | Mulai repair, pindah atau tertangkap, lalu lanjutkan dengan teman. Progres tetap sesuai aturan dan tidak terduplikasi. |
| QA-06 | M1/M2 | Aktifkan satu atau tiga genset sesuai profil. Tambahan +5% per genset kompetitif dan gate terbuka 5 detik setelah objektif terakhir. |
| QA-07 | M1 | Coba capture valid, terlalu jauh, terhalang dan tanpa tabung valid. Hanya capture valid mengisi slot. Catat state korban dan cooldown. |
| QA-08 | M1 | Tahan rescue 3 detik dan selesai sebelum deadline. Tabung kosong, Scientist aktif, proteksi 3 detik dan objective dihentikan selama proteksi. |
| QA-09 | M1 | Biarkan timer kompetitif mencapai 45 detik. Mutasi dan pelepasan tabung tercatat satu kali. |
| QA-10 | M1 | Catat waktu commit rescue sesaat sebelum, tepat pada, dan sesudah deadline. Hanya commit sebelum deadline berhasil, termasuk saat durasi hold cukup sebelum tick. |
| QA-11 | M2 | Lockdown pintu yang sudah unlocked selama 10 detik, cooldown 45 detik. Vent eligible tetap dapat dipakai. Profil satu zona menyembunyikan kedua aksi. |
| QA-12 | M1 | Uji Subject Zero keluar sebelum/sesudah escape, Scientist aktif/captured terakhir keluar, mutant keluar, dan Scientist terakhir bermutasi setelah rekan keluar. Cocokkan dengan decision table GDD §9.2. |
| QA-13 | M1 | Verifikasi server menolak payload test yang tidak valid dan aksi berulang berlebih. Pemain lain tetap dapat menyelesaikan objective. |
| QA-14 | M1 | Lewati area trigger saat gate tertutup dan sesudah terbuka. Escape hanya tercatat pada state yang sah. |
| QA-15 | M1/M2 | Ulangi latihan dan setiap role di HP. Sprint, hold, capture/slow, ping dan skill M2 bisa diakses sambil bergerak/kamera. |
| QA-16 | M1/M2 | Tangkap sebelum kartu pertama dan saat Lockdown M2. Rekam dua rute publik menuju tabung dan pastikan timer P0 tetap 45 detik. |
| QA-17 | M2 | Coba vent ketika satu zona masih terkunci, lalu setelah keduanya unlocked. Akses pertama ditolak, akses kedua berakhir di exit aman. |
| QA-18 | M1 | Reset avatar saat Captured. Pemain kembali ke state dan tabung yang sah dengan timer sama. |
| QA-19 | M1 | Gunakan slow dari lebih dari satu mutant. Efek tidak menumpuk dan immunity setelah slow berlaku. |
| QA-20 | M1/M2 | Coba jaga gate dari posisi terbaik. M1 pakai Subject Zero, M2 tambah beberapa mutant. Rekam jalur yang masih lolos atau buka tiket perubahan layout. |
| QA-21 | P1 | Simulasikan load gagal pada data test. Profil lama tetap ada dan pengalaman pemain mengikuti fallback yang disepakati. |
| QA-22 | M1/P1 | Uji latency tinggi dan reconnect. Klien kembali membaca snapshot dan roster. Pada P1 periksa tidak ada reward ganda. |
| QA-23 | M1 | Selesaikan solo, terima/tolak co-op, rescue berhasil/gagal, dan putus koneksi salah satu peserta. Arena dibersihkan dan statistik/reward kompetitif tidak berubah. |
| QA-24 | M1 | Pemain siap ketiga masuk saat latihan. Uji selesai/pindah ronde, satu arena, lalu pemain keluar saat Preparing dan roster dipilih ulang. |
| QA-25 | M1/M2 | Kunci roster 3 atau 4, ubah jumlah pemain saat Active. Pemain baru menunggu dan objective tetap sesuai profil yang dikunci. |
| QA-26 | M1 | Coba escape mendekati deadline, disconnect setelah cutoff, dan deadline infeksi/ronde yang bertepatan. Hanya state sah sebelum cutoff dihitung, satu hasil dan satu cleanup. |

Untuk QA-10 dan QA-26, bila input manual tidak cukup presisi, gunakan fixture waktu pada test harness server agar titik sebelum, sama dan sesudah deadline dapat diulang.

## Kriteria keputusan

- **M1** lulus ketika semua skenario M1 yang berlaku lolos, satu zona berfungsi dari latihan sampai hasil, 10 sesi berulang bersih, dan touch telah diuji di HP. Rekam beberapa ronde 1 lawan 2 serta baseline empat pemain untuk menilai peluang setelah mutasi pertama.
- **M2/M3** lulus ketika kasus M2 berjalan pada tiga zona, P0 sudah lulus pada build alpha, dan bug pemblokir core loop sudah ditutup atau build ditahan. Catat 30 FPS mobile dan 60 FPS PC sebagai target awal pada perangkat yang disebutkan.
- **P1** menambah bukti persistence, telemetry, aksesibilitas, performa dan hasil balancing per mode/roster.

## Log hasil

| Build / perangkat | Mode / roster | QA ID | Status | Hasil aktual dan tautan bukti | Tiket / retest |
|---|---|---|---|---|---|
| — | — | — | — | — | — |

Untuk bug, tulis langkah reproduksi, hasil aktual, hasil yang diharapkan dan frekuensinya. Sertakan timestamp build atau log saat masalah melibatkan timer, role, dan cleanup.
