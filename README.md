# DATA-ENGINEERING
# Proyek ETL: Analisis Dampak Tingkat HDI dan GDP terhadap Kesehatan Mental

## Deskripsi Proyek
Proyek ini bertujuan mengembangkan pipeline ETL untuk menganalisis korelasi antara indeks pembangunan manusia (HDI), GDP, dan tingkat kesehatan mental masyarakat secara global. Data diambil dari berbagai sumber resmi untuk diolah menjadi dataset bersih dan siap dianalisis atau digunakan sebagai dasar pengambilan kebijakan.

---

## Manfaat Data / Use Case
- **Tujuan Proyek:** Menyediakan data terintegrasi mengenai kesejahteraan dan kesehatan mental berdasarkan indikator HDI dan GDP.
- **Manfaat:**
  - Mendukung visualisasi hubungan demografis dan kesehatan mental.
  - Memberikan dasar bagi model prediktif untuk mengidentifikasi individu berisiko tinggi mengalami gangguan mental.
  - Menyediakan rekomendasi intervensi berbasis data untuk pemerintah dan organisasi kesehatan.

---

## Serving Analisis
Data hasil ETL disimpan dalam format CSV dan dapat divisualisasikan menggunakan tools seperti Tableau atau Power BI untuk mengevaluasi tren kesehatan mental di berbagai negara berdasarkan indeks pembangunan dan pendapatan.

## Serving Machine Learning
Data bersih yang dihasilkan disimpan dalam CSV dan siap digunakan untuk pelatihan model machine learning, misalnya klasifikasi risiko gangguan mental berdasarkan variabel demografi dan sosial ekonomi.

---

## Extract (Pengambilan Data) – 15 Poin
- **Sumber Data:**
  - Dataset *Mental Health* – Kaggle
  - Dataset *Suicide Rates* – Kaggle
  - WHO Nutrition Data – WHO (CSV URL)
  - Human Development Index – Our World in Data (CSV URL)
- **Metode:**
  - Unduh langsung dari URL (CSV)
  - Unduh file ZIP dari Kaggle → ekstraksi dan baca CSV pertama
- **Penanganan Error:**
  - Penanganan encoding dan delimiter secara dinamis
  - Logging dengan `logging` Python untuk pelacakan keberhasilan/gagal

---

## Transform (Pembersihan & Transformasi) – 15 Poin
- **Pembersihan:**
  - Menghapus baris duplikat (`drop_duplicates`)
  - Menghapus baris kosong (`dropna`)
  - Logging jumlah baris sebelum dan sesudah pembersihan
- **Transformasi:**
  - Menyimpan data mentah sebelum dan sesudah pembersihan untuk dokumentasi
  - Penyesuaian format data agar seragam dan siap digabung

---

## Load (Pemindahan ke Target) – 15 Poin
- **Target:**
  - CSV (digunakan sebagai format output utama)
- **Metode:**
  - Disimpan dengan fungsi `save_to_csv()` ke dalam file lokal
  - Verifikasi dengan `print(df.head())`
- **Integritas:**
  - Validasi hasil pembersihan dan pemantauan via logging

---

## Arsitektur / Workflow ETL – 15 Poin
- **Alur Modular:**
  - `source_data_from_csv()` – Baca dari URL atau lokal
  - `source_data_from_kaggle()` – Unduh dan ekstraksi ZIP dari Kaggle
  - `clean_data()` – Pembersihan null dan duplikat
  - `save_to_csv()` – Simpan hasil ke file
- **Tools yang Digunakan:**
  - Python 3.x
  - `pandas`, `requests`, `sqlite3`, `logging`, `zipfile`, `io`, `os`
  - Google Colab sebagai environment pemrosesan

---

## Kode Program – 10 Poin
- **Struktur Folder & File:**
