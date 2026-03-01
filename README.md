# Web Portofolio  - Satria Rajawali

**Oleh:** Satria Rajawali  
**NIM:** 2409116067 
---

##  Teknologi yang Digunakan
1. **HTML5:** Sebagai kerangka dasar *semantic web*.
2. **CSS:** Custom styling untuk menciptakan efek bayangan 3D (*Dark Neumorphism*) yang elegan dan *smooth hover transitions*.
3. **Bootstrap 5:** Digunakan secara masif untuk mempercepat proses *layouting*. Fitur yang dipakai meliputi: *Grid System* (`container`, `row`, `col-lg`), komponen siap pakai (`Navbar`, `Progress bar`, `Card`, `Button`), utilitas spasi (`mt`, `mb`, `py`, `gap`), serta memastikan desain responsif (*breakpoints*).
4. **Vue.js (via CDN):** Digunakan untuk memisahkan *data logic* dengan UI HTML. Menggunakan Option API `createApp({ data() })` untuk memusatkan semua data statis (teks, gambar, persentase skill). Data dirender secara reaktif menggunakan *Vue Interpolation* `{{ }}`, serta *Directive* seperti `v-for` untuk *looping* dan `v-bind` (`:src`, `:style`) untuk atribut dinamis.
5. **FontAwesome :** *Library* eksternal untuk ikon vektor (GitHub, Instagram, Database, Laravel).

---

##  Dokumentasi & Penjelasan Code Setiap Section

### 1. Navigation Bar (Navbar)
**Penjelasan Code:**
Menggunakan komponen bawaan Bootstrap `<nav class="navbar navbar-expand-lg">` agar menu otomatis berubah menjadi *hamburger icon* saat dibuka di HP. Terdapat fitur **Scrollspy** bawaan Bootstrap yang melacak posisi *scroll* pengguna (ditandai dengan `data-bs-spy="scroll"` pada tag `<body>`), sehingga menu navbar akan menyala sesuai *section* yang sedang aktif. Nama inisial dirender menggunakan Vue Interpolation `{{ inisial }}`.

**Tampilan:** \
<img src="https://github.com/user-attachments/assets/d27baf49-2e6b-4168-b034-aa75326e5bfb" width="800" alt="Tampilan Navbar">
<img src="https://github.com/user-attachments/assets/bef1c231-9dc3-44e2-8461-2224aa8468ec" width="800" alt="Tampilan HamburgNavbar">

---

### 2. Home (Hero Section)
**Penjelasan Code:**
Struktur tata letak dibangun dengan *Grid System* Bootstrap (`col-lg-7` untuk teks dan `col-lg-5` untuk gambar) agar sejajar di layar besar dan bertumpuk di layar kecil. Posisi diatur sejajar vertikal menggunakan *Flexbox* (`d-flex align-items-center`). Semua teks perkenalan, *tagline*, dan URL gambar profil dipanggil dari Javascript menggunakan Vue `{{ }}` dan `:src="profileImg"`. Tombol sosial media menggunakan perpaduan class `.btn` Bootstrap dan custom CSS Neumorphism.

**Tampilan:**

<img src="https://github.com/user-attachments/assets/90fcc600-f81e-4560-8a54-c479a3e902ab" width="800" alt="Tampilan Hero Section">


---

### 3. About Me & Technical Skills
**Penjelasan Code:**\
Bagian ini dibagi menjadi 2 kolom sama besar (`col-lg-6`). 
- **Experience:** Daripada menulis HTML berulang kali, data pengalaman di-*looping* dari array di Vue menggunakan directive `v-for="(exp, index) in pengalaman"`.
- **Technical Skills:** Menggunakan komponen `<div class="progress">` dari Bootstrap. Lebar warna pada *progress bar* tidak diatur manual di CSS, melainkan diikat secara dinamis ke data Vue menggunakan *Style Binding*: `:style="{ width: skill.progress + '%' }"`.

**Tampilan:**\
<img src="https://github.com/user-attachments/assets/f888a639-2634-4475-8eb0-70c7e59a361a" width="800" alt="Tampilan About and Skills">

---

### 4. Certificates (Achievement)
**Penjelasan Code:**
Menggunakan *Grid System* Bootstrap untuk membagi kartu menjadi 3 kolom di layar besar (`col-lg-4`). Struktur pembungkusnya menggunakan komponen `.card` dari Bootstrap yang garis pinggirnya dihilangkan dengan utilitas `.border-0` agar efek *Neumorphism* custom bisa menonjol. Gambar sertifikat dipanggil secara dinamis menggunakan pengikatan atribut `:src="cert.gambar"` di dalam *looping* `v-for` Vue.js.

**Tampilan:**\
<img src="https://github.com/user-attachments/assets/71413391-d3b5-407d-82d4-53f76b2cc3af" width="800" alt="Tampilan Certificates Section">
