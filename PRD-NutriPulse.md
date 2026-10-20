# PRD — NutriPulse: Web App Kalkulator Gizi & Pelacak Makro Harian

| | |
|---|---|
| **Versi** | 1.0 (Draft) |
| **Tanggal** | 20 Oktober 2026 |
| **Status** | Draft untuk review |
| **Platform** | Web App (mobile-first, responsif hingga desktop) |
| **Bahasa antarmuka** | Bahasa Indonesia (i18n disiapkan untuk bahasa lain) |
| **Sumber acuan** | `DESIGN.md` (Luminous Violet Macro Tracker) dan prototipe `code.html` |

---

## 1. Ringkasan Eksekutif

NutriPulse adalah web app untuk menghitung dan melacak asupan gizi harian (kalori, protein, karbohidrat, lemak). Pengguna bisa memperkirakan nilai gizi suatu makanan berdasarkan porsi (gram) secara instan, lalu mencatatnya ke jurnal harian per waktu makan (Sarapan, Siang, Malam, Camilan) dan melihat progresnya terhadap target pribadi.

Pembeda utama produk:

1. **Kalkulator instan** — pratinjau gizi berubah real-time saat porsi digeser, sebelum dicatat.
2. **Pencatatan cepat** — dari kalkulator ke jurnal dalam beberapa ketukan.
3. **Pengalaman positif & tidak menghakimi** — visual premium berwarna violet (bukan hijau klinis khas aplikasi diet), umpan balik lembut yang mendorong konsistensi.
4. **Konteks lokal** — basis data makanan Indonesia (nasi, tempe, tahu, dll.) dan antarmuka berbahasa Indonesia.

---

## 2. Latar Belakang & Masalah

### 2.1 Masalah pengguna
- Menghitung kalori dan makro secara manual itu melelahkan dan rawan salah.
- Aplikasi pelacak gizi yang ada sering rumit, penuh iklan, atau basis datanya tidak mengenal makanan lokal.
- Banyak aplikasi membuat pengguna merasa bersalah (angka merah, peringatan keras), sehingga mereka berhenti mencatat.
- Pengguna tidak tahu berapa target kalori dan makro yang sesuai untuk tubuh dan tujuan mereka.

### 2.2 Peluang
Pasar kesadaran gizi (diet, fitness, kontrol berat badan, manajemen kondisi tertentu) terus tumbuh. Produk yang cepat dipakai, akurat untuk makanan lokal, dan nyaman dilihat punya peluang retensi yang baik.

---

## 3. Tujuan & Non-Tujuan

### 3.1 Tujuan (Goals)
| # | Tujuan | Indikator keberhasilan |
|---|---|---|
| G1 | Pengguna dapat mencatat satu makanan dengan cepat | Median waktu catat ≤ 20 detik |
| G2 | Pengguna paham posisi asupan terhadap target hari ini | ≥ 80% pengguna aktif membuka layar Harian ≥ 4 hari/minggu |
| G3 | Pengguna mendapat target personal yang masuk akal | ≥ 70% pengguna baru menyelesaikan onboarding |
| G4 | Pencatatan menjadi kebiasaan | Retensi D7 ≥ 35%, D30 ≥ 20% |
| G5 | Data gizi dapat dipercaya | Cakupan database makanan Indonesia populer ≥ 90% pada pencarian umum |

### 3.2 Non-Tujuan (di luar cakupan v1)
- Diagnosis atau terapi medis (aplikasi bukan alat medis).
- Pemindaian foto makanan dengan AI.
- Pemindai barcode produk kemasan (dipertimbangkan v1.5).
- Fitur sosial (teman, papan peringkat, komunitas).
- Integrasi wearable/Apple Health/Google Fit (v2).
- Pelacakan mikronutrien lengkap (vitamin/mineral). Serat, gula, dan natrium hanya sebagai opsi tahap lanjut.
- Marketplace atau pemesanan makanan.

---

## 4. Target Pengguna

### 4.1 Persona

**Persona 1 — Rina, 27, Karyawan Kantoran (Penurun berat badan)**
Ingin turun 5 kg. Sering makan di luar, butuh pencatatan cepat saat jam istirahat lewat ponsel. Mudah menyerah jika aplikasi terasa menghakimi.

**Persona 2 — Dimas, 23, Mahasiswa & Pegiat Gym (Penambah massa otot)**
Fokus pada target protein harian. Mengetahui gramasi makanan dan ingin hasil hitung yang presisi serta data makro terperinci.

**Persona 3 — Bu Sari, 45, Menjaga Pola Makan Sehat**
Tidak terlalu paham istilah makro. Butuh panduan target otomatis dan tampilan yang sederhana dan mudah dibaca.

### 4.2 Kebutuhan inti
- Hasil cepat dan mudah dipahami
- Target yang dihitung otomatis dan dapat disesuaikan
- Basis data makanan lokal yang lengkap
- Tampilan bersih, ramah, tidak membuat bersalah

