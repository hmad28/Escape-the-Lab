# Escape the Lab · Map Blueprint Facility 07

Rencana blockout untuk [profil map GDD §8](ESCAPE_THE_LAB_GDD.md#8-map-design-blueprint) dan aset ENV/OBJ di [katalog](ASSET_CATALOG.md). Ukuran adalah target awal builder. Uji rute dalam Studio sebelum mengunci posisi prefab.

## Orientasi

```text
                       NORTH · RED
            Research / Security loop [kandidat R ×3]
                            [T1] [T2]
                                |
        Lobby → S1–S5 / CENTRAL HUB [T3] ← Killer Annex
                         [EXIT → trigger]
                      /                   \
               [T4] BLUE                  GREEN [T5]
             Cryo / Control           Containment / Specimen
             [kandidat B ×3]            [kandidat G ×3]

          M2 vent: Red↔Blue, Red↔Green, Blue↔Green.
          M1: cabang Blue/Green ditutup. T4/T5 di alcove hub.
```

Diagram menunjukkan hubungan area. Tabung berada di alcove publik dan masing-masing perlu dua pendekatan dari percabangan. Gate punya dua pendekatan dengan cover. Lobby memiliki batas akses arena sendiri. Spawn Scientist berada di hub, terpisah dari alcove tabung dan trigger.

| Elemen | Ukuran / waktu awal | Ukur dari |
|---|---|---|
| Footprint penuh | ±280 × 280 studs | Batas luar tiga zona |
| Central Hub | Diameter ±60 studs | Ruang sirkulasi utama |
| Lorong utama / sekunder | 12–16 / 8–12 studs | Lebar bersih setelah cover |
| Power room / tinggi ruang | ±24 × 24 / 12–18 studs | Ruang bersih setelah alat |
| Hub ke kandidat kunci terjauh | 8–15 detik lari normal | Dari pilar hub ke kandidat terjauh per warna |
| Rotasi vent | Target 6–9 detik | Dari pendekatan entrance sampai siap bergerak sesudah exit. Interaksi 1 detik, transit 4–6 detik dan cooldown 8 detik setelah keluar menurut GDD. |

## Penempatan per profil

| Tag atau komponen | ID/atribut | Satu zona · M1 dan latihan | Tiga zona · M2 utama |
|---|---|---|---|
| `ScientistSpawn` | `SpawnId` | S1–S5 | S1–S5 |
| `KillerSpawn` | `SpawnId` | Satu titik annex | Titik yang sama |
| `KeycardSpawn` | `SpawnId`, `Color` | Tiga kandidat Red | Tiga kandidat per warna |
| `InfectionTube` | `TubeId`, `AreaId` | T1–T5 | T1–T5 |
| `VentEntrance` | `VentId`, `ZoneId`, `LinkedVentId` | 0 | Enam mulut, link dua arah |
| `EvacuationGate`, `EscapeTrigger` | `GateId` bersama | Satu pasangan | Pasangan yang sama |

Pasang penghalang fisik pada cabang Blue/Green saat profil Red aktif. Letakkan kandidat kartu pada permukaan publik dan pisahkan dari tabung serta gate. Verifikasi spawn, jalur sprint, titik keluar tabung dan vent memakai avatar. Pada profil penuh seluruh zona bisa dimasuki sejak spawn.

## Walkthrough builder

- [ ] Dari semua S1–S5, jangkau kandidat kartu aktif, T1–T5, dan dua pendekatan gate sebelum kartu pertama diambil. Ulangi di kedua profil.
- [ ] Dari spawn annex, ikuti rute ke hub sesudah head start dan uji chase pada satu loop per zona.
- [ ] Ukur satu rute normal hub → kandidat kunci terjauh untuk setiap warna, lalu cek line of sight, cover, ruang kamera dan clearance.
- [ ] Untuk setiap tabung, rekam dua pendekatan publik dari percabangan. Ulangi setelah T4/T5 dipindahkan pada M2.
- [ ] Uji gate tertutup lalu terbuka dari dua pendekatan. Pastikan trigger hanya aktif di sisi evakuasi dan bisa dilintasi di seluruh lebar bukaan.
- [ ] Pada M2 uji keenam mulut vent, link dua arah, izin Scientist aktif dan exit aman di jalur publik. Pastikan vent tidak bisa mencapai escape trigger.
- [ ] Lampirkan screenshot top-down, ukuran hasil blockout, jarak tempuh, dan kasus camping ke [playtest checklist](PLAYTEST_CHECKLIST.md).
