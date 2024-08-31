# Tugas Resume 1 Visualisasi Data dan Informasi

**Nama : Raid Muhammad Naufal**\
**NIM : 122450027**\
**Kelas : RC**

# Introduction

Visualisasi data adalah alat penting dalam dunia bisnis yang didorong oleh data, di mana visualisasi membantu dalam pengambilan keputusan yang berdampak langsung pada pendapatan perusahaan. Dengan meningkatnya volume, kecepatan, dan keragaman data, kebutuhan akan metode visualisasi yang efisien dan efektif menjadi semakin mendesak. 

Proses visualisasi data dilakukan secara iteratif, yaitu:
1. Data import adalah mengambil data yang diperlukan dari sumber data yang diinginkan.
2. Data preparation adalah mempersiapkan data yang telah di-import untuk visualisasi, misalnya, menormalkan nilai, mengoreksi entri yang salah, dan menginterpolasi nilai yang hilang.
3. Data manipulation adalah memilih data yang akan divisualisasikan (alias penyaringan dari komunitas visualisasi) dan mungkin dengan operasi umum lainnya seperti penggabungan dan pengelompokan.
4. Mapping adalah memetakan data yang diperoleh dari proses di atas ke primitif geometris (misalnya, titik dan garis), bersama dengan atributnya (misalnya, warna, posisi, dan ukuran).
5. Rendering adalah mengubah data geometris menjadi
representasi visual.

# Visualization Specifications
## 1. The Specification of Data Visualizations
Visualisasi data terdiri dari tiga komponen utama:

Data: Mencakup data yang akan divisualisasikan, termasuk rekaman data dan transformasi data seperti pengelompokan, penyaringan, dan pengurutan.\
Marks (Tanda Visual): Representasi visual dari data, seperti batang, garis, atau titik, serta atribut seperti ukuran, warna, dan legenda.\
Mapping (Pemetaan): Menghubungkan data dengan tanda visual yang sesuai. Misalnya, memetakan kategori data ke sumbu X dan nilai numerik ke sumbu Y dalam grafik batang.

## 2. A Categorization of Data Visualization Languages
Bahasa visualisasi data dikategorikan berdasarkan tingkat ekspresivitas dan kemudahan penggunaannya. Bahasa tingkat rendah, seperti D3 dan Vega, memberikan pengguna kendali penuh untuk menentukan semua elemen pemetaan, memungkinkan fleksibilitas maksimum tetapi membutuhkan lebih banyak keahlian teknis. Di sisi lain, bahasa tingkat tinggi, seperti Vega-Lite dan ggplot2, menyediakan default yang lebih intuitif dan menyederhanakan proses pembuatan visualisasi, meskipun dengan fleksibilitas yang lebih sedikit.

Low-level Languages: Bahasa ini memungkinkan pengguna untuk menentukan setiap detail dari pemetaan data ke elemen visual. Contohnya termasuk D3 dan Vega, di mana pengguna harus menentukan fungsi pemetaan secara eksplisit.

High-level Languages: Bahasa ini lebih mudah digunakan karena mereka menyembunyikan banyak detail teknis dari pengguna dengan menyediakan default yang masuk akal. Contohnya termasuk Vega-Lite, yang memungkinkan pengguna untuk mendefinisikan visualisasi dengan spesifikasi minimal, dan ggplot2 yang didasarkan pada The Grammar of Graphics.

## 3. GUI-based Visual Operations
Selain menggunakan bahasa deklaratif untuk mendefinisikan visualisasi, spesifikasi visualisasi juga dapat dilakukan melalui operasi visual berbasis GUI (Graphical User Interface). Alat-alat seperti Tableau, Microsoft Power BI, dan Google Sheets memungkinkan pengguna untuk membuat visualisasi dengan cara menyeret dan meletakkan elemen data ke dalam kanvas visual. Pendekatan GUI ini sangat berguna bagi pengguna non-teknis karena lebih mudah diakses dan memungkinkan pembuatan visualisasi secara langsung tanpa perlu menulis kode.

Contoh Alat GUI: Tableau memungkinkan pengguna untuk menyeret atribut data ke sumbu X dan Y, serta memilih jenis grafik yang diinginkan melalui antarmuka visual, membuat proses ini lebih intuitif dibandingkan dengan penulisan kode manual.