---

## 5. Ruang Lingkup Produk & Peta Layar

Navigasi bawah (bottom navigation) pada desain terdiri dari 4 tab. Prototipe saat ini baru menampilkan tab **Harian**, sedangkan tab lain perlu didesain (lihat bagian 12).

| Tab | Ikon | Isi | Status desain |
|---|---|---|---|
| **Harian** | `event_note` | Ringkasan kalori & makro, kalkulator, jurnal waktu makan, ide resep | ✅ Tersedia |
| **Kalkulator** | `calculate` | Kalkulator gizi penuh + pencarian makanan + makanan kustom | ⚠️ Perlu didesain (saat ini hanya seksi di Harian) |
| **Analisis** | `monitoring` | Tren mingguan/bulanan, rata-rata makro, konsistensi | ❌ Belum ada |
| **Profil** | `account_circle` | Data tubuh, target, preferensi, akun | ❌ Belum ada |

Layar pendukung yang dibutuhkan: Onboarding, Modal **Atur Target** (tombol "Atur Target" ada di desain), Notifikasi, Daftar Resep ("Lihat Semua"), Detail Makanan, Buat Makanan Kustom, Pengaturan, dan Masuk/Daftar.

---

## 6. Kebutuhan Fungsional

Prioritas: **P0** = wajib untuk rilis pertama, **P1** = penting, **P2** = nice-to-have.

### 6.1 Onboarding & Penetapan Target (P0)

**Deskripsi:** Pengguna baru mengisi data dasar untuk menghasilkan target kalori dan makro otomatis.

**Input:** jenis kelamin, tanggal lahir/usia, tinggi (cm), berat (kg), tingkat aktivitas, tujuan (turun berat badan, menjaga, menaikkan berat/otot).

**User story:**
- Sebagai pengguna baru, saya ingin target dihitung otomatis agar saya tidak perlu menebak angka.
- Sebagai pengguna berpengalaman, saya ingin bisa menimpa target dengan angka sendiri.

**Acceptance criteria:**
- Onboarding maksimal 5 langkah dan dapat dilewati (skip) dengan target default.
- Hasil menampilkan target kalori, protein, karbohidrat, dan lemak beserta penjelasan singkat cara menghitungnya.
- Pengguna dapat mengubah target manual kapan saja (lihat 6.2).
- Validasi rentang input (lihat bagian 8.4).

### 6.2 Atur Target Harian (P0)

**Deskripsi:** Tombol **Atur Target** pada kartu hero membuka modal/bottom sheet (Level 3 elevation) untuk menyesuaikan target.

**Kebutuhan:**
- Slider penyesuaian target kalori dengan thumb violet `#6D28D9` dan track terisi dinamis, sesuai spesifikasi desain.
- Input numerik untuk protein, karbohidrat, lemak (gram), dengan opsi mode **gram** atau **persentase**.
- Total kalori dari makro (P×4 + K×4 + L×9) ditampilkan dan diselaraskan dengan target kalori. Jika selisih > 5%, tampilkan petunjuk lembut untuk menyelaraskan (bukan error keras).
- Tombol **Reset ke rekomendasi** untuk kembali ke hasil perhitungan otomatis.
- Perubahan target berlaku mulai hari ini; data hari-hari sebelumnya tetap memakai target saat itu (snapshot).

### 6.3 Kartu Ringkasan Harian / Hero (P0)

**Deskripsi:** Kartu hero bergradien violet di bagian atas layar Harian.

**Elemen (sesuai desain):**
- Badge "Ringkasan Hari Ini" dan tombol **Atur Target**.
- Kalori terkonsumsi / target (contoh: `1.420 / 2.100 kkal`) dengan pemisah ribuan format Indonesia.
- Chip sisa kalori (contoh: "680 kkal tersisa").
- Cincin kalori SVG dengan persentase tercapai (contoh: 68%).
- Tiga bar progres makro: **Protein**, **Karbohidrat**, **Lemak**, masing-masing menampilkan `konsumsi / target (persen)`.
- Tombol **Catat Makanan Cepat** yang menggulir ke kalkulator dan memfokuskan kolom pencarian.

**Acceptance criteria:**
- Semua angka dihitung ulang otomatis setiap ada penambahan, perubahan, atau penghapusan entri jurnal.
- Animasi perubahan progres halus (transisi ±500–700 ms), tanpa lonjakan tata letak (menggunakan tabular figures).
- Jika kalori melebihi target, kartu beralih ke status "melebihi" dengan nada lembut, misalnya "Kamu 120 kkal di atas target hari ini", bukan peringatan menakutkan. Warna Alert Rose `#F43F5E` dipakai secukupnya.
- Jika kalori mencapai target tanpa melebihi, tampilkan status sukses (Success Mint `#10B981`).
- Cincin dan bar tidak melebihi 100% secara visual, tetapi angka tetap menampilkan nilai sebenarnya.

