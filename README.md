
#  PORTOFOLIO

Website portofolio pribadi yang dibuat sebagai tugas pengembangan web, menampilkan profil, keahlian, pengalaman, dan sertifikat dalam tampilan yang modern, responsif, dan interaktif.

---

##  Teknologi yang Digunakan

| Teknologi | Keterangan |
|-----------|-----------|
| **HTML5** | Struktur dasar halaman web |
| **CSS3** | Styling, animasi, dan layout kustom |
| **Bootstrap 5** | Grid system, navbar, card, progress bar, utilities |
| **Google Fonts** | Font *Poppins* untuk tipografi |
| **Bootstrap Icons** | Ikon-ikon dekoratif dan fungsional |

---

## 📁 Struktur File

<img width="301" height="309" alt="image" src="https://github.com/user-attachments/assets/6fd83085-bd47-46fc-8046-f6bf4fb65c84" />


---

## 📸 Tampilan Setiap Section / Fitur

### 1.  Navbar

<img width="1355" height="74" alt="image" src="https://github.com/user-attachments/assets/525107e7-790e-4484-b1a8-b1e68959c3e5" />

- Navbar fixed di bagian atas halaman dengan efek *glassmorphism* (blur + transparansi)
- Berisi nama brand **"Irvan Alif"** dan tautan navigasi: Home, About Me, Certificates
- Responsif dengan tombol hamburger untuk tampilan mobile (menggunakan Bootstrap `navbar-toggler`)

```html
<nav class="navbar navbar-expand-lg fixed-top">
  <div class="container">
    <a class="navbar-brand" href="#home">Irvan Alif</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#menuNavbar">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="menuNavbar">
      <ul class="navbar-nav ms-auto">
        <li class="nav-item"><a class="nav-link" href="#home">Home</a></li>
        <li class="nav-item"><a class="nav-link" href="#about">About Me</a></li>
        <li class="nav-item"><a class="nav-link" href="#certificates">Certificates</a></li>
      </ul>
    </div>
  </div>
</nav>
```

---

### 2.  Section Home (Hero Section)

<img width="1352" height="680" alt="image" src="https://github.com/user-attachments/assets/054b16fa-bb37-4b32-8d9b-f83e2bef12b8" />

- Sapaan, nama lengkap, dan jabatan sebagai mahasiswa
- Deskripsi singkat tentang diri
- Dua tombol CTA: **"Lihat Sertifikat"** dan **"Tentang Saya"**
- Tiga kartu statistik: Semester, Koordinator, dan Sertifikat
- Foto profil bulat dengan animasi mengambang (*floating animation*)
- Badge universitas di bawah foto

```html
<section id="home" class="hero-section">
  <div class="container">
    <div class="row align-items-center min-vh-100 py-5">
      <div class="col-lg-7 order-2 order-lg-1">
        <p class="hero-sapaan">Halo, perkenalkan saya</p>
        <h1 class="hero-nama">Irvan Alif</h1>
        <h2 class="hero-jabatan">Mahasiswa Sistem Informasi</h2>
        ...
      </div>
      <div class="col-lg-5 order-1 order-lg-2 text-center">
        <img src="image/alip.jpeg" class="foto-profil" />
      </div>
    </div>
  </div>
</section>
```

**CSS — Animasi Floating Foto:**
```css
@keyframes mengambang {
  0%, 100% { transform: translateY(0); }
  50%       { transform: translateY(-14px); }
}
.foto-profil {
  animation: mengambang 4s ease-in-out infinite;
}
```

---

### 3.  Section About Me

Terbagi menjadi tiga bagian utama:
#### 3a. Informasi Pribadi

<img width="1349" height="674" alt="image" src="https://github.com/user-attachments/assets/76c3b4b3-2c72-477d-bcdb-803979376974" />

- Foto profil di sisi kiri dengan kartu floating bertuliskan jurusan
- Nama, jabatan, dan biografi singkat
- Kartu info: Lokasi, Email, Status, dan Jurusan

```html
<div class="col-12 col-sm-6">
  <div class="card info-item">
    <i class="bi bi-geo-alt-fill info-ikon"></i>
    <div class="ms-2">
      <small>Lokasi</small>
      <span>Samarinda, Kalimantan Timur</span>
    </div>
  </div>
</div>
```

#### 3b. Skills & Keahlian

<img width="1350" height="680" alt="image" src="https://github.com/user-attachments/assets/8c9ae732-ebb4-40ca-b4ff-d22ec609bb29" />