## 4. Underspecified Specifications
Dalam banyak kasus, pengguna mungkin tidak sepenuhnya tahu bagaimana mereka ingin data mereka divisualisasikan. Oleh karena itu, sistem visualisasi perlu mendukung spesifikasi yang tidak lengkap (underspecified). Dalam pendekatan ini, pengguna memberikan petunjuk atau referensi, dan sistem akan melengkapi visualisasi tersebut atau memberikan rekomendasi berdasarkan petunjuk tersebut. Misalnya, pengguna bisa mengetik "tampilkan grafik garis tentang listrik" dan sistem akan merekomendasikan beberapa visualisasi yang relevan.

Contoh Spesifikasi Tidak Lengkap: Sistem seperti zenvisage menerima visualisasi referensi dari pengguna dan kemudian merekomendasikan visualisasi lain yang serupa atau berbeda berdasarkan tren yang ada.

#  Efficient Approaches for Data Visualization
## 1. Exact Data Visualization
Pendekatan visualisasi data tepat bertujuan untuk menghasilkan visualisasi yang akurat secepat mungkin dengan memanfaatkan sistem basis data yang ada. Salah satu cara umum adalah dengan menerjemahkan permintaan visualisasi (visualization queries) menjadi query SQL yang dapat dieksekusi oleh sistem basis data, sehingga menghasilkan visualisasi berbasis data yang tepat. Selain itu, metode lain untuk meningkatkan efisiensi adalah mengintegrasikan sistem visualisasi langsung dengan sistem manajemen basis data (DBMS). Dengan integrasi yang lebih erat ini, optimasi seperti penggunaan index dan penyimpanan berbasis kolom (column-stores) dapat mempercepat proses visualisasi, terutama saat menangani data besar. Beberapa sistem seperti Tableau menggunakan teknik kolom-stores dan indeks untuk mempercepat pengambilan data serta pengolahan query visualisasi.

Prediction and Prefetching, di mana sistem mencoba memprediksi visualisasi atau data apa yang akan dieksplorasi pengguna berikutnya, dan memuat data tersebut sebelumnya untuk mempercepat proses interaksi.

Parallel Computation, di mana komputasi paralel digunakan untuk memproses query visualisasi secara bersamaan, terutama ketika pengguna bekerja dengan beberapa visualisasi atau dimensi data.

## 2. Approximate Data Visualization
Untuk menangani data dalam jumlah besar yang sulit divisualisasikan secara real-time, teknik visualisasi perkiraan digunakan. Sistem ini memungkinkan pengguna melihat visualisasi sementara yang didasarkan pada sampel data, yang kemudian diperbaiki secara bertahap. Salah satu teknik yang sering digunakan adalah AQP (Approximate Query Processing), yang menggunakan representasi subset data untuk menghasilkan visualisasi cepat dengan pengorbanan akurasi. Sebagai contoh, sistem seperti Sample+Seek menggunakan sampling berbasis atribut agregasi untuk memberikan hasil visualisasi dalam batas kesalahan yang dapat diterima oleh pengguna. Meskipun tidak akurat sepenuhnya, visualisasi perkiraan ini memberikan gambaran awal yang dapat membantu pengguna dalam proses eksplorasi data.

## 3. Progressive Data Visualization
Visualisasi progresif adalah metode di mana visualisasi terus diperbaiki dari waktu ke waktu, dengan hasil awal yang memberikan wawasan kasar tentang data, dan semakin akurat saat proses berjalan. Teknik ini memanfaatkan struktur hierarkis untuk melakukan agregasi data pada level yang berbeda, memungkinkan pengguna untuk menjelajahi visualisasi pada resolusi yang berbeda. Sistem seperti imMens menggunakan teknik range-based binning, di mana data dibagi dalam bins dengan ukuran yang sama untuk mendukung eksplorasi data multidimensi. Proses ini memungkinkan pengguna untuk secara interaktif memperbesar (zoom in) atau memperkecil (zoom out) visualisasi sesuai dengan kebutuhan, sehingga memberikan kontrol lebih besar atas bagaimana data divisualisasikan secara progresif.

# Visualization Recommendation
Sistem rekomendasi visualisasi dirancang untuk meringankan beban pengguna dalam menentukan visualisasi yang paling relevan dan efektif. Proses visualisasi seringkali membutuhkan modifikasi yang berulang-ulang, dan sistem rekomendasi dapat menyarankan visualisasi yang mungkin paling sesuai berdasarkan spesifikasi yang tidak lengkap, perilaku pengguna, atau data yang ada. Dengan demikian, pengguna dapat lebih mudah menemukan visualisasi yang tepat tanpa harus mencoba berbagai opsi secara manual.

