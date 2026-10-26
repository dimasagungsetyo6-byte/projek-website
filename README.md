# ☕ VIKING - Website Cafe, Smart Table Ordering & POS Management

Sistem website cafe modern **VIKING** yang menggabungkan katalog digital lengkap (50-500 produk), fitur **Scan-to-Order langsung dari meja**, portal kasir/sales POS, dan manajemen restoran untuk pemilik cafe.

---

## 🏗️ Pilihan Arsitektur & Tech Stack

Proyek ini telah disusun dalam arsitektur **Monorepo** modern yang fleksibel:

| Bagian | Teknologi | Lokasi Folder | Status |
|---|---|---|---|
| **Frontend** | **SvelteKit** + Tailwind CSS + Svelte Stores | `/frontend` | ✅ Siap Dijalankan |
| **Backend** | **Go Chi** (`go-chi/chi/v5`) + REST API | `/backend` | ✅ Siap Dijalankan |
| **Database** | **SQLite** (`modernc.org/sqlite` pure-Go) | `/backend/viking.db` | ✅ Otomatis Migrasi & Seeding |
| **Versi Standalone** | Vanilla ES6 JavaScript + Tailwind CDN | `/index.html` | ✅ Siap Buka Langsung (Zero-Build) |

---

## ⚡ Panduan Menjalankan Tech Stack Baru (SvelteKit + Go Chi + SQLite)

### 1. Menjalankan Backend (Go Chi + SQLite)
```powershell
cd c:\Users\HP DRAGONFLY\Documents\PROJEK\backend
go run cmd/api/main.go
```
- Server API aktif di: `http://localhost:8080/api`
- Otomatis membuat database SQLite `viking.db`, migrasi tabel, dan seeding 50+ menu, 20 meja, jadwal live music, dan profil cafe.

### 2. Menjalankan Frontend (SvelteKit)
```powershell
cd c:\Users\HP DRAGONFLY\Documents\PROJEK\frontend
npm install
npm run dev
```
- Frontend aktif di: `http://localhost:5173`
- Terhubung otomatis ke backend Go Chi melalui proxy `/api`.

*(Jika di komputer Anda belum terpasang Go atau Node.js, Anda dapat menginstalnya dengan mudah via PowerShell: `winget install GoLang.Go` dan `winget install OpenJS.NodeJS`)*

---

## 📌 Ringkasan Konteks Proyek

| Parameter | Spesifikasi |
|---|---|
| **Nama Cafe** | **VIKING** (*Specialty Coffee, Eatery & Smart Space*) |
| **Alamat Cafe** | Jl. Tidar, Pelindu, Karangrejo, Kec. Sumbersari, Kabupaten Jember, Jawa Timur 68124 |
| **Jenis Produk** | Coffee-Based, Non-Coffee, SNACK & Finger Food, Makanan Berat, Bakery & Pastry |
| **Kapasitas Katalog** | 50-500 produk (tersedia 50+ menu bawaan dengan fitur penambahan mandiri) |
| **Profil Pengguna** | 1. Pengunjung Publik / Pelanggan Meja<br>2. Sales / Pelayan / Kasir (POS)<br>3. Admin / Pemilik Resto |
| **Tujuan Utama** | 1. Katalog menu interaktif & pencarian cepat<br>2. Tempat duduk dilengkapi **Scan-to-Order** (QR Code Meja 01 - 20)<br>3. Manajemen pesanan langsung dapur & WhatsApp<br>4. Laporan penjualan & generator cetak kartu QR meja |
| **Bahasa Antarmuka** | **Dwibahasa (Bilingual)**: Bahasa Indonesia 🇮🇩 & English 🇬🇧 |
| **Format Standar** | Rupiah (`Rp`), Penanggalan Indonesia, Zona Waktu `Asia/Jakarta (WIB / UTC+7)` |

---

## 🌟 Fitur Utama Berdasarkan Peran Pengguna

### 1. Pengunjung Publik / Pelanggan
- **Scan-to-Order dari Meja**:
  - Pelanggan duduk di salah satu meja (Meja 01 - 20).
  - Scan akrilik QR Code di atas meja menggunakan kamera ponsel.
  - Halaman web terbuka dengan nomor meja yang otomatis terkunci (misal: *Meja 03 - Indoor AC*).
  - Bisa juga memilih meja secara visual lewat denah meja (*Floor Plan Modal*).
