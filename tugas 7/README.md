# Implementasi Generative Adversarial Network (GAN)

### Deskripsi Proyek
Proyek ini bertujuan untuk mengimplementasikan Generative Adversarial Network (GAN) menggunakan kerangka kerja PyTorch guna menghasilkan gambar yang realistis. Dalam proyek ini, kami melatih dua jaringan saraf, yaitu Generator dan Discriminator, yang bekerja secara kompetitif. Generator berfungsi untuk menciptakan gambar baru yang menyerupai data asli, sementara Discriminator bertugas untuk membedakan antara gambar asli dan gambar yang dihasilkan oleh Generator. Proses pelatihan dilakukan menggunakan dataset gambar sederhana, dengan tujuan menghasilkan output visual yang realistis dan berkualitas tinggi.

Tujuan utama dari proyek ini adalah untuk memahami konsep dasar GAN dan menerapkan pelatihan *adversarial* untuk menghasilkan *output* visual.

### Anggota Kelompok

* Jauhan Ahmad
* Mauludha Fiozaki
* Muhammad Abbas Al-Badowi
* Muhammad Setya Adjie
* Sabri Mutiur
* Wafa Bila Syaefurokhman


### Cara Menjalankan Kode
1.  **Lingkungan:** Pastikan Anda memiliki Python, PyTorch, dan Torchvision terinstal. Jika menggunakan Kaggle, *library* ini biasanya sudah tersedia.
2.  **Dataset:** Pastikan dataset gambar sederhana (seperti yang Anda gunakan) tersedia di lingkungan Anda.
3.  **Eksekusi:** Buka `gan_kelompokX.ipynb` di Jupyter atau Kaggle. Jalankan setiap sel secara berurutan untuk membuat file `.py` yang diperlukan (`models.py`, `utils.py`, `dataset.py`) dan menjalankan *training loop* utama.
4.  **Hasil:** Selama dan setelah pelatihan, gambar hasil *generate* akan disimpan di folder `generated_images/` dan model akan disimpan di folder `models/`.