## 1. Specification-based Recommendations
Ada dua jenis pendekatan utama dalam rekomendasi berbasis spesifikasi:

### A. Spesifikasi Tidak Lengkap: 
Dalam pendekatan ini, sistem membantu pengguna yang mungkin tidak memiliki spesifikasi visualisasi yang lengkap. Sistem dapat mengisi kekosongan dalam spesifikasi visualisasi atau memberikan saran berdasarkan elemen-elemen yang telah disediakan oleh pengguna. Contohnya adalah sistem seperti APT dan Voyager, di mana pengguna hanya perlu menentukan beberapa elemen kunci seperti kolom data yang diinginkan, dan sistem akan merekomendasikan visualisasi yang sesuai.

Beberapa sistem rekomendasi visualisasi menggunakan pembelajaran mesin untuk meningkatkan ketepatan rekomendasi. Pendekatan ini melibatkan pelatihan model menggunakan data dari contoh-contoh visualisasi yang sudah ada. Model ini kemudian dapat digunakan untuk menilai dan meranking visualisasi baru berdasarkan preferensi yang dipelajari dari data pelatihan. Sistem seperti DeepEye dan Draco menggunakan teknik ini untuk mengidentifikasi visualisasi yang paling relevan dengan kebutuhan pengguna.

Draco: Draco menggunakan learning-to-rank dengan model RankSVM untuk mempelajari preferensi pengguna dari visualisasi yang sudah ada. Sistem ini mengandalkan soft constraints yang diatur oleh manusia untuk menentukan urutan visualisasi yang disarankan.

DeepEye: DeepEye menggabungkan pendekatan berbasis aturan dengan pembelajaran mesin untuk secara otomatis mengidentifikasi dan meranking visualisasi. DeepEye menggunakan model pembelajaran berbasis contoh untuk menentukan apakah visualisasi itu baik atau buruk, dan kemudian menggunakan model learning-to-rank untuk memberikan peringkat pada visualisasi yang baik.

Pendekatan berbasis aturan menggunakan metrik efektivitas perseptual atau aturan statistik untuk menilai dan meranking visualisasi. Misalnya, Voyager menggunakan aturan perseptual yang mempertimbangkan tipe data, jumlah data, dan preferensi visual manusia untuk menentukan visualisasi yang paling efektif. Sementara itu, Rank-by-Feature adalah sistem yang menggunakan metrik statistik untuk meranking visualisasi berdasarkan distribusi data dan deteksi anomali.

### B. Spesifikasi sebagai Referensi: 
Di sini, spesifikasi yang diberikan pengguna digunakan sebagai titik awal, dan sistem kemudian merekomendasikan visualisasi lain yang mungkin menarik berdasarkan visualisasi referensi. Contohnya adalah sistem zenvisage yang memungkinkan pengguna untuk memasukkan satu visualisasi sebagai referensi dan kemudian menerima saran visualisasi lain yang serupa atau menunjukkan tren yang berbeda.

## 2. Behavior-based Recommendations
Rekomendasi berbasis perilaku melibatkan analisis interaksi dan preferensi pengguna selama eksplorasi data. Sistem belajar dari perilaku pengguna sebelumnya untuk memberikan rekomendasi yang lebih personal dan relevan. Misalnya, jika pengguna cenderung memilih grafik garis untuk data temporal, sistem akan lebih cenderung merekomendasikan grafik garis untuk dataset serupa di masa depan.

## 3. Personalized Recommendations
Selain menawarkan rekomendasi berbasis aturan atau data, beberapa sistem juga memungkinkan personalisasi, di mana rekomendasi visualisasi disesuaikan dengan preferensi individual pengguna berdasarkan interaksi mereka sebelumnya dengan sistem. Ini membuat sistem semakin relevan dan berguna untuk pengguna yang sering bekerja dengan jenis data tertentu atau yang memiliki preferensi visual tertentu.

Secara keseluruhan, rekomendasi visualisasi memainkan peran penting dalam membantu pengguna menemukan dan membuat visualisasi yang paling sesuai dengan kebutuhan mereka. Dengan menggabungkan berbagai pendekatan, seperti spesifikasi tidak lengkap, analisis perilaku, pembelajaran mesin, dan aturan perseptual, sistem ini dapat memberikan saran yang lebih cerdas dan relevan, sehingga mempermudah proses eksplorasi dan analisis data.

