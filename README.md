# Laporan Proyek Machine Learning

## **Domain Proyek**

Properti merupakan salah satu sektor yang berperan penting dalam pertumbuhan ekonomi Indonesia. Harga properti, khususnya rumah tinggal, mengalami fluktuasi yang dipengaruhi oleh banyak faktor seperti lokasi, luas tanah, luas bangunan, jumlah kamar tidur, jumlah kamar mandi, serta kondisi bangunan. Selain itu, akses terhadap fasilitas umum, pembangunan infrastruktur baru, dan kondisi sosial ekonomi suatu wilayah juga sangat menentukan nilai properti di pasaran.

Di wilayah urban seperti Jabodetabek, Surabaya, dan Bandung, harga properti terus menunjukkan tren kenaikan dalam beberapa tahun terakhir. Menurut laporan Indonesia Property Market Report 2023 oleh Rumah123.com, harga rumah tapak di beberapa kota besar mengalami pertumbuhan tahunan (year-on-year) sebesar 5–10% [1]. Peningkatan harga tersebut umumnya didorong oleh pembangunan infrastruktur seperti jalan tol, transportasi massal (MRT/LRT), serta perkembangan kawasan permukiman baru yang mendorong kenaikan permintaan.

Namun, pergerakan harga rumah yang tidak merata di setiap wilayah dan tingginya kompleksitas faktor yang mempengaruhinya membuat masyarakat dan investor kesulitan dalam memperkirakan nilai pasar suatu properti secara objektif. Kesalahan estimasi harga dapat menyebabkan keputusan pembelian yang merugikan atau kurang optimal, baik dari sisi konsumen maupun pengembang.

Dengan adanya teknologi machine learning dan ketersediaan data properti yang semakin luas, pendekatan prediktif berbasis data menjadi solusi yang menjanjikan. Model prediksi harga rumah dapat dilatih menggunakan fitur-fitur seperti luas bangunan (lb), luas tanah (lt), jumlah kamar tidur (kt), kamar mandi (km), dan kondisi rumah (misalnya, jumlah lantai dan status bangunan). Pendekatan ini telah digunakan dalam berbagai penelitian sebelumnya, seperti studi oleh Saputra dan Cahyani (2022), yang menerapkan regresi linier dan Random Forest untuk memprediksi harga rumah di Jakarta dengan tingkat akurasi yang cukup tinggi (RMSE di bawah 500 juta rupiah) [2].

Dengan membangun sistem prediksi harga properti menggunakan algoritma regresi seperti Linear Regression, Decision Tree, Random Forest, dan Gradient Boosting, proyek ini bertujuan untuk membantu pengguna (baik konsumen, agen properti, maupun pengembang) dalam memperkirakan nilai rumah secara lebih akurat dan efisien. Model ini diharapkan dapat memberikan insight yang berguna dalam proses pengambilan keputusan di sektor properti, sekaligus meningkatkan transparansi harga pasar.

---

### **Referensi**
[1] Rumah123.com. (2023). *Indonesia Property Market Report 2023: Tren Harga dan Permintaan Properti*. Retrieved from https://www.rumah123.com/berita/market-report-2023

[2] Saputra, R., & Cahyani, D. (2022). Prediksi Harga Rumah Menggunakan Algoritma Regresi pada Data Properti di Jakarta. *Jurnal Teknologi dan Informatika*, 8(1), 45–52.


---

## **Business Understanding**

Bagian ini menjelaskan proses identifikasi masalah dan tujuan proyek dalam konteks prediksi harga properti, yang berfokus pada analisis data rumah tinggal dan pengembangan model prediksi untuk mendukung pengambilan keputusan yang lebih tepat dan efisien dalam sektor properti.

---

### **Problem Statements**

1. Harga properti (rumah tinggal) sangat bervariasi tergantung pada berbagai faktor seperti lokasi, luas bangunan, jumlah kamar, dan kondisi bangunan, sehingga membuat calon pembeli dan penjual kesulitan dalam menentukan harga yang wajar.

2. Belum tersedia sistem berbasis data yang dapat membantu dalam memperkirakan harga rumah secara objektif, khususnya di pasar properti sekunder dan daerah dengan data terbatas.

3. Ketidakakuratan dalam penilaian harga rumah dapat menyebabkan kesalahan pengambilan keputusan dalam pembelian, penjualan, maupun investasi properti.

