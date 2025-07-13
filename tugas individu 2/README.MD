### Laporan Tugas Individu: Klasifikasi Teks Menggunakan RNN

* **Nama:** Wafa Bila Syaefurokhman
* **Tugas:** Klasifikasi Teks - Deteksi Berita Palsu

### 1. Pendahuluan
Seiring berkembangnya era digital, penyebaran informasi menjadi sangat cepat dan masif. Namun, kemudahan ini juga diiringi oleh tantangan besar, yaitu maraknya berita palsu (*fake news*) yang dapat meresahkan masyarakat. Kemampuan untuk membedakan berita asli dan palsu secara otomatis menjadi sangat krusial. Klasifikasi teks menggunakan *machine learning*, khususnya dengan arsitektur **Recurrent Neural Network (RNN)**, menawarkan solusi yang efektif karena kemampuannya dalam memahami konteks dan pola dalam data sekuensial seperti teks.

Tugas ini bertujuan untuk membangun sebuah model klasifikasi teks menggunakan arsitektur **LSTM (Long Short-Term Memory)**. Ruang lingkup proyek ini mencakup proses dari persiapan dataset, pra-pemrosesan teks, pembangunan model, hingga evaluasi performa model dalam mengklasifikasikan judul berita sebagai "asli (real)" atau "palsu (fake)".

---
### 2. Dataset
* **Sumber Data:**
    Dataset yang digunakan adalah **FakeNewsNet**, yang bersumber dari platform terbuka Kaggle.

* **Deskripsi Dataset:**
    Untuk memastikan model dapat belajar secara efektif, saya menggunakan sampel data yang lebih besar, yaitu **2000 judul berita**, yang dibagi seimbang menjadi **1000 data untuk kelas berita asli** dan **1000 data untuk kelas berita palsu**. Fitur utama yang digunakan sebagai input untuk model adalah `title` (judul berita), sedangkan `real` (dengan nilai 1 untuk asli dan 0 untuk palsu) digunakan sebagai label. Terdapat variasi gaya bahasa yang jelas, di mana judul berita palsu cenderung lebih sensasional dan provokatif, sementara judul berita asli lebih objektif.

* **Alasan Pemilihan Dataset:**
    Topik deteksi berita palsu dipilih karena relevansinya yang tinggi dengan kondisi sosial saat ini. Dataset ini menyediakan kasus klasifikasi biner yang jelas dan memiliki variasi gaya bahasa yang menantang, sehingga sangat cocok untuk menguji kemampuan model RNN dalam analisis teks.

---
### 3. Implementasi Model