### 6.4 Kalkulator Nutrisi Makanan (P0)

**Deskripsi:** Seksi interaktif untuk memperkirakan gizi sebelum dicatat.

**Komponen (sesuai desain):**
1. **Pemilih Kategori Waktu Makan** — segmented control 4 pilihan: Sarapan, Siang, Malam, Camilan. Nilai awal ditentukan otomatis dari jam saat ini (mis. 05:00–10:59 Sarapan, 11:00–15:59 Siang, 16:00–21:59 Malam, lainnya Camilan), dapat diubah manual.
2. **Pencarian Makanan** — input teks dengan autocomplete dari database.
3. **Porsi Konsumsi** — stepper (−/+ per 10 g), tampilan angka besar, dan slider (rentang 20–400 g, langkah 10 g).
4. **Pratinjau Nilai Gizi** — 4 kartu: Kalori (kkal), Protein (g), Karbo (g), Lemak (g), diperbarui real-time.
5. **Tombol "Tambahkan ke Jurnal Harian"** — menyimpan entri ke kategori terpilih, lalu menampilkan umpan balik sukses sementara ("Berhasil Ditambahkan!", ± 1,8 detik).

**Rumus:** `nilai = nilai_per_100g × (porsi_gram / 100)`. Kalori dibulatkan ke bilangan bulat, makro ke 1 desimal.

**Acceptance criteria:**
- Pratinjau diperbarui ≤ 100 ms setelah perubahan input.
- Pengguna dapat mengetik angka porsi langsung (di luar rentang slider), maksimum 5.000 g.
- Jika makanan **tidak ditemukan**, sistem **tidak boleh** memakai angka tebakan secara diam-diam. Tampilkan status "Makanan tidak ditemukan" dengan opsi **Buat makanan kustom** (lihat catatan di bagian 13).
- Autocomplete mendukung pencarian toleran huruf besar/kecil, sebagian kata, dan variasi ejaan umum.
- Setelah berhasil ditambahkan, kolom pencarian dikosongkan atau dipertahankan sesuai preferensi (diputuskan di bagian 14), dan kartu hero serta jurnal ter-update tanpa muat ulang halaman.

### 6.5 Jurnal Waktu Makan (P0)

**Deskripsi:** Daftar kartu per waktu makan yang merinci asupan hari ini ("Jurnal Waktu Makan", penanda jumlah sesi).

**Per kartu (Sarapan Pagi, Makan Siang, Makan Malam, Camilan Sehat):**
- Ikon kategori, judul, subjudul (mis. "Target ideal: 400–500 kkal"), dan total kalori kategori di kanan.
- Daftar item: nama makanan, ringkasan makro `P · K · L` (gram), dan kalori item.
- Tombol tambah per kategori ("Tambah Makanan Pagi", dll.) yang memilih kategori terkait, menggulir ke kalkulator, dan memfokuskan pencarian.
- **Empty state** ramah untuk kategori tanpa entri (contoh desain pada Camilan: "Belum Ada Camilan Tercatat" + tombol "Catat Camilan Sekarang").

**Kebutuhan tambahan (belum ada di desain, perlu ditambahkan):**
- **Ubah porsi** entri yang sudah tercatat (P0).
- **Hapus** entri, dengan opsi **Urungkan (Undo)** selama beberapa detik (P0).
- **Pindahkan** entri ke kategori lain (P2).
- **Salin dari kemarin / hari lain** (P1).
- **Makanan favorit & terakhir dipakai** untuk pencatatan satu ketukan (P1).

**Acceptance criteria:**
- Total kalori per kategori = jumlah kalori semua itemnya.
- Target ideal per kategori dihitung sebagai persentase dari target kalori harian (default: Sarapan 25%, Siang 35%, Malam 30%, Camilan 10%) dan bisa diubah di Pengaturan.
- Urutan item dalam kategori berdasarkan waktu pencatatan.

### 6.6 Navigasi Tanggal (P0)

Prototipe hanya menampilkan "hari ini". Aplikasi perlu:
- Memilih tanggal (kemarin, hari lain, kalender) untuk melihat/mengedit jurnal lampau.
- Label tanggal pada header (menggantikan atau melengkapi judul "Harian").
- Mencatat entri ke tanggal lampau (backfill) dengan batas wajar (mis. 30 hari).

### 6.7 Basis Data Makanan (P0)

