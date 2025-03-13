# Sentiment Analysis Danantara dengan LightGBM

## 📌 Definisi Danantara
Danantara, singkatan dari Daya Anagata Nusantara, adalah badan pengelola investasi nasional yang dibentuk untuk mengelola aset negara dan investasi strategis, dengan tujuan mendukung pertumbuhan ekonomi jangka panjang. 


---

## 🎯 Tujuan dan Manfaat Proyek
Proyek ini bertujuan untuk:
- Menganalisis opini masyarakat terhadap Danantara menggunakan teknik **Sentiment Analysis**.
- Mengklasifikasikan komentar menjadi **Positive dan Negative**.
- Memberikan wawasan mengenai bagaimana masyarakat merespons Danantara secara umum.
- Menggunakan model **LightGBM** untuk mendapatkan hasil klasifikasi yang optimal.

---

## 🔄 Proses Sentiment Analysis

### 1️⃣ Pengambilan Data
- Data dikumpulkan dari komentar pada beberapa video YouTube yang membahas Danantara.
- Data ini diekstrak menggunakan teknik web scraping.

### 2️⃣ Preprocessing Data
Untuk meningkatkan kualitas data, dilakukan preprocessing sebagai berikut:
- **Cleaning Text**: Menghapus karakter khusus, angka, tanda baca, dan whitespace berlebih.
- **Case Folding**: Mengubah semua teks menjadi huruf kecil.
- **Tokenization**: Memisahkan teks menjadi kata-kata individu.
- **Stopword Removal**: Menghapus kata-kata umum yang tidak memiliki makna signifikan.
- **Stemming**: Mengubah kata-kata menjadi bentuk dasar menggunakan stemming bahasa Indonesia.

### 3️⃣ Ekstraksi Fitur dengan TF-IDF
- Menggunakan **TF-IDF (Term Frequency - Inverse Document Frequency)** untuk mengubah teks menjadi representasi numerik.
- Parameter yang digunakan:
  - `max_features=8000` → Mempertimbangkan kata-kata yang paling sering muncul.
  - `min_df=5` → Menghapus kata-kata yang muncul di kurang dari 5 dokumen.
  - `max_df=0.8` → Menghapus kata-kata yang terlalu umum.

### 4️⃣ Modelling dengan LightGBM
- **LightGBM** dipilih karena memiliki performa tinggi dalam menangani data teks.
- Parameter utama yang digunakan:
  - `num_leaves=50` → Menangkap lebih banyak pola dalam data.
  - `learning_rate=0.05` → Agar training lebih stabil.
  - `n_estimators=200` → Meningkatkan jumlah estimasi untuk meningkatkan performa.

### 5️⃣ Evaluasi Model
- Model diuji dengan data latih dan data uji.
- Akurasi yang diperoleh untuk **data train** adalah **91%**.
- Akurasi yang diperoleh untuk **data test** adalah **84%**.

---

## 🎯 Kata yang Sering Muncul
- Sentimen Negative.
- ![image](https://github.com/user-attachments/assets/fd34e64c-6f60-4116-9c24-d88b4fecf168)

- Sentiment Positive.
- ![image](https://github.com/user-attachments/assets/1bb9c1df-c581-47b7-8eb4-2b08cc23df47)

---

## ✅ Kelebihan Model LightGBM
- **Cepat dan Efisien**: LightGBM lebih cepat dibanding model tree-based lainnya seperti XGBoost.
- **Mengatasi Data Imbalance**: Mampu menangani distribusi data yang tidak seimbang dengan baik.
- **Menangani Fitur dalam Jumlah Besar**: Cocok untuk dataset dengan banyak fitur, seperti hasil TF-IDF.
- **Mendukung Paralelisasi**: Memanfaatkan multi-threading untuk proses training yang lebih efisien.

---

## 📌 Kesimpulan
Proyek ini berhasil melakukan **sentiment analysis terhadap Danantara** dengan model **LightGBM**, mencapai **akurasi 84%** pada data uji. Dengan pemrosesan data yang baik dan pemilihan model yang tepat, analisis sentimen dapat memberikan wawasan yang lebih dalam tentang bagaimana suatu topik diterima oleh masyarakat.