- **Katalog Lengkap (50+ Produk)**:
  - **Coffee-Based**: Kopi Viking Aren (Signature), Spanish Latte, Americano, V60 Aceh Gayo, V60 Kintamani, Cold Brew, Dirty Matcha, Mocha, Affogato, dll.
  - **Non-Coffee**: Artisan Uji Matcha, Dark Belgian Chocolate, Red Velvet Cream, Earl Grey Lavender, Lychee Cooler, Mango Smoothie, Rosella Lemonade, dll.
  - **SNACK**: Truffle Parmesan Fries, Cireng Crispy Rujak, Crispy Chicken Wings, Singkong Keju, Nachos Beef Melt, Dimsum Mentai, Churros Dulce de Leche, Viking Platter, dll.
  - **Makanan Berat**: Gyudon Truffle Beef, Nasi Goreng Cakalang Asap, Spaghetti Aglio Olio Smoked Beef, Chicken Katsu Curry, Nasi Dori Sambal Matah, Gourmet Burger & Fries.
  - **Bakery & Pastry**: Butter Croissant French AOP, Almond Frangipane, Pain au Chocolat, Basque Burnt Cheesecake, Fudgy Brownie.
- **Panggung Live Music & Suasana Malam**:
  - Panggung live music rutin setiap **Jumat, Sabtu & Minggu malam** mulai pukul 19.30 WIB (Free Entry / Gratis tanpa tiket).
  - Jadwal mingguan: *Friday Jazz & Soul Night*, *Saturday Pop Acoustic Sing-Along*, dan *Sunday Chill & Indie Folk Session*.
  - Fitur interaktif **Song Request / Titip Lagu ke Band** langsung dari meja via WhatsApp.
  - Audio Synthesizer Web Audio API di navbar yang memutar alunan gitar live akustik & ambience cafe secara nyata.
  - Opsi booking meja khusus area *Outdoor Stage View* (Meja 09 - 14) pada formulir reservasi.
- **Kustomisasi Menu Lengkap**:
  - Pilihan suhu (Dingin / Panas), tingkat gula (Normal, Less Sugar, No Sugar), pilihan susu (Fresh Milk, Oat Milk, Almond Milk), tingkat pedas, dan catatan khusus.
- **Dua Opsi Checkout**:
  - **Kirim ke Dapur / Kasir**: Pesanan langsung masuk antrean kasir secara lokal.
  - **Kirim via WhatsApp**: Rincian pesanan dengan nomor meja tersusun otomatis dan dikirim ke admin WA.
- **Dukungan Dwibahasa**:
  - Tombol toggle instan `ID 🇮🇩` dan `EN 🇬🇧` di bar atas.

---

### 2. CMS & Admin Pengolah Website (Pemilik / Manajer Cafe)
- **Akses & Keamanan Terlindungi (PIN Login)**:
  - Tombol **"⚙️ CMS Admin"** tersedia di bar navigasi atas, menu mobile, dan footer.
  - Dilengkapi sistem login PIN (Default PIN: **`1234`**, dapat diubah di tab Keamanan).
  - Ketika login aktif, muncul bar mengambang **"👑 Mode CMS Admin Aktif"** di atas website.

- **7 Modul Lengkap Pengolah Website di CMS**:
  1. **📊 Dashboard & Ringkasan Toko**:
     - Memantau total omset penjualan (Rp), jumlah pesanan hari ini, antrean dapur, ketersediaan 20 meja, dan status menu aktif vs habis.
     - Kontrol status operasional cafe seketika: `🟢 Buka Normal`, `🟡 Jam Sibuk / Ramai`, atau `🔴 Tutup Sementara`.
  2. **🌐 Konten Website & Profil Toko**:
     - Mengubah Nama Cafe, Tagline, dan Deskripsi Hero.
     - Mengubah Teks Pengumuman Header (*Announcement Bar*) serta toggle tampilkan/sembunyikan.
     - Mengubah Alamat Lengkap, Patokan Kawasan, Jam Operasional (*Weekday & Weekend*), Nomor WhatsApp, Telepon, dan Tautan Google Maps.
     - Perubahan langsung tersimpan ke `localStorage` dan terupdate di tampilan website tanpa reload!
  3. **🎸 Jadwal Live Music Weekend**:
     - Mengubah jadwal panggung live music mingguan (Jumat Jazz, Sabtu Pop, Minggu Indie Folk).
     - Menambah jadwal show baru atau event khusus (Hari, Judul Event, Nama Band/Penampil, Jam, Genre, Lokasi Panggung, Deskripsi, Badge).
     - Menghapus jadwal atau mereset ke jadwal bawaan.
  4. **☕ Manajemen Katalog Menu & Harga (50-500 Produk)**:
     - Form penambahan produk baru ke katalog (Nama, Kategori, Harga Rp, Deskripsi, Foto, Badge).
     - **Modal Edit Produk**: Mengubah harga, nama, deskripsi, foto, kategori, atau badge produk apa pun.
     - Toggle cepat stok: Sekali klik ubah antara **"Tersedia"** dan **"Habis (Sold Out)"**.
     - **Fitur Backup & Restore JSON**: Download file backup katalog menu (`.json`) dan impor file JSON kapan saja.
  5. **🪑 Studio Meja & Generator QR Code**:
     - Memantau dan mengubah status 20 meja: *Kosong*, *Terisi*, atau *Reserved*.
     - **Cetak Kartu QR Satuan**: Menampilkan preview kartu akrilik per meja untuk dicetak.
     - **Batch Print (Cetak Semua 20 Meja Sekaligus)**: Format cetak lembaran kertas A4 siap potong dan dipasang pada akrilik meja resto.
  6. **🧾 Pesanan Dapur & POS Kasir**:
     - Melihat antrean pesanan seketika (*real-time*) dari pelanggan yang melakukan scan QR di meja.
     - Filter status pesanan: *Menunggu Konfirmasi*, *Sedang Dimasak*, *Diantar ke Meja*, dan *Selesai / Lunas*.
     - **Cetak Struk Kasir Thermal**: Format struk kasir profesional siap cetak.
  7. **🔐 Keamanan & Pemeliharaan Sistem**:
     - Ubah PIN login Admin.
     - Bersihkan riwayat antrean pesanan hari ini.
     - Fitur Reset Data ke setelan pabrik.

