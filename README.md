# -PCD2025_2B_D3_045_046_058-_ETS
# Aplikasi Analisis Wajah

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

## Instalasi
### 1. Clone repositori
```bash
git clone https://github.com/yourusername/face-analysis.git
cd face-analysis
```

### 2. Buat lingkungan virtual (direkomendasikan)
```bash
python -m venv venv
```

#### Aktifkan lingkungan virtual:
- **Windows**:
  ```bash
  venv\Scripts\activate
  ```
- **macOS/Linux**:
  ```bash
  source venv/bin/activate
  ```

### 3. Instal dependensi
```bash
pip install -r requirements.txt
```

## Isi `requirements.txt`
Buat file `requirements.txt` dengan isi berikut:

```
streamlit>=1.22.0
opencv-python>=4.6.0
numpy>=1.22.0
Pillow>=9.1.0
tensorflow>=2.9.0
scikit-learn>=1.1.0
matplotlib>=3.5.0
pandas>=1.4.0
seaborn>=0.11.0
```

## Menjalankan Aplikasi

### Jalankan aplikasi Streamlit
```bash
cd app
streamlit run app.py
```

Aplikasi akan terbuka di browser pada alamat `http://localhost:8501`

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

### 5. Deteksi Wajah Langsung
- Pilih menu "Live Face Detection"
- Pilih mode deteksi (Etnis, Gender, Usia, atau kombinasi)
- Izinkan akses kamera
- Deteksi dan klasifikasi wajah akan ditampilkan secara real-time
- Klik "Stop Detection" untuk berhenti

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

## Catatan Pengembangan
### Menambahkan Model Baru
Untuk menambah atau memperbarui model:
1. Letakkan file model (.h5) di folder `models/`
2. Perbarui fungsi klasifikasi terkait
3. Periksa dan sesuaikan label kelas jika diperlukan

### Kebutuhan Dataset
Untuk evaluasi kemiripan wajah:
- Dataset terstruktur di `dataset/raw/`
- Metadata ada di `dataset/metadata.csv`
- Pasangan gambar tersedia untuk pembandingan


## Terima Kasih
