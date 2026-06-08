# scikit-learn CookBook O'Rielly

Repository ini berisi kumpulan materi praktis dan latihan *Machine Learning* yang diimplementasikan menggunakan Python dan library **scikit-learn**. Terdapat 13 bab (chapter) yang mencakup seluruh alur kerja machine learning mulai dari persiapan data, pemodelan (supervised & unsupervised), evaluasi model, hingga siap dideploy ke lingkungan produksi.


Link buku : https://drive.google.com/file/d/1b7mWwNMYWxOVwnWbPZd8_njVXAgGEMQR/view?usp=sharing
---

## 📌 Daftar Isi & Ringkasan Chapter

Berikut adalah ringkasan umum dari setiap chapter yang ada di dalam repository ini:

### [Chapter 01 - Common Conventions and API Elements of scikit-learn]
Membahas prinsip dasar desain API scikit-learn seperti *Consistency, Simplicity, Modularity,* dan *Reusability*. Chapter ini menjelaskan siklus hidup objek utama scikit-learn:
* **Estimator:** Menggunakan `fit()` untuk belajar dari data dan `predict()` untuk menghasilkan prediksi.
* **Transformer:** Menggunakan `transform()` atau `fit_transform()` untuk manipulasi data (seperti scaling).
* **Pipeline:** Menggabungkan preprocessing dan pemodelan dalam satu workflow otomatis.
* **Hyperparameter Tuning:** Pengantar optimasi model menggunakan `GridSearchCV`.

### [Chapter 02 - Pre-Model Workflow and Data Preprocessing]
Fokus pada pembersihan dan penyiapan data mentah sebelum dilatih. Topik utama meliputi:
* **Handling Missing Values:** Menggunakan `SimpleImputer`, `KNNImputer`, dan `IterativeImputer`.
* **Feature Scaling:** Standardisasi dan normalisasi data.
* **Categorical Encoding:** One-Hot Encoding dan Ordinal Encoding.
* **Pipeline Integration:** Menyusun preprocessing agar terhindar dari *data leakage*.

### [Chapter 03 - Dimensionality Reduction Techniques]
Membahas metode reduksi dimensi untuk mengatasi *curse of dimensionality* (masalah fitur terlalu banyak) dengan tetap mempertahankan variansi informasi. Teknik yang dipelajari:
* **Principal Component Analysis (PCA):** Reduksi dimensi tanpa pengawasan (unsupervised) berbasis variansi.
* **Linear Discriminant Analysis (LDA):** Reduksi dimensi terawasi (supervised) untuk memaksimalkan keterpisahan antar kelas.
* **t-SNE:** Visualisasi data berdimensi tinggi ke ruang 2D/3D.

### [Chapter 04 - Building Models with Distance Metrics and Nearest Neighbors]
Mempelajari algoritma klasifikasi berbasis kedekatan jarak, khususnya **K-Nearest Neighbors (KNN)**.
* **Distance Metrics:** Memahami perbedaan jarak Euclidean, Manhattan, dan Minkowski.
* **Model Parameters:** Mempelajari pengaruh nilai `k` terhadap bias dan variansi model.
* **Data Scaling:** Mengapa scaling fitur sangat krusial sebelum menjalankan model berbasis jarak.

### [Chapter 05 - Linear Models and Regularization]
Membahas model regresi linear dan cara mengatasi overfitting menggunakan teknik regularisasi:
* **Linear Regression:** Konsep koefisien, intercept, residual, serta metrik evaluasi seperti MSE, MAE, dan $R^2$.
* **Regularisasi:** Ridge Regression (L2 penalty) untuk memperkecil koefisien, Lasso Regression (L1 penalty) untuk seleksi fitur (koefisien nol), dan ElasticNet (kombinasi L1 & L2).
* **Polynomial Regression:** Mengembangkan model linear untuk menangani hubungan non-linear.

### [Chapter 06 - Advanced Logistic Regression and Extensions]
Mengembangkan algoritma **Logistic Regression** untuk masalah klasifikasi biner dan multikelas:
* **Logistic Regression:** Log-odds, fungsi sigmoid, dan probabilitas keputusan.
* **Multiclass Strategies:** Perbedaan pendekatan *One-vs-Rest (OvR)* dan *Multinomial Logistic Regression*.
* **Regularisasi L1/L2** pada klasifikasi logistic regression.
* **Multilabel Classification:** Klasifikasi di mana satu sampel dapat memiliki lebih dari satu label.

### [Chapter 07 - Support Vector Machines and Kernel Methods]
Mempelajari **Support Vector Machines (SVM)** untuk klasifikasi (`SVC`) dan regresi (`SVR`):
* **Hyperplane & Margin:** Konsep pencarian decision boundary dengan margin maksimal dibantu *support vectors*.
* **Kernel Trick:** Memetakan data non-linear ke dimensi yang lebih tinggi menggunakan kernel Linear, Polynomial, dan RBF.
* **Tuning Hyperparameter:** Memahami dampak parameter regularisasi `C` dan parameter kernel `gamma`.

