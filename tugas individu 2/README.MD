# 📄 Klasifikasi Teks menggunakan RNN (LSTM) - Deteksi Berita Palsu

Proyek ini adalah implementasi tugas individu yang bertujuan untuk membangun model klasifikasi teks menggunakan Recurrent Neural Network (RNN), khususnya **Long Short-Term Memory (LSTM)**, untuk membedakan antara **Berita Asli (Real)** dan **Berita Palsu (Fake)**.

---
### 📌 Ringkasan Proyek

| Aspek | Keterangan |
| :--- | :--- |
| 🎯 **Tujuan** | Memprediksi apakah suatu berita termasuk dalam kategori **Berita Asli** atau **Berita Palsu**. |
| 📊 **Dataset** | **FakeNewsNet Dataset** dari Kaggle. |
| 🧠 **Model** | LSTM dengan lapisan **Embedding** dan **Dropout**. |
| ✅ **Akurasi Validasi Terbaik** | **~92.5%** |
| 💻 **Bahasa & Framework** | Python dengan TensorFlow/Keras. |

---
### 🧠 Arsitektur Model

Model yang digunakan terdiri dari beberapa *layer* utama untuk memproses teks secara sekuensial:
* **Embedding Layer:** Mengubah token kata menjadi vektor padat dengan dimensi 64. Ukuran kosakata dibatasi hingga 5000 kata.
* **LSTM Layer:** Memproses urutan vektor dengan 64 unit untuk menangkap dependensi jangka panjang.
* **Dropout Layer:** Menerapkan regularisasi dengan *rate* 0.3 untuk mengurangi *overfitting*.
* **Output Layer:** Menggunakan aktivasi `sigmoid` untuk klasifikasi biner (Berita Asli / Berita Palsu).

---
### 📂 Struktur Notebook

Proyek ini disusun dalam satu file *notebook Jupyter* dengan alur kerja sebagai berikut:

1.  **📦 Impor Library:** Memuat semua pustaka yang diperlukan seperti `pandas`, `numpy`, `tensorflow`, dan `matplotlib`.
2.  **📁 Muat Dataset:** Membaca data dari file `.csv` dan mengambil sampel seimbang (100 asli, 100 palsu) untuk pelatihan.
3.  **🧹 Pra-pemrosesan Teks:** Melakukan tokenisasi pada judul berita dan *padding* untuk menyeragamkan panjang input.
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
* **Akurasi Training Akhir:** ~98%
* **Akurasi Validasi Akhir:** ~92.5%
* **Kurva Pelatihan:** Kurva akurasi dan *loss* menunjukkan bahwa model belajar dengan stabil. Penambahan *dropout* efektif mencegah *overfitting* yang parah.

---
### Riwayat Eksperimen

Tabel berikut merangkum hasil dari beberapa percobaan yang dilakukan:

| Percobaan | Model | Dropout | Optimizer | Akurasi Validasi | Catatan |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **#1** | LSTM(64) | 0.0 | Adam | 85.0% | Performa awal cukup baik, tetapi ada indikasi *overfitting*. |
| **#2** | LSTM(64) | 0.3 | Adam | **92.5%** | **Hasil terbaik**. *Dropout* efektif mengurangi *overfitting* dan menstabilkan performa. |

---
### 🔍 Refleksi

* **🧩 Tantangan Utama**
    * Menangani **overfitting** saat model mulai menghafal data latih.
    * Membedakan **gaya bahasa sensasional** pada berita palsu dengan berita asli yang terkadang juga menggunakan judul yang menarik.

* **✅ Solusi yang Diterapkan**
    * Menggunakan **Dropout** sebagai teknik regularisasi yang efektif untuk meningkatkan generalisasi model.
    * Melakukan **visualisasi kurva akurasi dan *loss*** untuk memantau proses pelatihan secara cermat.
    * Melakukan **eksperimen berulang** dengan mengubah arsitektur untuk menemukan konfigurasi terbaik.

* **🤖 Pemanfaatan AI**
    Saya menggunakan *tool* AI generatif untuk membantu dalam beberapa aspek teknis, seperti mendapatkan penjelasan konsep RNN, menyusun struktur kode yang bersih, dan memberikan panduan dalam proses evaluasi model. Semua hasil tetap diverifikasi secara mandiri.

---
### 💡 Saran Pengembangan

* **Gunakan Konten Penuh:** Menganalisis **seluruh isi berita (`text`)**, tidak hanya judul (`title`), untuk mendapatkan konteks yang lebih kaya.
* **Coba Arsitektur Lain:** Bereksperimen dengan model seperti **Bi-LSTM** (Bidirectional LSTM) atau **GRU** (Gated Recurrent Unit).
* **Integrasikan Pre-trained Embedding:** Menggunakan *embedding* kata yang telah dilatih sebelumnya seperti **GloVe** atau **FastText**.

---
### 📚 Referensi
* FakeNewsNet Dataset - Kaggle
* François Chollet - *Deep Learning with Python*
* Dokumentasi Keras & TensorFlow

---
### 👤 Author

* **Nama:** Wafa Bila Syaefurokhman
* **Tugas:** Klasifikasi Teks - Deteksi Berita Palsu
