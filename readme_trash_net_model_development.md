# TrashNet – Model Development Repository

Repository ini berisi **kode pengembangan dan eksperimen model** untuk klasifikasi citra sampah menggunakan dataset **TrashNet**. Fokus utama repository ini adalah eksplorasi arsitektur **MobileNet**, optimasi model, serta penerapan teknik kompresi untuk menghasilkan model yang efisien dan siap deploy.

> Repository ini **terpisah dari repository deployment** (Streamlit). Repository ini hanya mencakup proses training, evaluasi, dan optimasi model.

---

## Ruang Lingkup Model

Pengembangan model dalam repository ini mencakup beberapa pendekatan berikut:

### 1. MobileNet Baseline
- MobileNetV1
- MobileNetV2
- MobileNetV3 (Small & Large)

Model baseline digunakan sebagai pembanding performa dari sisi:
- Akurasi
- Waktu komputasi
- Ukuran model

---

### 2. Model Pruning
Penerapan **structured pruning** menggunakan `tensorflow_model_optimization` (tfmot) untuk:
- Mengurangi jumlah parameter
- Menekan ukuran model
- Mempertahankan akurasi semaksimal mungkin

Pruning diterapkan pada MobileNet, khususnya MobileNetV3.

---

### 3. Model Quantization
Optimasi lanjutan dengan **Post-Training Quantization**, meliputi:
- FP16 Quantization
- INT16 Quantization

Tujuan kuantisasi adalah meningkatkan efisiensi inferensi dan mengurangi ukuran model tanpa penurunan performa yang signifikan.

---

### 4. Model Hybrid (Final Model)
Model akhir yang dihasilkan merupakan kombinasi dari beberapa teknik optimasi:

**Hybrid Model:**
- MobileNetV3 Large
- Structured Pruning
- Quantization (FP16 / INT16)

Model ini dipilih sebagai model terbaik berdasarkan keseimbangan antara:
- Akurasi klasifikasi
- Ukuran model
- Waktu inferensi

---

## Struktur Repository

```
├── dataset/
│   ├── train/
│   ├── validation/
│   └── test/
│
├── notebooks/
│   ├── mobilenet_v1.ipynb
│   ├── mobilenet_v2.ipynb
│   ├── mobilenet_v3.ipynb
│   ├── pruning_experiment.ipynb
│   └── quantization_experiment.ipynb
│
├── models/
│   ├── baseline/
│   ├── pruned/
│   └── quantized/
│
├── utils/
│   ├── preprocessing.py
│   └── evaluation.py
│
├── requirements.txt
└── README.md
```

---

## Teknologi yang Digunakan

- Python
- TensorFlow 2.x
- TensorFlow Model Optimization Toolkit (tfmot)
- NumPy
- Pillow
- Jupyter Notebook

---

## Output Utama Repository

- Model MobileNetV1–V3 (baseline)
- Model hasil pruning
- Model hasil kuantisasi (FP16 & INT16)
- Model hybrid siap deploy (TFLite)

Model hasil akhir selanjutnya digunakan pada repository deployment berbasis Streamlit.

---

## Catatan

- Repository ini berfokus pada **eksperimen dan pengembangan model**, bukan antarmuka aplikasi.
- Seluruh preprocessing dan konfigurasi training disesuaikan dengan kebutuhan penelitian dan penulisan skripsi.

---

## Lisensi

Repository ini digunakan untuk keperluan akademik dan penelitian.

