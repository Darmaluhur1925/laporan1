# Laporan Proyek Machine Learning - ALIFIA ZUMROTUL NISA'

## Domain Proyek

Supermarket adalah toko dengan sistem pelayanan mandiri, menjual berbagai barang secara eceran ataupun grosir. Sebuah pencatatan pada bidang keuangan pada sebuah supermarket sangat diperlukan untuk mengetahui bagaimana perkembangan suatu penjualan pada supermarket tersebut. Adapun yang mempengaruhi suatu penjualan yakni dari segi tempat, harga per unit, kuantitas, serta tax yang berlaku.

mencatat pengeluaran bisnis dapat mengurangi resiko pada manajemen keuangan. Resiko ini dapat terjadi jika pengelolaan terhadap keuangan yang buruk. Dengan mencatat dan melacak pengeluaran setiap hari dapat mengontrol biaya. Hal ini juga berdampak pada laba yang dapat diterima. Dengan mengontrol biaya inilah, kita dapat menyiapkan disaat pajak mulai bertambah.

Dengan mempertimbangkan pentingnya pencatatan penjualan inilah, kita dapat dengan cepat menetukan serta memprediksi sebarap menguntungkan bisnis yang sedang dijalankan. Hal ini dapat mencegah kita terjebak dalam asumsi bias tentang profitabilitas bisnis. 

## Business Understanding


### Problem Statements

berdasarkan domain proyek diatas, didapat beberapa permasalahan sebagai berikut?
- Bagaimana cara menganalisis data penjualan?
- Bagaimana cara mengolah data tersebut agar dapat dilatih dengan baik oleh model?
- Bagaiana cara membangun model yang dapat memprediksi keuntungan penjualan yang dilakukan dengan tingkat akurasi yang baik?

### Goals

Tujuan dalam melakukan penelitian yakni sebagai berikut:
- Dapat mengetahui cara menganalisis data penjualan.
- Dapat mengetahui cara mengolah data agar dapat dilatih dengan baik oleh model.
- Dapat mengetahui cara membangun model yang dapat memprediksi keuntungan penjualan yang dilakukan dengan tingkat akurasi yang baik.



    ### Solution statements
     Dari rumusan masalah serta tujuan yang telah dipaparkan, berikut solusi yang dapat dilkukan.
  -Melakukan analisis data meliputi investigasi awal pada data mengenai karakteristik, pola, anomali, serta asumsi yang terdapat pada data. selain itu, analisis data dapat kita lakukan dengan menangani missing value serta menangani outliers. setelah itu, kita dapat mencari tau hubungan antara dua atau lebih variabel pada data. 
  -Menggunakan algoritma K-Nearest Neighbor, Random Forest, dan Boosting Algorithm pada data yang dijadikan menjadi model regresi yakni persamaan matematik yang dapat meramalkan nilai-nilai suatu variabel tak bebas dari nilai-nilai variabel bebas (Walpole, 1982: 340)
  -Melakukan evaluasi pada data yang telah kita proses pada ketiga algoritma sebelumnya yang berupa data tes dan train.
  
   ###Data Understanding
   Dataset yang digunakan pada proyek ini adalah dataset yang diambil dari website https://www.kaggle.com/ lebih tepatnya yaitu [https://www.kaggle.com/datasets/aungpyaeap/supermarket-sales]
   Dimana dataset yang digunakan memiliki format .csv dan mempunyai total 1001 records dan 17 columns.
### Berikut kolom-kolom yangg terdapat dalam data tersebut: Invoice ID,Branch,City,Customer type,Gender,Product line,Unit price,Quantity,Tax 5%,Total,Date,Time,Payment,cogs,gross margin percentage,gross income,Rating


**TAHAPAN MEMAHAMI DATA)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data
    Mempertanyakan hal yang berkaitan dengan analisis data;
    Mendalami permasalahan yang dibahas;
    Menentukan tujuan searah dengan output yang diinginkan.
## Data Preparation
teknik data preparation yang digunakan dalam mengolah data adalah sebagai berikut:
- Membuang jenis kolom dengan isi kategori, dan diganti menggunakan encoding yang nantinya dapat mengubah data menjadi suatu bentuk yang dapat diterima oleh penerima. 
- Melakukan reduksi dengan PCA yakni teknik pengurangan dimensi dengan mereduksi dimensi, mengekstraksi fitur, dan mentransformasi data "n-dimensional space" ke dalam sistem berkoordinat baru dengan dimensi m, dimana m lebih kecil dari n
- Membagi dataset menjadi data train dan data test. hal ini dipergunakan agar tidak mengotori data test dengan informasi yang didapat dari data train. 
- Melakukan standarisasi agar data yang masuk dapat diloah oleh algoritma dengan lebih mudah

