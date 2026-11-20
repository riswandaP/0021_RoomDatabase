# Prak9 – Aplikasi CRUD Data Siswa (Room + Jetpack Compose)

Aplikasi Android sederhana untuk mengelola data siswa secara offline menggunakan **Room Database**, **Jetpack Compose**, **ViewModel**, dan **Navigation Compose**.

## Fitur

| Operasi | Keterangan |
|---------|-----------|
| **Create** | Menambah data siswa lewat tombol `+` di halaman Home |
| **Read** | Daftar siswa di Home dan detail siswa saat salah satu item diketuk |
| **Update** | Tombol edit (ikon pensil) di halaman Detail membuka form edit |
| **Delete** | Tombol *Hapus* di halaman Detail, dengan dialog konfirmasi |

## Struktur Proyek

```
com.example.prak9
├── room/            Siswa, SiswaDao, DatabaseSiswa
├── repositori/      RepositoriSiswa, ContainerApp
├── viewmodel/       HomeViewModel, EntryViewModel, DetailViewModel, EditViewModel
│   └── provider/    PenyediaViewModel
├── view/            HalamanHome, HalamanEntry, HalamanDetailSiswa, HalamanEdit
│   └── route/       DestinasiHome, DestinasiEntry, DestinasiDetailSiswa, DestinasiEditSiswa
└── uicontroller/    PetaNavigasi (NavHost + SiswaTopAppBar)
```

## Alur Navigasi

```
Home ──(+)──────────► Entry ──(Submit)──► Home
Home ──(ketuk item)─► Detail ──(Edit)───► Edit ──(Simpan)──► Detail
                      Detail ──(Hapus + Ya)──► Home
```

`DetailSiswa` dan `EditSiswa` menerima argumen `idSiswa` (`NavType.IntType`) yang dibaca oleh `DetailViewModel` dan `EditViewModel` melalui `SavedStateHandle`.

## Screenshot Hasil Operasi

### 1. Halaman Home (data kosong)
<img width="1919" height="1079" alt="Screenshot 2026-11-20 140837" src="https://github.com/user-attachments/assets/fec4b175-6db7-4351-b034-855172af4063" />

### 2. Create – mengisi form tambah siswa
<img width="1919" height="1079" alt="Screenshot 2026-11-20 140918" src="https://github.com/user-attachments/assets/c65a74b2-064a-49f8-97b6-a8b28fc3fedf" />

### 3. Read – daftar siswa di Home setelah data ditambahkan
<img width="1919" height="1079" alt="Screenshot 2026-11-20 140937" src="https://github.com/user-attachments/assets/9bd1292a-2937-4602-ac7b-d0446df3850c" />

### 4. Read – halaman detail siswa
<img width="1919" height="1079" alt="Screenshot 2026-11-20 141007" src="https://github.com/user-attachments/assets/5e9b3ac5-d912-43c5-a73c-ffa506d54e81" />

### 5. Update – form edit terisi data lama
<img width="1919" height="1079" alt="Screenshot 2026-11-20 141036" src="https://github.com/user-attachments/assets/edcdcf34-4e82-4a3b-9c4f-92128b529fce" />

### 6. Update – detail siswa setelah diedit
<img width="1919" height="1079" alt="Screenshot 2026-11-20 141045" src="https://github.com/user-attachments/assets/26d679cc-1183-4f48-ace1-1609f7b4c2e8" />

### 7. Delete – dialog konfirmasi hapus
<img width="1919" height="1079" alt="Screenshot 2026-11-20 141057" src="https://github.com/user-attachments/assets/04a9e147-de6b-4a82-aed7-040928165df6" />

### 8. Delete – Home setelah data dihapus
<img width="1919" height="1079" alt="Screenshot 2026-11-20 141103" src="https://github.com/user-attachments/assets/47f3accb-1a84-4123-8688-e4552303fef7" />

