# ✈️🚆🚢 Klasifikasi Topik Transportasi Twitter (X)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/Deep%20Learning-TensorFlow%20%7C%20Keras-orange?logo=tensorflow&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Machine%20Learning-Scikit--Learn-F7931E?logo=scikit-learn&logoColor=white)
![Jupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange?logo=jupyter&logoColor=white)

> **Proyek Akhir Semester (UAS) - Big Data & Data Mining**
>
> Studi komparasi model Machine Learning dan Deep Learning untuk mengklasifikasikan tweet terkait moda transportasi liburan ke dalam kategori **Darat**, **Laut**, atau **Udara**.

## 📖 Latar Belakang

Media sosial, khususnya Twitter (sekarang X), merupakan sumber data tekstual yang kaya akan opini publik. Dalam konteks transportasi dan pariwisata, banyak pengguna membagikan pengalaman perjalanan mereka.

Proyek ini bertujuan untuk membangun model klasifikasi teks otomatis yang dapat membedakan topik pembicaraan mengenai moda transportasi:
1.  **🚊 Darat** Contoh: (Kereta, Bus, Mobil, Motor)
2.  **🚢 Laut** Contoh: (Kapal Feri, Speedboat)
3.  **✈️ Udara** Contoh: (Pesawat Terbang)

Tantangan utama dalam proyek ini adalah menangani data teks tidak terstruktur, *slang word*, dan ambiguitas bahasa dalam tweet berbahasa Indonesia.

---

## ⚙️ Metodologi

Proyek ini mengikuti alur kerja *Data Mining* sebagai berikut:

1.  **Data Collection**: Scraping data dari Twitter menggunakan kata kunci terkait transportasi dengan rentang waktu dataset historis (2009-2024).
2.  **Preprocessing**:
    * *Cleaning*: Menghapus URL, mention, hashtag, dan karakter spesial.
    * *Normalization*: Mengubah kata gaul (*slang*) menjadi kata baku menggunakan kamus `slang.csv`.
    * *Stopword Removal*: Menghapus kata umum yang tidak bermakna.
    * *Tokenization*: Memecah kalimat menjadi kata-kata.
3.  **Labeling**: Pelabelan otomatis berbasis aturan (*rule-based*) dan validasi manual.
4.  **Modeling**: Melatih dan membandingkan performa 4 algoritma berbeda.
5.  **Evaluation**: Mengukur akurasi model pada data uji.

---

## 📊 Hasil Evaluasi Model

Berdasarkan eksperimen yang dilakukan, berikut adalah perbandingan akurasi dari model yang diuji:

| Peringkat | Model | Tipe | Akurasi | Keterangan |
| :---: | :--- | :--- | :---: | :--- |
| 🥇 | **CNN-1D** | Deep Learning | **97.5%** | Model Terbaik (Mampu menangkap fitur lokal teks) |
| 🥈 | **BiLSTM** | Deep Learning | **95.9%** | Baik dalam menangkap konteks urutan kata |
| 🥉 | **Logistic Regression**| Machine Learning | **95.0%** | Baseline yang kuat dan efisien |
| 4 | **Multinomial Naive Bayes**| Machine Learning | **86.1%** | Performa terendah dalam eksperimen ini |

> **Kesimpulan**: Model **CNN (Convolutional Neural Network)** terbukti paling efektif dalam mengklasifikasikan topik transportasi pada dataset ini.

---

## 📂 Struktur Repositori

```text
llm-twitter-transportation-topic-classification/
│
├── 📓 Revisi_Final_V2_UAS_BGTDMT.ipynb  # Notebook utama (Cleaning, Modeling, Evaluasi)
│
├── 📂 dataset_raw/                      # Data mentah hasil scraping (CSV per tahun/kategori)
│   ├── Darat/
│   ├── Laut/
│   └── Udara/
│
├── 📄 kamus.txt                         # Daftar kata dasar untuk stemming/validasi
├── 📄 slang.csv                         # Kamus normalisasi bahasa gaul
└── 📄 README.md                         # Dokumentasi proyek ini
