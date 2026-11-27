# Escape the Lab · Map Blueprint Facility 07

Rencana blockout untuk [profil map GDD §8](ESCAPE_THE_LAB_GDD.md#8-map-design-blueprint) dan aset ENV/OBJ di [katalog](ASSET_CATALOG.md). Ukuran adalah target awal builder. Uji rute dalam Studio sebelum mengunci posisi prefab.

## Orientasi

```text
                           NORTH · RED
                    Research / Security loop
                             [G-R]
                               |
                             [D-R]
                           [T1] [T2]
                               |
            Lobby → spawn S1–S6 / CENTRAL HUB ← Killer Annex
                        [T3]       [EXIT → trigger]
                        /                         \
                   [T4]                           [T5] [T6]
                    |                                 |
                  [D-B]                             [D-G]
          Cryo / Control loop                Containment / Specimen loop
                  [G-B]                             [G-G]
             SOUTHWEST · BLUE                   SOUTHEAST · GREEN

          Vent M2 menghubungkan Red↔Blue, Red↔Green, Blue↔Green.
```

Diagram menunjukkan hubungan area. Tabung berada di alcove publik dan masing-masing perlu dua pendekatan dari percabangan. Gate punya dua pendekatan dengan cover. Lobby memiliki batas akses arena sendiri. Spawn Scientist berada di hub, terpisah dari alcove T3 dan trigger.

| Elemen | Ukuran / waktu awal | Ukur dari |
|---|---|---|
| Footprint penuh | ±280 × 280 studs | Batas luar tiga zona |
| Central Hub | Diameter ±60 studs | Ruang sirkulasi utama |
| Lorong utama / sekunder | 12–16 / 8–12 studs | Lebar bersih setelah cover |
| Power room / tinggi ruang | ±24 × 24 / 12–18 studs | Ruang bersih setelah alat |
| Hub ke genset | 8–15 detik lari normal | Dari pilar hub ke prompt genset per warna |
| Rotasi vent | Target 6–9 detik | Dari pendekatan entrance sampai siap bergerak sesudah exit. Interaksi 1 detik, transit 4–6 detik dan cooldown 8 detik setelah keluar menurut GDD. |

## Penempatan per profil

| Tag atau komponen | ID/atribut | Satu zona · M1/latihan/pendek | Tiga zona · M2 utama |
|---|---|---|---|
| `ScientistSpawn` | `SpawnId` | S1–S3 | S1–S6 |
| `KillerSpawn` | `SpawnId` | Satu titik annex | Titik yang sama |
| `KeycardSpawn` | `SpawnId`, `Color` | Tiga kandidat Red | Tiga kandidat per warna |
| `ZoneDoor` | `ZoneId` | Red | Red, Blue, Green |
| `Generator` | `ZoneId`, `ObjectiveId` | Red | Satu per zona |
| `InfectionTube` | `TubeId`, `AreaId` | T1–T3 | T1–T6 |
| `VentEntrance` | `VentId`, `ZoneId`, `LinkedVentId` | 0 | Enam mulut, link dua arah |
| `EvacuationGate`, `EscapeTrigger` | `GateId` bersama | Satu pasangan | Pasangan yang sama |

Pasang penghalang fisik pada cabang Blue/Green saat profil satu zona aktif. Registrasi runtime hanya berisi objek profil yang aktif. Tandai lokasi kartu pada permukaan publik sebelum pintu zona. Sediakan ruang dua avatar di sisi servis genset dan clearance di pintu terbuka, jalur sprint, serta titik keluar tabung atau vent.

## Walkthrough builder

- [ ] Dari semua S1–S3, temukan tiga kandidat kartu Red, T1–T3 dan dua pendekatan gate dengan pintu zona tertutup. Ulangi untuk profil penuh.
- [ ] Dari spawn annex, ikuti rute ke hub sesudah head start dan uji chase pada satu loop per zona.
- [ ] Ukur satu rute normal hub → genset untuk setiap warna, lalu cek line of sight, cover, ruang kamera dan clearance.
- [ ] Untuk setiap tabung, rekam dua pendekatan publik dari percabangan. Pada M2 ulangi saat pintu zona Lockdown.
- [ ] Uji gate tertutup lalu terbuka dari dua pendekatan. Pastikan trigger hanya aktif di sisi evakuasi dan bisa dilintasi di seluruh lebar bukaan.
- [ ] Pada M2 uji keenam mulut vent, link dua arah, akses kedua zona, posisi exit aman dan tetap bisa digunakan selama Lockdown jika akses permanen sudah terbuka.
- [ ] Lampirkan screenshot top-down, ukuran hasil blockout, jarak tempuh, dan kasus camping ke [playtest checklist](PLAYTEST_CHECKLIST.md).
