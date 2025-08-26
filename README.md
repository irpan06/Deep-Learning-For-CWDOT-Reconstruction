# Penerapan CNN-UNET Sebagai Metode Rekonstruksi Pada Sistem CWDOT

Repositori ini berisi kode dan sumber daya untuk penelitian skripsi saya di Departemen Fisika, Universitas Airlangga, yang berfokus pada pengembangan metode rekonstruksi pada sistem *Continuous Wave Diffuse Optical Tomography* (CW-DOT) menggunakan *deep learning*.

---

### **Demonstrasi Hasil**

Berikut adalah perbandingan visual antara metode rekonstruksi konvensional (LSL) dengan model yang diusulkan.

![Perbandingan Hasil](outputs/figures/model-predict.png)
*(Gambar di atas menunjukkan bagaimana Model menghasilkan gambar yang mendekati objek asli)*

---

### **Metodologi**

Penelitian ini menggunakan pipeline dua tahap:
1.  **Model A (Rekonstruksi Awal):** Sebuah model CNN Encoder-Decoder yang mengubah data pengukuran mentah (sinogram 16x16) menjadi citra rekonstruksi awal (64x64).
2.  **Model B (Optimasi & Super-Resolution):** Sebuah arsitektur U-Net yang menerima output dari Model A dan merefinisinya menjadi citra akhir yang lebih tajam dan akurat.

---

### **Instalasi & Setup**

Untuk menjalankan proyek ini, pastikan Anda memiliki Python 3.8+ dan pustaka yang diperlukan.

1.  **Clone repositori ini:**
    ```bash
    git clone [https://github.com/nama-anda/proyek-skripsi-dot.git](https://github.com/nama-anda/proyek-skripsi-dot.git)
    cd proyek-skripsi-dot
    ```

2.  **Buat environment virtual (disarankan):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # Untuk Windows: venv\Scripts\activate
    ```

3.  **Install semua dependensi:**
    ```bash
    pip install -r requirements.txt
    ```

---

### **Cara Menggunakan**

1.  **Generate Dataset:** Jalankan skrip `src/01_generate_dataset.py` untuk membuat data simulasi.
2.  **Latih Model A:** Jalankan `src/03_train_model_a.py`.
3.  **Latih Model B:** Jalankan `src/04_train_model_b.py`.
4.  **Evaluasi Model:** Gunakan notebook `notebooks/02_visualisasi_hasil_model.ipynb` untuk memuat model yang telah dilatih dan mengevaluasi hasilnya.

---

### **Hasil**

Pipeline yang diusulkan berhasil mengungguli metode LSL secara signifikan, dengan peningkatan skor **Dice Coefficient** dari **(skor LSL)** menjadi **(skor Model B)** pada data uji.

---

### **Sitasi & Ucapan Terima Kasih**

* Simulasi numerik dijalankan menggunakan perangkat lunak yang dikembangkan oleh [Nama Peneliti, Tahun].
* Terima kasih kepada dosen pembimbing, Dr. Nuril Ukhrowiyah, M.Si dan Yhosep Gita Yhun Yhuwana, S.Si., M.T., atas bimbingan dan masukannya.