### [Chapter 08 - Tree-Based Algorithms and Ensemble Method]
Membahas algoritma berbasis pohon keputusan (*decision trees*) dan metode ansambel (*ensemble*):
* **Decision Tree:** Kriteria split menggunakan *Gini Impurity* dan *Entropy*.
* **Ensemble Methods:**
  * **Bagging (Bootstrap Aggregating):** Random Forest untuk menurunkan variansi model dan menghitung *feature importance*.
  * **Boosting:** Gradient Boosting Machine (GBM) untuk mengurangi bias secara sekuensial.
  * **Stacking:** Menggabungkan prediksi beberapa model dasar menggunakan meta-model.

### [Chapter 09 - Text Processing and Multiclass Classification]
Membahas alur pemrosesan data teks agar dapat dipahami oleh algoritma machine learning:
* **Text Vectorization:** Mengubah string menjadi angka dengan *Bag of Words* (`CountVectorizer`) dan *TF-IDF* (`TfidfVectorizer`).
* **Text Preprocessing:** Konsep corpus, tokenisasi, n-grams, stopwords, dan POS-tagging sederhana.
* **Text Classification:** Membangun pipeline klasifikasi teks multikelas.

### [Chapter 10 - Clustering Techniques]
Masuk ke konsep *unsupervised learning* untuk mengelompokkan data berdasarkan karakteristik kemiripan:
* **Centroid-Based:** K-Means clustering dan penggunaan *Elbow Method* untuk menentukan jumlah cluster $k$ terbaik.
* **Connectivity-Based:** Hierarchical Clustering (Agglomerative) dan pembacaan *dendrogram*.
* **Density-Based:** DBSCAN untuk mendeteksi cluster dengan bentuk non-convex dan menyaring noise.
* **Evaluasi Cluster:** Silhouette Score, Davies-Bouldin Index, Adjusted Rand Index (ARI), dan Calinski-Harabasz Index.
* **Teknik Lanjutan:** Spectral Clustering dan Gaussian Mixture Model (GMM).

### [Chapter 11 - Outlier and Novelty Detection]
Mempelajari cara mendeteksi anomali pada data:
* **Outlier Detection:** Mendeteksi anomali pada data training yang tercemar menggunakan **Local Outlier Factor (LOF)** berbasis densitas dan **Isolation Forest** berbasis partitioning.
* **Novelty Detection:** Mengidentifikasi apakah data baru menyimpang dari pola normal menggunakan **One-Class SVM** (dilatih hanya dengan data normal).
* **Evaluasi & Penanganan:** Matrik evaluasi anomali dan strategi penanganannya.

### [Chapter 12 - Cross Validation and Model Evaluation Techniques]
Fokus pada metode evaluasi performa model yang stabil dan jujur:
* **Cross-Validation:** Konsep *K-Fold*, *Stratified K-Fold* (untuk kelas tidak seimbang), dan *Leave-One-Out (LOO)*.
* **Nested Cross-Validation:** Memisahkan hyperparameter tuning dari evaluasi performa guna menghindari bias data leakage.
* **Tuning Hyperparameter:** GridSearchCV vs RandomizedSearchCV.
* **Curves Analysis:** Menggunakan *Learning Curve* dan *Validation Curve* untuk mendeteksi masalah underfitting dan overfitting.

### [Chapter 13 - Deploying scikit-learn Models in Production]
Membahas implementasi model di dunia nyata dan konsep MLOps dasar:
* **Model Serialization:** Menyimpan dan memuat model dengan `joblib` dan `pickle`.
* **Latency & Throughput:** Mengukur performa komputasi inferensi (single vs batch prediction).
* **Parallel Processing:** Memanfaatkan CPU multi-core dengan `n_jobs`.
* **Incremental Learning:** Melatih model secara bertahap pada data streaming menggunakan `partial_fit()`.
* **CI/CD/CT Logic:** Pembuatan gerbang kualitas otomatis (*deployment gates*) sebelum model dideploy ke produksi.

---

## 🛠️ Teknologi & Kebutuhan Sistem

Proyek ini dibangun menggunakan pustaka Python berikut:
* **Python** (versi 3.8+)
* **scikit-learn** (API pemodelan utama)
* **numpy** & **pandas** (pemrosesan data)
* **matplotlib** & **seaborn** (visualisasi data)
* **joblib** (serialisasi model)

---

## 🚀 Cara Menjalankan Notebook


1. **Buat virtual environment (opsional tetapi direkomendasikan):**
   ```bash
   python -m venv env
   # Aktifkan di Windows:
   .\env\Scripts\activate
   # Aktifkan di macOS/Linux:
   source env/bin/activate
   ```

2. **Install dependensi yang diperlukan:**
   ```bash
   pip install numpy pandas scikit-learn matplotlib seaborn joblib notebook
   ```

3. **Jalankan Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```
   Pilih salah satu notebook dari daftar untuk mulai mempelajari materi.
