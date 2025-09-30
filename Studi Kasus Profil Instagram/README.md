# Tugas: Profil Instagram (Bootstrap & Tailwind)

Studi kasus ini berisi dua implementasi halaman profil Instagram yang:
1. **Bootstrap 5** (`profil-instagram-bootstrap.html`)
2. **Tailwind CSS + DaisyUI** (`profil-instagram-tailwind.html`)

## Struktur Folder
```

.
├── index-bootstrap.html     
├── index-tailwind.html      
├── assets/
│   └── img/                 
└── README.md               

```

## Cara Menjalankan
1. Download / clone project.
2. Buka file HTML (`profil-instagram-bootstrap.html` atau `profil-instagram-tailwind.html`) langsung di browser.
3. Pastikan terkoneksi internet karena dependensi di-load dari CDN:
   - Bootstrap 5 + Bootstrap Icons
   - Tailwind + DaisyUI

---

## Bagian A: Versi Bootstrap

### Pertanyaan README
**1. Mengapa memilih konfigurasi `col-` tertentu untuk tiap breakpoint?**  
Agar layout feed responsif. Misalnya:
- `col-12` → 1 kolom di mobile
- `col-sm-6` → 2 kolom di tablet
- `col-md-4` → 3 kolom di layar sedang
- `col-lg-3` → 4 kolom di desktop  
Konfigurasi ini membuat tampilan tetap rapi di berbagai ukuran layar.

**2. Bagaimana memastikan tombol Follow/Edit tetap mudah dijangkau di mobile?**  
Menggunakan sistem grid & utility class `order` dari Bootstrap agar tombol berubah urutan di breakpoint kecil, serta memakai `btn-sm` supaya ukurannya sesuai layar kecil.

**3. Jika postingan bertambah jadi 50, apa potensi masalah dan solusi?**  
Masalah: halaman jadi panjang & berat untuk load gambar.  
Solusi: gunakan pagination / infinite scroll atau lazy loading gambar (`loading="lazy"`).

---

## Bagian B: Versi Tailwind + DaisyUI

### Penjelasan Desain 
1. **Layout grid feed** 
- `grid-cols-1` untuk mobile → foto tampil penuh agar jelas di layar kecil. 
- `sm:grid-cols-2` untuk tablet → 2 kolom agar lebih padat tapi tetap terbaca. 
- `md:grid-cols-3` untuk layar sedang → 3 kolom memberi keseimbangan antara kerapatan & keterbacaan. 
- `lg:grid-cols-4` untuk desktop → memanfaatkan ruang lebar dengan 4 kolom. 
- `gap-2` digunakan agar ada jarak antar foto. 

2. **Bagian profil** 
- Foto profil diberi class `rounded-full object-cover` untuk membulat sempurna. 
- Informasi username, jumlah posting/pengikut/diikuti ditampilkan dengan `font-bold` agar menonjol. 
- Bio menggunakan `text-gray-600` supaya lebih lembut. 

3. **Tombol interaksi (Follow / Edit Profile)** 
- Menggunakan komponen `btn` dari DaisyUI untuk konsistensi desain. 
- Diberi responsive utility `order-1 md:order-0` supaya tombol tetap rapi dan mudah diakses di mobile. 
- Variasi `btn-primary` dan `btn-outline` dipakai untuk membedakan fungsi. 

4. **Header dan Footer** 
- Header berupa navbar sederhana dengan logo Instagram (SVG) dan teks “Instagram”. 
- Footer dibuat minimalis (`text-gray-500 text-sm`) agar tidak mendistraksi isi halaman. 

---

### Pertanyaan README
**1. Jelaskan keputusan `grid-cols`/`gap` di tiap breakpoint.**  
- `grid-cols-1` (mobile) → agar 1 kolom full lebar.  
- `sm:grid-cols-2` → di tablet 2 kolom.  
- `md:grid-cols-3` → di layar sedang 3 kolom.  
- `lg:grid-cols-4` → di desktop 4 kolom.  
Gap antar item diset dengan `gap-2` agar jarak konsisten.

**2. Bagaimana memanfaatkan utility responsif untuk masalah layout di mobile?**  
Dengan `flex`, `order`, `col-span`, dan responsive prefix (`sm:`, `md:`, `lg:`).  
Contoh: tombol Follow & Edit bisa diatur urutannya (`order-1 md:order-0`) supaya lebih nyaman di mobile.

**3. Jelaskan trade-off antara banyak utility classes vs custom CSS.**  
- **Utility classes:** cepat, konsisten, mudah di-maintain.  
- **Custom CSS:** lebih ringkas di HTML tapi butuh file CSS tambahan.  
Trade-off: Utility bisa membuat HTML panjang, tapi mengurangi kebutuhan file CSS eksternal.

---

## Dependensi
- **Bootstrap version**:
  - [Bootstrap 5.3](https://getbootstrap.com/)
  - [Bootstrap Icons](https://icons.getbootstrap.com/)
- **Tailwind version**:
  - [Tailwind CDN](https://tailwindcss.com/docs/installation/play-cdn)
  - [DaisyUI CDN](https://daisyui.com/)

---