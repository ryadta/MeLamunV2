# MeLamun V2

**MeLamun V2** adalah sebuah platform aplikasi berbasis web cerdas (AI-Powered) yang didesain untuk mengenali dan mengklasifikasikan berbagai spesies lamun (seagrass) pada foto bawah air dengan tingkat akurasi yang tinggi. Proyek ini memadukan desain UI yang *clean*, modern, dan responsif dengan integrasi machine learning di sisi klien (browser).

## 🌟 Fitur Utama

- **Identifikasi Ganda (YOLOv8 & MobileNetv4)**: Sistem ini menggunakan dua model AI yang dapat digunakan secara terpisah maupun bersamaan dalam mode perbandingan (Comparison Mode).
- **Database Spesies Interaktif (Model 3D)**: Menyediakan ensiklopedia spesies lamun (seperti *Cymodocea rotundata*, *Enhalus acoroides*, dll.) lengkap dengan model 3D interaktif yang dapat diputar dan di-zoom langsung di browser Anda.
- **Deteksi Langsung**: Anda dapat mengunggah gambar dari perangkat Anda atau mengambil foto secara langsung menggunakan kamera.
- **Analisis Akurat**: Sistem akan memproses gambar dan menampilkan probabilitas/kepercayaan (confidence score) dari tiap spesies yang terdeteksi secara *real-time*.
- **Desain UI/UX Premium**: Antarmuka bergaya *Apple-inspired* dengan efek glassmorphism, *smooth scrolling*, animasi yang dinamis, dan responsif untuk semua ukuran perangkat (Mobile & Desktop).

## 🚀 Teknologi yang Digunakan

- **Frontend**: HTML5, Vanilla JavaScript, Tailwind CSS (melalui CDN)
- **Model 3D Viewer**: `<model-viewer>` dari Google untuk merender file `.glb`
- **Machine Learning (Inference)**: 
  - YOLOv8 (Ultralytics) - untuk deteksi objek (Bounding box)
  - MobileNetv4 - untuk klasifikasi gambar (Image classification)
- **Icons & Media**: SVG Icons terintegrasi

## 📋 Cara Penggunaan (Local Development)

Proyek ini tidak memerlukan *build tools* yang kompleks seperti Node.js atau Webpack. Namun, karena sistem ini menggunakan *fetching* untuk memuat file model AI dan 3D, Anda harus menjalankannya melalui local server.

1. **Clone repositori ini**
   ```bash
   git clone https://github.com/ryadta/MeLamunV2.git
   cd MeLamunV2
   ```

2. **Jalankan Local Web Server**
   Anda dapat menggunakan ekstensi seperti **Live Server** di VS Code, atau menggunakan Python:
   ```bash
   python -m http.server 8000
   ```
   Atau PHP:
   ```bash
   php -S localhost:8000
   ```

3. **Buka di Browser**
   Buka `http://localhost:8000` di web browser Anda.

## 📁 Struktur Direktori Utama

```
MeLamunV2/
├── index.html           # Halaman utama aplikasi (UI & Logic JS)
├── README.md            # Dokumentasi proyek
└── assets/              # Folder untuk media (video, logo, gambar)
    └── models/          # Folder untuk menyimpan file 3D (.glb)
```
*(Catatan: Anda mungkin perlu menambahkan file model 3D .glb Anda masing-masing ke dalam folder `assets/models/` sesuai nama spesiesnya jika diunduh dari environment aslinya).*

## 💡 Troubleshooting
Jika file `.glb` tidak dapat dirender saat dihosting (misalnya di InfinityFree atau hosting cPanel), pastikan file `.htaccess` di dalam direktori `assets/models/` memiliki pengaturan MIME type berikut:
```apache
AddType model/gltf-binary .glb
```

## 📄 Lisensi
Hak Cipta &copy; 2026 MeLamun Project.
