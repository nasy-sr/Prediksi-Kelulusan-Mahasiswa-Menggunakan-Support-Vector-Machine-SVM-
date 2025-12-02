# 🌟 Proyek Machine Learning: Prediksi Kelulusan Mahasiswa Menggunakan Support Vector Machine (SVM)

## 👤 Identitas Mahasiswa

| Detail | Isi |
| :--- | :--- |
| **Nama** | [NAMA LENGKAP ANDA] |
| **NIM** | [NOMOR INDUK MAHASISWA ANDA] |
| **Kelas/Mata Kuliah** | [NAMA MATA KULIAH / KELAS ANDA] |

---

## 📄 Deskripsi Proyek

Proyek ini bertujuan untuk membangun model klasifikasi menggunakan algoritma **Support Vector Machine (SVM)** untuk memprediksi **STATUS KELULUSAN** mahasiswa, yaitu apakah mereka lulus **TEPAT WAKTU** atau **TERLAMBAT**.

Dataset yang digunakan berisi 14 atribut mahasiswa, termasuk nilai IPS per semester, IPK kumulatif, umur, jenis kelamin, dan status keaktifan/pernikahan.

---

## 🛠️ Langkah Pengerjaan

Pengerjaan proyek ini terbagi menjadi 6 tahap utama yang tercakup dalam *notebook* `SVM_kelulusan.ipynb`:

1.  **Setup & Loading Dataset (Bagian A):** Memuat data CSV, pemeriksaan awal tipe data, dan identifikasi *missing values*.
2.  **Exploratory Data Analysis (EDA) (Bagian B):** Analisis statistik deskriptif dan visualisasi (Histogram IPK, Countplot Status Kelulusan) untuk memahami distribusi data dan hubungan antar fitur.
3.  **Preprocessing Data (Bagian C):** Penanganan *missing values* (imputasi), *Encoding* data kategorikal (Label dan One-Hot Encoding), dan *Feature Scaling* menggunakan **StandardScaler**.
4.  **Training Model SVM (Bagian D):** Pelatihan model klasifikasi SVM dengan kernel **Linear** dan **RBF**. Dilakukan **Hyperparameter Tuning** menggunakan **GridSearchCV** untuk mencari kombinasi parameter terbaik (`C` dan `gamma`).
5.  **Evaluasi Model & Interpretasi (Bagian E):** Penghitungan metrik kinerja (Akurasi, Precision, Recall, F1-score) dan analisis fitur dominan (IPK) yang mempengaruhi keputusan model.
6.  **Deployment Sederhana (Bagian F):** Pembuatan fungsi Python `predict_status()` untuk simulasi prediksi status kelulusan berdasarkan input mahasiswa baru.

---

## 📊 Hasil Evaluasi Model Terbaik

Model terbaik dipilih melalui Grid Search pada *Test Set* (20% data) setelah *training* dengan kernel dan *hyperparameter* tertentu.

**Model Terbaik:** `Kernel: [ISI KERNEL TERBAIK DARI BAGIAN D, contoh: rbf]`, `C: [ISI NILAI C TERBAIK]`, `Gamma: [ISI NILAI GAMMA TERBAIK]`

| Metrik Evaluasi | Nilai |
| :--- | :--- |
| **Akurasi** | [ISI AKURASI DARI BAGIAN D, contoh: 0.9231] |
| **Precision (Rata-rata)** | [ISI NILAI DARI CLASSIFICATION REPORT] |
| **Recall (Rata-rata)** | [ISI NILAI DARI CLASSIFICATION REPORT] |
| **F1-Score (Rata-rata)** | [ISI NILAI DARI CLASSIFICATION REPORT] |

**Confusion Matrix:**  
