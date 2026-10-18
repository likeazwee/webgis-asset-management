# 📍 Automated Public Asset Monitoring & Web-GIS Dashboard

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![GeoPandas](https://img.shields.io/badge/GIS-GeoPandas-green)
![Folium](https://img.shields.io/badge/Interactive-Folium%20%2F%20Leaflet-blue)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

## 📋 Studi Kasus: Manajemen Aset Publik & Pemeliharaan Fasilitas Kota

### 1. Latar Belakang Masalah
Di perkotaan dan fasilitas umum, pengelolaan aset seperti **pohon peneduh jalan** dan **penerangan jalan umum (PJU)** sering kali mengalami kendala dalam hal visibilitas spasial. Petugas di lapangan kesulitan mengidentifikasi titik mana saja yang memerlukan tindakan cepat (misalnya: pohon berisiko tumbang yang butuh pemangkasan, atau lampu jalan yang padam/rusak). Pendekatan pencatatan manual dalam tabel Excel biasa tidak mampu memberikan gambaran visual mengenai sebaran geografis aset-aset yang bermasalah tersebut.

### 2. Solusi IT & Integrasi GIS
Mengacu pada konsep yang dipaparkan oleh **Widi Primadepa** (*Asset Management Analyst* di City Care Property, Selandia Baru) pada *Informatics Practitioner Lecture Series*, lulusan Teknik Informatika dapat bertindak sebagai **GIS Developer & Integrator**. 

Proyek ini dibangun untuk mengotomatisasi alur kerja manajemen aset melalui tahap berikut:
* **Pengolahan Data Spasial Otomatis:** Mengubah koordinat geografis (Latitude & Longitude) dari format tabular (`.csv`) menjadi objek spasial `GeoDataFrame`.
* **Deteksi & Filter Prioritas:** Menyaring secara otomatis aset dengan kondisi kritis (`Rawat Segera`, `Rusak`, atau `Perlu Pemangkasan`).
* **Penyajian Web-GIS Interaktif:** Mengekspor hasil analisis menjadi peta interaktif berbasis web (`index.html`) yang dapat diakses oleh publik atau pengambil keputusan tanpa memerlukan perangkat lunak GIS berbayar maupun API Key khusus.

---

## ✨ Fitur Utama

- 🗺️ **Peta Interaktif Bebas API Key:** Menggunakan *tile basemap* Esri WorldStreetMap yang stabil, jernih, dan tidak memerlukan pendaftaran API Key.
- 🎨 **Visualisasi Indikator Kondisi Aset:**
  - 🟢 **Hijau (`Baik`):** Aset dalam kondisi aman.
  - 🟠 **Oranye (`Perlu Pemangkasan`):** Pohon yang membutuhkan perawatan rutin.
  - 🔴 **Merah (`Rawat Segera`):** Aset yang memerlukan tindakan secepatnya.
  - 🟤 **Merah Tua (`Rusak`):** Lampu/fasilitas yang tidak berfungsi.
- 📌 **Marker Cluster:** Mengelompokkan titik-titik aset secara dinamis saat peta di-zoom out agar tampilan tetap bersih.
- 💾 **Ekspor Standar Geospasial (GeoJSON):** Data aset prioritas diekspor otomatis ke file `priority_assets.geojson` untuk kebutuhan analisis lanjutan di software profesional seperti QGIS.

---

## 📁 Struktur Repositori

```
├── GIS_Asset_Analysis.ipynb # Jupyter / Google Colab Notebook (Kode utama)
├── index.html               # Peta Web-GIS Interaktif (Tampilan utama GitHub Pages)
├── sample_assets.csv        # Dataset mentah aset publik (CSV)
├── priority_assets.geojson  # Output data aset prioritas bermasalah (GeoJSON)
└── README.md                # Dokumentasi utama proyek
```

---

## 🚀 Cara Menjalankan Kode (Google Colab / Local Jupyter)

### 1. Menjalankan di Google Colab
1. Buka file `GIS_Asset_Analysis.ipynb` di repositori ini.
2. Klik tombol **Open in Colab** atau unduh file `.ipynb` tersebut lalu unggah ke [Google Colab](https://colab.research.google.com/).
3. Jalankan seluruh sel (*cells*) secara berurutan dari atas ke bawah.
4. Sel terakhir akan otomatis mengunduh file hasil olahan `index.html` dan `priority_assets.geojson` ke komputer Anda.

### 2. Menjalankan di Jupyter Notebook Lokal
1. Pastikan Anda telah menginstal pustaka yang dibutuhkan:
   ```bash
   pip install pandas geopandas folium shapely
   ```
2. Jalankan server Jupyter Notebook:
   ```bash
   jupyter notebook GIS_Asset_Analysis.ipynb
   ```
3. Eksekusi semua sel untuk menghasilkan peta `index.html`.

---

## 🌐 Publikasi ke GitHub Pages (Live Web-GIS)

Untuk membuat peta Web-GIS ini dapat diakses publik secara *online*:
1. Upload file `GIS_Asset_Analysis.ipynb`, `index.html`, `sample_assets.csv`, `priority_assets.geojson`, dan `README.md` ke repositori GitHub Anda.
2. Masuk ke **Settings** repositori di GitHub.
3. Pilih menu **Pages** di panel sebelah kiri.
4. Pada bagian **Build and deployment > Branch**, pilih `main` dan folder `/ (root)`.
5. Klik **Save**. Dalam beberapa menit, peta Anda akan aktif di URL `https://UsernameAnda.github.io/NamaRepoAnda/`.

---

## 👥 Referensi & Kredit
* **Pemateri:** Widi Primadepa (*Asset Management Analyst / GIS Analyst* at City Care Property, Christchurch, New Zealand).
* **Materi:** *"Career and Competition in Industrial Era with GIS"* - Informatics Practitioner Lecture Series, Universitas Bengkulu.
