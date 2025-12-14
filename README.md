# 📘 Judul Proyek
*Klasifikasi Jamur Beracun dan Aman Menggunakan Pendekatan Machine Learning dan Deep Learning*

## 👤 Informasi
- **Nama:** DZAKI ANWAR ZULFAHMI  
- **Repo:** https://archive.ics.uci.edu/dataset/848/secondary+mushroom+dataset 
- **Video:** https://drive.google.com/file/d/1ug0GlVzT7ykP695zMOkYG-qVX3psUuQw/view?usp=drive_link

---

# 1. 🎯 Ringkasan Proyek
-Masalah Utama: Mengatasi risiko keselamatan fatal (False Negative) dalam klasifikasi jamur.

-Data Preparation: Data tabular diproses melalui Imputasi Modus, One-Hot Encoding, dan Standard Scaling.

-Model: Membangun Logistic Regression (Baseline), Random Forest (Advanced), dan MLP Neural Network (Deep Learning).

-Evaluasi: Model terbaik (MLP) mencapai Recall 100% dan 0 False Negative.  

---

# 2. 📄 Problem & Goals
**Problem Statements:**  
- Model harus mampu memprediksi kelas jamur dengan akurasi tinggi dan meminimalkan risiko keselamatan (FN).
- Diperlukan model Deep Learning untuk memecahkan pemisah keputusan non-linier yang kompleks pada data berdimensi tinggi.

**Goals:**  
- Membangun tiga model ML dengan Akurasi $\ge$ 95%.
- Menentukan model yang mencapai Recall 100% pada kelas beracun (FN = 0) sebagai tujuan kritis proyek.

---
## 📁 Struktur Folder
```
project/
│
├── data/                   # Dataset (secondary_data.csv)
│
├── notebooks/              # Jupyter notebooks
│   └── ML_Project.ipynb
│
├── src/                    # Source code
│   
├── models/                 # Saved models
│   ├── model_baseline.pkl
│   ├── model_rf.pkl
│   └── model_cnn.h5
│
├── images/                 # Visualizations
│   └── lr_confusion_matrix.png
│
├── requirements.txt        # Dependencies
├── .gitignore
└── README.md
```
---

# 3. 📊 Dataset
- **Sumber:** Secondary Mushroom Dataset (Data Sekunder)
- **Jumlah Data:** 61.069 baris 
- **Tipe:**Tabular (Kategorikal & Float) 

### Fitur Utama
| Fitur | Keterangan |
|------|------------|
| class | Kelas jamur (target): p = beracun, e = dapat dimakan |
| cap-diameter | Diameter topi jamur (cm) |
| cap-shape | Bentuk topi jamur |
| cap-surface | Tekstur permukaan topi |
| cap-color | Warna topi jamur |
| does-bruise-or-bleed | Apakah jamur memar atau berdarah |
| gill-attachment | Cara insang melekat pada tangkai |
| gill-spacing | Jarak antar insang |
| gill-color | Warna insang |
| stem-height | Tinggi tangkai jamur (cm) |
| stem-width | Lebar tangkai jamur (mm) |
| stem-root | Bentuk akar tangkai |
| stem-surface | Tekstur permukaan tangkai |
| stem-color | Warna tangkai jamur |
| veil-type | Jenis selubung atau cincin (jika ada) |
| veil-color | Warna selubung |
| has-ring | Apakah memiliki cincin |
| ring-type | Jenis cincin |
| spore-print-color | Warna cetakan spora |
| habitat | Lingkungan tempat tumbuh |
| season | Musim tumbuh |



---

# 4. 🔧 Data Preparation
-Cleaning: Ditemukan Missing Values signifikan (mis. veil-type 57k+) dan Duplikat minor (0.24%). Ditangani dengan Imputasi Modus pada kolom kategorikal.

-Transformasi: One-Hot Encoding (OHE) diterapkan pada 17 fitur kategorikal, menghasilkan total 119 fitur. Fitur numerik di-scale menggunakan StandardScaler.

-Splitting: Data dibagi 80% Train (48.855) dan 20% Test (12.214) menggunakan Stratified Split.

---

# 5. 🤖 Modeling
- **Model 1 – Baseline:** Logistic Regression. Sederhana, menetapkan patokan FN awal.
- **Model 2 – Advanced ML:** Random Forest Classifier. Model ensemble non-linier, dipilih untuk mengurangi FN secara signifikan.
- **Model 3 – Deep Learning:** Multilayer Perceptron (MLP). Arsitektur dengan minimal 2 hidden layers (64 dan 32 neuron). Dipilih untuk memproses 119 fitur berdimensi tinggi.

---

# 6. 🧪 Evaluation
**Metrik:** Accuracy / F1 / MAE / MSE (pilih sesuai tugas)

### Hasil Singkat
| Model | Accuracy | Recall (Poisonous) | False Negative (FN) |
|------|----------|--------------------|--------------------|
| Baseline (LR) | 84.72% | 85.36% | 992 |
| Advanced (RF) | 96.28% | 95.51% | 304 |
| Deep Learning (NN) | 99.99% | 100.00% | 0 |


---

# 7. 🏁 Kesimpulan
- Model terbaik: Deep Learning (MLP Neural Network).
  
- Alasan: Model ini mencapai Recall 100% dan 0 False Negative (FN) pada Test Set, sepenuhnya memenuhi tujuan kritis keselamatan proyek.
  
- Insight penting: Kompleksitas model DL diperlukan untuk mencapai hasil sempurna; model RF yang canggih sekalipun masih meninggalkan 304 kasus risiko fatal.

---

# 8. 🔮 Future Work
-[ ] Tambah data (mengintegrasikan primary_data.csv).

-[ ] Coba arsitektur DL lain (dengan Batch Normalization/Dropout).

-[X] Deployment (Membuat API untuk model terbaik).

-[ ] Tuning model (Hyperparameter tuning RF untuk memverifikasi batas FN).

---

# 9. 🔁 Reproducibility
-Gunakan environment:Python Version: 12

-Main Libraries & Versions: pandas, numpy, scikit-learn, tensorflow/keras (untuk DL), matplotlib, seaborn.
