# Implementasi Generative Adversarial Network (GAN)

### Deskripsi Proyek
Proyek ini bertujuan untuk mengimplementasikan Generative Adversarial Network (GAN) menggunakan PyTorch. Kami melatih dua jaringan saraf (Generator dan Discriminator) dalam proses kompetitif untuk menghasilkan gambar yang realistis dari dataset gambar sederhana.

Tujuan utama dari proyek ini adalah untuk memahami konsep dasar GAN dan menerapkan pelatihan *adversarial* untuk menghasilkan *output* visual.

### Anggota Kelompok
* Wafa Bila Syaefurokhman
* Muhammad Abbas Al-Badowi
* Mauludha Fiozaki
* Jauhan Ahmad
* Sabri Mutiur
* Muhammad Setya Adjie

### Cara Menjalankan Kode
1.  **Lingkungan:** Pastikan Anda memiliki Python, PyTorch, dan Torchvision terinstal. Jika menggunakan Kaggle, *library* ini biasanya sudah tersedia.
2.  **Dataset:** Pastikan dataset gambar sederhana (seperti yang Anda gunakan) tersedia di lingkungan Anda.
3.  **Eksekusi:** Buka `gan_kelompokX.ipynb` di Jupyter atau Kaggle. Jalankan setiap sel secara berurutan untuk membuat file `.py` yang diperlukan (`models.py`, `utils.py`, `dataset.py`) dan menjalankan *training loop* utama.
4.  **Hasil:** Selama dan setelah pelatihan, gambar hasil *generate* akan disimpan di folder `generated_images/` dan model akan disimpan di folder `models/`.
