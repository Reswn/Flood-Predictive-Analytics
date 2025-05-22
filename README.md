
# Laporan Proyek Machine Learning -  RENI KARTIKA SUWANDI
# Flood Predictive Analytics
![Contoh Gambar](https://github.com/Reswn/Flood-Predictive-Analytics/blob/master/src/banjir.jpeg?raw=true)

## Domain Proyek
Banjir merupakan salah satu bencana alam paling merusak yang secara global menyebabkan kerugian ekonomi besar, kerusakan lingkungan, dan risiko terhadap keselamatan manusia. Menurut World Meteorological Organization (2021), banjir menyumbang lebih dari 40% kejadian bencana hidrometeorologi di seluruh dunia. Dengan meningkatnya urbanisasi, perubahan iklim, dan kerusakan ekosistem, risiko banjir menjadi semakin sulit diprediksi dengan cara konvensional.

Proyek ini bertujuan membangun model prediktif menggunakan teknik machine learning berbasis dataset historis, untuk memprediksi tingkat probabilitas banjir berdasarkan kombinasi fitur lingkungan, sosial, dan infrastruktur.

**Referensi:**
World (2021). 2021 State of Climate Services. [online] Wmo.int. Available at: https://library.wmo.int/records/item/57630-2021-state-of-climate-services [Accessed 21 May 2025].

___
## **Business Understanding**
___
Dalam era modern yang ditandai dengan urbanisasi cepat dan perubahan iklim ekstrem, banjir menjadi salah satu bencana alam yang paling merugikan. Tidak hanya mengakibatkan kerusakan infrastruktur, banjir juga berdampak pada sektor pertanian, ekonomi lokal, serta mengancam keselamatan penduduk. Oleh karena itu, pengembangan sistem prediktif berbasis machine learning untuk mengidentifikasi potensi banjir sangatlah penting, khususnya dalam mendukung pengambilan keputusan oleh otoritas kebencanaan, perencana wilayah, dan pemerintah daerah.

Dengan memanfaatkan berbagai indikator seperti intensitas curah hujan, pengelolaan sungai, kerusakan ekosistem, dan faktor tata kota, proyek ini bertujuan membangun model klasifikasi yang dapat memprediksi apakah suatu wilayah memiliki probabilitas tinggi mengalami banjir. Model ini diharapkan mampu mempercepat respons mitigasi dan meningkatkan efektivitas sistem peringatan dini banjir.

### **Problem Statement**
Beberapa masalah utama yang ingin dijawab dalam proyek ini antara lain:

- Bagaimana membangun model machine learning yang dapat mengklasifikasikan risiko banjir berdasarkan faktor lingkungan dan infrastruktur?

- Algoritma klasifikasi apa yang paling optimal dalam memberikan prediksi akurat terhadap risiko banjir?

- Bagaimana hasil prediksi dari model ini dapat digunakan untuk mendukung pengambilan keputusan oleh stakeholder seperti pemerintah, badan penanggulangan bencana, dan masyarakat?

### **Goals**
Tujuan dari proyek prediksi banjir ini meliputi:

- Merancang sistem klasifikasi berbasis machine learning yang mampu memprediksi tingkat risiko banjir dari data.

- Melakukan evaluasi terhadap beberapa algoritma klasifikasi untuk menentukan metode paling akurat dalam kasus ini.

- Menyediakan rekomendasi berbasis data yang dapat dimanfaatkan oleh pengambil kebijakan dalam merancang langkah preventif dan perencanaan tata kota.

### **Solution Statement**
Untuk mencapai tujuan di atas, beberapa solusi teknis dan pendekatan analitik yang dilakukan antara lain:

- Eksplorasi Data
Melakukan eksplorasi data menyeluruh (univariate dan multivariate analysis), visualisasi hubungan antar variabel, dan pemeriksaan korelasi antar fitur serta target (FloodProbability).

- Pra-pemrosesan Data
Menerapkan teknik normalisasi untuk fitur numerik, menghindari data leakage, dan menghapus fitur redundan.

- Eksperimen Model
Mengembangkan dan membandingkan performa dari beberapa algoritma klasifikasi populer, yaitu:

- 1) Decision Tree Classifier: Struktur pohon keputusan yang memecah data berdasarkan fitur penting untuk klasifikasi risiko banjir.

- 2) Random Forest Classifier: Ensembel dari banyak decision tree yang dikombinasikan untuk meningkatkan stabilitas dan akurasi.

- 3) Support Vector Machine (SVM): Algoritma yang menemukan hyperplane optimal untuk membedakan antara wilayah dengan dan tanpa risiko banjir.

- Evaluasi Model
Setiap model dievaluasi menggunakan metrik Accuracy dan Area Under Curve (AUC), untuk menilai kemampuan klasifikasi dan keakuratan prediksi.

