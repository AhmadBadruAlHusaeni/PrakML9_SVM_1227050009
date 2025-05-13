# 📝 Sentiment Analysis dengan SVM

## 🎯 Tujuan Proyek

Proyek ini bertujuan untuk melakukan analisis sentimen (positif/negatif) pada data teks menggunakan algoritma **Support Vector Machine (SVM)** dengan pendekatan **CountVectorizer + TruncatedSVD**. Dataset yang digunakan adalah `Training.txt` yang berisi label dan teks ulasan.

---

## 🧰 Teknologi & Library

- Python
- pandas, numpy
- nltk (untuk stopwords)
- scikit-learn
- seaborn, matplotlib

---

## 📂 Struktur Dataset

Dataset `Training.txt` berisi:

- Kolom 1: Label (0 = negatif, 1 = positif)
- Kolom 2: Ulasan dalam bentuk teks

---

## 🔄 Langkah-Langkah Implementasi

### 1. Import Library

Semua library penting untuk NLP dan machine learning diimpor, termasuk downloader untuk stopwords dari `nltk`.

### 2. Preprocessing

- Mengubah huruf menjadi lowercase
- Menghapus tanda baca
- Menghapus stopwords bahasa Inggris

Contoh:

```
Input : "I really love this movie!!!"
Output: "really love movie"
```

### 3. Feature Extraction

- Menggunakan `CountVectorizer` dengan `ngram_range=(1,2)` untuk menangkap konteks dua kata
- Fitur dikurangi dimensinya dengan `TruncatedSVD` (100 komponen)

### 4. Model

- Model menggunakan **SVM dengan kernel RBF** (`SVC(kernel='rbf')`)
- Pipeline dibuat agar proses training lebih efisien

### 5. Evaluasi

Model dievaluasi dengan:

- Classification Report (precision, recall, f1-score)
- Confusion Matrix
- Weighted F1 Score
- Visualisasi matrix dengan heatmap

---

## 📊 Contoh Output Evaluasi

```
Classification Report:
              precision    recall  f1-score   support

    0       0.80      0.85      0.82        20
    1       0.88      0.84      0.86        30

    accuracy                           0.84        50
   macro avg       0.84      0.84      0.84        50
weighted avg       0.85      0.84      0.84        50

F1 Score: 0.84
```

---

## 🧠 Catatan Penting

- `nltk.download('stopwords')` dijalankan otomatis agar preprocessing tidak gagal
- Pipeline dan `TruncatedSVD` membuat model scalable dan lebih cepat
- Kernel `'rbf'` dipilih sebagai variasi dari model SVM biasa

---

## 🚀 Pengembangan Selanjutnya

- Menambahkan GridSearchCV untuk tuning hyperparameter
- Mencoba balancing dataset (SMOTE)
- Membandingkan performa dengan model lain seperti Naive Bayes atau Logistic Regression

---

## 📁 Cara Menjalankan

1. Pastikan `Training.txt` ada di direktori yang sama
2. Jalankan script Python
3. Hasil evaluasi dan visualisasi akan tampil di console dan plot

---

© 2025 | Analisis Sentimen dengan SVM oleh \[AHMAD BADRU AL HUSAENI]
