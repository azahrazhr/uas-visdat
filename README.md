# Dashboard Informasi Potensi Desa (PODES) di Indonesia menggunakan Tableau

Link project: 
https://public.tableau.com/views/DashboardInformasiPodesIndonesia/DashboardPodes?:language=en-US&:display_count=n&:origin=viz_share_link

## Dokumentasi Proses Pembuatan Dashboard Informasi

### Pengantar

Dashboard informasi potensi desa ini dibuat untuk menggambarkan kondisi desa/kelurahan menurut keberadaan agen bahan bakar dan keluarga pengguna listrik.

### Pengumpulan Data

Penelitian ini menggunakan data sekunder yang diperoleh dari situs resmi Badan Pusat Statistik (https://www.bps.go.id/), yaitu data Potensi Desa di Indonesia. Data yang dimaksud yaitu data banyaknya desa/kelurahan menurut keberadaan agen/penjual bahan bakar dan keluarga pengguna listrik tahun 2014, 2018, dan 2021. Dataset didapatkan dalam format excel (.xlsx).

Selain data BPS, diambil pula data spasial tentang latitude dan longitude per provinsi yang ada di Indonesia. Data ini diperoleh dari website GADM (https://gadm.org/data.html) dan didapatkan dalam format shapefile (.shp). Data ini digunakan untuk kepentingan visualisasi pemetaan wilayah

### Preprocessing

Setelah data dikumpulkan, tahap selanjutnya yaitu melakukan preprocessing data untuk memperbaiki data yang ada. Pada penelitian ini, peneliti melakukan pengolahan data PODES dengan menggunakan Microsoft Excel. Data yang diolah akan digunakan dalam visualisasi data menggunakan Tableau. Gambar 2 menunjukkan pengolahan data pada Microsoft Excel.

Kemudian, data PODES yang telah diproses dan data spasial dihubungkan ke Tableau. Kedua data tersebut digabung menggunakan inner join berdasarkan provinsinya. Data source yang digunakan dapat terlihat pada Gambar 3.

### Implementasi dan Analisis Hasil

Pada tahap ini dilakukan pembuatan visualisasi terhadap data yang sudah diproses dengan menggunakan software Tableau. Visualisasi yang digunakan dalam dashboard ini antara lain adalah bar chart, stacked bar chart, peta choropleth, serta elemen lain yaitu teks. 

Bar chart digunakan untuk membandingkan kategori dari data, yaitu menggambarkan urutan provinsi tertinggi ke terendah dengan banyak desa menurut agen bahan bakar dan keluarga pengguna listrik. 
Stacked bar chart menggambarkan persentase banyaknya desa menurut agen bahan bakar atau keluarga pengguna listrik yang dibedakan berdasarkan tahun dan subkategorinya. 
Peta choropleth berfungsi untuk memetakan data geospasial, sehingga chart ini dibuat agar user dapat melihat persebaran dan perbandingan jumlah agen bahan bakar dan keluarga pengguna listrik berdasarkan daerahnya. 
Sedangkan teks digunakan untuk menampilkan total agen bahan bakar atau keluarga pengguna listrik berdasarkan daerahnya. Setelah itu dibuat output akhir berupa information dashboard tentang kondisi desa/kelurahan menurut keberadaan agen bahan bakar dan keluarga pengguna listrik dengan menggabungkan chart dan teks yang telah dibuat.  

Berdasarkan pengolahan data yang telah dilakukan di Tableau, maka didapatkan hasil sebagai berikut:

**A. Bar Chart**

Gambar 4 menunjukkan provinsi dengan banyak desa menurut agen bahan bakar dan keluarga pengguna listriknya dalam bentuk bar chart. Hasil diurutkan dari provinsi dengan jumlah tertinggi ke terendah.

Dari gambar di atas, dapat dilihat bahwa provinsi yang memiliki nilai tertinggi adalah Jawa Timur, Jawa Tengah, dan Sumatera Utara.

**B. Stacked Bar Chart**

Dua kategori yang digunakan dalam visualisasi stacked bar chart adalah banyaknya desa/kelurahan menurut agen bahan bakar dan keluarga pengguna listrik. Gambar 5 merupakan visualisasi berbentuk stacked bar chart dari persentase banyaknya desa menurut agen bahan bakar yang dibedakan berdasarkan tahun, yaitu 2014, 2018, dan 2021. Warna merah tua menunjukkan tidak adanya agen, warna orange tua merepresentasikan minyak tanah, sedangkan warna orange muda adalah LPG.
Berdasarkan gambar di atas, dapat terlihat bahwa secara keseluruhan, persentase banyak desa menurut agen bahan bakar terbesar di Indonesia adalah agen/penjual LPG.

Gambar 6 menggambarkan visualisasi berbentuk stacked bar chart dari persentase banyaknya desa menurut keluarga pengguna listrik yang dibedakan berdasarkan tahun, yaitu 2014, 2018, dan 2021. Warna biru tua menunjukkan tidak adanya listrik, warna biru agak tua merepresentasikan PLN, sedangkan warna biru muda adalah non-PLN.
Berdasarkan gambar di atas, dapat terlihat bahwa secara keseluruhan, persentase banyak desa menurut keluarga pengguna listrik terbesar di Indonesia adalah menggunakan PLN.

**C. Peta Choropleth**

Pada Gambar 7, persebaran agen bahan bakar dan keluarga pengguna listrik di setiap provinsi di Indonesia ditampilkan dalam bentuk peta choropleth berupa kartogram area, dimana tiap provinsi diwakili oleh banyak desa menurut jumlah agen bahan bakar dan keluarga pengguna listriknya masing-masing. Semakin gelap warna biru yang terdapat pada peta, maka semakin tinggi nilai rata-rata jumlah agen bahan bakar dan keluarga pengguna listrik.
Dari tampilan peta pesebaran tersebut dapat kita lihat sejumlah provinsi yang terdapat di Pulau Jawa, yaitu Jawa Timur dan Jawa Tengah, merupakan provinsi dengan jumlah agen bahan bakar dan keluarga pengguna listrik tertinggi di Indonesia, selebihnya agen bahan bakar dan keluarga pengguna listrik tertinggi juga dihasilkan di Provinsi Sumatera Utara dan Aceh yang lebih sedikit dibandingkan Jawa Timur dan Jawa Tengah.

**D. Teks**

Selain menggunakan chart, teks juga akan digunakan untuk mengetahui total banyak desa/kelurahan menurut agen bahan bakar dan keluarga pengguna listrik. 
Gambar 8 menunjukkan total banyak desa menurut agen bahan bakar dalam bentuk teks
Gambar 9 menunjukkan total banyak desa menurut keluarga pengguna listrik dalam bentuk teks.

**C. Information Dashboard**

![alt text](https://github.com/azahrazhr/uas-visdat/blob/images/Screenshot (2930).png?raw=true)


Agar representasi lebih efektif dan efisien, grafik dan teks yang telah dibuat digabung pada sebuah dashboard seperti Gambar 10 agar pengguna dapat melihat secara langsung keterkaitan antar grafiknya.

Pada gambar di atas, ditampilkan dashboard yang berguna memudahkan pengguna dalam melihat pemetaan jumlah agen bahan bakar dan keluarga pengguna listrik, mengetahui total dan persentase agen bahan bakar dan keluarga pengguna listrik, dan juga melihat urutan tertinggi ke terendah dari provinsi di Indonesia dengan banyak desa menurut jumlah agen bahan bakar dan keluarga pengguna listrik.

Information dashboard ini bersifat interaktif, karena pengguna dapat memfilter data berdasarkan provinsi dan tahun yang ada. Filter berdasarkan provinsi dapat dilakukan dengan tiga cara. Pertama, dengan mengklik atau melakukan rectangular selection pada provinsi yang diinginkan di peta choropleth. Kedua, dengan mengklik provinsi yang diinginkan di bar chart. Ketiga, dengan menggunakan filter dropdown yang tersedia di bagian kiri dashboard. Pengguna juga dapat melihat informasi detail berdasarkan chart yang ada ketika melakukan hover. Selain itu, pada dashboard ini ditampilkan judul, penjelasan singkat, serta sumber dan pembuat dashboard di bagian kiri dashboard.