- Pemilihan Model Terbaik
Model dengan kombinasi akurasi tertinggi dan AUC mendekati 1 dipilih sebagai solusi terbaik untuk kasus ini, dan akan direkomendasikan untuk implementasi praktis dalam sistem deteksi banjir.


___
## **Data Understanding**

### **Informasi Dataset**

| **Informasi**           | **Detail**                                                                 |
|------------------------|-----------------------------------------------------------------------------|
| **Nama Dataset**        | Flood Prediction Dataset                                                   |
| **Pembuat**             | Naiya Khalid                                                               |
| **Platform**            | [Kaggle](https://www.kaggle.com/datasets/naiyakhalid/flood-prediction-dataset) |
| **Tahun Pembuatan**     | Sekitar 2024 *(berdasarkan waktu unggahan terakhir)*                       |
| **Deskripsi Asal Data** | Tidak disebutkan secara eksplisit                                          |
| **Sumber Data**         | Tidak dijelaskan                                                           |
| **Lisensi**             | Tidak tercantum secara jelas di halaman dataset                            |
| **Fitur Dataset**       | 22 fitur input + 1 label target (`FloodProbability`)                       |
| **Tujuan Dataset**      | Prediksi kemungkinan banjir berdasarkan faktor-faktor lingkungan dan sosial|


## EDA (Exploratory Data Analysis)

### 5 Baris Pertama Dataset

Berikut merupakan tampilan lima baris pertama dari dataset *Flood Prediction* yang digunakan dalam proyek ini:

| MonsoonIntensity | TopographyDrainage | RiverManagement | Deforestation | Urbanization | ClimateChange | DamsQuality | Siltation | AgriculturalPractices | Encroachments | DrainageSystems | CoastalVulnerability | Landslides | Watersheds | DeterioratingInfrastructure | PopulationScore | WetlandLoss | InadequatePlanning | PoliticalFactors | FloodProbability |
|------------------|--------------------|------------------|----------------|---------------|----------------|--------------|-----------|------------------------|----------------|------------------|------------------------|------------|-------------|-----------------------------|------------------|--------------|---------------------|-------------------|-------------------|
| 3                | 8                  | 6                | 6              | 4             | 4              | 6            | 2         | 3                      | 2              | 10               | 7                      | 4          | 2           | 3                           | 4                | 3            | 2                   | 6                 | 0.450             |
| 8                | 4                  | 5                | 7              | 7             | 9              | 1            | 5         | 5                      | 4              | 9                | 2                      | 6          | 2           | 1                           | 1                | 9            | 1                   | 3                 | 0.475             |
| 3                | 10                 | 4                | 1              | 7             | 5              | 4            | 7         | 4                      | 9              | 7                | 4                      | 4          | 8           | 6                           | 1                | 8            | 3                   | 6                 | 0.515             |
| 4                | 4                  | 2                | 7              | 3             | 4              | 1            | 4         | 6                      | 4              | 4                | 2                      | 6          | 6           | 8                           | 8                | 6            | 6                   | 10                | 0.520             |
| 3                | 7                  | 5                | 2              | 5             | 8              | 5            | 2         | 7                      | 5              | 7                | 6                      | 5          | 3           | 3                           | 4                | 4            | 3                   | 4                 | 0.475             |

> Catatan: Setiap baris merepresentasikan kondisi lingkungan dan sosial pada satu titik observasi, dengan `FloodProbability` sebagai target variabel berupa nilai kontinu antara 0 hingga 1 yang menunjukkan tingkat risiko banjir.


### Variabel Dataset Flood Prediction

Dataset ini berisi berbagai fitur yang merepresentasikan kondisi lingkungan, sosial, dan infrastruktur yang memengaruhi kemungkinan terjadinya banjir. Berikut adalah deskripsi masing-masing variabel:

| **Nama Variabel**              | **Deskripsi** |
|-------------------------------|---------------|
| `MonsoonIntensity`            | Tingkat intensitas hujan musiman di suatu wilayah. Nilai yang lebih tinggi menunjukkan curah hujan yang lebih deras dan berkelanjutan. |
| `TopographyDrainage`          | Efektivitas sistem drainase alami berdasarkan kontur dan topografi wilayah. Semakin tinggi nilainya, semakin baik sistem drainase alami. |
| `RiverManagement`             | Kualitas dan efektivitas pengelolaan sungai, termasuk tanggul, pengerukan, dan pengendalian aliran. |
| `Deforestation`               | Skor yang merepresentasikan tingkat deforestasi (penggundulan hutan) di wilayah tersebut. Deforestasi yang tinggi meningkatkan risiko banjir. |
| `Urbanization`                | Tingkat urbanisasi atau pembangunan wilayah yang mengurangi area resapan air. |
| `ClimateChange`               | Indikator dampak perubahan iklim terhadap curah hujan dan pola cuaca ekstrem di wilayah tersebut. |
| `DamsQuality`                 | Kualitas struktur dan pemeliharaan bendungan di area terkait. Bendungan yang buruk bisa memicu banjir. |
| `Siltation`                   | Tingkat pengendapan lumpur di sungai, waduk, atau saluran air yang dapat menghambat aliran air. |
| `AgriculturalPractices`       | Dampak dari aktivitas pertanian terhadap lingkungan, terutama terkait penggunaan air dan degradasi tanah. |
| `Encroachments`               | Tingkat perambahan manusia terhadap lahan konservasi, bantaran sungai, atau area rawan banjir lainnya. |
| `DrainageSystems`             | Efektivitas sistem drainase buatan, seperti selokan dan kanal. Nilai lebih tinggi menunjukkan sistem yang lebih efisien. |
| `CoastalVulnerability`        | Kerentanan wilayah terhadap banjir akibat naiknya permukaan laut atau badai pesisir. |
| `Landslides`                  | Risiko atau sejarah kejadian tanah longsor yang dapat memperburuk dampak banjir. |
| `Watersheds`                  | Kualitas dan kapasitas daerah aliran sungai (DAS) dalam menampung dan mengalirkan air hujan. |
| `DeterioratingInfrastructure`| Tingkat kerusakan atau penurunan kualitas infrastruktur publik, seperti jalan, jembatan, atau bendungan. |
| `PopulationScore`             | Kepadatan atau tekanan penduduk yang dapat memengaruhi pengelolaan sumber daya air dan sistem peringatan dini. |
| `WetlandLoss`                 | Hilangnya lahan basah yang berfungsi sebagai daerah penyerapan air alami. Kehilangan ini meningkatkan potensi banjir. |
| `InadequatePlanning`          | Skor yang menunjukkan seberapa buruk perencanaan tata ruang dan pembangunan wilayah. |
| `PoliticalFactors`            | Stabilitas kebijakan dan komitmen pemerintah terhadap pengelolaan risiko bencana. |
| `FloodProbability`            | Target variabel berupa probabilitas (0–1) terjadinya banjir di wilayah tersebut. Semakin tinggi nilainya, semakin besar kemungkinan banjir terjadi. |

> Catatan: Seluruh variabel input dinyatakan dalam bentuk skor (misalnya 1–10), yang merepresentasikan tingkat pengaruh atau keparahan dari masing-masing faktor.

### Ringkasan Informasi Dataset

Dataset prediksi banjir ini terdiri dari **50.000 baris data** dengan struktur sebagai berikut:

- **Jumlah Fitur**: 20 fitur independen bertipe `int64`, mewakili skor kondisi lingkungan, sosial, dan infrastruktur. Seluruh fitur bersifat diskret dan umumnya berada dalam skala ordinal (nilai 1–10).
- **Target Variabel**:
  - `FloodProbability` → tipe `float64`, nilai kontinu antara 0–1, digunakan untuk prediksi regresi.
  - `FloodLabel` → nilai biner (0 atau 1), hasil binarisasi dari `FloodProbability`, digunakan dalam klasifikasi.

### Ciri Statistik dan Distribusi Data:
- Semua kolom lengkap (tidak ada missing values) dan tidak mengandung duplikat.
- Distribusi fitur cenderung **simetris**, dengan nilai rata-rata mendekati median (mean ≈ median).
- Terdapat **potensi outlier** di beberapa fitur karena nilai maksimum melebihi Q3 secara signifikan.
- Penyebaran nilai fitur sebagian besar berada di rentang **3–6**, menunjukkan konsentrasi data di tengah.
- Distribusi `FloodProbability` cukup sempit dan menyerupai kurva normal (Gaussian-like).

### Implikasi untuk Modeling:
- **Scaling diperlukan** untuk model seperti SVM dan Logistic Regression karena variasi skala antar fitur.
- Fitur `PoliticalFactors` memiliki distribusi relatif rendah (skor rendah mendominasi), disarankan untuk diuji signifikansinya terhadap target.
- Dataset cocok untuk dua pendekatan:
  - **Regresi**, dengan `FloodProbability` sebagai target.
  - **Klasifikasi**, menggunakan `FloodLabel` sebagai target kategorikal biner.


### Distribusi Fitur numerik
![Contoh Gambar](https://github.com/Reswn/Flood-Predictive-Analytics/blob/master/src/Gambar%20Numerik.png)


### 1. **Distribusi Data Secara Umum**
   - Sebagian besar fitur memiliki distribusi yang cenderung **skew ke kanan** (positif). Ini artinya, nilai-nilai lebih sering terkonsentrasi di sekitar nilai rendah, sementara nilai tinggi lebih jarang.
   - Beberapa fitur seperti `MonsoonIntensity`, `TopographyDrainage`, dan `RiverManagement` menunjukkan pola yang mirip, dengan puncak frekuensi terjadi pada rentang nilai antara 0 hingga 5.

### 2. **Kemiripan Pola Antara Fitur**
   - Banyak fitur memiliki pola distribusi yang sangat mirip, seperti:
     - `MonsoonIntensity`, `TopographyDrainage`, `RiverManagement`, `Deforestation`, `Urbanization`, `ClimateChange`, `DamsQuality`, `Siltation`, `AgriculturalPractices`, `Encroachments`, `IneffectiveDisasterPreparedness`, `DrainageSystems`, `CoastalVulnerability`, `Landslides`, `Watersheds`, `DeterioratingInfrastructure`, `PopulationScore`, `WetlandLoss`, `InadequatePlanning`, dan `PoliticalFactors`.
   - Hal ini menunjukkan bahwa banyak variabel dalam dataset mungkin memiliki korelasi atau hubungan yang kuat satu sama lain, karena mereka mengikuti pola distribusi yang serupa.

### 3. **Rentang Nilai**

   - Rentang nilai untuk sebagian besar fitur tampaknya terbatas antara **0 hingga 15**, meskipun ada beberapa outlier yang mencapai nilai lebih tinggi (misalnya, `WetlandLoss` memiliki nilai maksimum di atas 20).
   - Ini menunjukkan bahwa data telah dinormalisasi atau diskala ke dalam rentang tertentu, sehingga memudahkan analisis perbandingan antar fitur.

### 4. **Frekuensi Nilai Tertentu**
   - Nilai **0** memiliki frekuensi yang cukup tinggi pada banyak fitur. Ini bisa menunjukkan bahwa beberapa faktor alam atau manusia tidak selalu aktif atau relevan di setiap lokasi atau kasus banjir.
   - Misalnya, `Deforestation` atau `Urbanization` mungkin tidak signifikan di daerah-daerah tertentu, sehingga nilai tersebut menjadi nol.

### 5. **Insight Spesifik Terhadap Setiap Fitur**
   - **MonsoonIntensity**: Frekuensi tertinggi terjadi pada nilai 0-5, menunjukkan bahwa intensitas musim hujan biasanya tidak terlalu ekstrem di sebagian besar lokasi.
   - **TopographyDrainage**: Distribusi yang mirip dengan `MonsoonIntensity` menunjukkan bahwa topografi dan sistem drainase juga memiliki variasi yang relatif rendah.
   - **RiverManagement**: Frekuensi tertinggi terjadi pada nilai 0-5, menunjukkan bahwa manajemen sungai di banyak lokasi masih belum optimal.
   - **Deforestation**: Ada peningkatan frekuensi pada nilai 0-5, tetapi ada lonjakan kecil pada nilai 10-15, yang mungkin menunjukkan adanya lokasi dengan deforestasi yang signifikan.
   - **Urbanization**: Distribusi yang mirip dengan fitur lain menunjukkan bahwa urbanisasi juga memiliki variasi yang terbatas.
   - **ClimateChange**: Frekuensi tertinggi terjadi pada nilai 0-5, menunjukkan bahwa dampak perubahan iklim mungkin belum begitu signifikan di banyak lokasi.
   - **DamsQuality**: Frekuensi tertinggi terjadi pada nilai 0-5, menunjukkan bahwa kualitas bendungan di banyak lokasi masih kurang baik.
   - **Siltation**: Distribusi yang mirip dengan fitur lain menunjukkan bahwa sedimentasi juga memiliki variasi yang terbatas.
   - **AgriculturalPractices**: Frekuensi tertinggi terjadi pada nilai 0-5, menunjukkan bahwa praktik pertanian yang tidak ramah lingkungan mungkin masih terbatas di banyak lokasi.
   - **Encroachments**: Frekuensi tertinggi terjadi pada nilai 0-5, menunjukkan bahwa encroachment (penyekapan) di area rawan banjir masih terbatas.
   - **IneffectiveDisasterPreparedness**: Frekuensi tertinggi terjadi pada nilai 0-5, menunjukkan bahwa persiapan bencana yang tidak efektif masih umum di banyak lokasi.
   - **DrainageSystems**: Distribusi yang mirip dengan fitur lain menunjukkan bahwa sistem drainase di banyak lokasi masih belum optimal.
   - **CoastalVulnerability**: Frekuensi tertinggi terjadi pada nilai 0-5, menunjukkan bahwa kerentanan pantai masih terbatas di banyak lokasi.
   - **Landslides**: Frekuensi tertinggi terjadi pada nilai 0-5, menunjukkan bahwa kemungkinan longsoran tanah masih terbatas di banyak lokasi.
   - **Watersheds**: Distribusi yang mirip dengan fitur lain menunjukkan bahwa kondisi kawasan hulu di banyak lokasi masih relatif stabil.
   - **DeterioratingInfrastructure**: Frekuensi tertinggi terjadi pada nilai 0-5, menunjukkan bahwa degradasi infrastruktur masih terbatas di banyak lokasi.
   - **PopulationScore**: Frekuensi tertinggi terjadi pada nilai 0-5, menunjukkan bahwa skor populasi (mungkin berkaitan dengan kerentanan sosial) masih relatif rendah di banyak lokasi.
   - **WetlandLoss**: Ada lonjakan frekuensi pada nilai 0-5, tetapi ada outlier yang mencapai nilai lebih tinggi (>20), menunjukkan bahwa hilangnya lahan gambut di beberapa lokasi sangat signifikan.
   - **InadequatePlanning**: Frekuensi tertinggi terjadi pada nilai 0-5, menunjukkan bahwa perencanaan yang tidak memadai masih umum di banyak lokasi.
   - **PoliticalFactors**: Distribusi yang mirip dengan fitur lain menunjukkan bahwa faktor politik juga memiliki variasi yang terbatas.

### 6. **Outlier dan Nilai Ekstrem**
   - Beberapa fitur seperti `WetlandLoss` memiliki outlier dengan nilai yang jauh lebih tinggi dibandingkan dengan rentang nilai utama. Ini menunjukkan bahwa ada lokasi tertentu yang mengalami dampak yang sangat signifikan dari faktor-faktor tersebut.
   - Outlier ini penting untuk dianalisis lebih lanjut, karena mereka mungkin merepresentasikan kasus-kasus khusus yang memerlukan perhatian khusus.


### Distribusi Korelasi Fitur Variabel
![Contoh Gambar](https://github.com/Reswn/Flood-Predictive-Analytics/blob/master/src/gambar%20kategorikal.png)


### **1. Hubungan Antara Fitur dan Probabilitas Banjir (`FloodProbability`)**
   - **Insight Utama**: Beberapa fitur memiliki korelasi positif dengan probabilitas banjir (`FloodProbability`), meskipun nilainya relatif rendah.
     - **Fitur dengan Korelasi Tertinggi**:
       - `TopographyDrainage`: 0.23
       - `RiverManagement`: 0.23
       - `Deforestation`: 0.22
       - `Urbanization`: 0.22
       - `ClimateChange`: 0.23
       - `DamsQuality`: 0.23
       - `Siltation`: 0.23
       - `Encroachments`: 0.23
       - `IneffectiveDisasterPreparedness`: 0.23
       - `DrainageSystems`: 0.22
       - `CoastalVulnerability`: 0.22
       - `Landslides`: 0.23
       - `Watersheds`: 0.23
       - `DeterioratingInfrastructure`: 0.23
       - `PopulationScore`: 0.23
       - `WetlandLoss`: 0.22
       - `InadequatePlanning`: 0.22
       - `PoliticalFactors`: 0.21
     - **Interpretasi**: Semua fitur ini memiliki korelasi positif dengan probabilitas banjir, meskipun tingkat korelasinya relatif rendah (sekitar 0.2–0.23). Ini menunjukkan bahwa faktor-faktor ini memengaruhi risiko banjir, tetapi pengaruhnya tidak dominan secara individu.

---

### **2. Hubungan Antar Fitur**
   - **Insight Utama**: Sebagian besar fitur memiliki korelasi yang sangat rendah satu sama lain (nilai mendekati 0).
     - **Contoh Korelasi Rendah**:
       - Misalnya, `MonsoonIntensity` memiliki korelasi rendah dengan sebagian besar fitur lainnya (nilai korelasi di bawah 0.05).
       - Hal serupa juga terjadi pada `TopographyDrainage`, `RiverManagement`, dan sebagian besar fitur lainnya.
     - **Interpretasi**: Banyak fitur tampaknya independen satu sama lain atau memiliki hubungan yang sangat lemah. Ini bisa menjadi indikasi bahwa faktor-faktor ini bekerja secara bersamaan tetapi tidak saling bergantung secara signifikan.

---

### **3. Faktor yang Memiliki Korelasi Tinggi Dengan Diri Sendiri**
   - **Insight Utama**: Beberapa fitur memiliki korelasi yang cukup tinggi dengan diri sendiri (diagonal utama matriks adalah 1.0), tetapi beberapa pasangan fitur juga memiliki korelasi yang lebih tinggi dibandingkan dengan rata-rata.
     - **Contoh**:
       - `Deforestation` memiliki korelasi tinggi dengan `Urbanization` (0.01).
       - `ClimateChange` memiliki korelasi tinggi dengan `DamsQuality` (0.01).
       - `Siltation` memiliki korelasi tinggi dengan `Encroachments` (0.01).
       - `DrainageSystems` memiliki korelasi tinggi dengan `CoastalVulnerability` (0.01).
     - **Interpretasi**: Meskipun korelasinya masih rendah, hal ini menunjukkan adanya hubungan antar faktor tertentu. Misalnya, deforestasi dan urbanisasi mungkin saling terkait karena keduanya dapat meningkatkan risiko banjir melalui perubahan lahan.

---

### **4. Faktor yang Memiliki Pengaruh Signifikan**
   - **Insight Utama**: Beberapa fitur memiliki korelasi yang lebih tinggi dibandingkan dengan yang lain terhadap probabilitas banjir.
     - **Fitur dengan Pengaruh Potensial**:
       - `TopographyDrainage`, `RiverManagement`, dan `Deforestation` memiliki korelasi tertinggi dengan `FloodProbability` (0.23).
       - `ClimateChange` juga memiliki korelasi yang cukup tinggi (0.23).
     - **Interpretasi**: Faktor-faktor ini kemungkinan besar merupakan faktor utama yang memengaruhi risiko banjir. Topografi dan sistem drainase, manajemen sungai, deforestasi, serta perubahan iklim tampaknya memiliki dampak yang lebih besar dibandingkan faktor lainnya.

---

### **5. Faktor yang Kurang Berpengaruh**
   - **Insight Utama**: Beberapa fitur memiliki korelasi yang sangat rendah dengan probabilitas banjir.
     - **Contoh**:
       - `MonsoonIntensity` memiliki korelasi rendah dengan `FloodProbability` (0.22).
       - `AgriculturalPractices` memiliki korelasi rendah dengan `FloodProbability` (0.22).
     - **Interpretasi**: Meskipun faktor seperti musim hujan monsun dan praktik pertanian memiliki potensi untuk memengaruhi banjir, dampaknya tampaknya kurang signifikan dibandingkan dengan faktor lainnya.

---

## Data Preparation

Pada tahap ini, data dipersiapkan agar siap digunakan dalam proses pelatihan model machine learning. Tujuan dari *data preparation* adalah memastikan data bersih, konsisten, dan dalam format yang tepat sehingga dapat memberikan performa model yang optimal. Berikut adalah langkah-langkah yang dilakukan:

### 1. Pembersihan Data

#### a. **Missing Values**
 Tidak ditemukan nilai kosong (`NaN`) pada seluruh fitur dataset (total 50.000 baris data lengkap).

#### b. **Duplicate Rows**
Tidak ada duplikasi baris terdeteksi.

#### c. **Konsistensi Tipe Data**
Semua fitur numerik bertipe `int64`, sedangkan target `FloodProbability` bertipe `float64`.
- **Alasan**: Memastikan semua kolom memiliki tipe data yang benar agar kompatibel dengan operasi numerik dan model machine learning.

---

### 2. Pembagian Data (Train-Test Split)

#### a. **Binarisasi Target**
- **Deskripsi**: Kolom target `FloodProbability` dikonversi menjadi label biner `FloodLabel` menggunakan threshold 0.5:
  ```python
  df['FloodLabel'] = (df['FloodProbability'] > 0.5).astype(int)
  ```
- **Alasan**: Model klasifikasi memerlukan label kelas diskrit (0 atau 1), sementara `FloodProbability` merupakan kontinu. Threshold 0.5 digunakan sebagai batas natural untuk konversi probabilitas ke label biner.

#### b. **Split Fitur dan Label**
- **Deskripsi**:
  ```python
  X = df.drop(['FloodProbability', 'FloodLabel'], axis=1)
  y = df['FloodLabel']
  ```
- **Alasan**: Memisahkan variabel prediktor (`X`) dan variabel target (`y`) sebelum pembagian data latih dan uji.

#### c. **Pembagian Data Latih dan Uji**
- **Deskripsi**:
  ```python
  X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
  ```
- **Alasan**: Membagi data menjadi 80% untuk pelatihan dan 20% untuk evaluasi. Parameter `random_state` digunakan untuk mereproduksi hasil split yang sama setiap kali kode dijalankan.

---

### 3. Standarisasi Fitur

#### a. **Standardisasi Data**
- **Deskripsi**:
  ```python
  scaler = StandardScaler()
  X_train_scaled = scaler.fit_transform(X_train)
  X_test_scaled = scaler.transform(X_test)
  ```
- **Alasan**:  algoritma machine learning (seperti SVM) sensitif terhadap skala fitur. Dengan standardisasi, semua fitur diubah menjadi distribusi normal dengan rata-rata 0 dan deviasi standar 1, sehingga model lebih stabil dan cepat konvergen.

---

##  Ringkasan Tahapan

| No | Tahapan                  | Tujuan                                                                 |
|----|---------------------------|------------------------------------------------------------------------|
| 1  | Pembersihan Data          | Memastikan data bersih, tanpa missing values, duplikasi, dan valid   |
| 2  | Binarisasi Target         | Mengubah target kontinu menjadi label biner untuk klasifikasi        |
| 3  | Split Fitur dan Label     | Memisahkan variabel input dan output                                 |
| 4  | Train-Test Split          | Mempersiapkan data latih dan uji                                     |
| 5  | Standardisasi             | Menyesuaikan skala fitur agar kompatibel dengan model                 |

---




## Modeling

Dalam proyek ini, dilakukan pelatihan dan evaluasi model prediksi banjir dengan menggunakan tiga algoritma machine learning populer yang cocok untuk tugas klasifikasi biner, yaitu:

### 1. Decision Tree Classifier

Algoritma ini membuat struktur pohon keputusan berdasarkan pemisahan fitur yang paling informatif. Model akan terus memecah dataset hingga mencapai keputusan prediksi. Dalam implementasi ini, digunakan parameter default tanpa pembatasan kedalaman.

**Kelebihan:**
- Mudah dipahami dan divisualisasikan.
- Cepat dalam pelatihan dan prediksi.
- Tidak memerlukan scaling fitur.

**Kekurangan:**
- Rawan mengalami overfitting, terutama jika pohon terlalu dalam.
- Kurang stabil terhadap perubahan kecil pada data.

---

### 2. Random Forest Classifier

Random Forest merupakan model ansambel yang terdiri dari banyak pohon keputusan. Model ini bekerja dengan menggabungkan hasil voting dari masing-masing pohon untuk menentukan prediksi akhir.

**Parameter utama:** `n_estimators = 100`

**Kelebihan:**
- Lebih akurat dibanding satu pohon karena menggunakan banyak model.
- Tidak mudah overfitting seperti Decision Tree tunggal.
- Mampu menangani data berdimensi tinggi.

**Kekurangan:**
- Sulit diinterpretasikan karena kompleksitas model.
- Lebih lambat dalam proses pelatihan dan prediksi dibanding model tunggal.

---

### 3. Support Vector Machine (SVM)

SVM merupakan algoritma klasifikasi yang bekerja dengan mencari garis batas (hyperplane) terbaik yang memisahkan dua kelas. Dalam proyek ini digunakan kernel default `rbf` dengan opsi `probability=True` agar dapat menghitung AUC.

**Kelebihan:**
- Sangat efektif dalam menangani data berdimensi tinggi.
- Umumnya memberikan hasil yang baik untuk data yang tidak terlalu besar.
- Dapat digunakan untuk klasifikasi linier maupun non-linier.

**Kekurangan:**
- Membutuhkan normalisasi atau standardisasi data.
- Kurang efisien jika dataset sangat besar.
- Sulit untuk memilih parameter (kernel, C, gamma) yang optimal.

---

## Evaluation

Evaluasi performa model dilakukan dengan menggunakan dua metrik utama:

- **Accuracy**: Proporsi prediksi yang benar terhadap seluruh jumlah data.
- **AUC (Area Under Curve)**: Mengukur kemampuan model membedakan antara kelas positif dan negatif.


###  Hasil Evaluasi Model
![Contoh Gambar](https://github.com/Reswn/Flood-Predictive-Analytics/blob/master/src/Peforma%20Model.png)


| Model              | Accuracy | AUC     |
|-------------------|----------|---------|
| SVM               | **0.9913** | **0.9997** |
| Random Forest      | 0.8888   | 0.9683  |
| Decision Tree      | 0.6880   | 0.6860  |

> Berdasarkan hasil evaluasi di atas, **SVM menjadi model terbaik** karena memberikan akurasi dan nilai AUC tertinggi, menunjukkan kemampuannya dalam mengklasifikasikan data secara akurat dan stabil.


## Kesimpulan: Mengapa Support Vector Machine (SVM) adalah Model Terbaik

Setelah membandingkan tiga model klasifikasi—Decision Tree, Random Forest, dan Support Vector Machine (SVM)—berdasarkan metrik **Accuracy** dan **AUC (Area Under Curve)**, diperoleh hasil bahwa **SVM adalah model terbaik** untuk klasifikasi risiko banjir dalam studi ini.

### Alasan Mengapa SVM Unggul:

- **Akurasi Tertinggi (99.13%)**  
  Ini berarti bahwa 99.13% dari prediksi yang dilakukan oleh model SVM pada data uji sesuai dengan label sebenarnya. Angka ini jauh mengungguli Random Forest (88.88%) dan Decision Tree (68.80%).

- **AUC Tertinggi (0.9997)**  
  Nilai AUC mendekati 1 menunjukkan bahwa SVM memiliki kemampuan luar biasa dalam membedakan antara dua kelas, yaitu risiko banjir (1) dan tidak banjir (0). Ini menunjukkan bahwa model tidak hanya akurat, tetapi juga sangat sensitif terhadap perbedaan antara kelas.

- **Generalisasi yang Lebih Baik**  
  SVM cenderung lebih stabil dan tidak mudah mengalami overfitting dibandingkan dengan Decision Tree. Bahkan jika dibandingkan dengan Random Forest yang merupakan ensemble model, SVM masih menunjukkan performa lebih baik dalam konteks dataset ini.

---

## Kesimpulan

Berdasarkan hasil eksperimen dan evaluasi terhadap beberapa model klasifikasi dalam proyek ini, diperoleh kesimpulan utama yang menjawab rumusan masalah secara menyeluruh:

### Pembangunan Model Klasifikasi Risiko Banjir
Model machine learning telah berhasil dikembangkan untuk memprediksi risiko banjir dengan memanfaatkan **20 fitur** yang merepresentasikan berbagai faktor lingkungan, sosial, dan infrastruktur. Tahapan proyek mencakup:
- Exploratory Data Analysis (EDA)
- Data preprocessing & normalisasi
- Pelatihan model klasifikasi
- Evaluasi performa berdasarkan metrik akurasi dan AUC

---

### Model Terbaik: Support Vector Machine (SVM)

Dari tiga model yang dikomparasikan—**Decision Tree**, **Random Forest**, dan **SVM**—diperoleh hasil evaluasi sebagai berikut:

| Model           | Accuracy | AUC     |
|----------------|----------|---------|
| SVM            | **99.13%** | **0.9997** |
| Random Forest  | 88.88%   | 0.9683  |
| Decision Tree  | 68.80%   | 0.6860  |

🔹 **Support Vector Machine (SVM)** terbukti unggul secara signifikan dalam hal:
- **Akurasi tertinggi (99.13%)** → prediksi sangat presisi terhadap data uji.
- **AUC tertinggi (0.9997)** → kemampuan luar biasa dalam membedakan antara kelas "banjir" dan "tidak banjir".
- **Generalization** yang lebih baik dan tahan terhadap overfitting dibanding model lainnya.

---

### Manfaat Model bagi Pengambilan Keputusan

Dengan performa yang sangat tinggi dan konsisten, model SVM memiliki potensi besar untuk:
- **Mendukung sistem peringatan dini banjir** secara otomatis dan data-driven.
- **Membantu pemerintah daerah** dalam menetapkan zona rawan dan rencana mitigasi.
- **Memfasilitasi badan penanggulangan bencana** dalam mengalokasikan sumber daya secara strategis.
- **Meningkatkan kesiapsiagaan masyarakat**, terutama di wilayah berisiko tinggi.

> Model SVM tidak hanya menunjukkan performa klasifikasi terbaik, tetapi juga berkontribusi langsung dalam mendukung pengambilan keputusan yang lebih cepat, akurat, dan efisien dalam konteks mitigasi bencana banjir.

---
## Referensi

1. GeeksforGeeks. (2024). *Random Forest Algorithm in Machine Learning*. [Online]. Available at: https://www.geeksforgeeks.org/random-forest-algorithm-in-machine-learning/ [Accessed 20 May 2025].

2. Built In. (2022). *Decision Tree Classification | Built In*. [Online]. Available at: https://builtin.com/data-science/classification-tree [Accessed 20 May 2025].

3. GeeksforGeeks. (2021). *Support Vector Machine (SVM) Algorithm*. [Online]. Available at: https://www.geeksforgeeks.org/support-vector-machine-algorithm/ [Accessed 20 May 2025].

4. Puspasari, R. L., Yoon, D., Kim, H., & Kim, K.-W. (2023). *Machine Learning for Flood Prediction in Indonesia: Providing Online Access for Disaster Management Control*. Economic and Environmental Geology, 56(1), 65–73. [Online]. Available at: http://dx.doi.org/10.9719/EEG.2023.56.1.65

5. Khaldi, L., EL Bilali, A., Elabed, A., Krakauer, N., & El Khanchoufi, A. (2025). *Developing an explainable and interpretable machine learning model for flood susceptibility mapping*. Ecological Engineering & Environmental Technology, 26(1), 201–215. [Online]. Available at: https://doi.org/10.12912/27197050/195845

6. Yang, J., Ahn, D., Bahk, J., Park, S., Rizqihandari, N., & Cha, M. (2024). *Assessing climate risks from satellite imagery with machine learning: A case study of flood risks in Jakarta*. Climate Risk Management. *(In Press)*

7. Movva, S. S. (2022). *Flood Prediction Analysis Using Explainable Artificial Intelligence*. European Journal of Advances in Engineering and Technology, 9(3), 139–146.

‌
