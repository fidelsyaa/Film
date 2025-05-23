# Laporan Proyek Machine Learning - Fidel Lusiana Putri

## Project Overview

Sistem rekomendasi adalah alat yang sangat berguna dalam aplikasi berbasis data, yang dapat memudahkan pengguna untuk menemukan pilihan yang relevan, baik itu produk, film, musik, atau lainnya[[1]](https://ejournal.undip.ac.id/index.php/jmasif/article/view/31482) [[2]](https://ejournal.unsrat.ac.id/index.php/decartesian/article/view/28274). Dalam hal ini, kita akan fokus pada pembuatan sistem rekomendasi film. Sistem rekomendasi film bertujuan untuk memberikan saran film kepada pengguna berdasarkan preferensi atau interaksi mereka dengan platform[[1]](https://ejournal.undip.ac.id/index.php/jmasif/article/view/31482) [[2]](https://ejournal.unsrat.ac.id/index.php/decartesian/article/view/28274).

Seiring dengan berkembangnya platform streaming, seperti Netflix, Hulu, dan Amazon Prime, kemampuan untuk menyediakan rekomendasi film yang sesuai dengan preferensi individu menjadi sangat penting. Rekomendasi yang baik dapat meningkatkan pengalaman pengguna, meningkatkan kepuasan pelanggan, dan meningkatkan waktu yang dihabiskan di platform tersebut [[2]](https://ejournal.unsrat.ac.id/index.php/decartesian/article/view/28274) [[3]](https://lintar.untar.ac.id/repository/penelitian/buktipenelitian_10393012_4A040824110850.pdf). Dengan berbagai film yang tersedia, pengguna sering kali merasa kewalahan untuk memilih film yang sesuai [[2]](https://ejournal.unsrat.ac.id/index.php/decartesian/article/view/28274) [[4]](https://j-ptiik.ub.ac.id/index.php/j-ptiik/article/view/9163). Oleh karena itu, sistem rekomendasi dapat membantu mengatasi masalah ini.

Sistem rekomendasi film ini bertujuan untuk membantu pengguna dengan memberikan rekomendasi film yang relevan berdasarkan dua pendekatan utama dalam teknik sistem rekomendasi[[5]](https://online-journal.unja.ac.id/msa/article/view/32136):

1. Content-Based Filtering: Pendekatan ini mengandalkan atribut atau fitur film itu sendiri, seperti genre, sutradara, atau aktor, untuk memberikan rekomendasi film yang mirip dengan film yang sebelumnya disukai atau dinilai oleh pengguna. Contohnya, jika seorang pengguna menyukai film bergenre aksi, maka sistem akan merekomendasikan film aksi lainnya.

2. Collaborative Filtering: Pendekatan ini mengandalkan data interaksi antar pengguna, seperti rating film, untuk menemukan pola preferensi yang sama antara pengguna yang memiliki perilaku serupa. Dengan pendekatan ini, sistem dapat memberikan rekomendasi film yang disukai oleh pengguna lain dengan selera serupa[[1]](https://ejournal.undip.ac.id/index.php/jmasif/article/view/31482).

Sistem rekomendasi film ini penting karena:

- Personalization: Membantu memberikan pengalaman yang lebih personal kepada setiap pengguna berdasarkan preferensi mereka.

- Efisiensi Waktu: Mempercepat proses pencarian film bagi pengguna dengan menyarankan pilihan yang relevan, mengurangi waktu yang dihabiskan untuk mencari.

- Peningkatan Retensi: Platform dengan rekomendasi yang baik akan lebih cenderung meningkatkan tingkat kepuasan dan membuat pengguna kembali untuk menonton lebih banyak film.

Menurut riset[[6]](https://ieeexplore.ieee.org/abstract/document/1423975), penerapan sistem rekomendasi berbasis collaborative filtering dan content-based filtering telah terbukti efektif dalam meningkatkan kualitas rekomendasi dan mengatasi masalah “cold-start” yang sering muncul, yaitu ketika data interaksi pengguna terbatas atau baru.

Dengan mengembangkan sistem rekomendasi berbasis content-based filtering dan collaborative filtering, proyek ini bertujuan untuk meningkatkan pengalaman pengguna dengan memberikan rekomendasi film yang lebih relevan dan menarik berdasarkan data yang tersedia.

### Referensi

[1] A. H. Ritdrix and P. W. Wirawan, “Sistem Rekomendasi Buku Menggunakan metode item-based collaborative filtering,” JURNAL MASYARAKAT INFORMATIKA, vol. 9, no. 2, pp. 24–32, Nov. 2018. doi:10.14710/jmasif.9.2.31482 

[2] V. L. Jaja, B. Susanto, and L. R. Sasongko, “Penerapan Metode Item-Based Collaborative Filtering Untuk Sistem Rekomendasi Data MovieLens”, dCJMA, vol. 9, no. 2, pp. 78–83, Sep. 2020.

[3] D. A. Nugroho, C. Lubis, and N. J. Perdana, “Sistem rekomendasi film menggunakan metode neural collaborative filtering,” Journal of Information Technology and Computer Science (INTECOMS), vol. 7, no. 3, pp. 926–937, 2024.

[4] M. Fajriansyah, P. P. Adikara, dan A. W. Widodo, “Sistem Rekomendasi Film Menggunakan Content Based Filtering”, J-PTIIK, vol. 5, no. 6, hlm. 2188–2199, Mei 2021.

[5] T. Ridwansyah, B. Subartini, and S. Sylviani, “Penerapan metode content-based filtering Pada Sistem Rekomendasi,” Mathematical Sciences and Applications Journal, vol. 4, no. 2, pp. 70–77, Apr. 2024. doi:10.22437/msa.v4i2.32136 

[6] G. Adomavicius and A. Tuzhilin, "Toward the next generation of recommender systems: a survey of the state-of-the-art and possible extensions," in IEEE Transactions on Knowledge and Data Engineering, vol. 17, no. 6, pp. 734-749, June 2005, doi: 10.1109/TKDE.2005.99.

## Business Understanding

### Problem Statements
Sistem rekomendasi telah menjadi komponen krusial dalam berbagai platform digital, terutama di layanan streaming seperti Netflix, Disney+, dan Amazon Prime Video. Namun, terdapat beberapa tantangan yang perlu dipecahkan agar sistem rekomendasi bisa bekerja secara efektif:

- Cold-Start Problem: Bagaimana cara memberikan rekomendasi kepada pengguna baru yang belum memiliki histori interaksi atau rating?
- Data Sparsity: Banyak pengguna hanya memberikan rating terhadap sedikit film, sehingga menyulitkan sistem untuk menemukan pola yang akurat.
- Personalized Recommendation: Bagaimana sistem bisa memberikan saran film yang benar-benar sesuai dengan preferensi pengguna secara individual?
- Scalability: Bagaimana membuat sistem yang mampu menangani jumlah pengguna dan film yang terus bertambah secara efisien?

### Goals
Tujuan utama dari proyek ini adalah membangun sistem rekomendasi film yang efektif dan personal, dengan target sebagai berikut:
- Mengatasi Cold-Start Problem dengan pendekatan berbasis konten (content-based), yang bisa memberikan rekomendasi meskipun pengguna belum pernah memberikan rating.
- Menghasilkan Rekomendasi yang Personalized berdasarkan kesamaan preferensi antar pengguna menggunakan teknik collaborative filterin
- Meningkatkan Akurasi Rekomendasi dengan memanfaatkan kombinasi dua pendekatan sistem rekomendasi yang berbeda.
- Menguji dan Mengevaluasi Performa Sistem dengan metrik yang tepat untuk mengukur efektivitas prediksi rekomendasi.

### Solution statements
Untuk menyelesaikan permasalahan di atas dan mencapai tujuan yang telah ditentukan, dua pendekatan utama digunakan dalam sistem rekomendasi ini:

1. Content-Based Filtering
   Pendekatan ini merekomendasikan film yang serupa dengan film yang disukai oleh pengguna di masa lalu, berdasarkan metadata film seperti genre. Dalam proyek ini digunakan:
   - TF-IDF Vectorization untuk merepresentasikan genre sebagai fitur numerik.
   - Cosine Similarity untuk mengukur tingkat kemiripan antar film. 
2. Collaborative Filtering (RecommenderNet)
   Pendekatan ini menggunakan histori interaksi pengguna (rating) dan pola perilaku pengguna lain untuk memberikan rekomendasi. Model yang digunakan adalah RecommenderNet, sebuah neural network sederhana berbasis embedding.

Dengan kombinasi kedua pendekatan di atas, sistem rekomendasi diharapkan dapat:
- Mengakomodasi pengguna baru (dengan content-based),
- Memberikan rekomendasi yang akurat untuk pengguna aktif (dengan collaborative filtering),
- Menyediakan pengalaman pengguna yang lebih menyenangkan secara menyeluruh.

## Data Understanding
Dataset yang digunakan dalam proyek ini diambil dari MovieLens Latest Dataset, yang disediakan oleh GroupLens Research. MovieLens merupakan salah satu dataset benchmark yang paling banyak digunakan untuk pengembangan dan evaluasi sistem rekomendasi, karena memiliki struktur data yang jelas dan kualitas anotasi yang tinggi.

📎 Link Dataset: https://grouplens.org/datasets/movielens/latest/

Versi yang digunakan: ml-latest-small.zip
- Jumlah data rating: 100,836
- Jumlah pengguna: 610
- Jumlah film: 9,742

  Data menunjukkan adanya sparsity, yaitu sebagian besar pengguna hanya memberi rating ke sebagian kecil film yang tersedia — kondisi ini umum pada sistem rekomendasi berbasis pengguna.

Data yang saya pakai untuk membuat sistem rekomendasi ini yaitu movie.csv dan ratings.csv:

### 1. movies.csv

jumlah data: 9742 rows × 3 columns

![Cuplikan layar 2025-04-30 132357](https://github.com/user-attachments/assets/9151e4ac-6bf9-4991-8400-cd4f77991615)

| Kolom  | Deskripsi  |
|---|---|
|  movieId |  ID unik film (tipe: integer)|
| title  | Judul film beserta tahun rilis (tipe: object) |
|  genres | Genre film  (bisa lebih dari satu, dipisah dengan “|”) |

Deskripsi statistik untuk dataset movies.csv dilihat pada gambar di bawah ini.
- Min: 1
- Max: 193609
- Standar deviasi: 35530.99
- Kuartil:
  - 25%: 1199
  - 50%: 2991
  - 75%: 8122

Artinya:
   1. Film yang dirating tersebar sangat luas dengan ID film sangat tinggi (hingga 193609), meskipun total film hanya sekitar 9742.
   2.  Banyak ID film kosong atau meloncat dalam dataset (misalnya karena penghapusan atau subset dari database lebih besar).
   3.  Sebagian besar rating terkonsentrasi di film dengan ID kecil (Q3 = 8122).
  
  ![Cuplikan layar 2025-04-30 134117](https://github.com/user-attachments/assets/e58b71c5-2cc0-455b-94f1-da94f6f22731)

### 2. ratings.csv

jumlah data: 100836 rows × 4 columns

![Cuplikan layar 2025-04-30 132616](https://github.com/user-attachments/assets/f82e6d8c-e8fc-4430-8426-0757f0a81c34)

|  Kolom | 	Deskripsi |
|---|---|
|  userId | ID unik pengguna (1–610)  |
| movieId  | 	ID film yang diberi rating oleh pengguna  |
| rating  | Nilai rating yang diberikan (skala: 0.5 – 5.0)  |
| timestamp  | Waktu rating diberikan (format UNIX time)  |

Deskripsi statistik untuk dataset ratings.csv dilihat pada gambar di bawah ini.
- Jumlah pengguna: 610 pengguna unik
- Min (terendah): 1
- Max (tertinggi): 610
- Rata-rata (mean): 326.13
- Standar deviasi (std): 182.62
- Kuartil:
   - 25% (Q1): 177
   - 50% (Median/Q2): 325
   - 75% (Q3): 477

Artinya User ID tersebar merata dari 1 hingga 610, Median dan mean hampir sama, menunjukkan distribusi ID cukup seimbang.

![Cuplikan layar 2025-04-30 134127](https://github.com/user-attachments/assets/2b9071c2-ee5f-43de-a182-e1415dfbf50b)

### - Distribusi Rating

![download](https://github.com/user-attachments/assets/3bd7b9a5-6709-4363-baa8-ca5e98ec272f)

- Histogram dan KDE menunjukkan:
   - Mayoritas rating berada pada 3.0 hingga 5.0
   - Distribusi cenderung ke kanan (positif) → artinya pengguna lebih sering memberi rating tinggi
   - Sedikit pengguna memberi rating sangat rendah (0.5–1.0)

### - Genre Film Paling Populer

![download (1)](https://github.com/user-attachments/assets/91c0e8f9-ecc9-4201-8feb-1cbbf81a27a7)

Visualisasi bar chart menunjukkan Top 10 Genre Film berdasarkan jumlah kemunculannya, Genre Drama dan Comedy mendominasi konten film dalam dataset. Drama adalah genre paling sering muncul (lebih dari 4000 film), Diikuti oleh Comedy, Thriller, dan Action. Hal ini umum karena kedua genre ini banyak diproduksi dan mudah diakses.

### - Statistik Rating Film Populer
Tabel ini menunjukkan 10 film dengan rating rata-rata tertinggi yang memiliki jumlah rating cukup tinggi:

![Cuplikan layar 2025-04-30 134236](https://github.com/user-attachments/assets/664f609e-1acc-4fd3-aafe-046d4759870f)

Film dengan rating tinggi dan rating count tinggi menandakan film tersebut populer dan disukai pengguna, Film-film ini juga kebanyakan merupakan film klasik dan terkenal secara global.

## Data Preparation

Pada tahap ini, dilakukan serangkaian langkah preprocessing untuk memastikan bahwa data dalam kondisi yang bersih, konsisten, dan siap digunakan dalam proses modeling. Berikut ini tahapan data preparation yang dilakukan:

   1.  Pengecekan Missing Value
         - **Teknik**: isnull().sum()
          - **Proses**: Saya memeriksa adanya nilai kosong atau missing value pada kedua dataset, yaitu movies dan ratings. Hasil pengecekan menunjukkan bahwa tidak terdapat nilai kosong pada kedua dataset:

![Cuplikan layar 2025-04-30 134243](https://github.com/user-attachments/assets/823e1c1a-24e7-48e4-b3f5-d7cce32ac6bf)

Pengecekan missing value penting dilakukan agar tidak ada nilai yang hilang saat proses analisis dan modeling. Missing value yang tidak ditangani dapat menyebabkan error atau hasil prediksi yang tidak akurat.

   2. Pengecekan dan Penanganan Duplikasi
      - **Teknik**: duplicated()
      - **Proses**: Pemeriksaan dilakukan untuk memastikan tidak ada entri duplikat yang dapat menyebabkan bias dalam model rekomendasi. Berikut pengecekan duplikasi berdasarkan kolom unik:

![Cuplikan layar 2025-04-30 134249](https://github.com/user-attachments/assets/82cbc285-e0f2-4e55-8a46-e9ceee815648)

Data yang duplikat bisa memberikan bobot berlebih terhadap item tertentu, yang dapat menyebabkan bias model dan rekomendasi yang tidak akurat. Oleh karena itu, penting memastikan data unik.

   3. Cleaning Kolom 'genres'
      - **Teknik**: replace()
      - **Proses**: Pada dataset movies, terdapat 34 film dengan entri "(no genres listed)" di kolom genres. Hal ini dapat menyulitkan sistem rekomendasi berbasis konten karena genre menjadi salah satu fitur utama. Oleh karena itu, nilai tersebut diganti dengan label 'Unknown'.
     
![Cuplikan layar 2025-04-30 134257](https://github.com/user-attachments/assets/f15863cd-b802-4c0d-80f8-bd39522ecf9c)

Pembersihan genre penting untuk menjaga konsistensi data. Dengan mengganti nilai yang tidak informatif ((no genres listed)) menjadi 'Unknown', sistem dapat tetap mengolah data tersebut tanpa kesalahan, dan tetap memungkinkan untuk dimasukkan dalam pemrosesan genre saat menggunakan teknik seperti TF-IDF untuk content-based filtering.

#### - Content Based Filltering Preparation
1. Inisialisasi TfidfVectorizer
   
Proses ini mengonversi teks genre menjadi representasi numerik yang bisa digunakan dalam Content-Based Filtering. Setiap film nanti akan direpresentasikan sebagai vektor TF-IDF berdasarkan genre-nya, yang bisa digunakan untuk menghitung kemiripan antar film menggunakan cosine similarity.

      tf.get_feature_names_out()
   
Ini menghasilkan daftar kata unik (fitur) yang ditemukan dan diproses oleh TfidfVectorizer. Output yang ditampilkan:

![Cuplikan layar 2025-05-07 105749](https://github.com/user-attachments/assets/2e5af275-b698-44a4-98bd-2e0c5d51f4b2)

2. Mengubah Sparse Matrix menjadi Dense Matrix
   
tfidf_matrix awalnya adalah sparse matrix (karena sebagian besar nilainya nol). Fungsi .todense() mengubahnya menjadi dense matrix (semua nilai ditampilkan, termasuk nol).
         
![Cuplikan layar 2025-05-07 110155](https://github.com/user-attachments/assets/30ddde2f-a4e1-49e0-90e6-cf32e29896be)

3. Ekstraksi Fitur dengan TF-IDF Vectorizer
   
      - Menggunakan TfidfVectorizer dari sklearn.feature_extraction.text untuk mengubah informasi genres pada dataset movies menjadi vektor numerik.
      - TF-IDF (Term Frequency-Inverse Document Frequency) menghitung pentingnya sebuah kata (genre) dalam sebuah dokumen (film) relatif terhadap seluruh korpus.
      - Hasil: matriks TF-IDF berukuran (9742, 22) — menunjukkan 9742 film dan 22 genre unik.
      - Matriks ini kemudian divisualisasikan menggunakan DataFrame agar bisa dievaluasi secara manual.
     
![Cuplikan layar 2025-05-04 022901](https://github.com/user-attachments/assets/f8314bcb-6edb-483d-a4dd-ad3f46d41798)

#### Collaborative Filltering Preparation
1. Encode Label
Mengubah userId dan movieId dari nilai aslinya (yang bisa berupa angka besar atau tidak berurutan) menjadi angka indeks kecil dan berurutan mulai dari 0 agar efisien digunakan dalam model, terutama model yang menggunakan embedding layer seperti RecommenderNet atau matrix factorization.
2. Split Data
Tahap ini dilakukan dengan membagi data dengan rasio 80:20, di mana 80% untuk data latih (training data) dan 20% sisanya adalah untuk data uji (validation data).

## Modeling

Permasalahan yang ingin diselesaikan adalah bagaimana merekomendasikan film kepada pengguna secara personal berdasarkan preferensi mereka sebelumnya. Sistem rekomendasi dirancang untuk membantu pengguna menemukan film yang relevan tanpa harus mencarinya secara manual di antara ribuan pilihan yang tersedia.
Untuk itu, dibangun dua pendekatan algoritma berbeda dalam sistem rekomendasi, yaitu:
- Content-Based Filtering menggunakan TF-IDF dan Cosine Similarity
- Collaborative Filtering menggunakan RecommenderNet (model embedding + dot product berbasis neural network)

### 1. Content-Based Filtering
   - Penghitungan Similarity
     - Menggunakan cosine_similarity untuk mengukur kemiripan antar film berdasarkan vektor genre-nya.
     - Hasil cosine similarity: cosine_sim_df berukuran (9742, 9742) menandakan telah menghitung kemiripan antar seluruh film. Ini mendukung sistem yang cepat memberikan rekomendasi berbasis konten.
      ![Cuplikan layar 2025-05-04 023038](https://github.com/user-attachments/assets/e1c00e39-b899-42fa-aa6f-05cc8caefa1b)


   - Pembuatan Fungsi Rekomendasi
     - Membuat fungsi content_recommendations(title) untuk menghasilkan top-10 film terdekat (paling mirip secara konten) berdasarkan kemiripan cosine.
     - Rekomendasi untuk "Toy Story": Hasil yang ditampilkan sangat relevan (film animasi lain), menunjukkan bahwa model ini bekerja dengan baik.
       
   ![Cuplikan layar 2025-05-04 023046](https://github.com/user-attachments/assets/d055652c-d175-4e3a-a09b-f70211b77626)

Rekomendasi dihasilkan melalui perhitungan cosine similarity antara representasi film "Toy Story (1995)" dengan seluruh film lain dalam dataset, menggunakan representasi TF-IDF dari genre. Semakin tinggi nilai cosine similarity, semakin mirip film tersebut dengan Toy Story (1995) berdasarkan genre-nya.

Semua film di atas memiliki genre yang hampir identik dengan Toy Story (1995), yaitu:

Adventure | Animation | Children | Comedy | Fantasy

Dengan demikian, Kesamaan genre sangat tinggi — semua film direkomendasikan karena genre-nya persis sama. Ini menunjukkan bahwa content-based filtering bekerja dengan baik jika pengguna menyukai film dengan genre spesifik yang konsisten.


### 2. Collaborative Filtering
- Encode user dan movie ke dalam bentuk angka (index), agar bisa digunakan sebagai input embedding.
- Bangun model RecommenderNet:
  - Embedding Layer untuk merepresentasikan user dan movie dalam vektor berdimensi rendah.
  - Dot Product antar embedding untuk memprediksi skor rating.
  - Split Training: Tahap ini dilakukan dengan membagi data dengan rasio 80:20, di mana 80% untuk data latih (training data) dan 20% sisanya adalah untuk data uji (validation data).
  - Sistem dilatih dengan data rating untuk mempelajari preferensi pengguna.
  - Hasil Rekomendasi :
![Cuplikan layar 2025-05-04 023159](https://github.com/user-attachments/assets/18a77a3f-4585-4810-ac36-1361de3bf6e8)

Berdasarkan hasil di atas, RecommenderNet berhasil mempelajari pola preferensi pengguna secara implisit, bukan hanya dari genre film yang ditonton, tetapi dari perilaku pengguna lain dengan minat serupa. Rekomendasi yang dihasilkan memperhitungkan kesamaan pola rating antar pengguna, sehingga mampu menyarankan film yang relevan meskipun berbeda genre secara eksplisit.

Bagian: Movies with high ratings from user
Ini adalah daftar film yang telah diberi rating tinggi oleh user ke-1. Film-film ini menjadi fondasi penting dalam Collaborative Filtering karena merepresentasikan preferensi pengguna. Contohnya:
- Rob Roy (1995) – Action, Drama, Romance, War
- X-Men (2000) – Action, Adventure, Sci-Fi
- Road Warrior, The (Mad Max 2) (1981) – Action, Adventure, Sci-Fi, Thriller

Bagian 2: "Top 10 movie recommendation"
Berikut adalah rekomendasi film yang diberikan oleh model RecommenderNet untuk pengguna ini. Model merekomendasikan berdasarkan pola preferensi pengguna lain yang memiliki kesamaan perilaku rating. Misalnya:
- Star Wars: Episode VI - Return of the Jedi (1983) – Action, Adventure, Sci-Fi
- Mummy, The (1999) – Action, Adventure, Comedy, Fantasy, Horror, Thriller
- Gladiator (2000) – Action, Adventure, Drama
- Pinocchio (1940) – Animation, Children, Fantasy, Musical

Rekomendasi ini tidak semata-mata mirip dari sisi genre, namun secara tidak langsung menunjukkan pola ketertarikan yang serupa, seperti pada genre action, adventure, hingga thriller. Ini menunjukkan bahwa model mampu memberikan saran yang personalized dengan mengandalkan kemiripan perilaku antar pengguna, bukan hanya konten film.

Dari pendekatan yang sudahdiambil, berikut beberapa kelebihan dan kekuarangannya:
#### 1. Content-Based Filtering (CBF)
Sistem menganalisis konten dari item (film) seperti genre, deskripsi, atau kata kunci. Dalam kasus ini, digunakan TF-IDF untuk representasi genre, dan Cosine Similarity untuk mengukur kemiripan antar film.

✅ Kelebihan:
1. Tidak bergantung pada data pengguna lain (independen):
Sistem hanya membutuhkan informasi dari item yang disukai pengguna, sehingga bisa bekerja dengan baik bahkan jika hanya ada satu pengguna (solusi cold-start untuk user).

3. Bisa dijelaskan (interpretable):
Rekomendasi dapat dijelaskan dengan logika “karena kamu menyukai film dengan genre X, maka kamu mungkin menyukai film ini yang juga bergenre X.”

5. Cocok untuk sistem yang ingin menonjolkan kesamaan konten:
Misalnya, menyarankan film dengan genre yang sama, sutradara yang sama, atau sinopsis yang serupa.

7. Cepat dan ringan:
Setelah preprocessing (TF-IDF matrix dan similarity matrix terbentuk), sistem bekerja sangat cepat.

❌ Kekurangan:
1. Kurang personalisasi terhadap selera kolektif pengguna:
Sistem tidak memanfaatkan pola kesukaan pengguna lain. Akibatnya, sistem hanya merekomendasikan film yang sangat mirip, tanpa menangkap potensi eksplorasi selera baru.

2. Tidak memperhitungkan kualitas atau popularitas:
Semua item diperlakukan setara selama genre-nya mirip, meskipun film tersebut memiliki rating buruk.

3. Bisa terlalu sempit (overspecialization):
Rekomendasi cenderung berputar pada konten yang terlalu mirip, dan mengurangi keberagaman.

5. Butuh fitur konten yang lengkap:
Jika metadata (genre, deskripsi) tidak tersedia atau tidak akurat, kualitas rekomendasi menurun drastis.

#### 2. Collaborative Filtering (RecommenderNet – Deep Learning Embedding Based)
Menggunakan user-item interaction matrix (dalam hal ini, rating film oleh pengguna) dan model embedding neural network (RecommenderNet) untuk mempelajari representasi laten (hidden preferences) dari user dan item.

✅ Kelebihan:
1. Memberikan personalisasi mendalam:
Sistem belajar dari pola perilaku pengguna secara implisit, bukan hanya berdasarkan konten yang tampak. Misalnya, jika dua pengguna menyukai film berbeda tetapi memberi rating serupa, sistem bisa mengenali bahwa mereka punya selera yang mirip.

2. Rekomendasi lebih variatif:
Tidak hanya menyarankan film yang mirip secara konten, tapi bisa menyarankan film yang disukai pengguna dengan pola serupa meski genre-nya berbeda.

3. Bisa menangkap hubungan kompleks user-item:
Dengan neural network, model mampu belajar representasi fitur kompleks dan non-linear yang sulit ditangkap oleh algoritma klasik.

5. Berskala besar dan efisien setelah pelatihan:
Setelah model dilatih, rekomendasi bisa dihasilkan dengan cepat menggunakan dot product antara embedding.

❌ Kekurangan:

1. Cold-Start Problem:
   - User baru tanpa riwayat interaksi tidak bisa langsung diberikan rekomendasi akurat.
   - Item baru (film baru tanpa rating) juga sulit direkomendasikan karena belum memiliki embedding representatif.
     
2. Butuh dataset yang cukup besar dan bersih:
Model belajar dari data interaksi, sehingga kualitas sangat tergantung pada jumlah dan keakuratan data rating.

3. Lebih kompleks:
Memerlukan proses pelatihan (training) dan tuning parameter. Juga butuh pemahaman arsitektur model (embedding size, loss function, epoch, dll).

4. Kurang interpretatif:
Sulit menjelaskan mengapa sebuah film direkomendasikan. Model hanya menunjukkan bahwa berdasarkan vektor laten, film itu cocok untuk user, tanpa penjelasan eksplisit seperti genre.

## Evaluation
Untuk mengevaluasi performa kedua pendekatan yang digunakan, dipilih metrik evaluasi sebagai berikut:
### a. Content-Based Filtering
- Precision: Mengukur proporsi item yang relevan dari 10 item yang direkomendasikan.
  - formula:
    
    Precision@10 = Jumlah item relevan yang direkomendasikan pada top-K / K

       - Untuk setiap pengguna, sistem merekomendasikan 10 film teratas berdasarkan kemiripan konten (genre, sinopsis, dll.).
      - Precision@10 mengukur berapa banyak dari 10 film tersebut yang benar-benar disukai pengguna (misalnya yang pernah diberi rating tinggi).
      - Misalnya, dari 10 film yang direkomendasikan berdasarkan Toy Story (1995), semuanya memiliki genre yang tumpang tindih (seperti Animation, Adventure, atau Children), sehingga precision@10 = 10 / 10 = 1.00.
      - Semakin tinggi precision@10, semakin tepat sasaran sistem dalam memberikan rekomendasi.

- Recall: Mengukur proporsi item relevan yang berhasil ditemukan oleh sistem dalam 10 item teratas.
  - formula:

      Recall@10 = Jumlah item relevan yang direkomendasikan pada top-K / Total item relevan yang tersedia

    - Misalnya, Toy Story (1995) memiliki 3 genre utama. Jika genre-genre tersebut berhasil ter-cover secara konsisten di rekomendasi, recall bisa lebih tinggi dari 1.
    - Dalam kasus ini, recall@10 = 2.00, yang berarti rekomendasi tidak hanya mencakup seluruh genre input, tapi bahkan mengulang atau memperkuat keterkaitan tersebut lebih dari satu kali..
    - Recall@10 mengukur kelengkapan rekomendasi — seberapa baik sistem “meng-cover” film yang benar-benar disukai pengguna.

  - F1-Score: Harmonic mean dari precision dan recall.
    - formula:
![Cuplikan layar 2025-05-01 213017](https://github.com/user-attachments/assets/162c2975-c4af-4975-9256-c6a67713a934)

F1-Score@10 sangat berguna untuk mengevaluasi sistem rekomendasi secara menyeluruh — terutama jika tidak ingin terlalu berat ke precision atau recall saja.

### b. Collaborative Filtering (RecommenderNet)
- Root Mean Squared Error (RMSE): Mengukur seberapa jauh prediksi model dari rating sebenarnya. Lebih sensitif terhadap kesalahan besar.

![Cuplikan layar 2025-05-01 213437](https://github.com/user-attachments/assets/cb9741fe-a936-47c3-83d5-b516e6014a99)

  
- Mean Absolute Error (MAE): Rata-rata dari selisih absolut antara nilai aktual dan prediksi. Lebih stabil terhadap outlier.
      
​![Cuplikan layar 2025-05-01 213444](https://github.com/user-attachments/assets/2792aacb-9499-469b-9651-7e86a99a76b0)

- Visualisasi Loss – Model Collaborative Filtering (RecommenderNet)

![Cuplikan layar 2025-05-04 024252](https://github.com/user-attachments/assets/d87bfae0-66cf-4bca-a326-1a1a68921e37)

   - Pada beberapa epoch pertama, terjadi penurunan loss yang signifikan, kemudian kurva mulai melandai.
   - Training loss terus menurun hingga mendekati nol, sementara validation loss stabil di kisaran 1.5.
   - Hal ini menunjukkan bahwa model tidak mengalami overfitting secara signifikan.

### Hasil Evaluasi Model
Content-Based Filtering:
- Precision@10 = 1.00 → Dari 10 film yang direkomendasikan, semuanya memiliki kemiripan genre dengan film input (Toy Story (1995)).
- Recall@10 = 2.00 → Model berhasil menangkap lebih dari satu kemiripan genre dari film input, menunjukkan bahwa rekomendasi mencakup berbagai aspek genre yang relevan.
- F1-Score@10 = 1.33 → Menandakan keseimbangan precision dan recall yang sangat tinggi. Ini menunjukkan bahwa pendekatan berbasis konten mampu memberikan rekomendasi yang sangat relevan dalam konteks genre.

Film dianggap relevan jika memiliki setidaknya satu genre yang sama dengan film input.
Misalnya, jika Toy Story (1995) memiliki genre Animation|Children|Comedy, maka film yang memiliki salah satu dari genre tersebut (misalnya Animation, Comedy, atau Children) dianggap relevan.

Semakin banyak genre yang tumpang tindih, semakin besar kemungkinan film tersebut cocok dengan preferensi pengguna.

Collaborative Filtering (RecommenderNet):
- RMSE = 1.2572 → Nilai ini menunjukkan bahwa rata-rata selisih antara rating yang diprediksi oleh model dan rating sebenarnya adalah sekitar ±1.26 poin.
Karena skala rating berkisar dari 0.5 hingga 5.0, maka deviasi ini masih tergolong cukup wajar.
RMSE memperbesar penalti untuk kesalahan besar — jadi nilai ini mengindikasikan bahwa sebagian besar prediksi model tidak terlalu jauh meleset, meskipun ada beberapa kasus yang meleset cukup besar.
- MAE = 0.9256 → MAE mengukur rata-rata selisih absolut antara rating aktual dan rating hasil prediksi, tanpa memperbesar pengaruh kesalahan ekstrem seperti pada RMSE.
Dengan nilai MAE sekitar 0.93, artinya prediksi model rata-rata meleset kurang dari 1 poin rating, yang merupakan performa cukup solid.
Ini menandakan bahwa model RecommenderNet mampu menangkap pola preferensi pengguna dengan cukup akurat, meskipun tidak sempurna.  

### Evaluasi Berdasarkan Business Understanding
Mengacu pada bagian Business Understanding, berikut evaluasi berdasarkan pernyataan masalah dan goals:
- Cold-Start Problem: Selesai dengan pendekatan Content-Based Filtering, yang memungkinkan rekomendasi tanpa histori rating.
- Data Sparsity: Collaborative Filtering dengan RecommenderNet mampu menangani sparsity dan memberikan rekomendasi meski data yang tersedia terbatas.
- Personalized Recommendation: Kedua metode memberikan rekomendasi yang sesuai dengan preferensi pengguna, dengan RecommenderNet lebih unggul dalam akurasi.
- Scalability: RecommenderNet dapat di-scale, meskipun untuk penggunaan besar perlu optimasi lebih lanjut.

### Evaluasi Terhadap Goals Proyek
- Sistem berhasil memberikan rekomendasi kepada pengguna baru melalui Content-Based Filtering.
- RecommenderNet menghasilkan rekomendasi yang lebih personal dan relevan dengan prediksi rating yang akurat.
- Penggabungan kedua pendekatan meningkatkan ketepatan dan ketahanan sistem dalam mengatasi berbagai masalah rekomendasi.
- Metrik yang digunakan (Precision, Recall, RMSE, MAE) sudah tepat untuk mengukur kualitas rekomendasi dan prediksi rating.

### Dampak Solusi
- Content-Based Filtering memberikan rekomendasi yang transparan dan bisa dijelaskan, sangat cocok untuk tahap awal user onboarding. Ini memberikan dampak nyata dalam mengatasi cold-start dan membangun kepercayaan pengguna awal.
- Collaborative Filtering via RecommenderNet memberikan hasil yang lebih dalam dan akurat dalam jangka panjang, memungkinkan sistem memahami pola kompleks preferensi pengguna berdasarkan histori interaksi.
- Gabungan dua pendekatan memperkuat sistem: content-based untuk kecepatan dan cold-start, collaborative untuk personalisasi dan akurasi prediktif.
 

