# Fine-tuning BERT for Text Classification & Emotion Detection

Proyek ini berisi dua eksperimen fine-tuning model **BERT-base-uncased** untuk tugas klasifikasi teks:
1. **Task 1 – AG News Topic Classification (Single-label, 4 kelas)**
2. **Task 1A – GoEmotions Emotion Detection (Multi-label, 28 emosi)**

Model dilatih menggunakan dataset publik dari HuggingFace Datasets dan dievaluasi menggunakan metrik klasifikasi standar.

---

## 1. Task 1 – AG News Classification

### 📌 Deskripsi
Klasifikasi berita ke dalam 4 kategori:
- World
- Sports
- Business
- Sci/Tech

### ⚙️ Konfigurasi Training
| Parameter | Nilai |
|----------|------|
| Model | bert-base-uncased |
| Max sequence length | 128 |
| Epochs | 3 |
| Learning rate | 2e-5 |
| Train batch size | 16 |
| Eval batch size | 32 |
| Weight decay | 0.01 |

### 📊 Ukuran Dataset
| Split | Jumlah Data |
|------|------------|
| Train | 108,000 |
| Validation | 12,000 |
| Test | 7,600 |

### 📈 Hasil Evaluasi

| Split | Loss | Accuracy | Macro-F1 |
|------|-----|---------|----------|
| Validation | 0.1883 | **94.85%** | 0.9483 |
| Test | 0.1965 | **94.55%** | 0.9455 |

**Kesimpulan:**  
Model BERT berhasil melakukan klasifikasi topik berita dengan performa sangat tinggi (>94% accuracy), menunjukkan kemampuan generalisasi yang baik pada data test.

---

## 2. Task 1A – GoEmotions Multi-label Emotion Classification

### 📌 Deskripsi
Tugas multi-label classification untuk mendeteksi 28 jenis emosi dalam satu kalimat.

### ⚙️ Konfigurasi Training
| Parameter | Nilai |
|----------|------|
| Model | bert-base-uncased |
| Max sequence length | 128 |
| Epochs | 3 |
| Learning rate | 2e-5 |
| Train batch size | 16 |
| Eval batch size | 32 |
| Weight decay | 0.01 |

### 📊 Ukuran Dataset
| Split | Jumlah Data |
|------|------------|
| Train | 168,980 |
| Validation | 21,122 |
| Test | 21,123 |

### 📈 Hasil Evaluasi

| Split | Loss | Micro-F1 | Macro-F1 | Micro-Precision | Micro-Recall |
|------|-----|----------|----------|----------------|--------------|
| Validation | 0.1105 | 0.3760 | 0.2867 | 0.5948 | 0.2749 |
| Test | 0.1109 | **0.3771** | 0.2846 | 0.5989 | 0.2752 |

**Kesimpulan:**  
Model mampu mengenali berbagai emosi secara multi-label, namun masih memiliki Macro-F1 yang relatif rendah karena ketidakseimbangan distribusi label (class imbalance) dan kompleksitas multi-label learning.

---

## 🧠 Kesimpulan Umum
- BERT sangat efektif untuk tugas **single-label classification** (AG News).
- Untuk **multi-label emotion detection**, performa cukup baik namun masih dapat ditingkatkan dengan teknik lanjutan seperti:
  - Class weighting
  - Focal loss
  - Threshold tuning
  - Data augmentation

---

## 📦 Teknologi
- Python
- PyTorch
- HuggingFace Transformers & Datasets
- Scikit-learn