- Daftar skill dengan **progress bar** Bootstrap
- Skill: Jaringan Komputer, Manajemen Event, HTML & CSS, Leadership, Microsoft Office, Problem Solving

```html
<div class="mb-3">
  <div class="d-flex justify-content-between mb-1">
    <span class="skill-nama">Jaringan Komputer (MikroTik)</span>
    <span class="skill-persen">90%</span>
  </div>
  <div class="progress skill-progress">
    <div class="progress-bar" style="width: 90%"></div>
  </div>
</div>
```

#### 3c. Pengalaman

<img width="1351" height="678" alt="image" src="https://github.com/user-attachments/assets/aa3ae6ef-ae93-4167-ac2d-74df50066542" />

- Layout grid 2 kolom menggunakan Bootstrap Card
- Setiap kartu berisi: periode, jabatan, organisasi/lembaga, dan deskripsi
- Efek hover: kartu naik ke atas

```css
.exp-kartu:hover {
  transform: translateY(-7px);
  box-shadow: 0 18px 45px rgba(0,0,0,0.4) !important;
}
```

---

### 4.  Section Certificates

<img width="1348" height="680" alt="image" src="https://github.com/user-attachments/assets/e8359e65-c7ac-40f1-9b3a-c914af3db0ce" />

- 5 sertifikat dalam layout grid responsif (1–2–3 kolom)
- Setiap **card sertifikat** berisi:
  - **Header** — gradient warna unik per kategori + ikon + badge
  - **Body** — judul, penerbit, tanggal, deskripsi
  - **Footer** — ID sertifikat + tombol "Lihat"

```html
<div class="row g-4">
  <div class="col-md-6 col-lg-4">
    <div class="card cert-kartu h-100 border-0">
      <div class="card-header" style="background: linear-gradient(135deg, #29323c, #485563)">
        <i class="bi bi-router cert-ikon"></i>
        <span class="cert-badge-kat">Jaringan & Infrastruktur</span>
      </div>
      <div class="card-body">
        <h5 class="cert-judul">Sertifikasi LSP Jaringan Komputer - MikroTik</h5>
        ...
      </div>
      <div class="card-footer">
        <small class="cert-id">ID: LSP-TKJ-MIKROTIK</small>
        <a href="#" class="btn tombol-cert">Lihat</a>
      </div>
    </div>
  </div>
</div>
```

---

### 5.  Footer

<img width="1359" height="234" alt="image" src="https://github.com/user-attachments/assets/736da5b3-5e11-427d-9b2e-6eb9a82d995e" />

- Nama dengan efek teks gradient
- Ikon sosial media (GitHub, LinkedIn, Instagram, Email) dengan efek hover
- Teks hak cipta

```html
<footer class="footer-section py-5">
  <div class="container text-center">
    <p class="footer-nama">Irvan Alif</p>
    <div class="d-flex justify-content-center gap-3 my-3">
      <a href="#" class="sosmed-link"><i class="bi bi-github"></i></a>
      <a href="#" class="sosmed-link"><i class="bi bi-linkedin"></i></a>
      ...
    </div>
  </div>
</footer>
```

---

## 💡 Penjelasan CSS Utama

### Variabel Warna Global
```css
:root {
  --bg: #0f0f1a;       /* Background utama (gelap) */
  --surface: #1a1a2e;  /* Warna card/section */
  --aksen: #7c6fe8;    /* Ungu — aksen utama */
  --aksen2: #e8a87c;   /* Oranye — aksen sekunder */
  --teks: #e8e8f4;     /* Teks utama */
  --redup: #8888a0;    /* Teks sekunder/abu */
}
```

### Navbar Glassmorphism
```css
.navbar {
  background: rgba(15, 15, 26, 0.88);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(255,255,255,0.09);
}
```

### Animasi Fade Up (Hero)
```css
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(20px); }
  to   { opacity: 1; transform: translateY(0); }
}
.hero-nama { animation: fadeUp 0.5s ease both 0.25s; }
```

### Progress Bar Gradient
```css
.skill-progress .progress-bar {
  background: linear-gradient(90deg, var(--aksen), var(--aksen2));
}
```

---

## 📱 Responsivitas

| Breakpoint | Tampilan |
|-----------|---------|
| `< 576px` | 1 kolom, tombol full-width |
| `576px – 767px` | 2 kolom untuk info card |
| `768px – 991px` | 2 kolom untuk certificate cards |
| `≥ 992px` | 3 kolom certificates, hero & about side-by-side |

---
