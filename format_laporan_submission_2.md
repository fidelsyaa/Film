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

1. **movies.csv**

![Cuplikan layar 2025-04-30 132357](https://github.com/user-attachments/assets/9151e4ac-6bf9-4991-8400-cd4f77991615)

| Kolom  | Deskripsi  |
|---|---|
|  movieId |  ID unik film |
| title  | Judul film beserta tahun rilis  |
|  genres | Genre film  |

2. **ratings.csv**

![Cuplikan layar 2025-04-30 132616](https://github.com/user-attachments/assets/f82e6d8c-e8fc-4430-8426-0757f0a81c34)

|  Kolom | 	Deskripsi |
|---|---|
|  userId | ID unik pengguna  |
| movieId  | 	ID film yang diberi rating oleh pengguna  |
| rating  | Nilai rating yang diberikan (skala: 0.5 – 5.0)  |
| timestamp  | Waktu rating diberikan (format UNIX time)  |



## Data Preparation

Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model sisten rekomendasi yang Anda buat untuk menyelesaikan permasalahan. Sajikan top-N recommendation sebagai output.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menyajikan dua solusi rekomendasi dengan algoritma yang berbeda.
- Menjelaskan kelebihan dan kekurangan dari solusi/pendekatan yang dipilih.

## Evaluation
Pada bagian ini Anda perlu menyebutkan metrik evaluasi yang digunakan. Kemudian, jelaskan hasil proyek berdasarkan metrik evaluasi tersebut.

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.
