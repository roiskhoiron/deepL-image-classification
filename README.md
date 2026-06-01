# Image Submission Classification

Klasifikasi gambar produk fashion menjadi 7 kategori menggunakan deep learning.

## Spesifikasi Model

- **Arsitektur:** Custom CNN (3 Conv2D + MaxPooling layers)
- **Input:** 128x128 pixels, 3 channels (RGB)
- **Output:** 7 kelas (Accessories, Apparel, Footwear, Free Items, Home, Personal Care, Sporting Goods)
- **Augmentasi:** RandomFlip, RandomRotation, RandomZoom
- **Optimizer:** Adam
- **Loss:** Sparse Categorical Crossentropy
- **Akurasi Test:** ~96%

## Format Model yang Tersedia

| Format | Lokasi | Keterangan |
|--------|--------|------------|
| TensorFlow SavedModel | `saved_model/` | Model original dengan augmentation |
| TensorFlow Lite | `tflite/model.tflite` + `label.txt` | Model lightweight untuk mobile/border |
| TensorFlow.js | `tfjs_model/model.json` + `group1-shard1of1.bin` | Model untuk web/browser |

## Struktur Folder

```
submission/
├── tfjs_model/
│   ├── group1-shard1of1.bin
│   └── model.json
├── tflite/
│   ├── model.tflite
│   └── label.txt
├── saved_model/
│   ├── saved_model.pb
│   └── variables/
├── notebook.ipynb
├── README.md
└── requirements.txt
```

## Cara Menjalankan

1. Buka `notebook.ipynb` di Jupyter atau Google Colab
2. Jalankan semua cell dari atas ke bawah
3. Notebook akan:
   - Mengunduh dataset dari Kaggle
   - Melatih model selama ~18 epoch (early stopping)
   - Mengevaluasi akurasi test
   - Menyimpan model dalam 3 format (SavedModel, TFLite, TFJS)

## Dataset

Sumber: [Kaggle - Fashion Product Images Small](https://www.kaggle.com/datasets/paramaggarwal/fashion-product-images-small)
- ~44,000 gambar produk fashion
- 7 kategori produk (masterCategory)
- Metadata dalam file `styles.csv`

## Author

- **Nama:** Rois Hoiron
- **Email:** rois.khoiron@gmail.com
- **ID Dicoding:** khoironrois