---

### **Goals**

1. Menganalisis faktor-faktor utama yang memengaruhi harga rumah berdasarkan data historis properti seperti luas bangunan, luas tanah, jumlah kamar tidur, kamar mandi, dan garasi.

2. Membangun model prediksi harga rumah berbasis regresi yang mampu memperkirakan harga properti dengan akurasi terukur.

3. Menyediakan sistem pendukung keputusan yang berbasis data untuk membantu konsumen, agen, dan pengembang dalam mengambil keputusan beli, jual, atau investasi properti.

---

### **Solution Statements**

1. Mengimplementasikan algoritma Regresi Linier sebagai baseline model untuk memprediksi harga rumah menggunakan fitur-fitur numerik seperti luas bangunan (lb), luas tanah (lt), jumlah kamar tidur (kt), jumlah kamar mandi (km), serta kondisi rumah (grs).

2. Melakukan evaluasi performa model dengan menggunakan metrik regresi berikut:

    - **Root Mean Squared Error (RMSE)**: untuk mengukur rata-rata deviasi prediksi dari nilai aktual,

    - **Mean Absolute Error (MAE)**: untuk mengetahui rata-rata kesalahan absolut,

    - **Mean Squared Error (MSE)**: untuk menghitung rata-rata kuadrat dari kesalahan prediksi, dan

   - **R-squared (R²)**: untuk mengukur proporsi variansi harga rumah yang dapat dijelaskan oleh fitur input.

3. Membandingkan hasil prediksi dari Regresi Linier dengan model lain seperti Decision Tree Regressor, Random Forest Regressor, dan Gradient Boosting Regressor untuk mengetahui model dengan performa terbaik berdasarkan data yang tersedia.

---
## **Data Understanding**
|   NO     | NAMA RUMAH |HARGA| LB | LT    | KT | KM | GRS | 
|--------|--------|--------|------------|------------|-------------|--------|---------|
|1 |    Rumah Murah Hook Tebet Timur, Tebet, Jakarta S...    | 3800000000      | 220 	 | 220 | 3 	 | 3 | 0  |
| 2 |    Rumah Modern di Tebet dekat Stasiun, Tebet, Ja...    | 4600000000 	| 180 	 | 137  | 4  | 3 	 | 2   | 
| 3 |   Rumah Mewah 2 Lantai Hanya 3 Menit Ke Tebet, T...     | 3000000000  | 267 	 | 250  | 4    | 4 	 | 4  | 
| 4 |   Rumah Baru Tebet, Tebet, Jakarta Selatan     | 430000000   | 40	 | 25   | 2  | 2 	 | 0      |
| 5 |    Rumah Bagus Tebet komp Gudang Peluru lt 350m, ...    | 9000000000 	     | 400 	 | 355 	| 6     | 5 	  | 3      |