# Other Research Directions 
## 1. Data Preparation for Data Visualization
Visualisasi data yang tidak dipersiapkan dengan baik bisa menyesatkan pengguna, terutama jika data tersebut "kotor" (dirty data). Masalah data seperti duplikasi, nilai yang hilang, dan pencilan dapat menyebabkan visualisasi yang bias. Oleh karena itu, penting untuk membersihkan data sebelum divisualisasikan, yang melibatkan proses seperti normalisasi nilai, deduplikasi, imputasi nilai yang hilang, dan deteksi outlier.

What-if Analysis for Outliers: Sistem seperti Scorpion memungkinkan pengguna untuk mengidentifikasi dan menghilangkan pencilan dari hasil query agregasi tanpa mempengaruhi data yang valid.\
Evaluating Visualizations with Missing Data: Studi dilakukan untuk mengukur faktor-faktor yang mempengaruhi akurasi respon dan kualitas data dalam visualisasi time series dengan data yang hilang. Studi ini juga meneliti berbagai metode imputasi seperti zero-filling dan interpolasi linear.

Peluang Penelitian:

Detecting Biased Visualizations: Mendeteksi visualisasi yang tampaknya baik tetapi sebenarnya bias adalah tantangan penting yang dapat dieksplorasi lebih lanjut, terutama dalam konteks data yang "kotor".\
Task-aware Data Cleaning: Pembersihan data yang disesuaikan dengan tugas tertentu dapat lebih efisien dibandingkan pembersihan data secara keseluruhan.

## 2. Data Visualization Benchmarks
Seperti halnya benchmark dalam bidang lain, penting untuk mengembangkan benchmark untuk mengukur kinerja dan kualitas rekomendasi visualisasi. Benchmark ini harus sesuai dengan tugas analisis visual, menyediakan data yang dapat digunakan kembali, dan memiliki cakupan serta kualitas label yang tinggi.

VizNet: Sebuah karya penelitian yang menyediakan korpus besar dari lebih dari 31 juta dataset dari repositori data terbuka dan galeri visualisasi online, yang bertujuan untuk menjadi baseline yang umum untuk membandingkan teknik desain visualisasi dan mengembangkan model benchmark.

Peluang Penelitian:

Categorization of Visualizations: Menentukan kategori untuk visualisasi seperti "trend" atau "distribution" masih menjadi tantangan, tidak seperti kategori objek pada gambar yang lebih mudah diidentifikasi.\
Training Data: Memberikan label pada visualisasi untuk melatih model pembelajaran mesin atau deep learning dalam memprediksi visualisasi yang baik untuk tugas tertentu adalah tugas yang kompleks.

## 3. Data Visualization for Database-related Applications
Visualisasi data juga memiliki peran penting dalam aplikasi terkait basis data seperti Excel, Google Sheets, dan Microsoft Power BI. Dengan perkembangan teknik visualisasi, ada lebih banyak peluang untuk menggunakan visualisasi data dalam aplikasi ini.

Peluang Penelitian:

Data Visualization for Data Discovery: Visualisasi data dapat membantu dalam memahami dataset yang ditemukan selama proses penemuan data dari "data lake" yang berisi ribuan atau jutaan silo data.\
Data Visualization for Data Debugging: Kombinasi visualisasi data dalam proses debugging data dapat membantu mengidentifikasi kesalahan dalam hasil analitik yang disebabkan oleh data yang salah, bukan bug dalam program.

# Conclusion
Dalam menghadapi tantangan data yang semakin kompleks, visualisasi data yang efisien dan efektif menjadi kunci dalam memaksimalkan potensi analisis data. Jurnal ini menekankan pentingnya integrasi antara sistem visualisasi dan basis data untuk menciptakan solusi visualisasi yang cepat dan responsif. Selain itu, teknik-teknik seperti visualisasi perkiraan, pengoptimalan berbasis persepsi manusia, dan rekomendasi berbasis pembelajaran mesin terbukti penting untuk mengatasi keterbatasan dalam proses visualisasi tradisional. Dengan adopsi pendekatan-pendekatan ini, visualisasi data dapat lebih diandalkan dan mudah diakses, memungkinkan pengguna untuk mendapatkan wawasan yang lebih mendalam dan mendukung pengambilan keputusan yang lebih baik dalam lingkungan data yang cepat berubah.