- Nilai gizi disimpan **per 100 g** (kalori, protein, karbohidrat, lemak).
- Sumber data: Tabel Komposisi Pangan Indonesia (TKPI, Kemenkes), USDA FoodData Central untuk makanan global, serta data produk yang divalidasi tim konten. Lisensi tiap sumber harus diverifikasi sebelum dipakai.
- Cakupan awal v1: minimal **500 makanan** populer Indonesia (nasi putih/merah, lauk, sayur, buah, jajanan, minuman) dan **300 makanan umum global**.
- Setiap item menyimpan: nama (ID), alias/sinonim, kategori, nilai per 100 g, satuan porsi umum (mis. "1 butir telur ≈ 55 g", "1 centong nasi ≈ 100 g"), sumber data, dan status verifikasi.
- **Satuan porsi alternatif** (butir, potong, centong, sendok makan, gelas) selain gram, dengan konversi ke gram (P1).
- Makanan kustom buatan pengguna (nama, per 100 g atau per porsi) bersifat privat (P1).
- Makanan dengan beberapa bahan / resep sendiri (P2).

### 6.8 Analisis & Tren (P1)

**Deskripsi:** Tab **Analisis** menampilkan perkembangan asupan.

- Rentang: 7 hari, 30 hari, kustom.
- Grafik kalori harian terhadap target (bar/line).
- Rata-rata harian untuk kalori dan makro, serta distribusi makro (persen protein/karbo/lemak).
- Jumlah hari berhasil mencatat dan **streak** pencatatan, memakai aksen amber tertiary untuk pencapaian sesuai desain.
- Wawasan ringan dan netral (mis. "Protein rata-rata kamu 82% dari target minggu ini").
- Tren berat badan (input berat manual, opsional).

**Acceptance criteria:** Grafik dapat dibaca pada layar 360 px; angka memakai tabular figures; hari tanpa data ditampilkan sebagai kosong, bukan nol.

### 6.9 Profil & Pengaturan (P1)

- Data tubuh dan tujuan (dapat diubah dan memicu opsi hitung ulang target).
- Preferensi: satuan (metrik), format angka, pembagian target per waktu makan, jam pengingat.
- Manajemen akun: masuk, daftar, keluar, hapus akun dan seluruh data.
- Ekspor data (CSV) (P2).
- Tampilan: terang (default). Mode gelap dipertimbangkan (P2); desain saat ini hanya mode terang.

### 6.10 Notifikasi (P1)

- Ikon lonceng pada header membuka pusat notifikasi.
- Pengingat catat makan (opsional, jam bisa diatur) dengan bahasa yang mendorong, bukan menekan.
- Ringkasan mingguan.
- Izin notifikasi diminta secara kontekstual, bukan saat pertama membuka aplikasi.

### 6.11 Ide Resep Rendah Kalori (P2)

- Bagian kartu resep (grid 2 kolom) dengan foto, lencana kalori, nama, dan label ("Tinggi Protein & Serat").
- Tautan **Lihat Semua** menuju daftar resep dengan filter (rentang kalori, tinggi protein, waktu makan).
- Detail resep dengan gizi per porsi dan tombol **Tambahkan ke Jurnal**.

### 6.12 Akun & Sinkronisasi (P0)

- Mode tamu (data lokal di perangkat) agar pengguna bisa mencoba tanpa mendaftar.
- Masuk dengan email dan Google; data tersinkron antar perangkat.
- Saat tamu mendaftar, data lokal digabung ke akun.
- Dukungan **offline dasar**: catat dan lihat jurnal tanpa internet, sinkron saat online (PWA) (P1).

---

## 7. Logika Perhitungan Gizi

### 7.1 Kebutuhan energi
- **BMR** (Mifflin–St Jeor):
  - Pria: `10 × berat(kg) + 6,25 × tinggi(cm) − 5 × usia + 5`
  - Wanita: `10 × berat(kg) + 6,25 × tinggi(cm) − 5 × usia − 161`
- **TDEE** = BMR × faktor aktivitas:

| Tingkat aktivitas | Faktor |
|---|---|
| Sangat jarang bergerak | 1,2 |
| Ringan (olahraga 1–3×/minggu) | 1,375 |
| Sedang (3–5×/minggu) | 1,55 |
| Aktif (6–7×/minggu) | 1,725 |
| Sangat aktif | 1,9 |

### 7.2 Target kalori sesuai tujuan
| Tujuan | Penyesuaian dari TDEE |
|---|---|
| Menurunkan berat badan | −10% hingga −20% (default −15%) |
| Menjaga berat badan | 0% |
| Menaikkan berat/otot | +5% hingga +15% (default +10%) |

### 7.3 Pembagian makro (default, dapat diubah)
| Tujuan | Protein | Karbohidrat | Lemak |
|---|---|---|---|
| Turun berat badan | 30% | 40% | 30% |
| Menjaga | 25% | 50% | 25% |
| Naik berat/otot | 30% | 45% | 25% |

Konversi ke gram: protein dan karbohidrat 4 kkal/g, lemak 9 kkal/g.

> Nilai default di atas adalah titik awal produk dan **harus divalidasi oleh ahli gizi/dietisien** sebelum rilis.

