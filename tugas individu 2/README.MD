# 📄 Klasifikasi Teks menggunakan RNN (LSTM) - Deteksi Berita Palsu

[cite_start]Proyek ini adalah implementasi tugas individu yang bertujuan untuk membangun model klasifikasi teks menggunakan Recurrent Neural Network (RNN), khususnya **Long Short-Term Memory (LSTM)**, untuk membedakan antara **Berita Asli (Real)** dan **Berita Palsu (Fake)**. [cite: 1, 6]

---
### 📌 Ringkasan Proyek

| Aspek | Keterangan |
| :--- | :--- |
| 🎯 **Tujuan** | Memprediksi apakah suatu berita termasuk dalam kategori **Berita Asli** atau **Berita Palsu**. |
| 📊 **Dataset** | [cite_start]**FakeNewsNet Dataset** dari Kaggle. [cite: 10] |
| 🧠 **Model** | [cite_start]LSTM dengan lapisan **Embedding**. [cite: 20, 21] |
| ❌ **Akurasi Akhir** | [cite_start]**42.50% (Gagal Belajar)** [cite: 40] |
| 💻 **Bahasa & Framework** | Python dengan TensorFlow/Keras. |

---
### 🧠 Arsitektur Model

[cite_start]Model yang digunakan terdiri dari beberapa *layer* utama untuk memproses teks secara sekuensial: [cite: 20]
* [cite_start]**Embedding Layer:** Mengubah token kata menjadi vektor padat dengan dimensi 64. Ukuran kosakata dibatasi hingga 5000 kata. [cite: 21, 22]
* [cite_start]**LSTM Layer:** Memproses urutan vektor dengan 64 unit untuk menangkap dependensi jangka panjang. [cite: 23]
* [cite_start]**Output Layer:** Menggunakan aktivasi `sigmoid` untuk klasifikasi biner (Berita Asli / Berita Palsu). [cite: 24]

---
### 📂 Struktur Notebook

Proyek ini disusun dalam satu file *notebook Jupyter* dengan alur kerja sebagai berikut:

1.  **📦 Impor Library:** Memuat semua pustaka yang diperlukan seperti `pandas`, `numpy`, `tensorflow`, dan `matplotlib`.
2.  [cite_start]**📁 Muat Dataset:** Membaca data dari file `.csv` dan mengambil sampel seimbang (100 asli, 100 palsu) untuk pelatihan. [cite: 12]
3.  [cite_start]**🧹 Pra-pemrosesan Teks:** Melakukan tokenisasi pada judul berita dan *padding* untuk menyeragamkan panjang input. [cite: 27, 28]
4.  **🏗️ Pembangunan Model LSTM:** Mendefinisikan arsitektur jaringan saraf berbasis LSTM.
5.  **🎯 Pelatihan dan Visualisasi:** Melatih model serta memvisualisasikan kurva akurasi dan *loss*.
6.  **📊 Evaluasi dan Analisis:** Mengevaluasi model pada data uji untuk mengukur performa akhir.

---
### ⚙️ Cara Menjalankan

Untuk mereproduksi hasil dari proyek ini, ikuti langkah-langkah berikut:

1.  **📥 Unduh File Proyek**
    * Unduh file *notebook* (misalnya, `fake_news_classification.ipynb`).
    * Unduh dataset **FakeNewsNet.csv** dari Kaggle dan pastikan berada di direktori yang dapat diakses oleh *notebook*.

2.  **🛠️ Instalasi Dependensi**
    Pastikan Anda telah menginstal semua *library* yang dibutuhkan.
    ```bash
    pip install pandas numpy scikit-learn tensorflow matplotlib
    ```
3.  **▶️ Jalankan Kode**
    Buka *notebook* dan jalankan setiap sel kode secara berurutan dari atas ke bawah.

---
### 📊 Hasil & Evaluasi
* [cite_start]**Akurasi Akhir pada Data Uji:** **42.50%** [cite: 40]
* [cite_start]**Analisis Hasil:** Performa model sangat buruk dan gagal belajar. [cite: 43] [cite_start]Akurasi yang didapat lebih rendah dari tebakan acak (50%), yang mengindikasikan model tidak mampu menemukan pola yang berguna dari data yang diberikan. [cite: 62]
* [cite_start]**Kurva Pelatihan:** Grafik *learning curve* menunjukkan kurva *loss* dan akurasi yang tidak beraturan (*erratic*), mengonfirmasi bahwa model gagal melakukan konvergensi. [cite: 41, 42]

---
### Riwayat Eksperimen

[cite_start]Proses eksperimen difokuskan pada analisis performa model dasar. [cite: 36]

| Percobaan | Model | Dropout | Optimizer | Akurasi Validasi | Catatan |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **#1** | LSTM(64) | 0.0 | Adam | **~40-50%** (tidak stabil) | **Model gagal belajar**. [cite_start]Akurasi yang dihasilkan lebih buruk dari tebakan acak, mengindikasikan masalah pada jumlah data yang terlalu sedikit. [cite: 37] |

---
### 🔍 Refleksi

* **🧩 Tantangan Utama**
    [cite_start]Tantangan utama yang teridentifikasi setelah melihat hasil adalah **jumlah data yang sangat terbatas** (200 sampel). [cite: 47] [cite_start]Model *deep learning* seperti LSTM membutuhkan ribuan contoh untuk dapat belajar secara efektif. [cite: 48] [cite_start]Dengan data yang minim, model justru "bingung" dan tidak bisa belajar. [cite: 49]

* **✅ Solusi yang Diterapkan**
    [cite_start]Solusi yang paling jelas untuk masalah ini adalah dengan **menambah jumlah data secara signifikan**. [cite: 51] [cite_start]Percobaan dengan 200 data ini menjadi bukti bahwa kuantitas data adalah prasyarat utama sebelum arsitektur model dapat bekerja secara efektif. [cite: 52]

* **🤖 Pemanfaatan AI**
    [cite_start]Saya menggunakan *tool* AI generatif untuk membantu dalam beberapa aspek teknis, seperti menyusun kerangka kode awal, memberikan penjelasan fungsi *library*, dan membantu menyusun draf laporan. [cite: 54] [cite_start]Semua hasil tetap diverifikasi secara mandiri. [cite: 55]

---
### 💡 Saran Pengembangan

[cite_start]Berdasarkan analisis kegagalan, langkah perbaikan yang paling prioritas adalah: [cite: 65]
* [cite_start]**Menambah Jumlah Data (Prioritas Utama):** Meningkatkan jumlah sampel data secara drastis (misalnya, menjadi 2000 data, 1000 per kelas). [cite: 66]
* [cite_start]**Menggunakan Konten Penuh:** Menganalisis **seluruh isi berita (`text`)**, tidak hanya judul (`title`), untuk mendapatkan konteks yang lebih kaya. [cite: 67]
* [cite_start]**Mencoba Model yang Lebih Sederhana:** Sebagai perbandingan, mencoba model klasik seperti Naive Bayes untuk melihat apakah data yang sedikit lebih cocok untuk model yang lebih sederhana. [cite: 68]

---
### 📚 Referensi
* [cite_start]FakeNewsNet Dataset - Kaggle [cite: 10]
* [cite_start]virgantara/Deep-Learning-Course [cite: 70]

---
### 👤 Author

* **Nama:** Wafa Bila Syaefurokhman
* **Tugas:** Klasifikasi Teks - Deteksi Berita Palsu
