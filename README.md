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

[cite_start]Proyek ini adalah tugas **Supervised Classification** menggunakan algoritma **Support Vector Machine (SVM)** untuk memprediksi **STATUS KELULUSAN** mahasiswa (TEPAT WAKTU / TERLAMBAT)[cite: 21].

[cite_start]Dataset yang digunakan, `datakelulusanmahasiswa.csv`, berisi 14 atribut mahasiswa, termasuk Indeks Prestasi Kumulatif (IPK), nilai IPS per semester, umur, dan status demografi[cite: 24, 34].

Tujuan utama adalah:
1. [cite_start]Melakukan **Eksplorasi** dan **Preprocessing** data[cite: 26, 27].
2. [cite_start]Membangun model klasifikasi SVM dengan kernel **Linear** dan **RBF**[cite: 76, 77].
3. [cite_start]Mengevaluasi kinerja model dan menginterpretasikan fitur dominan[cite: 29, 93].

---

## III. Langkah Pengerjaan

| Tahap | Fokus Utama |
| :--- | :--- |
| **Bagian A & B** | [cite_start]**Data Insight:** Loading data, pemeriksaan *missing values* [cite: 56][cite_start], **Exploratory Data Analysis** (Statistik deskriptif dan visualisasi distribusi IPK)[cite: 59, 61]. |
| **Bagian C** | [cite_start]**Data Preparation:** Penanganan *missing values* [cite: 68][cite_start], **Encoding** data kategorikal [cite: 69][cite_start], **Feature Scaling** menggunakan StandardScaler (wajib) [cite: 70, 73][cite_start], dan **Train-Test Split**[cite: 71]. |
| **Bagian D** | [cite_start]**Model Training:** Melatih model SVM menggunakan **GridSearchCV** untuk **Hyperparameter Tuning** (`C` dan `Kernel`)[cite: 78, 79, 81]. |
| **Bagian E & F** | [cite_start]**Interpretation & Deployment:** Analisis fitur berpengaruh, kesimpulan [cite: 93, 95][cite_start], dan pembuatan fungsi `predict_status()` untuk simulasi prediksi[cite: 97, 99]. |

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

1.  **Keputusan Kernel:** Model terbaik yang dipilih adalah **Linear** dengan parameter $C=0.1$. [cite_start]Meskipun data mungkin tidak sepenuhnya *linearly separable*, parameter $C$ yang kecil menunjukkan model lebih mengutamakan *margin* pemisah yang luas untuk meningkatkan generalisasi pada data uji[cite: 89].
2.  **Kinerja Kelas:** Model sangat efektif ketika memprediksi status **TERLAMBAT** (Precision = $0.96$), namun menunjukkan kesulitan dalam mengidentifikasi $7$ mahasiswa yang sebenarnya terlambat (False Negative), yang mengurangi *Recall* kelas tersebut ($0.79$).
3.  **Generalisasi:** Akurasi keseluruhan sebesar $89.47\%$ menunjukkan model telah dilatih dengan baik, dan fitur akademik merupakan prediktor yang kuat.

---

## V. Cara Menjalankan & Screenshot

1.  Instal pustaka yang dibutuhkan: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`.
2.  Buka dan jalankan *notebook* `SVM_kelulusan.ipynb`.


### Bukti Eksekusi (Screenshot Hasil Prediksi Bagian F)

![SS hasil prediksi](https://github.com/user-attachments/assets/ce9f0f78-1130-475c-840a-80cb99600992)
