
# PENGEMBANGAN SISTEM PENGENALAN WAJAH DAN DETEKSI SUKU MENGGUNAKAN COMPUTER VISION
## Ringkasan
Aplikasi Analisis Wajah ini merupakan alat berbasis web yang dibangun dengan **Streamlit** dan menyediakan berbagai fitur analisis wajah, antara lain:
- Klasifikasi Etnis
- Klasifikasi Gender
- Klasifikasi Kelompok Usia
- Perbandingan Kemiripan Wajah
- Deteksi Wajah Secara Langsung (Live)

## Fitur
- **Klasifikasi Etnis**: Mengidentifikasi etnis dari gambar yang diunggah atau melalui kamera
- **Klasifikasi Gender**: Mendeteksi jenis kelamin dari gambar atau webcam
- **Klasifikasi Kelompok Usia**: Mengklasifikasikan usia (Muda, Dewasa, Lansia)
- **Kemiripan Wajah**: Membandingkan dua wajah dan menghitung skor kemiripan serta metrik evaluasi
- **Deteksi Wajah Langsung**: Deteksi wajah secara real-time dengan berbagai pilihan klasifikasi

## Prasyarat
- Python versi 3.8 atau lebih baru
- Webcam (untuk fitur deteksi langsung)
- Disarankan menggunakan GPU untuk pemrosesan lebih cepat

## Struktur Proyek
```
face-analysis/
├── app/
│   ├── main.py                   # Aplikasi utama Streamlit
│   ├── preprocess.py             # Utilitas pra-pemrosesan gambar
│   ├── extract_embedding.py      # Ekstraksi embedding wajah
│   ├── face_similarity.py        # Utilitas pembandingan wajah
│   ├── pair_creation.py          # Utilitas pembuatan pasangan wajah
│   ├── evaluation.py             # Metrik evaluasi
│   ├── visualization.py          # Utilitas visualisasi
│   ├── tsne_visualization.py     # Visualisasi embedding dengan t-SNE
│   ├── train_model.py            # Utilitas pelatihan model
│   ├── ethnicity_classifier.py   # Fungsi klasifikasi etnis
│   ├── classify_gender.py        # Fungsi klasifikasi gender
│   └── classify_age.py           # Fungsi klasifikasi usia
├── models/
│   ├── ethnicity_classifier.h5   # Model klasifikasi etnis
│   ├── gender_model.h5           # Model klasifikasi gender
│   └── agemodel.h5               # Model klasifikasi usia
├── dataset/
│   ├── metadata.csv              # Metadata dataset
│   └── raw/                      # Gambar wajah mentah
└── requirements.txt              # Daftar dependensi proyek
```

### **Instalasi**
#### **1. Clone Repositori**
```bash
git clone https://github.com/yourusername/face-analysis.git
cd face-analysis
```

#### **2. Buat Lingkungan Virtual (Direkomendasikan)**
```bash
python -m venv venv
```

#### **Aktifkan Lingkungan Virtual:**
- **Windows**:
  ```bash
  venv\Scripts\activate
  ```
- **macOS/Linux**:
  ```bash
  source venv/bin/activate
  ```

#### **3. Instal Dependensi**
```bash
pip install -r requirements.txt
```

### **Isi `requirements.txt`**
Buat file `requirements.txt` dengan isi berikut:
```
streamlit==1.44.1
opencv-python==4.9.0.80
numpy==1.24.3
pillow==10.2.0
tensorflow==2.19.0
pandas==2.2.3
scikit-learn==1.3.2
matplotlib==3.10.1
seaborn==0.13.2
scipy==1.15.2
joblib==1.4.2
```

---
### **Download Model**
Ketiga file model (`agemodel.h5`, `ethnicity_classifier.h5`, `gender_model.h5`) perlu diunduh dan disalin ke dalam folder **`model`** dalam direktori proyek kamu.

#### **4. Mengunduh File Model**
Unduh file model dari folder Google Drive yang telah disediakan:
buka [Google Drive Folder](https://drive.google.com/drive/folders/14oslvqGxroMW4AlJmbeKrF2Yq_Mtuc7Y?usp=sharing) dan klik **Download All**.

Setelah itu, ekstrak file ZIP tersebut dan letakkan ketiga file (`agemodel.h5`, `ethnicity_classifier.h5`, dan `gender_model.h5`) ke dalam folder **`model`** di dalam proyek kamu. Pastikan struktur folder proyek kamu menjadi seperti berikut:

```
└── model/
    ├── agemodel.h5
    ├── ethnicity_classifier.h5
    └── gender_model.h5
```

#### **5. Menjalankan Aplikasi Streamlit**
```bash
cd app
streamlit run app.py
```
Aplikasi akan terbuka di browser pada alamat `http://localhost:8501`.


## Panduan Penggunaan
### 1. Klasifikasi Etnis
- Pilih menu "Identify Ethnicity"
- Unggah gambar atau gunakan webcam
- Jika unggah gambar, pilih gambar wajah
- Jika gunakan webcam, arahkan wajah ke kamera
- Hasil prediksi dan skor kepercayaan akan ditampilkan

### 2. Klasifikasi Gender
- Pilih menu "Identify Gender"
- Unggah gambar atau gunakan webcam
- Ikuti instruksi untuk melihat hasil klasifikasi gender

### 3. Klasifikasi Usia
- Pilih menu "Age Group Classification"
- Unggah gambar atau gunakan webcam
- Hasil klasifikasi usia akan ditampilkan (Muda, Dewasa, Lansia)

### 4. Kemiripan Wajah
- Pilih menu "Face Similarity"
- Unggah dua gambar wajah
- Sistem akan menampilkan:
  - Skor kemiripan
  - Status cocok/tidak cocok
  - Visualisasi perbandingan wajah
  - (Jika tersedia dataset) Metrik lanjutan seperti TAR, FAR, FRR, dan kurva ROC

## Pemecahan Masalah
### Masalah dalam Memuat Model
- Pastikan semua file model ada di folder `models/`
- Periksa format file model (.h5)
- Pastikan instalasi TensorFlow kompatibel dengan sistem Anda

### Masalah Akses Kamera
- Pastikan webcam terhubung dengan benar
- Pastikan tidak ada aplikasi lain yang menggunakan webcam
- Izinkan akses kamera di browser

### Masalah Performa
- Gunakan sistem dengan dukungan GPU untuk performa lebih baik
- Turunkan resolusi atau frame rate jika memungkinkan
- Tutup aplikasi lain yang berat

## Terima Kasih




