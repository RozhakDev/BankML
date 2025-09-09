# Proyek Analisis Perilaku Nasabah Bank

Ini adalah proyek submisi untuk kelas **Belajar Machine Learning untuk Pemula** dalam program **Asah by Dicoding (Studi Independen Bersertifikat Kampus Merdeka)**. Proyek ini berfokus pada analisis data transaksi perbankan untuk melakukan segmentasi nasabah (clustering) dan memprediksi segmen nasabah (klasifikasi) guna mendukung pengambilan keputusan bisnis yang lebih baik.

## Deskripsi Proyek

Dalam industri perbankan, memahami perilaku nasabah adalah kunci untuk menyediakan layanan yang relevan dan menjaga keamanan finansial. Proyek ini bertujuan untuk mengembangkan model machine learning yang dapat mengelompokkan nasabah ke dalam segmen-segmen tertentu berdasarkan aktivitas transaksi mereka. Selanjutnya, model klasifikasi dibangun untuk memprediksi segmen nasabah, yang dapat dimanfaatkan untuk strategi pemasaran tertarget, deteksi anomali, atau personalisasi layanan.

## Struktur Direktori

Proyek ini disusun dengan struktur direktori sebagai berikut untuk memudahkan navigasi dan pemeliharaan:

```text
.
├── data/
│   ├── bank_transactions_data.csv   # Dataset utama
│   └── ...
├── notebooks/
│   ├── [Clustering]_Submission_Akhir_BMLP_Rozhak.ipynb
│   └── [Klasifikasi]_Submission_Akhir_BMLP_Rozhak.ipynb
├── models/
│   ├── model_clustering.h5
│   └── tuning_classification.h5
├── LICENSE
└── README.md
```

## Dataset

Dataset yang digunakan adalah `bank_transactions_data.csv`, yang berisi catatan transaksi keuangan sintetis. Dataset ini mencakup berbagai atribut seperti demografi nasabah, detail aktivitas perbankan, dan pola perilaku digital. Karakteristik ini menjadikannya ideal untuk tugas analisis segmentasi dan prediksi dalam konteks layanan finansial.

## Metodologi

Proses analisis dibagi menjadi dua tugas utama: clustering dan klasifikasi.

### 1. Clustering (Segmentasi Nasabah)

Tujuan dari tahap ini adalah untuk mengelompokkan nasabah ke dalam beberapa segmen tanpa label yang ditentukan sebelumnya.

* **Pra-pemrosesan Data:** Data dibersihkan, nilai yang hilang ditangani, dan fitur-fitur yang relevan dipilih untuk pemodelan.
* **Pemilihan Algoritma:** Algoritma K-Means Clustering digunakan untuk mengidentifikasi kelompok-kelompok nasabah yang memiliki karakteristik serupa.
* **Evaluasi Model:** Elbow method digunakan untuk menentukan jumlah cluster optimal, dan hasil clustering dievaluasi menggunakan _Silhouette Score_.

Gambar: [_Visualisasi Cluster Pelanggan (Hasil PCA)_](assets/visualisasi_cluster_pelanggan_pca.png)

### 2. Klasifikasi (Prediksi Segmen Nasabah)

Setelah nasabah disegmentasi, label cluster dari tahap sebelumnya digunakan sebagai target untuk melatih model klasifikasi.

* **Persiapan Data:** Label hasil clustering ditambahkan ke dataset sebagai variabel target. Data kemudian dibagi menjadi set pelatihan dan pengujian.
* **Pemilihan Algoritma:** Beberapa algoritma dieksplorasi, termasuk Decision Tree dan Random Forest, untuk menemukan model dengan performa terbaik.
* **Evaluasi Model:** Performa model diukur menggunakan metrik standar seperti Akurasi, Presisi, Recall, dan F1-Score.

Gambar: [_Confusion Matrix dari model klasifikasi dengan performa terbaik._](assets/laporan_klasifikasi_rf_tuning.png)

### Instalasi & Penggunaan

Untuk menjalankan notebook dan mereplikasi hasil analisis, ikuti langkah-langkah berikut:

1. **Clone Repositori**
   
   ```bash
   git clone https://github.com/RozhakDev/BankML.git
   cd BankML
   ```

2. **Instal Dependensi**
    Pastikan Anda memiliki library Python yang diperlukan. Anda bisa menginstalnya menggunakan pip:
   
   ```bash
   pip install numpy pandas scikit-learn matplotlib seaborn jupyter
   ```

3. **Jalankan Jupyter Notebook**
    Buka dan jalankan file `.ipynb` di dalam direktori `notebooks/` untuk melihat proses analisis secara detail.
   
   ```bash
   jupyter notebook
   ```

## Lisensi

Proyek ini dilisensikan di bawah [MIT License](LICENSE).