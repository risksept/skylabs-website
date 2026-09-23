# Skylabs Studio Website — Sesi Handoff & Rekapitulasi Proyek

> **Catatan Pemindahan Sesi:**  
> Dokumen ini dibuat untuk mentransfer seluruh konteks arsitektur, kode, status pengerjaan, dan catatan teknis website **Skylabs Studio** ke sesi chat baru yang dibuka langsung di dalam folder workspace **`D:\Android Project\skylabs-web`**.

---

## 1. Identitas & Repositori Proyek
* **Direktori Lokal:** `D:\Android Project\skylabs-web`
* **Remote Git:** `https://github.com/risksept/skylabs-website.git`
* **Branch Utama:** `main`
* **Commit Terakhir:** `058447c` — `feat: initial commit for Skylabs Studio website & brand assets`
* **Tujuan Utama:**
  1. **Profil Resmi Studio:** Etalase pengembang independen *Skylabs Indonesia* (katalog karya, visi produk offline-first, dan kontak resmi).
  2. **Privacy Policy Hub:** Menyediakan URL Kebijakan Privasi resmi publik (*Privacy Policy*) yang wajib diinput ke **Google Play Console** untuk aplikasi `eling` dan `SimplePOS`.

---

## 2. Arsitektur Teknis & Desain Sistem
* **Stack:** Single Page Application (SPA) murni — Vanilla HTML5, Tailwind CSS via CDN (`https://www.gstatic.com/antigravity/web/dev/tailwindcss.min.js`), dan Google Fonts (*Plus Jakarta Sans*, *JetBrains Mono*, *Sora*).
* **Zero Dependencies / No Build Tools:** Dapat dijalankan langsung dengan klik ganda `index.html` di browser atau hosting statis mana pun tanpa perlu `npm install` atau bundler.
* **Sistem Navigasi Dinamis (View Switcher):**
  * `showHomeView()`: Menampilkan beranda utama (Tentang Kami, Prinsip Offline-First, Daftar 3 Produk, Kontak).
  * `showProjectDetail(projectId)`: Menampilkan halaman statis detail per produk (`exam`, `eling`, `simplepos`).
* **Deep Linking Hash Support (URL Routing):**
  * `#exam` ➔ Otomatis membuka detail EXAM.
  * `#eling` / `#privacy-eling` ➔ Otomatis membuka detail eLing dan melompat (*scroll*) ke bagian Kebijakan Privasi eLing.
  * `#simplepos` / `#privacy-simplepos` ➔ Otomatis membuka detail SimplePOS.
* **Desain Visual:** Clean Light Theme (Slate-50 / White), tipografi tajam, kontras tinggi, aksen warna produk (Blue, Emerald, Sky).

---

## 3. Katalog Produk yang Terdaftar di Website

### 1. EXAM (Electronic XML Automation Module)
* **Kategori & Platform:** Aplikasi Desktop Windows (10/11), Database SQLite Lokal.
* **Status:** `(telah rilis)` — Digunakan secara aktif oleh **250+ Instansi Pemerintah** di Indonesia.
* **Fitur Utama:** Otomasi pembuatan Bukti Potong Pajak (BPA1, BPA2, BPMP, BP21 Final), konversi multi-sumber (SimGaji Taspen, GPP, GajiWeb, TPP), validasi selisih PPh, dan ekspor XML Coretax DJP.
* **Call to Action (CTA):** Tautan resmi ke channel Telegram `https://t.me/exam544`.

### 2. SimplePOS (Website Mandiri: simpleposkasir.com)
* **Kategori & Platform:** Aplikasi Kasir Android, 100% Offline-First.
* **Status:** `(website mandiri aktif)` — Memiliki domain dan situs tersendiri di **`https://simpleposkasir.com`** serta Privacy Policy mandiri di **`https://simpleposkasir.com/privacy`**.
* **Ketentuan di Web Skylabs:** **Tidak perlu dituliskan detail panjang ataupun memuat kebijakan privasi di web Skylabs.** Cukup dituliskan poin-poin intinya saja (POS offline, manajemen katalog, radar pajak UMKM) sebagai portofolio studio dengan tautan yang mengarah ke website resminya.

### 3. eLing
* **Kategori & Platform:** Aplikasi Pengingat Dokumen Android (Android 8.0+), Material 3, Room SQLite Lokal.
* **Status:** `(dalam proses)`
* **Fitur Utama:** Pengingat Pajak Kendaraan Bermotor (PKB tahunan), Plat STNK 5 Tahunan, Smart SIM Indonesia, Widget Home Screen 3D Squircle, dan privasi luring 100%.
* **Kebijakan Privasi:** Sudah terpasang lengkap di dalam halaman detail (`#privacy-section-eling`) mencakup deklarasi offline-first, izin `SCHEDULE_EXACT_ALARM`, `POST_NOTIFICATIONS`, `RECEIVE_BOOT_COMPLETED`, AdMob, dan In-App Billing.

### 4. SimpleKOS
* **Kategori & Platform:** Aplikasi Android Native (Kotlin + Jetpack Compose), Room SQLite Lokal, 100% Offline-First.
* **Status:** `(dalam proses)` — Pra-Pengembangan / Prototipe.
* **Fitur Utama:** Siklus okupansi kamar 5-state (Available, Booked, Occupied, Cleaning, Maintenance), otomasi tagihan & kuitansi WhatsApp Intent 1-klik, kalkulasi utilitas sub-meter kWh listrik & air, siklus sewa prorata & multi-termin, serta pengingat perawatan preventif AC/tandon.

