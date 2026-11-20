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
![Home kosong](screenshots/01_home_kosong.png)

### 2. Create – mengisi form tambah siswa
![Form tambah](screenshots/02_create_form.png)

### 3. Read – daftar siswa di Home setelah data ditambahkan
![Home berisi data](screenshots/03_home_berisi.png)

### 4. Read – halaman detail siswa
![Detail siswa](screenshots/04_detail.png)

### 5. Update – form edit terisi data lama
![Form edit](screenshots/05_edit_form.png)

### 6. Update – detail siswa setelah diedit
![Detail setelah edit](screenshots/06_detail_setelah_edit.png)

### 7. Delete – dialog konfirmasi hapus
![Dialog hapus](screenshots/07_delete_dialog.png)

### 8. Delete – Home setelah data dihapus
![Home setelah hapus](screenshots/08_home_setelah_hapus.png)
