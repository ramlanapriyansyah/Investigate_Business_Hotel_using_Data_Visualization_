# Overview
Sangat penting bagi suatu perusahaan untuk selalu menganalisa performa bisnisnya. Pada kesempatan kali ini, kita akan lebih mendalami bisnis dalam bidang perhotelan. Fokus yang kita tuju adalah untuk mengetahui bagaimana perilaku pelanggan kita dalam melakukan pemesanan hotel, dan hubungannya terhadap tingkat pembatalan pemesanan hotel. Hasil dari insight yang kita temukan akan kita sajikan dalam bentuk data visualisasi agar lebih mudah dipahami dan bersifat lebih persuasif.

# Dataset dan Tools
Kumpulan data ini berisi informasi 119.390 pemesanan hotel dari tahun 2017 hingga 2019. Setiap baris mewakili satu pemesanan hotel.</br> 
Kedua hotel yang terdapat pada dataset ini terletak di Portugal: Resort Hotel berada di wilayah Algarve dan City Hotel berada di kota Lisbon.


Analisis dan visualisasi data dilakukan menggunakan bahasa pemrograman **Python**. 

# Data Preprocessing
## 1. Mengatasi Missing Values
Dalam mengatasi missing value atau nilai null dilakukan beberapa pendekatan yaitu:
- Menghapus kolom `company`. Hal tersebut dilakukan karena nilai null sangat banyak (lebih dari 50% data).
- Mengganti nilai null menjadi “Unknown” pada kolom `city` dan `agent`.
- Menghapus nilai null pada kolom `children`. Hal ini dikarenakan nilai null yang sedikit sehingga menghapusnya tidak mempengaruhi keterwakilan data.
## 2. Mengganti Nilai yang Tidak Sesuai
Mengganti nilai “Undefined” pada kolom `meal` menjadi “No Meal” dengan asumsi bahwa hotel yang tidak memberi keterangan meal memang tidak menyediakan meal.
## 3. Membuang Data yang Tidak Diperlukan
Menjumlahkan kolom `adults`, `children`, dan `babies` menjadi kolom baru dengan nama `total_guests`, kemudian membuang kolom-kolom yang sudah digabungkan tersebut.

Syntax selengkapnya dapat dilihat pada file berikut: [Data Preprocessing.ipynb](https://github.com/ramlanapriyansyah/Investigate_Business_Hotel_using_Data_Visualization_/blob/main/Data%20Preprocessing.ipynb)

# Analisis Booking Hotel Bulanan berdasarkan Tipe Hotel
<img width="900" alt="image" src="https://github.com/ramlanapriyansyah/Investigate_Business_Hotel_using_Data_Visualization_/assets/135192484/5a066676-b72d-4912-aa6b-e5af1101c6bb">


**Business Insight:**
1. Terjadi tren peningkatan jumlah booking dari bulan Maret hingga Juli pada periode tahun 2017-2019.</br>
   Hal ini diasumsikan karena bertepatan dengan musim semi dan musim panas di Portugal, yang mana hal itu merupakan waktu yang populer bagi para turis untuk berkunjung. Selain itu, di rentang waktu ini juga bertepatan dengan hari libur sekolah, yaitu *spring break* dan *summer vacation*, di beberapa negara.
2. Pada bulan Agustus hingga September pengunjung lebih memilih Resort Hotel dibandingkan City Hotel. </br>
Hal ini diasumsikan karena bertepatan dengan puncak musim panas dimana pengunjung lebih ingin untuk menikmati suasana resort seperti pesisir pantai.
3. Pada bulan Oktober hingga Desember pengunjung cenderung lebih memilih City Hotel dibandingkan Resort Hotel. </br>
Hal ini diasumsikan karena terjadi pergantian musim dan mulai memasuki awal musim dingin sehingga pengunjung lebih memilih untuk bermalam di City Hotel dibandingkan Resort Hotel.

Syntax selengkapnya dapat dilihat pada file berikut: [Monthly Hotel Booking Analysis.ipynb](https://github.com/ramlanapriyansyah/Investigate_Business_Hotel_using_Data_Visualization_/blob/main/Monthly%20Hotel%20Booking%20Analysis.ipynb)

# Analisis Hubungan antara Lama Menginap (*Stay Duration*) dan Tingkat Pembatalan Pesanan (*Cancellation Rates*)
<img width="900" alt="image" src="https://github.com/ramlanapriyansyah/Investigate_Business_Hotel_using_Data_Visualization_/assets/135192484/d59ad2d8-0390-403f-84ca-53932d92613c">

**Business Insight:** </br>

Dari visualisasi di atas dapat disimpulkan bahwa **tidak ada hubungan linear antara _Stay Duration_ dan _Cancellation Rates_.** </br> Pengunjung dengan lama menginap (_Stay Duration_) antara 20-29 hari memiliki tingkat pembatalan booking (_Cancellation Rates_) tertinggi baik untuk City Hotel maupun Resort Hotel, yaitu sebesar 51% untuk City Hotel dan 23.9% untuk Resort Hotel.</br>

Walaupun pengunjung Resort Hotel dengan _Stay Duration_ 50-59 hari terlihat memiliki _Cancellation Rates_ yang tinggi, namun jumlah pengunjung dengan lama menginap sebanyak ini hanya berjumlah 4 orang sehingga belum bisa dikatakan valid.

Syntax selengkapnya dapat dilihat pada file berikut: [Correlation between Stay Duration and Cancellation Rates.ipynb](https://github.com/ramlanapriyansyah/Investigate_Business_Hotel_using_Data_Visualization_/blob/main/Correlation%20between%20Stay%20Duration%20and%20Cancellation%20Rates.ipynb)

# Analisis Hubungan antara Lama Waktu Pemesanan (_Lead Time_) dan Tingkat Pembatalan (_Cancellation Rates_)
<img width="900" alt="image" src="https://github.com/ramlanapriyansyah/Investigate_Business_Hotel_using_Data_Visualization_/assets/135192484/9c3f8d83-cc53-4b12-a0e4-8ffef37089c7">

**Business Insight:** </br>

Dari visualisasi di atas dapat dilihat bahwa _Cancellation Rates_ kedua tipe hotel mengalami tren yang cenderung meningkat seiring meningkatnya _Lead Time_. </br>
Artinya semakin lama jarak waktu pemesanan, semakin tinggi pula tingkat pembatalan pesanan yang mungkin terjadi. 

Walau Resort Hotel memiliki _Cancellation Rates_ 0% pada _Lead Time_ 19-21 bulan, total booking yang terjadi dengan jarak waktu pemesanan ini hanya sebanyak 50 booking sehingga diasumsikan nilai ini belum bisa dikatakan valid.

Syntax selengkapnya dapat dilihat pada file berikut: [Correlation between Lead Time and Cancellation Rates.ipynb](https://github.com/ramlanapriyansyah/Investigate_Business_Hotel_using_Data_Visualization_/blob/main/Correlation%20between%20Lead%20Time%20and%20Cancellation%20Rates.ipynb)