### 5. SimpleRent
* **Kategori & Platform:** Aplikasi Android Native (Kotlin + Jetpack Compose), Room SQLite Lokal, Mini Printer Thermal Bluetooth (ESC/POS 58/80mm), 100% Offline-First.
* **Status:** `(dalam proses)` — Pra-Pengembangan / Prototipe.
* **Fitur Utama:** Sub-minute counter check-out (<1 menit serah terima), kalender ketersediaan anti-double-booking dengan cleaning/turnaround buffer, checklist & foto bukti fisik kondisi barang saat keluar/masuk, settlement engine denda & deposit, serta konsinyasi kemitraan bagi hasil (*partner revenue sharing*) via WhatsApp.

---

## 4. Inventaris Aset Brand Studio (`assets/`)

Folder `assets/` telah dilengkapi identitas visual resmi:
| Nama File | Keterangan & Penggunaan |
| :--- | :--- |
| `skylabs-cloud-blue.png` | Logo cloud mark biru resmi Skylabs Studio (digunakan di header navbar). |
| `skylabs-cloud-cyan.png` & `skylabs-cloud-dark.png` | Variasi warna cloud mark (cyan cerah & gelap). |
| `skylabs-logo-transparent.png` & `skylabs-logo-dark.png` | Logo horizontal lengkap teks "Skylabs Studio". |
| `skylabs-icon-dark.png` & `skylabs-icon-transparent.png` | Ikon studio transparan & gelap. |
| `skylabs-avatar-512.png` | Avatar kotak resolusi 512x512 untuk profil akun/medsos. |
| `skylabs-playstore-header.jpg` | Banner header grafis fitur Google Play Store (1024x500). |
| `exam-logo.png` | Ikon resmi aplikasi desktop EXAM. |
| `simplepos-logo.png` | Ikon resmi aplikasi kasir SimplePOS. |
| `eling-logo.png` | Ikon resmi 3D brand mark aplikasi eLing. |
| `simplekos-logo.svg` | Ikon vektor brand mark aplikasi SimpleKOS. |
| `simplerent-logo.svg` | Ikon vektor brand mark aplikasi SimpleRent. |
| `favicon.png` & `favicon-32.png` | Favicon browser web. |

---

## 5. Panduan Deployment ke Cloudflare Pages (Gratis Selamanya)
Website ini dirancang untuk di-hosting di **Cloudflare Pages** (gratis, zero-cost, SSL otomatis, server edge CDN super cepat di Jakarta):

1. Login ke [Cloudflare Dashboard](https://dash.cloudflare.com/) ➔ pilih **Workers & Pages**.
2. Klik **Create application** ➔ Tab **Pages**.
3. **Pilihan A (Hubungkan Git - Direkomendasikan):**
   * Pilih *Connect to Git* ➔ Pilih repo `risksept/skylabs-website`.
   * Branch: `main`, Build command: *(kosongkan)*, Output directory: `.` (root).
   * Setiap kali Anda melakukan `git push`, Cloudflare akan otomatis meng-update website secara instan!
4. **Pilihan B (Direct Upload):**
   * Pilih *Upload assets* ➔ Drag & drop seluruh isi folder `skylabs-web`.
5. URL hasil produksi: **`https://skylabs.pages.dev`** (atau nama subdomain yang dipilih).

---

## 6. URL Resmi untuk Google Play Console
Berikut URL Privacy Policy resmi yang digunakan pada kolom **App Content > Privacy Policy** di Google Play Console:

* **Kebijakan Privasi eLing:**  
  `https://skylabs.pages.dev/#privacy-eling` *(Dihosting di Skylabs Studio)*
* **Kebijakan Privasi SimplePOS:**  
  `https://simpleposkasir.com/privacy` *(Dihosting mandiri di domain resmi SimplePOS)*

---

## 7. Catatan Teknis & Backlog yang Perlu Diselesaikan (Action Items)

1. 🧹 **Penyederhanaan Tampilan SimplePOS di Web Skylabs:**
   * Karena SimplePOS telah memiliki situs mandiri (`simpleposkasir.com`), bagian SimplePOS di web Skylabs tidak memerlukan halaman detail panjang atau kebijakan privasi.
   * Cukup sediakan ringkasan poin ringkas dan tombol CTA *"Kunjungi simpleposkasir.com"* atau tautan Google Play Store.
2. 🚀 **Sinkronisasi Fitur Baru eLing:**
   * eLing baru saja menambahkan modul **Paspor RI** dan **Kartu Bank** di branch `feature/additional-menus`. Daftar fitur eLing di `index.html` dapat diperbarui untuk mencantumkan kedua dokumen baru ini.
3. 🌐 **Eksekusi Deploy Cloudflare:**
   * Lakukan integrasi repo GitHub `skylabs-website` ke Cloudflare Pages agar URL `https://skylabs.pages.dev` langsung aktif untuk kebutuhan privasi eLing dan profil studio.

---

## 8. Panduan Membuka Chat Baru
Jika Anda membuka chat baru di folder workspace `D:\Android Project\skylabs-web`, cukup berikan instruksi berikut:

> *"Halo, tolong baca dokumen `HANDOFF_SESSION.md` untuk memahami seluruh arsitektur, aset, status pengerjaan, dan backlog website Skylabs Studio, lalu bantu saya menyelesaikan poin-poin pada Bab 7 (Action Items)."*