Dataset yang digunakan dalam proyek ini berisi informasi harga rumah yang berlokasi di wilayah Tebet, Jakarta Selatan. Data ini diperoleh dari sumber terbuka melalui [Kaggle](https://www.kaggle.com/datasets/wisnuanggara/daftar-harga-rumah) data didapat dari web rumah123.com dan berfokus pada berbagai spesifikasi fisik properti serta harga jualnya. Dataset ini terdiri dari 1100 entri dan 8 kolom yang mencerminkan karakteristik rumah secara umum.

### **Struktur Dataset**

Dataset terdiri dari 8 kolom sebagai berikut

1. **NO**: Nomor urut data (integer), digunakan hanya sebagai indeks identifikasi.
2. **NAMA RUMAH**: Deskripsi atau judul listing properti (string), berisi informasi alamat dan fitur pemasaran rumah.
3. **HARGA**: Harga jual rumah (integer), dinyatakan dalam satuan Rupiah dan merupakan target prediksi dalam proyek ini.
4. **LB** (Luas Bangunan): Luas bangunan rumah dalam satuan meter persegi (integer).
5. **LT** (Luas Tanah): Luas total tanah tempat rumah berdiri, dalam meter persegi (integer).
6. **KT** (Kamar Tidur): Jumlah kamar tidur dalam properti (integer).
7. **KM** (Kamar Mandi): Jumlah kamar mandi dalam properti (integer).
8. **GRS** (Garasi): Jumlah mobil yang dapat ditampung dalam garasi rumah tersebut (integer).

### **Kondisi Data**

- **Jumlah Baris (Data)**: 1010 entri properti.
- **Jumlah Kolom**: 8 kolom
- **Jenis Data**: Kombinasi antara data numerik dan teks.
- **Data Kosong (Missing Values)**: 0(Tidak ditemukan nilai kosong pada seluruh kolom.).
- **Data Duplikat**: 0(Tidak ditemukan baris yang terduplikasi).
- **Outlier**: Ditemukan beberapa outlier pada kolom numerik seperti harga, lt, dan lb, yang tampak jauh lebih tinggi dibanding mayoritas data. Contoh outlier pada harga melebihi 20 miliar, sementara sebagian besar rumah berada di bawah 10 miliar. Penanganan outlier dilakukan pada tahap Data Preparation.

### **Target Prediksi**
Variabel **harga** menjadi target utama prediksi dalam proyek ini. Model akan belajar dari fitur properti rumah (seperti luas dan jumlah ruangan) untuk memprediksi harga jual rumah.

### **Variabel Penting**
Variabel yang dianggap paling penting untuk memprediksi harga rumah adalah:
- **lb (Luas Bangunan)**: Semakin besar bangunan, biasanya harga rumah semakin tinggi.
- **lt (Luas Tanah)**: Luas tanah juga memberikan kontribusi besar terhadap nilai total properti.
- **kt, km, grs**: Jumlah kamar tidur, kamar mandi, dan garasi turut memengaruhi kenyamanan dan nilai jual rumah.

### Eksplorasi Data dan Visualisasi
Eksplorasi data dilakukan untuk melihat dan memahami pola dan karakter dalam dataset harga rumah. Visualisasi berikut dapat memberi insight yang membantu proses analisis dan pemilihan fitur yang dapat digunakan:

* **Distribusi Harga Rumah**: Histogram harga menunjukkan distribusi data tidak simetris (right-skewed), dengan sebagian besar rumah berada pada harga menengah ke bawah, dan sedikit rumah dengan harga sangat tinggi.
* **Distribusi Luas Bangunan dan Tanah**: Histogram menunjukkan penyebaran luas bangunan dan tanah cenderung normal, tetapi dengan beberapa nilai tinggi yang signifikan.
* **Distribusi Jumlah Kamar dan Garasi**: Sebagian besar rumah memiliki 2–4 kamar tidur dan 1–2 kamar mandi, dengan mayoritas memiliki 1 garasi.
* **Boxplot Harga Berdasarkan Fitur Kategori**: Boxplot antara harga dan jumlah kamar/garasi menunjukkan bahwa rata-rata harga rumah meningkat seiring bertambahnya jumlah kamar tidur, kamar mandi, atau garasi.
* **Scatter Plot Harga terhadap Luas**: Terdapat korelasi positif yang jelas antara harga rumah dengan luas bangunan dan luas tanah.
* **Matriks Korelasi**: Korelasi tertinggi ditemukan antara harga dan luas bangunan, diikuti oleh luas tanah. Fitur-fitur lain seperti jumlah kamar dan garasi juga menunjukkan korelasi positif meskipun tidak sekuat dua fitur utama.

---

## **Data Preparation**

Pada tahap ini, dilakukan serangkaian langkah untuk mempersiapkan data agar dapat digunakan secara optimal oleh model machine learning. Tujuan utama dari tahap ini adalah memastikan data bersih, relevan, dan dalam format yang sesuai. Berikut adalah langkah-langkah yang diambil dalam proses persiapan data:

### **1. Memuat Dataset**

* Dataset awal berisi 8 kolom dan 1010 baris data.

    ```
    url = "https://raw.githubusercontent.com/Meio047/Predictive-Analytics/refs/heads/main/data_rumah.csv"
    df = pd.read_csv(url)
    ```

### **2. Mengubah nama kolom**

* Mengubah nama kolom dari huruf kapital menjadi huruf kecil agar lebih mudah diproses pada tahap selanjutnya.

    ```
    df = df.rename(columns={
        'NO': 'nomor',
        'NAMA RUMAH': 'nama_rumah',
        'HARGA': 'harga',
        'LB': 'lb',
         'LT': 'lt',
        'KT': 'kt',
        'KM': 'km',
        'GRS': 'grs'
    })
    df.head()
    ```

### **3. Pemeriksaan dan Penyesuaian Tipe Data**
- Beberapa kolom seperti HARGA, LB, LT, KT, KM, dan GRS dipastikan bertipe numerik (integer).
- Kolom NAMA RUMAH adalah deskriptif dan tidak digunakan dalam proses pelatihan model.

### **4. Pengecekan dan Penanganan Missing Values**
- Dataset ini tidak mengandung nilai kosong (missing values), sehingga tidak diperlukan imputasi atau penghapusan baris.

### **5. Deteksi dan Penghapusan Outlier**
- Outlier pada kolom **harga** diidentifikasi dan dihapus menggunakan metode **Interquartile Range (IQR)**. Langkah ini penting untuk mencegah model belajar dari data ekstrem yang dapat mengganggu hasil prediksi.
  ```python
  Q1 = df['harga'].quantile(0.25)
  Q3 = df['harga'].quantile(0.75)
  IQR = Q3 - Q1
  df = df[~((df['harga'] < (Q1 - 1.5 * IQR)) | (df['harga'] > (Q3 + 1.5 * IQR)))]
  ```

### **6. Penghapusan Kolom yang Tidak Relevan**


- Kolom NO dan NAMA RUMAH tidak memberikan kontribusi prediktif terhadap harga rumah, sehingga dihapus.

  ```python
  df = df.drop(columns=['NO', 'NAMA RUMAH'])
  ```


### **7. Mengubah satuan harga**
- Kolom harga diubah satuannya dengan satuan awal yaitu rupiah diubah menjadi juta rupiah
  ```python
  df['harga'] = (df['harga']/1000000).astype(int)
  ```
### **8. Menambahkan fitur baru `tingkat_harga`**
- Fitur tingkat_harga ditambahkan untuk mengelompokkan rumah ke dalam tiga kategori berdasarkan harga, yaitu Murah, Menengah, dan Mahal. Kategori ini dibuat untuk memudahkan analisis distribusi harga rumah dan visualisasi jumlah rumah dalam tiap kelompok harga.Fitur ini bersifat kategorikal dan digunakan sebagai pendukung eksplorasi data
-
  ```python
  q1 = df['harga'].quantile(0.25)
  median = df['harga'].median()
  q3 = df['harga'].quantile(0.75)
  def classification_harga(harga):
    if harga <= q1:
        return 'Murah'
    elif harga <= median:
        return 'Menengah'
    else:
        return 'Mahal'

  # Menambahkan kolom baru
  df['tingkat_harga'] = df['harga'].apply(classification_harga)

  df.head()
  ```


### **9. Pemisahan Fitur dan Target**
- Kolom HARGA dijadikan sebagai **target (y)** untuk diprediksi, sementara kolom LB, LT, KT, KM, dan GRS dijadikan sebagai **fitur (X)**.

  ```python
  X = df[['lb', 'lt', 'kt', 'km', 'grs']]
  y = df['harga']
  ```

### **10. Pembagian Data**
- Data dibagi menjadi data training (80%) dan data testing (20%) menggunakan fungsi train_test_split.

  ```python
  X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
  ```

  Hasil pembagian data (setelah penghapusan outlier):
  - **Total datasets:** 916
  - **Data Latih (Training):** ~80% dari total (732)
  - **Data Uji (Testing):** ~20% dari total (184)

### **11. Normalisasi Data**
- Karena fitur numerik memiliki skala berbeda-beda (misalnya LB dan LT jauh lebih besar dari KT atau KM), dilakukan normalisasi menggunakan MinMaxScaler untuk skala [0, 1].

  ```python
  scaler = MinMaxScaler()
  scaler.fit(X_train)
  X_train_scaled = scaler.transform(X_train)
  X_test_scaled = scaler.transform(X_test)
  ```

## **Model Development**

Dalam proyek ini, digunakan tiga algoritma regresi populer untuk memprediksi harga rumah berdasarkan fitur-fitur properti seperti luas bangunan, luas tanah, jumlah kamar tidur, kamar mandi, dan garasi. Model-model yang digunakan meliputi:

### Linear Regression
Linear Regression digunakan sebagai baseline model karena sederhana dan mudah untuk diinterpretasikan. Model ini mengasumsikan hubungan linier antara fitur input dan target (HARGA). Linear Regression merupakan algoritma supervised learning yang digunakan untuk memprediksi nilai numerik dengan cara membangun persamaan linear antara variabel independen (fitur) dan variabel dependen (target). Algoritma ini mencari garis terbaik (best fit line) yang meminimalkan selisih kuadrat antara nilai prediksi dan nilai aktual (menggunakan metode Ordinary Least Squares). Persamaan umumnya berbentuk:

``y = β₀ + β₁x₁ + β₂x₂ + ... + βₙxₙ + ε``

di mana:

    y = variabel target (harga rumah),
    x₁ ... xₙ = fitur,
    β₀ = intercept,
    β₁ ... βₙ = koefisien regresi,
    ε = error/residual.

Parameter yang digunakan:
- fit_intercept=True (default): menghitung intercept (
- copy_X=True (default): membuat salinan data 
- n_jobs=None: menggunakan 1 core (
- Catatan: Data fitur telah diskalakan (X_train_scaled, X_test_scaled) sebelum diterapkan ke model ini.


**Kelebihan:**
- Interpretasi koefisien sederhana
- Cepat dilatih dan digunakan

**Kekurangan:**
- Tidak cocok jika hubungan antara fitur dan target bersifat non-linier

---

### Decision Tree Regressor
Model Decision Tree digunakan untuk menangkap hubungan non-linear antar fitur. Model ini disetel dengan parameter max_depth=5 untuk mencegah overfitting. Decision Tree adalah algoritma yang bekerja dengan cara membagi data ke dalam segmen berdasarkan fitur tertentu yang menghasilkan impurity terkecil (dalam regresi biasanya menggunakan kriteria mean squared error). Proses ini dilakukan secara rekursif hingga mencapai kedalaman tertentu atau kondisi minimum split lainnya. Hasil akhir berupa struktur pohon keputusan, di mana setiap daun berisi nilai prediksi (rata-rata dari target di subset tersebut).

Parameter yang digunakan:
- max_depth=5: membatasi kedalaman pohon agar tidak overfitting.
- random_state=None: menggunakan default untuk hasil tidak deterministik.
- Data tidak diskalakan karena pohon tidak sensitif terhadap skala fitur.

**Kelebihan:**
- Dapat menangani hubungan non-linear
- Tidak memerlukan normalisasi data

**Kekurangan:**
- Rentan overfitting pada data latih jika tidak diatur kedalamannya

---

### Random Forest Regressor
Random Forest digunakan untuk meningkatkan akurasi prediksi dan mengurangi variansi model Decision Tree. Model ini dibangun dari banyak pohon keputusan dan disetel dengan n_estimators=100 dan max_depth=7. Random Forest adalah algoritma ensemble learning yang menggabungkan beberapa Decision Tree untuk meningkatkan performa dan mengurangi overfitting. Model membentuk banyak pohon dengan bootstrapped dataset dan subset acak dari fitur (bagging). Prediksi akhir diperoleh dari rata-rata hasil prediksi seluruh pohon.

Parameter yang digunakan:
- n_estimators=100: jumlah pohon dalam hutan.
- max_depth=7: batas kedalaman tiap pohon.
- random_state=None: menggunakan default.

**Kelebihan:**
- Lebih stabil dan akurat dibanding satu pohon
- Lebih tahan terhadap overfitting

**Kekurangan:**
- Waktu pelatihan dan prediksi lebih lama
- Lebih sulit diinterpretasikan

### Gradient Boosting Regressor
Gradient Boosting digunakan untuk memaksimalkan akurasi prediksi dengan membangun model secara bertahap, di mana setiap pohon baru mencoba memperbaiki kesalahan dari pohon sebelumnya. Model ini sangat efektif dalam menangani hubungan kompleks antar fitur. Dalam proyek ini, digunakan dengan parameter default dan tanpa normalisasi. Gradient Boosting adalah teknik boosting yang membangun model secara bertahap. Setiap model baru dilatih untuk meminimalkan kesalahan residu dari model sebelumnya dengan menggunakan metode gradient descent terhadap loss function (biasanya MSE untuk regresi). Model akhir merupakan gabungan dari semua model yang sudah dibangun, dengan bobot tertentu.

Parameter yang digunakan:
- n_estimators=100 (default): jumlah boosting stages.
- learning_rate=0.1 (default): besarnya langkah 
- max_depth=3 (default): kedalaman maksimum pohon 
- random_state=None: hasil tidak 
- Data tidak diskalakan karena tree-based model.

**Kelebihan:**
- Mampu menangkap hubungan non-linear yang kompleks
- Cenderung memberikan performa prediksi tinggi
- Lebih presisi dibandingkan model individual seperti Decision Tree

**Kekurangan:**
- Waktu pelatihan lebih lama dibandingkan model lain
- Rentan terhadap overfitting jika tidak disetel dengan benar

---

Model terbaik dipilih berdasarkan performa pada metrik evaluasi, seperti dijelaskan di bawah.

---

## **Evaluation (Evaluasi Model)**

### **1. Metrik Evaluasi dan Penjelasannya**
Untuk mengukur keandalan model prediksi harga rumah, digunakan beberapa metrik evaluasi regresi untuk memprediksi nilai harga, yaitu:

* **Mean Absolute Error (MAE)**
  MAE mengukur rata-rata selisih absolut antara nilai aktual dan nilai yang diprediksi.
  **Rumus:**

      MAE = (1/n) * Σ |yᵢ - ŷᵢ|

  MAE memberikan gambaran mengenai kesalahan dalam satuan harga. Metrik ini cocok untuk konteks atau bidang bisnis karena interpretasinya yang intuitif atau rata-rata seberapa meleset prediksi dari kenyataan

* **Mean Squared Error (MSE)**
  MSE menghitung rata-rata dari kuadrat selisih antara nilai aktual dan prediksi.
  **Rumus:**

      MSE = (1/n) * Σ (yᵢ - ŷᵢ)²

  MSE menekankan kesalahan besar, sehingga berguna untuk menghindari model dengan prediksi ekstrem.

* **Root Mean Squared Error (RMSE)**
  RMSE adalah akar kuadrat dari MSE, yang menjadikannya berada dalam satuan yang sama dengan target.
  **Rumus:**

      RMSE = √MSE

  Dalam konteks ini, RMSE menunjukkan secara langsung seberapa jauh, dalam satuan juta rupiah, prediksi menyimpang dari nilai aktual.

* **R-squared (R² Score)**
  R² mengukur proporsi variabilitas dalam target yang bisa dijelaskan oleh model.
  **Rumus:**

      R² = 1 - (Σ (yᵢ - ŷᵢ)² / Σ (yᵢ - ȳ)²)

  Nilai R² mendekati 1 menandakan bahwa model menjelaskan hampir seluruh variasi dalam data, yang sangat penting untuk prediksi harga yang akurat.

---

### **2. Hasil Evaluasi Model**

Berikut adalah perbandingan hasil ketiga model:
**Catatan: Seluruh nilai MSE dan RMSE ditulis dalam jutaan rupiah (Rp juta).**

| Model             | MAE        | MSE           | RMSE       | R²         |
| ----------------- | ---------- | ------------- | ---------- | ---------- |
| Linear Regression | 1291.123620   | 4.500612e+06    | 2121.464566     | 0.591316     |
| Decision Tree     | 1030.987640    | 2.764451e+06    | 1662.663789     | 0.748970     |
| Random Forest     | **964.934583** | **2.347286e+06** | **1532.085463** | **0.786852** |
| Gradient Boosting   | 993.817080 | 2.392081e+06 | 1546.635427 | 0.782784 |


### **Analisis Hasil**

Dari hasil evaluasi terhadap empat model regresi untuk prediksi harga rumah, Random Forest Regressor menunjukkan performa terbaik berdasarkan keseluruhan metrik evaluasi:

  * **MAE** sekitar **Rp953 juta**, yang berarti rata-rata kesalahan prediksi harga rumah mendekati angka tersebut.
  * **RMSE** sebesar **Rp1,52 miliar**, menunjukkan bahwa sebagian besar kesalahan prediksi masih dalam kisaran wajar untuk data harga rumah skala miliaran.
  * **R² = 0.789**, artinya sekitar **78,9%** variabilitas harga rumah berhasil dijelaskan oleh model, yang menandakan model ini memiliki performa prediksi yang baik.

Jika dibandingkan dengan baseline Linear Regression, Random Forest jauh lebih unggul. Linear Regression hanya menjelaskan 59,1% variabilitas data (R² = 0.591) dan memiliki MAE di atas Rp1,29 miliar, yang berarti kesalahan prediksinya jauh lebih besar secara konsisten.

Decision Tree dan Gradient Boosting memberikan hasil yang kompetitif, namun Random Forest tetap unggul di seluruh metrik evaluasi, baik dari sisi akurasi (MAE/RMSE) maupun daya jelaskan model (R²).

Secara keseluruhan, Random Forest Regressor merupakan model paling efektif untuk kasus prediksi harga rumah ini, dengan akurasi tinggi dan kesalahan yang paling kecil di antara semua model yang diuji.

---


### **3. Keterkaitan dengan Business Understanding**

#### **Apakah sudah menjawab Problem Statements?**

* **Problem 1:** Harga properti (rumah tinggal) sangat bervariasi tergantung pada berbagai faktor seperti lokasi, luas bangunan, jumlah kamar, dan kondisi bangunan, sehingga membuat calon pembeli dan penjual kesulitan dalam menentukan harga yang wajar.
   *Model prediksi harga rumah yang dikembangkan dalam proyek ini memberikan estimasi harga yang lebih akurat dan objektif, membantu pembeli dan penjual dalam mengambil keputusan yang lebih tepat dalam transaksi properti.*

* **Problem 2:** Belum tersedia sistem berbasis data yang dapat membantu dalam memperkirakan harga rumah secara objektif, khususnya di pasar properti sekunder dan daerah dengan data terbatas.
    *Dengan membangun model regresi menggunakan algoritma Random Forest, kini tersedia sistem estimasi harga rumah berbasis data historis yang relevan dengan kondisi lokal, khususnya wilayah Tebet.*

* **Problem 3:** Ketidakakuratan dalam penilaian harga rumah dapat menyebabkan kesalahan pengambilan keputusan dalam pembelian, penjualan, maupun investasi properti.
    *Model prediksi yang telah dievaluasi dan menunjukkan performa baik dapat menjadi alat bantu pengambilan keputusan yang lebih andal, mengurangi risiko kesalahan estimasi harga dalam proses transaksi.*

#### **Apakah sudah mencapai Goals?**

* **Goal 1:** Menganalisis faktor-faktor utama yang memengaruhi harga rumah berdasarkan data historis properti seperti luas bangunan, luas tanah, jumlah kamar tidur, kamar mandi, dan garasi.
    Melalui eksplorasi dan analisis data, diperoleh insight bahwa fitur seperti luas bangunan (LB), luas tanah (LT), jumlah kamar tidur (KT), kamar mandi (KM), dan jumlah garasi (GRS) memiliki kontribusi signifikan terhadap harga rumah.

* **Goal 2:** Membangun model prediksi harga rumah berbasis regresi yang mampu memperkirakan harga properti dengan akurasi terukur.
     Model Random Forest Regressor menghasilkan MAE sekitar Rp964 juta, dan RMSE sekitar Rp1,53 miliar (1.532 juta), dengan R² sebesar 0.786, yang menandakan bahwa model ini mampu menjelaskan sekitar 78,6% variabilitas harga rumah di data.

* **Goal 3:**     Menyediakan sistem pendukung keputusan yang berbasis data untuk membantu konsumen, agen, dan pengembang dalam mengambil keputusan beli, jual, atau investasi properti.
     Model yang dibangun dapat diintegrasikan ke dalam sistem estimasi harga rumah untuk mendukung proses pengambilan keputusan berbagai pihak yang terlibat dalam industri properti.

#### **Apakah solusi yang dirancang berdampak?**

Solusi ini tidak hanya memberikan baseline dengan regresi linear, tetapi juga membandingkan performa dengan model lain (Decision Tree dan Gradient Boosting). Random Forest menghasilkan prediksi terbaik, dan dapat digunakan sebagai alat bantu keputusan harga yang berdampak nyata bagi pelaku bisnis properti di Tebet

---

### **Kesimpulan Evaluasi**

Model Random Forest Regressor memberikan prediksi harga rumah yang unggul dibanding model lainnya. Dengan nilai R² sebesar 0.789 dan kesalahan prediksi rata-rata (MAE) sekitar Rp953 juta, model ini terbukti mampu menangkap pola harga secara akurat dan konsisten.

Seluruh aspek dari problem statement, goals, hingga implementasi solusi telah dipenuhi secara menyeluruh. Proyek ini berhasil secara teknis dan relevan secara praktis untuk mendukung keputusan strategis dalam pasar properti, khususnya di wilayah Tebet, Jakarta Selatan.
