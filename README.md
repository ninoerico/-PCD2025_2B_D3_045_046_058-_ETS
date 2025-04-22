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
face-analysis/
│
├── app/
│   ├── app.py
│
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

---
