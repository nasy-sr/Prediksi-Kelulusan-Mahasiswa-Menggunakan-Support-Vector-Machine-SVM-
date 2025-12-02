# Proyek Machine Learning: Prediksi Kelulusan Mahasiswa Menggunakan Support Vector Machine (SVM)

## I. Identitas Proyek & Mahasiswa

| Detail | Isi |
| :--- | :--- |
| **Nama Mahasiswa** | Nasywa Salsabiila Romadhona |
| **NIM** | 2457201002354 |
| **Kelas/Mata Kuliah** | Machine Learning/Sistem Informasi 3A |
| **Dosen Pengampu** | Dr. Dwi Wahyu Prabowo, S. Si, M. Eng |

---

## II. Deskripsi & Tujuan Proyek

Proyek ini adalah tugas **Supervised Classification** menggunakan algoritma **Support Vector Machine (SVM)** untuk memprediksi **STATUS KELULUSAN** mahasiswa (TEPAT WAKTU / TERLAMBAT).

Dataset yang digunakan, `datakelulusanmahasiswa.csv`, berisi 14 atribut mahasiswa, termasuk Indeks Prestasi Kumulatif (IPK), nilai IPS per semester, umur, dan status demografi.

Tujuan utama adalah:
1. Melakukan **Eksplorasi** dan **Preprocessing** data.
2. Membangun model klasifikasi SVM dengan kernel **Linear** dan **RBF**.
3. Mengevaluasi kinerja model dan menginterpretasikan fitur dominan.

---

## III. Langkah Pengerjaan

| Tahap | Fokus Utama |
| :--- | :--- |
| **Bagian A & B** | **Data Insight:** Loading data, pemeriksaan *missing values*, **Exploratory Data Analysis** (Statistik deskriptif dan visualisasi distribusi IPK). |
| **Bagian C** | **Data Preparation:** Penanganan *missing values*, **Encoding** data kategorikal, **Feature Scaling** menggunakan StandardScaler (wajib), dan **Train-Test Split**. |
| **Bagian D** | **Model Training:** Melatih model SVM menggunakan **GridSearchCV** untuk **Hyperparameter Tuning** (`C` dan `Kernel`). |
| **Bagian E & F** | **Interpretation & Deployment:** Analisis fitur berpengaruh, kesimpulan, dan pembuatan fungsi `predict_status()` untuk simulasi prediksi. |

---

## IV. Hasil Evaluasi Model Terbaik (GridSearchCV)

Model terbaik dipilih melalui Grid Search pada *Test Set* (20% data) setelah *training*.

### A. Detail Model dan Kinerja Keseluruhan

| Kriteria | Hasil |
| :--- | :--- |
| **Model Terbaik** | **SVM Kernel Linear** |
| **Best Parameter** | `{'C': 0.1, 'kernel': 'linear'}` |
| **Akurasi Test Set (Overall)** | **$0.8947$** (89.47%) |
| **Best Cross-Validation Score (Training)** | $0.8845$ |

### B. Confusion Matrix & Analisis Kinerja Kelas

| Prediksi | Sebenarnya TEPAT (Support: 43) | Sebenarnya TERLAMBAT (Support: 33) |
| :--- | :--- | :--- |
| **Prediksi TEPAT** | 42 (True Negative) | 1 (False Positive) |
| **Prediksi TERLAMBAT** | 7 (False Negative) | 26 (True Positive) |

#### Kinerja Kelas (Classification Report)

| Kelas | Precision | Recall | F1-Score |
| :--- | :--- | :--- | :--- |
| **TEPAT** | $0.86$ | $0.98$ | $0.91$ |
| **TERLAMBAT** | **$0.96$** | $0.79$ | $0.87$ |
| **Weighted Avg** | $0.90$ | $0.89$ | $0.89$ |

### C. Interpretasi dan Kesimpulan

1.  **Keputusan Kernel:** Model terbaik yang dipilih adalah **Linear** dengan parameter $C=0.1$. Meskipun ada kemungkinan data tidak sepenuhnya *linearly separable*, parameter $C$ yang kecil menunjukkan model lebih mengutamakan *margin* pemisah yang luas untuk meningkatkan generalisasi pada data uji.
2.  **Kinerja Kelas:** Model sangat efektif ketika memprediksi status **TERLAMBAT** (Precision = $0.96$). Namun, adanya $7$ kasus False Negative menunjukkan adanya kesulitan dalam mengidentifikasi sebagian mahasiswa yang sebenarnya terlambat (Recall = $0.79$).
3.  **Generalisasi:** Akurasi keseluruhan sebesar $89.47\%$ menunjukkan model telah dilatih dengan baik, dan fitur akademik merupakan prediktor yang kuat.

---

## V. Cara Menjalankan & Screenshot

1.  Instal pustaka yang dibutuhkan: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`.
2.  Buka dan jalankan *notebook* `SVM_kelulusan.ipynb`.

### Bukti Eksekusi (Screenshot Hasil Prediksi Bagian F)

![SS hasil prediksi](https://github.com/user-attachments/assets/ce9f0f78-1130-475c-840a-80cb99600992)