### 7.4 Pembulatan & tampilan
- Kalori: bilangan bulat; makro: 1 desimal pada kalkulator, bilangan bulat pada ringkasan.
- Persentase progres: dibulatkan ke bilangan bulat terdekat.
- Format angka Indonesia: titik sebagai pemisah ribuan (`2.100`), koma sebagai desimal pada tampilan teks (`46,5`).

---

## 8. Kebutuhan Non-Fungsional

### 8.1 Performa
- Largest Contentful Paint ≤ 2,5 detik pada jaringan 4G menengah.
- Interaksi kalkulator (geser slider, ketik) tanpa jank, ≥ 60 fps.
- Pencarian makanan: hasil autocomplete ≤ 300 ms (p95).
- Ukuran bundel awal dioptimalkan. Catatan: prototipe memakai Tailwind via CDN, yang **tidak boleh** dipakai di produksi (gunakan build-time Tailwind).

### 8.2 Responsif & Layout (sesuai DESIGN.md)
| Breakpoint | Grid | Margin | Catatan |
|---|---|---|---|
| Mobile (≤ 599 px) | 4 kolom, gutter 0,75 rem | 1,25 rem | Kartu penuh atau 2 kolom untuk makro |
| Tablet (600–1023 px) | 8 kolom, gutter 1 rem | 2 rem | Ringkasan 5 kolom + side-rail jurnal 3 kolom |
| Desktop (≥ 1024 px) | 12 kolom, maks. 1.200 px | 3 rem | Cincin makro menempel kiri (4 kolom), jurnal di kanan (8 kolom) |

Prototipe baru memenuhi tampilan mobile. Layout tablet dan desktop perlu didesain dan diimplementasikan.

### 8.3 Aksesibilitas
- Target WCAG 2.2 level AA.
- Area sentuh minimal 44×44 px (sudah diterapkan pada navigasi dan ikon header).
- Kontras teks terhadap latar: ≥ 4,5:1. **Periksa khusus** teks `on-primary-container` di atas gradien violet pada kartu hero dan teks `outline` kecil (10 px).
- Cincin dan bar progres memiliki alternatif teks (`aria-valuenow`, label), informasi tidak disampaikan hanya lewat warna.
- Slider, stepper, dan segmented control dapat dioperasikan dengan keyboard dan pembaca layar. Segmented control memakai pola radio group dan menandai pilihan aktif dengan `aria-checked`.
- Hormati `prefers-reduced-motion` (nonaktifkan animasi pulse dan transisi panjang).
- Hapus `maximum-scale=1.0, user-scalable=no` dari viewport, karena menghalangi zoom pengguna.

### 8.4 Validasi input
| Field | Rentang |
|---|---|
| Usia | 14–100 tahun (di bawah 18 butuh persetujuan/peringatan, lihat 9) |
| Tinggi | 100–250 cm |
| Berat | 25–300 kg |
| Porsi | 1–5.000 g |
| Target kalori | 800–6.000 kkal |
| Target makro | ≥ 0 g; total kalori makro wajar terhadap target |

### 8.5 Keamanan & Privasi
- Data kesehatan bersifat sensitif: enkripsi saat transit (TLS) dan saat disimpan.
- Kepatuhan terhadap **UU No. 27 Tahun 2022 tentang Pelindungan Data Pribadi (UU PDP)**: persetujuan eksplisit, hak akses/koreksi/hapus data, kebijakan privasi yang jelas dalam Bahasa Indonesia.
- Kebijakan retensi dan penghapusan akun yang tuntas.
- Tanpa penjualan data pengguna ke pihak ketiga. Analitik bersifat teranonimkan.
- Proteksi terhadap penyalahgunaan: rate limiting API, validasi sisi server, CSP yang ketat.

### 8.6 Kompatibilitas
- Browser: dua versi mayor terakhir Chrome, Safari, Firefox, Edge. Utamakan Chrome Android dan Safari iOS.
- Dukungan safe-area (notch) sudah ada di desain (`pt-safe`, `pb-safe`).
- PWA: dapat dipasang ke layar utama, dengan manifest dan service worker.

### 8.7 Lokalisasi
- Seluruh teks lewat sistem i18n (default `id-ID`).
- Format angka dan tanggal mengikuti locale.

---

## 9. Keamanan Pengguna, Etika & Kepatuhan

Produk ini menyangkut kesehatan dan berpotensi memengaruhi perilaku makan. Prinsip yang wajib diterapkan:

