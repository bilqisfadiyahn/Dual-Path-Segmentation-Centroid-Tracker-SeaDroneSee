# Penerapan Metode Dual-Path Segmentation Berbasis MOG2 dan Thresholding Menggunakan Centroid Tracker untuk Pelacakan Objek pada Dataset Sea Drone See

## Deskripsi Proyek

Proyek ini merupakan implementasi sistem **Computer Vision** untuk melakukan deteksi dan pelacakan objek pada lingkungan maritim menggunakan dataset **Sea Drone See**.

Metode yang digunakan menggabungkan **Dual-Path Segmentation** berbasis **MOG2** dan **Thresholding**, kemudian hasil segmentasi diproses menggunakan **Centroid Tracker** untuk mempertahankan identitas objek antar frame.

Sistem ini dirancang untuk mendeteksi dan melacak objek seperti **boat** dan **person** pada citra udara laut serta menghasilkan visualisasi hasil tracking dalam bentuk GIF.

---

## Penyusun

Proyek ini disusun sebagai bagian dari tugas mata kuliah Pengolahan Citra Digital.

1. Ruthtatia Grace Astridia
2. Bilqis Fadiyah Nisrina
3. Frelin Theresia Pania

---

## 💾 Dataset

Dataset yang digunakan adalah **Sea Drone See Dataset**, yaitu dataset citra maritim yang dikembangkan untuk penelitian deteksi dan pelacakan objek menggunakan drone.

Objek utama yang digunakan dalam proyek ini meliputi:

- Boat
- Person

Dataset diunduh secara **otomatis menggunakan Kaggle API**, sehingga pengguna tidak perlu mengunduh dataset secara manual.

🔗 **Link Sumber Dataset:**

https://www.kaggle.com/datasets/ubiratanfilho/sds-dataset/data

> ⚠️ **Catatan Penting:** Dataset tidak disimpan di repository GitHub karena diunduh secara otomatis melalui Kaggle API. Sebelum menjalankan notebook, pengguna harus mengisi `KAGGLE_USERNAME` dan `KAGGLE_KEY` milik sendiri. Jangan mengunggah API Key asli ke repository publik.

---

## 📂 Struktur Folder Repository

```text
├── Code/
│   └── notebook_project.ipynb
│
├── Output/
│   └── hasil_tracking.gif
│
└── README.md
```

- **Code/** : Berisi Jupyter Notebook untuk proses download dataset, preprocessing, segmentasi, tracking, dan visualisasi hasil.
- **Output/** : Berisi hasil akhir berupa GIF tracking objek.
- **README.md** : Dokumentasi proyek.

---

## Arsitektur Sistem

```text
Kaggle API
     │
     ▼
Download Dataset
     │
     ▼
Preprocessing
     │
     ▼
Dual-Path Segmentation
     ┌───────────┐
     ▼           ▼
   MOG2     Thresholding
     └─────┬─────┘
           ▼
 Segmentasi Gabungan
           ▼
Morphological Processing
           ▼
 Noise Filtering
           ▼
Centroid Tracker
           ▼
Object Classification
           ▼
Visualisasi Hasil
           ▼
GIF Output
```

---

# Tahapan Sistem

## 1. Akuisisi Dataset

Dataset diunduh secara otomatis menggunakan Kaggle API.

Tahapan yang dilakukan:

- Koneksi ke Kaggle API
- Download dataset
- Ekstraksi dataset
- Persiapan folder kerja

---

## 2. Preprocessing Data

Tahap preprocessing dilakukan untuk menyiapkan data sebelum proses segmentasi.

Proses yang dilakukan meliputi:

- Membaca frame gambar
- Penyesuaian format citra
- Persiapan data untuk proses segmentasi

---

## 3. Dual-Path Segmentation

Proses segmentasi dilakukan menggunakan dua metode yang berjalan secara bersamaan.

### MOG2

Digunakan untuk mendeteksi objek bergerak berdasarkan perubahan background.

### Thresholding

Digunakan untuk memisahkan objek dari background berdasarkan nilai intensitas piksel.

Hasil kedua metode kemudian digabungkan untuk memperoleh area objek yang lebih akurat.

---

## 4. Morphological Processing dan Noise Filtering

Untuk mengurangi kesalahan deteksi dilakukan proses tambahan berupa:

- Morphological Operation
- Noise Filtering
- Penyaringan objek kecil

Tahap ini membantu mengurangi noise dan false detection.

---

## 5. Object Tracking

Pelacakan objek dilakukan menggunakan **Centroid Tracker**.

Tahapan yang dilakukan:

- Menghitung titik centroid objek
- Memberikan ID pada objek
- Mempertahankan identitas objek antar frame

---

## 6. Visualisasi Hasil

Output sistem berupa:

- Bounding Box
- Label objek
- Tracking ID
- GIF hasil tracking

Visualisasi ini digunakan untuk mengevaluasi performa sistem.

---

## Hasil Implementasi

Sistem mampu:

- Mendeteksi objek pada lingkungan maritim
- Melacak perpindahan objek antar frame
- Mempertahankan identitas objek
- Menghasilkan visualisasi tracking dalam bentuk GIF

---

## Library yang Digunakan

- Python
- OpenCV
- NumPy
- Pandas
- Matplotlib
- Pillow
- Kaggle API

---

## Output Proyek

Hasil akhir dari proyek ini berupa:

- Sistem deteksi objek maritim
- Sistem pelacakan objek menggunakan Centroid Tracker
- Visualisasi bounding box dan tracking ID
- GIF hasil tracking objek

Contoh struktur output:

```text
Output/
└── hasil_tracking.gif
```

---

## Konsep yang Diimplementasikan

- Computer Vision
- Image Processing
- Object Detection
- Object Tracking
- Dual-Path Segmentation
- Background Subtraction (MOG2)
- Thresholding
- Morphological Processing
- Noise Filtering
- Centroid Tracking
