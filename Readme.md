# 🐍 CNN Image Classification: Cat, Dog, Snake

Proyek ini bertujuan untuk membangun model **Convolutional Neural Network (CNN)** sederhana untuk mengklasifikasikan gambar menjadi 3 kelas: **Cat**, **Dog**, dan **Snake**.

---

## 📂 Struktur Proyek

- `main.ipynb`  
  Notebook utama untuk **memproses dan melatih model CNN**. Berisi:
  - Training model CNN.
  - Menyimpan model dalam format:
    - TensorFlow SavedModel (`saved_model/`)
    - TensorFlow Lite (`tflite/`)
    - TensorFlow.js (`tfjs_model/`)

- `filtering_data.ipynb`  
  Notebook tambahan untuk **memisahkan dan menyiapkan dataset**. Berisi:
  - Memindahkan data dari direktori `source/` menjadi `data/` yang terbagi ke dalam:
    - `train/`
    - `valid/`
    - `test/`
  - Membuat file `labels.csv` berisi path gambar dan label.

- `requirements.txt`  
  Berisi daftar library Python yang diperlukan untuk menjalankan proyek.

---

## 📁 Struktur Direktori

```
├───tfjs_model/
│   ├───group1-shard1of1.bin
│   └───model.json
│
├───tflite/
│   ├───model.tflite
│   └───label.txt
│
├───saved_model/
│   ├───saved_model.pb
│   └───variables/
│
├───data/
│   ├───train/
│   ├───test/
│   └───valid/
│
├───source/
│   ├───cat/
│   ├───dog/
│   └───snake/
│
├───main.ipynb
├───filtering_data.ipynb
├───README.md
└───requirements.txt
```

---

## ⚙️ Penjelasan Filtering Data

- Dataset awal berada di `source/` dan terdiri dari tiga folder: `cat/`, `dog/`, dan `snake/`.
- Dengan `filtering_data.ipynb`, gambar dipindahkan ke dalam folder `data/` dengan rasio:
  - **70%** untuk training (`train/`)
  - **15%** untuk validasi (`valid/`)
  - **15%** untuk testing (`test/`)
- Proses ini juga membuat `labels.csv` yang mencatat semua gambar dan labelnya.

Contoh distribusi hasil split:

```
📁 TRAIN
  - cat: 8757 file
  - dog: 8761 file
  - snake: 2980 file

📁 VALID
  - cat: 1876 file
  - dog: 1877 file
  - snake: 638 file

📁 TEST
  - cat: 1878 file
  - dog: 1879 file
  - snake: 640 file
```

---

## 🎯 Target Proyek

- **Mencapai akurasi ≥ 95%** pada validasi menggunakan Early Stopping.
- Model harus ringan dan cepat, cocok untuk deployment ke berbagai platform:
  - Mobile (TFLite)
  - Web (TensorFlow.js)