1. **Disclaimer jelas:** NutriPulse bukan pengganti saran medis. Tampil saat onboarding dan di Pengaturan. Pengguna dengan kondisi medis (diabetes, penyakit ginjal, hamil/menyusui, dll.) disarankan berkonsultasi dengan tenaga kesehatan.
2. **Batas aman target kalori:** sistem tidak merekomendasikan target di bawah batas minimal wajar (acuan awal: ±1.200 kkal untuk wanita dewasa dan ±1.500 kkal untuk pria dewasa, **divalidasi oleh ahli gizi**). Jika pengguna memasukkan target lebih rendah secara manual, tampilkan peringatan informatif dan sarankan konsultasi.
3. **Tidak ada pesan yang mempermalukan:** hindari kata "gagal", "buruk", "dosa", atau bahasa yang menghakimi. Pelampauan target disajikan netral.
4. **Pengguna di bawah 18 tahun:** tidak ditawarkan target penurunan berat badan. Tampilkan catatan bahwa kebutuhan gizi remaja berbeda.
5. **Kewaspadaan gangguan makan:** hindari mekanisme gamifikasi yang mendorong pembatasan ekstrem (mis. hadiah untuk defisit besar). Sediakan opsi menyembunyikan angka kalori dan tautan sumber bantuan.
6. **Transparansi data:** setiap makanan menampilkan sumber data dan tingkat verifikasi. Nilai gizi adalah **estimasi**.

---

## 10. Spesifikasi Desain (Ringkasan dari DESIGN.md)

Implementasi wajib mengikuti sistem desain **Luminous Violet Macro Tracker**.

### 10.1 Warna semantik makro
| Makro | Warna |
|---|---|
| Protein | Deep Violet `#6D28D9` |
| Karbohidrat | Vibrant Purple `#8B5CF6` |
| Lemak | Warm Amber `#F59E0B` (juga untuk pencapaian/streak) |
| Sukses (target tercapai) | Mint `#10B981` |
| Melebihi target | Rose `#F43F5E` |
| Latar komponen/track | Soft Lavender `#EDE9FE` |
| Latar kanvas | `#FAFAFC` (token `surface` pada kode: `#fcf8ff`) |

### 10.2 Tipografi
- **Plus Jakarta Sans** (400/600/700/800), dengan skala `display-lg` hingga `label-sm` dan `numeric-stat`.
- Angka (kalori, makro, porsi) wajib memakai `font-feature-settings: "tnum" 1`.
- Label makro mikro (PRO, CARB, FAT) memakai `label-sm` huruf kapital dengan letter-spacing 0,04em.

### 10.3 Elevasi
Level 0 (kanvas), Level 1 (kartu ringkasan & meal), Level 2 (aktif/popover/FAB), Level 3 (bottom bar & modal berefek kaca buram `backdrop-blur 16px`).

### 10.4 Bentuk
Radius default 8 px (chip, input kecil), 16 px (kartu meal), 24 px (hero, bottom sheet, modal), pill penuh (tombol utama, segmented control, track progres).

### 10.5 Komponen utama
Tombol primer/sekunder pill, cincin progres SVG (round cap, track 8 px), kartu meal dengan bar makro linear 6 px, chip kategori, input numerik 48 px dengan focus ring, slider kustom, checkbox 20 px dengan animasi pegas, dan FAB 56 px.

### 10.6 Selisih antara DESIGN.md dan prototipe `code.html` (perlu diselaraskan)
| Hal | DESIGN.md | code.html | Tindak lanjut |
|---|---|---|---|
| FAB Quick-Add | Ada (56 px, Level 2) | Tidak ada; diganti tombol "Catat Makanan Cepat" di hero | Putuskan: FAB atau tombol hero atau keduanya |
| Warna makro di hero | Protein `#6D28D9`, Karbo `#8B5CF6`, Lemak `#F59E0B` | Memakai varian *fixed* pastel agar kontras di atas gradien | Tetapkan palet khusus latar gelap/gradien |
| Radius | `rounded: DEFAULT 0.5rem, lg 1rem, xl 1.5rem` | Konfigurasi Tailwind mendefinisikan `DEFAULT 0.25rem, lg 0.5rem, xl 0.75rem`, dan kartu memakai `rounded-2xl` bawaan | Samakan token radius dengan DESIGN.md |
| Segmented meal toggle | Chip terpilih berlatar `#EDE9FE`, teks `#6D28D9` | Terpilih berlatar solid `bg-primary` teks putih | Tetapkan satu gaya standar |
| Kartu kalkulator & meal | Level 1: border tipis violet + shadow lembut | Memakai `shadow-sm` tanpa border violet | Terapkan token Level 1 |
| Ukuran label 10 px | `label-sm` 10 px | Dipakai untuk teks penting (mis. "KKAL LEFT", batas slider) | Uji keterbacaan, pertimbangkan minimal 11–12 px |

---

## 11. Alur Pengguna Utama

### 11.1 Mencatat makanan lewat kalkulator
1. Pengguna membuka layar **Harian**.
2. Ketuk **Catat Makanan Cepat** (atau **Tambah …** pada kartu waktu makan tertentu).
3. Layar menggulir ke kalkulator, kategori waktu makan terpilih, kolom pencarian fokus.
4. Pengguna mengetik/memilih makanan dari autocomplete.
5. Mengatur porsi (stepper, slider, atau ketik).
6. Meninjau pratinjau kalori dan makro.
7. Ketuk **Tambahkan ke Jurnal Harian**; tombol menampilkan "Berhasil Ditambahkan!".
8. Kartu hero (angka, cincin, bar) dan kartu waktu makan terbarui otomatis.

