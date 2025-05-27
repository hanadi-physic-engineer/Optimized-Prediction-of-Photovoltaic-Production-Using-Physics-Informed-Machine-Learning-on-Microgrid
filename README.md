# PV Microgrid Hybrid System - XGBoost Modeling & Analysis

## Deskripsi Proyek

Proyek ini bertujuan untuk melakukan analisis, pemodelan, dan prediksi performa sistem PV Microgrid Hybrid menggunakan pendekatan data-driven dan physics-informed machine learning, khususnya dengan algoritma XGBoost. Proyek ini mencakup proses persiapan data, eksplorasi data, pemodelan regresi dan klasifikasi, serta evaluasi performa model.

## Struktur Folder

- **Data Preparation**  
  Semua proses pembersihan, penggabungan, dan visualisasi data dilakukan di folder [`preparasi data`](preparasi%20data).
  - Contoh file: `Data_Preparation_afterremoveoutlier_Final.ipynb`, `Data_PV_Microgrid_after_remove_outlier.csv`, dll.

- **Modeling & Analysis**  
  Berisi notebook utama untuk pemodelan dan analisis:
  - `Model 1_Fix.ipynb` : Model XGBoost dengan pendekatan physics-informed untuk kondisi 1.
  - `Model2-CLF_fix.ipynb` : Model XGBoost untuk kondisi 2 (regresi & klasifikasi).
  - `Model3-CO-FIC.ipynb` : Model XGBoost untuk kondisi 3.
  - Notebook lain untuk eksperimen dan validasi.

- **Data**  
  Berisi file data utama seperti `Data_XGBoost.csv`, `Data_costhetaAOI.csv`, dll.

- **Output & Visualisasi**  
  Hasil visualisasi dan evaluasi model, seperti file PNG hasil plot dan file model terlatih (`Modelkondisi1baru.pkl`, dst).

## Alur Kerja

1. **Persiapan Data**
   - Data diolah dan dibersihkan di notebook pada folder [`preparasi data`](preparasi%20data).
   - Data yang telah dibersihkan digunakan untuk proses modeling.

2. **Feature Engineering**
   - Penambahan fitur waktu (month, day, hour, dst).
   - Encoding variabel kategorikal (`Op_GriSwStt`).

3. **Pemodelan**
   - Model regresi dan klasifikasi dibangun menggunakan XGBoost.
   - Terdapat custom loss function (physics-informed) untuk regresi.
   - Hyperparameter tuning menggunakan `RandomizedSearchCV`.

4. **Evaluasi**
   - Evaluasi model menggunakan metrik: RMSE, MAE, MAPE, R2 (regresi) dan Accuracy, Precision, Recall, F1 (klasifikasi).
   - Visualisasi hasil prediksi vs aktual.

5. **Penyimpanan Model**
   - Model disimpan dalam format `.pkl` untuk deployment atau validasi lebih lanjut.

## Cara Menjalankan

1. **Persiapan Lingkungan**
   - Pastikan Python 3.x dan library berikut terinstall:
     - numpy, pandas, matplotlib, scikit-learn, xgboost, jcopml, joblib

2. **Urutan Eksekusi**
   - Jalankan notebook di folder [`preparasi data`](preparasi%20data) untuk menghasilkan data siap modeling.
   - Jalankan notebook modeling utama (`Model 1_Fix.ipynb`, `Model2-CLF_fix.ipynb`, `Model3-CO-FIC.ipynb`) untuk training dan evaluasi model.
   - Hasil model dan visualisasi akan tersimpan otomatis.

## File Penting

- [`Model1_fix.ipynb`](Model1_fix.ipynb): Notebook utama untuk modeling kondisi 1.
- [`Model2-CLF_fix.ipynb`](Model2-CLF_fix.ipynb): Notebook utama untuk modeling kondisi 2.
- [`Model3-CO-FIC.ipynb`](Model3-CO-FIC.ipynb): Notebook utama untuk modeling kondisi 3.
- [`preparasi data/Data_Preparation_afterremoveoutlier_Final.ipynb`](preparasi%20data/Data_Preparation_afterremoveoutlier_Final.ipynb): Notebook utama untuk persiapan data.
- [`Data_XGBoost.csv`](Data_XGBoost.csv): Dataset utama untuk training dan testing model.

## Catatan

- Pastikan format dan nama kolom pada data konsisten dengan script di notebook.
- Model menggunakan custom loss function yang menggabungkan pendekatan data-driven dan physics-based.
- Untuk validasi data baru, gunakan cell yang sudah disediakan di setiap notebook model.

---

**Penulis:**  
Tim Peneliti PV Microgrid Hybrid  
2024