#### 3.1 Arsitektur RNN
Model yang diimplementasikan menggunakan jenis **LSTM (Long Short-Term Memory)**. Arsitektur final (Percobaan #2) yang memberikan hasil terbaik dibangun secara sekuensial menggunakan Keras dan terdiri dari:
* **Embedding Layer:** Mengubah input berupa urutan indeks kata menjadi vektor padat. Parameter yang digunakan: `input_dim=5000` (ukuran kosakata) dan `output_dim=64` (dimensi vektor).
* **LSTM Layer:** Lapisan inti yang memproses urutan vektor untuk menangkap dependensi dan konteks dalam teks. Lapisan ini memiliki 64 unit.
* **Dropout Layer:** Lapisan regularisasi dengan *rate* **0.3** untuk mencegah *overfitting* dan meningkatkan generalisasi model.
* **Dense Layer:** Lapisan output dengan **1 unit** dan fungsi aktivasi **sigmoid** untuk menghasilkan probabilitas klasifikasi biner.

#### 3.2 Preprocessing
Langkah pra-pemrosesan yang dilakukan adalah sebagai berikut:
* **Tokenisasi:** Teks judul diubah menjadi urutan integer menggunakan `Tokenizer` dari Keras dengan batasan **5000 kata** yang paling sering muncul.
* **Padding:** Setiap urutan disamakan panjangnya menjadi **50 token** menggunakan `pad_sequences` untuk memastikan input model seragam.

#### 3.3 Pengaturan Eksperimen
* **Optimizer:** `adam`
* **Loss Function:** `binary_crossentropy`
* **Metrics:** `accuracy`
* **Epochs:** `10`
* **Batch Size:** `16`

#### 3.4 Log Eksperimen
Saya melakukan dua kali percobaan untuk menemukan konfigurasi terbaik.

| Percobaan | Model | Dropout | Optimizer | Akurasi Validasi | Catatan |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **#1** | LSTM(64) | 0.0 | Adam | 85.0% | Performa awal cukup baik, tetapi ada indikasi *overfitting*. |
| **#2** | LSTM(64) | 0.3 | Adam | **92.5%** | **Hasil terbaik**. *Dropout* efektif mengurangi *overfitting* dan menstabilkan performa. |

---
### 4. Evaluasi Hasil

* **Metrik:** Model final (Percobaan #2) dievaluasi pada data uji dan berhasil mencapai akurasi akhir sekitar **92.5%**. Ini menunjukkan model mampu menggeneralisasi pengetahuannya pada data yang belum pernah dilihat sebelumnya.
* **Visualisasi:** Grafik *learning curve* menunjukkan bahwa proses pelatihan berjalan dengan baik. Kurva *training* dan *validasi* naik secara bersamaan dan stabil, tanpa adanya celah yang signifikan, yang mengonfirmasi bahwa penambahan *Dropout* berhasil mencegah *overfitting*.
* **Analisis Performa:** Model terbukti efektif dalam mengenali pola linguistik pada judul berita. Penggunaan *Dropout* pada Percobaan #2 menjadi kunci untuk menstabilkan performa model dan meningkatkan kemampuan generalisasi.

---
### 5. Refleksi Pribadi

* **Tantangan Utama:**
    Tantangan utama yang dihadapi adalah menangani **overfitting** saat model mulai menghafal data latih, serta membedakan **gaya bahasa sensasional** pada berita palsu dengan berita asli yang terkadang juga menggunakan judul yang menarik.

* **Solusi yang Diterapkan:**
    Solusi yang paling efektif adalah menerapkan lapisan **Dropout** sebagai teknik regularisasi. Hasilnya, model menjadi lebih stabil dan kemampuan generalisasinya meningkat, yang terlihat dari naiknya akurasi validasi.

* **Pemanfaatan AI Assistant:**
    Dalam tugas ini, saya memanfaatkan AI Assistant untuk: 1) membantu menyusun kerangka kode awal, 2) memberikan penjelasan fungsi setiap *library*, dan 3) membantu menyusun draf laporan ini. Seluruh kode, hasil, dan analisis telah saya verifikasi dan jalankan secara mandiri.

* **Pelajaran Paling Penting:**
    Pelajaran terpenting dari tugas ini adalah bahwa keberhasilan sebuah model tidak hanya bergantung pada arsitektur yang canggih, tetapi juga pada **kualitas dan kuantitas data** serta **proses eksplorasi yang iteratif** untuk optimasi.

---
### 6. Kesimpulan dan Saran

* **Kesimpulan:**
    Model klasifikasi teks berbasis **LSTM** dengan regularisasi **Dropout** berhasil dibangun untuk membedakan berita asli dan palsu. Model ini menunjukkan performa yang sangat baik dengan akurasi **~92.5%** pada data uji, membuktikan bahwa analisis judul berita saja sudah bisa menjadi indikator yang kuat.

* **Rekomendasi untuk Pengembangan Selanjutnya:**
    1.  **Menggunakan Konten Penuh:** Melatih model dengan menggunakan seluruh isi berita (`text`), tidak hanya judul, untuk mendapatkan konteks yang lebih kaya.
    2.  **Mencoba Arsitektur Lain:** Bereksperimen dengan arsitektur seperti **Bi-LSTM** (Bidirectional LSTM) atau **GRU**.
    3.  **Menggunakan Pre-trained Embeddings:** Memanfaatkan *word embeddings* seperti GloVe atau FastText untuk meningkatkan pemahaman semantik awal model.

---
### 7. Referensi
* FakeNewsNet Dataset. (2020). Kaggle. Diakses dari: `/kaggle/input/fake-news/FakeNewsNet.csv`
* Chollet, F. (2021). *Deep Learning with Python, Second Edition*. Manning Publications.
* virgantara/Deep-Learning-Course. (n.d.). GitHub. Diakses dari: https://github.com/virgantara/Deep-Learning-Course
