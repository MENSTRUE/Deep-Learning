# Eksplorasi Autoencoder pada Fashion MNIST

Proyek ini adalah implementasi tugas individu yang bertujuan untuk membangun, melatih, dan menganalisis sebuah **Convolutional Autoencoder (CAE)** menggunakan dataset **Fashion MNIST**.

---
### 📌 Ringkasan Proyek

| Aspek | Keterangan |
| :--- | :--- |
| 🎯 **Tujuan** | 1. Merekonstruksi gambar pakaian. <br> 2. Memvisualisasikan pengelompokan data di ruang laten (*latent space*). |
| 📊 **Dataset** | **Fashion MNIST** (60,000 gambar latih, 10,000 gambar uji). |
| 🧠 **Model** | **Convolutional Autoencoder** (3 lapis Encoder, 3 lapis Decoder). |
| ✅ **Hasil Utama** | Rekonstruksi gambar akurat (MSE Loss ~0.015) dan klaster data yang jelas di ruang laten. |
| 💻 **Bahasa & Framework** | Python dengan **PyTorch**. |

---
### 🖼️ Hasil Visualisasi

#### Hasil Rekonstruksi
Model mampu merekonstruksi gambar dari data uji dengan tingkat kemiripan yang tinggi, menunjukkan bahwa fitur-fitur penting berhasil ditangkap oleh *encoder*.

![Hasil Rekonstruksi](https://i.imgur.com/your-reconstruction-image.png) 
*(Catatan: Ganti dengan screenshot hasil rekonstruksi Anda)*

#### Visualisasi Ruang Laten
Plot sebar dari ruang laten 2D menunjukkan model berhasil mengelompokkan item pakaian yang serupa secara berdekatan.

![Ruang Laten](https://i.imgur.com/your-latent-space-image.png) 
*(Catatan: Ganti dengan screenshot visualisasi laten Anda)*

---
### ⚙️ Cara Menjalankan

1.  **Prasyarat:**
    Pastikan Anda telah menginstal pustaka yang dibutuhkan:
    ```bash
    pip install torch torchvision pandas numpy matplotlib
    ```
2.  **Dataset:**
    Unduh dataset **Fashion MNIST** dari Kaggle dan pastikan file `fashion-mnist_train.csv` dan `fashion-mnist_test.csv` berada di direktori yang benar sesuai *path* di dalam *notebook*.

3.  **Jalankan Notebook:**
    Buka file `.ipynb` menggunakan Jupyter Notebook atau Google Colab, lalu jalankan setiap sel kode secara berurutan.

---
### 👤 Author

* **Nama:** Wafa Bila Syaefurokhman
* **Tugas:** Tugas Individu - Eksplorasi Autoencoder
