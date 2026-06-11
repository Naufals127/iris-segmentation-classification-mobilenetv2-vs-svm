# iris-segmentation-classification-mobilenetv2-vs-svm
Digital-Image-Processing-Project
---
Judl: "Segmentasi dan Klasifikasi Citra Iris menggunakan MobileNetV2 vs SVM"
author: "Guntoro Satriaji, Naufal Shalih, Indah Faizah Salsabillah Ramdhany Wadjo"
date: "`r Sys.Date()`"
output: github_document
---

## Gambaran Umum Proyek

Proyek ini mengimplementasikan sistem pengenalan iris yang terdiri atas tahapan **segmentasi iris**, **pra-pemrosesan citra**, **normalisasi menggunakan daugman rubber sheet** **ekstraksi fitur dan klasifikasi menggunakan MobileNetV2**, serta **klasifikasi menggunakan Support Vector Machine (SVM)**. Penelitian ini bertujuan untuk mengevaluasi efektivitas pemodelan metode **deep learning** dengan algoritma **machine learning** tradisional dalam tugas klasifikasi iris.

Iris merupakan salah satu karakteristik biometrik yang memiliki tingkat keunikan dan kestabilan tinggi, sehingga banyak digunakan dalam sistem identifikasi individu. Namun, variasi pencahayaan, keberadaan kelopak mata dan bulu mata, serta kualitas citra dapat memengaruhi kinerja sistem pengenalan iris. Oleh karena itu, proses segmentasi yang akurat dan metode ekstraksi fitur yang robust sangat diperlukan untuk meningkatkan performa klasifikasi.

## Alur Penelitian

Tahapan yang dilakukan dalam proyek ini meliputi:

1. **Akuisisi Data**
   - Mengumpulkan dataset citra iris dari sumber yang tersedia.

2. **Pra-pemrosesan Citra**
   - Specular Reflection Handling dan Contrast Limited Adaptive Histogram Equalization (CLAHE). 

3. **Segmentasi Iris**
   - Mengisolasi area iris dari bagian mata lainnya seperti sklera, kelopak mata, dan bulu mata.
   - Menghasilkan citra iris yang siap digunakan pada tahap ekstraksi fitur.

4. **Normalisasi (Daugman Rubber Sheet)**

5. **Augmentasi**
   - Teknik yang diaplikasikan meliputi pergeseran horizontal (horizontal shift), yang secara matematis ekuivalen dengan simulasi efek rotasi atau kemiringan sudut kamera pada citra mata asli, serta variasi kecerahan (brightness variation) untuk menyimulasikan kondisi intensitas cahaya yang berbeda di lingkungan nyata

6. **Pemodelan: MobileNetV2 & SVM**
   - Memanfaatkan MobileNetV2 yang telah dilatih pada dataset ImageNet sebagai *feature extractor* yang kemudian diklasifikasikan dengan head classififer MobileNetV2
   - Menerapkan Ekstraksi Fitur Log-Gabor sebagai *feature extractor* yang kemudian melatih model untuk klasifikasi dengan SVM

7. **Evaluasi Kinerja Model**
   - Accuracy
   - Precision
   - Recall
   - F1-Score
   - Confusion Matrix

## Tujuan Penelitian

- Melakukan segmentasi iris secara akurat dari citra masukan
- - Mengklasifikasikan citra iris menggunakan model Deep Learning MobileNetV2
- Mengekstraksi fitur iris menggunakan Log Gabor sebagai *feature extractor* untuk diklasifikasikan dengan SVM
- Mengevaluasi performa perbandingan MobileNetV2 dan SVM dalam sistem pengenalan iris

## Struktur Repository

```text
├── data/                   # Dataset citra iris
├── classification/         # Pelatihan Model
    ├── MobileNetV2
    ├──SVM
├── results/                # Hasil pengujian dan visualisasi
└── README.Rmd
```

## Lisensi

Proyek ini dikembangkan untuk tujuan pendidikan dan penelitian.