### 11.2 Onboarding pertama kali
Splash → pengantar singkat → data tubuh → tujuan → peninjauan target (dengan penjelasan) → izin notifikasi (opsional) → layar Harian dengan empty state ramah.

### 11.3 Menyesuaikan target
Ketuk **Atur Target** → bottom sheet → ubah kalori/makro → lihat sinkronisasi total → **Simpan** → kartu hero ter-update.

### 11.4 Mengoreksi entri
Ketuk item pada jurnal → ubah porsi atau hapus → konfirmasi/undo → total diperbarui.

---

## 12. Daftar Kebutuhan Desain yang Belum Ada

Desain yang diunggah baru mencakup tab Harian. Untuk rilis perlu ditambahkan:
- Layar onboarding dan hasil target
- Modal **Atur Target**
- Layar **Kalkulator** penuh (pencarian, daftar hasil, favorit, terakhir dipakai)
- Detail makanan dan form **Makanan Kustom**
- Menu aksi pada item jurnal (ubah/hapus/pindah/salin)
- Layar **Analisis**
- Layar **Profil & Pengaturan**
- Pusat notifikasi
- Daftar dan detail resep
- Pemilih tanggal / navigasi hari
- Status: loading (skeleton), error, offline, makanan tidak ditemukan, melebihi target, target tercapai
- Layout tablet dan desktop
- Masuk/Daftar dan mode tamu

---

## 13. Catatan Temuan pada Prototipe Saat Ini

Hasil tinjauan `code.html` yang memengaruhi kebutuhan produk:

1. **Fallback nilai gizi diam-diam:** jika nama makanan tidak cocok, kode memakai nilai default (140 kkal, 10 g protein, 18 g karbo, 4 g lemak per 100 g) tanpa memberi tahu pengguna. Ini menyesatkan untuk aplikasi gizi. Produk harus menampilkan status "tidak ditemukan" atau meminta input manual.
2. **Pencocokan berbasis `includes` dua arah:** teks pendek seperti "a" dapat cocok dengan item pertama yang memuat huruf tersebut. Perlu pencarian yang proper (peringkat relevansi, minimal 2 karakter).
3. **Tombol "Tambahkan ke Jurnal" baru memberi animasi:** belum menyimpan data apa pun. Seluruh angka hero dan jurnal masih statis (HTML). Perlu model data dan state yang sebenarnya.
4. **Tombol "Atur Target", "Lihat Semua", notifikasi, dan navigasi bawah** belum memiliki fungsi.
5. **Kartu Sarapan dan Makan Malam mencantumkan item berupa hidangan gabungan** (mis. "Salmon Panggang & Salad Sayur"). Data harus mendukung entri gabungan dan resep kustom.
6. **Target makro vs target kalori:** pada contoh, target 140 g protein, 220 g karbo, 65 g lemak setara ±2.025 kkal, sedangkan target kalori 2.100 kkal (selisih ±3,6%). Produk harus menjaga keselarasan ini secara otomatis.
7. **Tailwind CDN, viewport yang mengunci zoom, dan ikon Google Fonts** perlu diganti untuk produksi (build-time CSS, izinkan zoom, subset ikon).
8. **Gambar logo dan resep** memakai URL eksternal sementara. Perlu aset yang di-host sendiri.

---

## 14. Pertanyaan Terbuka

1. Apakah login wajib sejak awal, atau mode tamu cukup untuk MVP?
2. Apakah pencatatan memakai gram saja atau juga satuan rumah tangga (butir, centong) sejak v1?
3. Setelah "Tambahkan ke Jurnal", apakah kolom pencarian dikosongkan atau dipertahankan untuk menambah makanan serupa?
4. Sumber data makanan utama dan lisensinya: TKPI, USDA, atau kombinasi dengan input tim konten?
5. Apakah target ideal per waktu makan (mis. Sarapan 400–500 kkal) dihitung otomatis atau ditetapkan statis?
6. Model bisnis: gratis penuh, freemium (analisis lanjutan berbayar), atau langganan?
7. Siapa ahli gizi/dietisien yang memvalidasi rumus, default, dan batas keamanan?
8. Apakah ide resep masuk MVP atau ditunda ke rilis berikutnya?
9. Perlukah mode gelap pada v1?
10. Stack teknologi dan infrastruktur backend (di luar dokumen ini).

---

## 15. Metrik Keberhasilan & Analitik