## Modeling
Model yang digunakan pada proyek kali ini adalah model development, yaitu KNN, random forest, dan adaptive boosting.

-K-Nearest Neighbors (KNN) K-Nearest Neighbors atau KNN merupakan algoritma machine learning yang bekerja dengan mengklasifikasikan data baru menggunakan kemiripan antara data baru dengan sejumlah data (k) pada data yang telah ada. Algoritma ini dapat digunakan untuk klasifikasi dan regresi. Untuk hyperparameter yang digunakan pada model ini hanya 1 yaitu n_neighbors, hyperparameter ini adalah jumlah tetangga yang diperlukan untuk menentukan letak data baru. Dimana n_neighbors memiliki nilai sebesar 1 dan 10.
Kelebihan dari K-Nearest Neighbors (KNN) adalah dapat menerima data yang masih noisy, sangat efektif apabila jumlah datanya banyak, dan mudah diimplementasikan. Sedangkan kekurangan dari K-Nearest Neighbors (KNN) adalah sensitif pada outlier dan rentan pada fitur yang kurang informatif.
-Random Forest  merupakan salah satu metode dalam Decision Tree. Decision Tree atau pohon pengambil keputusan adalah sebuah diagram alir yang berbentuk seperti pohon yang memiliki sebuah root node yang digunakan untuk mengumpulkan data, 
Sebuah inner node yang berada pada root node yang berisi tentang pertanyaan tentang data dan  sebuah leaf node yang digunakan untuk memecahkan masalah serta membuat keputusan. Decision tree mengklasifikasikan suatu sampel data yang belum diketahui kelasnya kedalam kelas – kelas yang ada. Penggunaan decision tree agar dapat menghindari overfitting pada sebuah set data saat mencapai akurasi yang maksimum.
Random forest  adalah kombinasi dari  masing – masing tree yang baik kemudian dikombinasikan  ke dalam satu model. Random Forest bergantung pada sebuah nilai vector random dengan distribusi yang sama pada semua pohon yang masing masing decision tree memiliki kedalaman yang maksimal.
Random forest adalah classifier yang terdiri dari classifier yang berbentuk pohon {h(x, θ k ), k = 1, . . .} dimana θk adalah random vector yang diditribusikan secara independen dan masing masing tree pada sebuah unit kan memilih class yang paling popular pada input x.
-Adaptive boosting (adaboost) merupakan salah satu dari beberapa varian pada algoritma boosting [1]. Adaboost merupakan ensemble learning yang sering digunakan pada algoritma
boosting. Boosting bisa dikombinasikan dengan classifier algoritma yang lain untuk meningkatkan performa klasifikasi. Tentunya secara intuitif, penggabungan beberapa model akan membantu jika
model tersebut berbeda satu sama lain  Adaboost dan variannya telah sukses diterapkan pada beberapa bidang (domain) karena dasar teorinya yang kuat, presdiksi yang akurat, dan kesederhanaan yang besar.


## Evaluation
Untuk evaluasi pada proyek kali ini adalah menggunakan mse (mean squared error), dimana metrik tersebut digunakan untuk mengukur seberapa dekat garis pas dengan titik data.

![](https://user-images.githubusercontent.com/97511774/191058303-7e790b2b-31bc-45c8-890d-0d6e01b3a274.png)
![](![image](https://user-images.githubusercontent.com/113841726/192191572-bf98f0de-3a27-46a6-9722-f8ba77341867.png)
Berdasarkan tabel diatas, nilai mse pada model KNN lebih besar dibandingkan 2 model lainnya. hal ini dapat disimpulkan bahwa model RF dan Boosting lebih optimal dibandingkan dengan KNN.
oleh karena itu, model RF dan Boosting dapat dijadikan sebuah model yang dapat dipakai untuk memprediksi suatu penjualan yang dikemudian hari dapat membantu para pemilik bisnis dalam menentukan serta memprediksi bisnis yang dijalankannya
Dan dibawah ini merupakan hasil plot visualisasi mse (mean squared error).
![](![image](https://user-images.githubusercontent.com/113841726/192191825-5c2b6b68-7476-40bc-b1f7-359111704d08.png)



**Reference**
[https://algorit.ma/blog/exploratory-data-analysis-2022/]
[https://www.javatpoint.com/k-nearest-neighbor-algorithm-for-machine-learning]
[https://www.analyticsvidhya.com/blog/2021/09/adaboost-algorithm-a-complete-guide-for-beginners/]