---

## 🚀 Cara Menjalankan Website

Aplikasi ini dibangun menggunakan arsitektur **Modern Vanilla Web (HTML5, Tailwind CSS, JavaScript ES6)** sehingga **100% langsung jalan tanpa perlu instalasi Node.js atau kompilasi build**.

1. Buka folder proyek di komputer Anda: `c:\Users\HP DRAGONFLY\Documents\PROJEK`
2. Klik ganda (**double click**) pada file **`index.html`**.
3. Website langsung terbuka di browser Anda (Google Chrome, Edge, Firefox, Safari).

### Cara Simulasi Fitur Scan QR Meja:
- Buka tautan dengan parameter meja di browser:
  - `index.html?table=03#menu` ➔ Otomatis scroll ke katalog menu, mengunci Meja 03, dan memunculkan banner selamat datang dengan harga & aneka macam makanan/minuman.
  - `index.html?table=07#menu` ➔ Otomatis terkunci di Meja 07 (Outdoor Garden).
- Atau klik salah satu tombol **"Simulasi Scan Meja"** pada section akrilik meja di halaman depan (Meja 01, Meja 03, Meja 07, Meja 12, Meja 16).
- Atau klik tombol **"Pilih Meja"** di navbar untuk memilih dari denah visual 20 meja lengkap.
- **Tampilan Menu Fleksibel**:
  - Pelanggan dapat beralih antara **"Kartu Foto (Grid)"** dan **"Daftar Harga Ringkas (List View)"** untuk kemudahan melihat semua harga secara cepat.
  - Tersedia filter cepat: *Best Seller*, *Dingin / Segar*, *Hangat*, *Kudapan Gurih*, *Manis & Pastry*, serta *Pedas Nampol*.

---

## 📁 Struktur Berkas

```
PROJEK/
├── index.html           # Tampilan utama lengkap (Pengunjung, Meja, Scan QR, & Portal Staff)
├── README.md            # Dokumentasi & panduan teknis
├── css/
│   └── style.css        # Gaya kustom, tipografi Playfair, tema kopi, akrilik 3D, animasi
└── js/
    ├── i18n.js          # Kamus dwibahasa (ID & EN) dan language switcher
    ├── data.js          # Database 50+ menu, data 20 meja, info cafe, testimoni, FAQ
    ├── orders.js        # Engine manajemen pesanan, status pesanan, & struk kasir
    ├── cart.js          # Keranjang belanja, integrasi nomor meja, & dual checkout
    ├── reservation.js   # Sistem reservasi meja online & WhatsApp dispatcher
    ├── admin.js         # Portal kasir POS, order live tracking, CRUD menu & QR generator
    └── app.js           # Kontrol katalog interaktif, dual view (grid/list), filter & ambience
```
    ├── admin.js         # Panel staff kasir, generator QR meja, & editor katalog
    └── app.js           # Kontrol UI, pencarian, pengurutan, audio ambient, modal
```

---

© 2026 **VIKING** - Specialty Coffee, Eatery & Smart Table Ordering.
Semoga bisnis cafe Anda semakin sukses dan ramai pengunjung! ☕⚔️