### 15.1 Metrik produk
| Metrik | Target (3 bulan setelah rilis) |
|---|---|
| Penyelesaian onboarding | ≥ 70% |
| Pengguna yang mencatat ≥ 1 makanan di hari pertama | ≥ 60% |
| Rata-rata entri per pengguna aktif per hari | ≥ 4 |
| Retensi D7 / D30 | ≥ 35% / ≥ 20% |
| Waktu median dari buka aplikasi hingga entri tersimpan | ≤ 20 detik |
| Pencarian tanpa hasil | ≤ 8% |
| Skor kepuasan (CSAT) | ≥ 4,2 / 5 |

### 15.2 Peristiwa yang dilacak
`onboarding_started/completed`, `target_adjusted`, `food_searched`, `food_not_found`, `portion_changed`, `entry_added/edited/deleted`, `quick_log_tapped`, `analysis_viewed`, `notification_opt_in`, `custom_food_created`, `app_installed_pwa`.

Analitik dikumpulkan dengan persetujuan pengguna dan tanpa data pribadi yang dapat mengidentifikasi.

---

## 16. Rencana Rilis

| Fase | Cakupan | Prioritas |
|---|---|---|
| **MVP (v1.0)** | Onboarding & target otomatis, Atur Target, hero ringkasan, kalkulator, jurnal per waktu makan (tambah/ubah/hapus), navigasi tanggal, database makanan Indonesia, mode tamu + akun, layout mobile, disclaimer & batas keamanan | P0 |
| **v1.1** | Analisis & tren, Profil & Pengaturan lengkap, favorit & terakhir dipakai, salin dari kemarin, satuan porsi rumah tangga, makanan kustom, notifikasi pengingat, PWA offline, layout tablet/desktop | P1 |
| **v1.5** | Resep rendah kalori, pemindai barcode, ekspor data, mode gelap, tren berat badan | P2 |
| **v2.0** | Integrasi kesehatan (Apple Health/Google Fit), resep multi-bahan, rencana makan, rekomendasi cerdas | Eksplorasi |

---

## 17. Risiko & Mitigasi

| Risiko | Dampak | Mitigasi |
|---|---|---|
| Data gizi tidak akurat atau tidak lengkap | Kepercayaan pengguna turun | Sumber resmi (TKPI/USDA), label verifikasi, fitur laporkan kesalahan |
| Pengguna menetapkan target ekstrem | Risiko kesehatan | Batas aman, peringatan informatif, disclaimer |
| Pencatatan terasa merepotkan sehingga retensi rendah | Pengguna berhenti | Quick log, favorit, salin kemarin, pengingat lembut |
| Perlindungan data pribadi tidak memadai | Risiko hukum & reputasi | Kepatuhan UU PDP, enkripsi, audit keamanan |
| Basis data makanan lokal kurang lengkap | Pencarian gagal | Kurasi konten prioritas, makanan kustom, pantau pencarian tanpa hasil |
| Kontras teks di atas gradien violet kurang | Aksesibilitas | Audit WCAG sebelum rilis, sesuaikan token |
| Perbedaan DESIGN.md dan implementasi | Inkonsistensi UI | Satu sumber token desain, review desain berkala |

---

## 18. Asumsi & Ketergantungan

**Asumsi**
- Pengguna utama memakai ponsel; sebagian besar sesi singkat (< 2 menit).
- Pengguna bersedia memasukkan data tubuh dasar untuk mendapat target personal.
- Perkiraan gizi berbasis gram cukup untuk MVP.

**Ketergantungan**
- Lisensi dan kurasi basis data makanan.
- Validasi ahli gizi atas rumus dan batas keamanan.
- Penyelesaian desain layar tambahan (bagian 12).
- Layanan autentikasi, penyimpanan, dan hosting.

---

## 19. Lampiran

### A. Glosarium
- **Makro (makronutrien):** protein, karbohidrat, lemak.
- **BMR:** laju metabolisme basal, energi yang dibutuhkan tubuh saat istirahat.
- **TDEE:** total kebutuhan energi harian termasuk aktivitas.
- **kkal:** kilokalori.
- **Tabular figures:** angka berlebar sama agar tidak bergeser saat nilai berubah.

### B. Data contoh (dari prototipe, per 100 g)
| Makanan | kkal | Protein | Karbo | Lemak |
|---|---|---|---|---|
| Dada ayam panggang | 165 | 31 | 0 | 3,6 |
| Nasi merah | 110 | 2,6 | 23 | 0,9 |
| Telur rebus | 155 | 13 | 1,1 | 11 |
| Oatmeal buah segar | 95 | 4,2 | 17 | 1,8 |
| Salmon panggang | 206 | 22 | 0 | 12 |
| Alpukat mentega | 160 | 2 | 9 | 15 |
| Greek yogurt plain | 73 | 10 | 4 | 2 |
| Pisang Cavendish | 89 | 1,1 | 23 | 0,3 |

> Nilai di atas berasal dari prototipe dan perlu diverifikasi ulang terhadap sumber resmi sebelum dipakai di produksi.
