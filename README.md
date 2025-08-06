# 🚴‍♂️ Bike Sales Analysis (3 Store Branches)

## 📌 Objective
Menganalisis data penjualan sepeda dari 3 toko cabang untuk mendapatkan insight bisnis, seperti:
- Tren pendapatan dari waktu ke waktu
- Kinerja masing-masing toko
- Produk paling laris

## 🛠️ Tools & Technologies
- **SQL Server**: Query untuk ekstraksi dan filter data
- **Excel**: PivotTable, visualisasi, dan dashboard
- **Power BI**: Dashboard interaktif

## 📊 Dataset
Analisis ini menggunakan data yang berasal dari [SQL Server Tutorial – Sample Database](https://www.sqlservertutorial.net/getting-started/load-sample-database/). Dataset ini merupakan database BikeStores, yang berisi informasi terkait toko sepeda, produk, pelanggan, penjualan, dan pegawai.
Database ini terdiri dari beberapa tabel utama dengan struktur sebagai berikut:
- Total 9 tabel yang tersebar dalam dua skema: sales dan production.
- Tiap tabel memiliki jumlah kolom yang bervariasi, mulai dari 2 hingga 9 kolom.
- Proses analisis akan menggunakan query SQL untuk menampilkan kolom-kolom yang relevan.
- Total data yang digunakan untuk visualisasi berjumlah 4.722 baris.

Struktur relasi antar tabel dapat dilihat pada diagram ERD di bawah:
![](https://raw.githubusercontent.com/alzwork-buzz/BikeStoreSales_DA/main/ERD_Database.JPG)

## 🔍 Analysis
### 1. Data Preparation
Tahap awal dilakukan dengan menyusun query SQL untuk menggabungkan beberapa tabel yang relevan dalam database BikeStores, seperti sales.orders, sales.order_items, production.products, dan sales.customers. Tujuan dari query ini adalah untuk memilih kolom-kolom yang dibutuhkan guna membentuk dataset baru yang siap dianalisis dan divisualisasikan. Proses ini mencakup:
  - Melakukan JOIN antar tabel.
  - Memilih kolom-kolom penting seperti tanggal pemesanan, nama produk, nama toko, wilayah pelanggan, dan kolom lain yang mendukung analisis.

Berikut ini adalah query SQL yang digunakan:\
![](https://raw.githubusercontent.com/alzwork-buzz/BikeStoreSales_DA/main/QuerySQL.JPG)

Berikut ini output yang dihasilkan dari eksekusi query SQL:
![](https://raw.githubusercontent.com/alzwork-buzz/BikeStoreSales_DA/main/Output_SQL.JPG)

### 2. Exploratory Data Analysis (EDA)
Pada tahap EDA, dilakukan pemeriksaan terhadap data menggunakan Excel untuk mendeteksi apakah terdapat missing value dan duplicate. Namun, penggunaan Excel untuk keperluan ini sebenarnya kurang efisien. Sebagai alternatif, pemeriksaan missing value dapat dilakukan menggunakan SQL dengan menerapkan sintaks IS NULL, sedangkan untuk mendeteksi duplikat dapat digunakan perintah DISTINCT di SQL atau fitur Remove Duplicates di Excel.

Pemindahan data hasil query dari SQL ke Excel dapat dilakukan dengan memanfaatkan fitur Get Data pada Excel. Langkah ini melibatkan koneksi ke database lokal, kemudian memasukkan query SQL secara langsung melalui antarmuka yang disediakan.

berikut ini hasil dari pemindahan data hasil query SQL ke Excel:
![](https://raw.githubusercontent.com/alzwork-buzz/BikeStoreSales_DA/main/excel.JPG)

### 3. Data Visualization
#### 1. Excel
- Data divisualisasikan menggunakan **PivotTable** untuk menganalisis dan merangkum data.
- Kemudian, dibuat **PivotChart** untuk menampilkan visualisasi grafis dari hasil PivotTable.
- Dashboard interaktif dibuat dengan menambahkan fitur **Slicer** yang memungkinkan pengguna memilih filter berdasarkan waktu dan wilayah.
![](https://raw.githubusercontent.com/alzwork-buzz/BikeStoreSales_DA/main/dashboard%20excel.JPG)

#### 2. Power BI
- Data diimpor ke Power BI untuk analisis lebih lanjut.
- Visualisasi dibuat menggunakan berbagai jenis grafik seperti bar chart, line chart, dan peta (map visual).
- Dashboard interaktif dilengkapi dengan **Slicer** untuk filter dinamis berdasarkan dimensi waktu dan wilayah.

## 📎 Results
- Temuan penting
- Visualisasi atau ringkasan insight

## 📁 Files
- `notebook.ipynb` – kode Python
- `dashboard.png` – dashboard Power BI
- `queries.sql` – skrip SQL
