# DATA-ENGINEERING  
# Proyek ETL: Analisis Dampak Tingkat HDI dan GDP terhadap Kesehatan Mental

## Deskripsi Proyek  
Proyek ini bertujuan mengembangkan pipeline ETL untuk menganalisis korelasi antara Indeks Pembangunan Manusia (HDI), GDP, dan tingkat kesehatan mental masyarakat secara global. Data dikumpulkan dari berbagai sumber resmi, dibersihkan, dan disiapkan untuk dianalisis atau digunakan dalam model machine learning sebagai dasar pengambilan kebijakan berbasis data.

---

## Manfaat Data / Use Case  
- **Tujuan Proyek:** Menyediakan data terintegrasi mengenai kesejahteraan dan kesehatan mental berdasarkan indikator HDI dan GDP.  
- **Manfaat:**  
  - Mendukung visualisasi hubungan indikator demografi dan kesehatan mental.  
  - Menjadi dasar untuk model prediktif guna mengidentifikasi individu atau kelompok berisiko tinggi mengalami gangguan mental.  
  - Menyediakan insight dan rekomendasi intervensi berbasis data untuk pemerintah dan organisasi kesehatan.

---

## Serving Analisis  
Data hasil ETL disimpan dalam format CSV dan siap digunakan untuk analisis eksploratif serta visualisasi tren menggunakan tools seperti Tableau, Power BI, atau Python (Matplotlib/Seaborn).

## Serving Machine Learning  
Dataset yang telah dibersihkan dan distandardisasi digunakan untuk pelatihan model machine learning seperti klasifikasi risiko kesehatan mental berdasarkan variabel sosial ekonomi dan demografi.

---

## Extract (Pengambilan Data) – 15 Poin  
- **Sumber Data:**  
  - Mental Health – Kaggle  
    https://www.kaggle.com/datasets/imtkaggleteam/mental-health  
  - Suicide Rates – Kaggle  
    https://www.kaggle.com/datasets/omkargowda/suicide-rates-overview-1985-to-2021  
  - WHO Nutrition Data – WHO  
    https://ourworldindata.org/grapher/gdp-per-capita-worldbank?tab=table
  - Human Development Index – Our World in Data  
    https://ourworldindata.org/grapher/human-development-index?time=latest

- **Metode Pengambilan:**  
  - File CSV dari URL  
  - File ZIP dari Kaggle diunduh menggunakan `requests` lalu diekstrak menggunakan `zipfile`  
  - Pengambilan otomatis dari beberapa format dan encoding  

- **Penanganan Error:**  
  - Penanganan kesalahan encoding dan delimiter  
  - Logging menggunakan modul `logging` untuk pencatatan proses dan error

---

## Transform (Pembersihan & Transformasi) – 15 Poin  
- **Pembersihan:**  
  - Menghapus baris duplikat menggunakan `drop_duplicates()`  
  - Menghapus baris kosong menggunakan `dropna()`  
  - Logging jumlah baris sebelum dan sesudah transformasi  

- **Transformasi:**  
  - Menyimpan data mentah sebelum dan sesudah dibersihkan sebagai dokumentasi proses  
  - Standardisasi format dan kolom agar seragam sebelum penggabungan antar dataset

---

## Load (Pemindahan ke Target) – 15 Poin  
- **Target:**  
  - File CSV sebagai output utama yang siap dianalisis atau diproses lebih lanjut  

- **Metode:**  
  - Fungsi `save_to_csv()` digunakan untuk menyimpan hasil ke direktori lokal  
  - Data diverifikasi menggunakan `print(df.head())` setelah disimpan  

- **Integritas Data:**  
  - Validasi ukuran data dan isi kolom setelah transformasi  
  - Logging digunakan untuk memastikan proses load berjalan tanpa error

---

## Arsitektur / Workflow ETL – 15 Poin  
- **Alur Modular:**  
  - `source_data_from_csv()` – Membaca dari file lokal/URL  
  - `source_data_from_kaggle()` – Unduh dan ekstrak ZIP dari Kaggle  
  - `clean_data()` – Proses pembersihan data  
  - `save_to_csv()` – Menyimpan data hasil transformasi  

- **Tools yang Digunakan:**  
  - Python 3.x  
  - Library: `pandas`, `requests`, `zipfile`, `os`, `io`, `sqlite3`, `logging`  
  - Google Colab digunakan sebagai environment untuk pemrosesan dan eksperimen

---

## Kode Program – 10 Poin  
- **Struktur Kode:**  
  - Kode ditulis terpisah dan modular berdasarkan fungsi: ekstraksi, transformasi, penyimpanan, dan ML.  
  - Penamaan variabel dan fungsi deskriptif sesuai standar Python.  

- **Komentar dan Logging:**  
  - Kode diberi komentar yang cukup untuk menjelaskan alur  
  - Menghindari hardcoding path/file  

- **Referensi Notebook:**  
  - ETL Pipeline:  
    https://colab.research.google.com/drive/1fDnC6YKmCtZwOcNrFpUZdqOFloB20OaC?usp=sharing 
  - Machine Learning:  
    https://colab.research.google.com/drive/1KEcULm3MVCqHXBeLA8TonuOG-AoTcFL7?usp=sharing  

---

## Dokumentasi – 10 Poin  
- **Penjelasan Alur:**  
  Setiap tahapan (Extract, Transform, Load) dijelaskan dengan detail dalam kode dan README ini.  

- **Sumber Data:**  
  Seluruh sumber data bersifat publik dan dapat diverifikasi dari URL yang tersedia di atas.  

- **Libraries:**  
  - pandas  
  - requests  
  - scikit-learn  
  - matplotlib  
  - zipfile  
  - sqlite3 (opsional)  

---

## Presentasi / Demo – 15 Poin  
- Mahasiswa mempresentasikan alur ETL dan penggunaan data dalam model prediktif.  
- Penjelasan disampaikan dalam waktu maksimal 10 menit.  
- Semua pertanyaan teknis dijawab berdasarkan pemahaman terhadap pipeline dan data.  
- Proyek ini telah diunggah ke GitHub dengan deskripsi lengkap dan daftar kontributor.

---

## Kontributor

| Nama Lengkap                        | NIM         | Peran                |
|------------------------------------|-------------|----------------------|
| Balqis Amanda Putri Hambali        | 234311008   | Project Manager      |
| Cantikka May Aristianti            | 234311010   | Data Analyst         |
| Dionesyus Divo Crista Marvino      | 234311012   | Data Engineer        |
| Shaffa Dwiaji Feryansyah Putra     | 234311028   | Data Engineer        |
