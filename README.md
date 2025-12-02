# Proyek Machine Learning: Prediksi Kelulusan Mahasiswa Menggunakan Support Vector Machine (SVM)

## Identitas Mahasiswa

| Detail | Isi |
| :--- | :--- |
| **Nama** | Nasywa Salsabiila Romadhona |
| **NIM** | 2457201002354 |
| **Kelas/Mata Kuliah** | Machine Learning/Sistem Informasi 3A |

---

## Deskripsi Proyek

Proyek ini bertujuan untuk membangun model klasifikasi menggunakan algoritma **Support Vector Machine (SVM)** untuk memprediksi **STATUS KELULUSAN** mahasiswa, yaitu apakah mereka lulus **TEPAT WAKTU** atau **TERLAMBAT**.

Dataset yang digunakan berisi 14 atribut mahasiswa, termasuk nilai IPS per semester, IPK kumulatif, umur, jenis kelamin, dan status keaktifan/pernikahan.

---

## Langkah Pengerjaan

Pengerjaan proyek ini terbagi menjadi 6 tahap utama yang tercakup dalam *notebook* `SVM_kelulusan.ipynb`:

1.  **Setup & Loading Dataset (Bagian A):** Memuat data CSV, pemeriksaan awal tipe data, dan identifikasi *missing values*.
2.  **Exploratory Data Analysis (EDA) (Bagian B):** Analisis statistik deskriptif dan visualisasi (Histogram IPK, Countplot Status Kelulusan) untuk memahami distribusi data dan hubungan antar fitur.
3.  **Preprocessing Data (Bagian C):** Penanganan *missing values* (imputasi), *Encoding* data kategorikal (Label dan One-Hot Encoding), dan *Feature Scaling* menggunakan **StandardScaler**.
4.  **Training Model SVM (Bagian D):** Pelatihan model klasifikasi SVM. Dilakukan **Hyperparameter Tuning** menggunakan **GridSearchCV** untuk mencari kombinasi parameter terbaik (`C` dan `gamma`/`kernel`).
5.  **Evaluasi Model & Interpretasi (Bagian E):** Penghitungan metrik kinerja (Akurasi, Precision, Recall, F1-score) dan analisis fitur dominan.
6.  **Deployment Sederhana (Bagian F):** Pembuatan fungsi Python `predict_status()` untuk simulasi prediksi status kelulusan.

---

## Hasil Evaluasi Model Terbaik

Model terbaik dipilih melalui Grid Search pada *Test Set* (20% data) setelah *training*.

### Detail Model Terbaik

* **Best Parameters:** `{'C': 0.1, 'kernel': 'linear'}`
* **Best Cross-Validation Score (Training):** `0.8845`
* **Akurasi pada Test Set:** **`0.8947`**

### Confusion Matrix

Menunjukkan bagaimana model mengklasifikasikan data pada *Test Set* (43 TEPAT, 33 TERLAMBAT):
