# Dashboard Informasi Potensi Desa (PODES) di Indonesia menggunakan Tableau


### Pengantar

Dashboard informasi potensi desa ini dibuat untuk menggambarkan kondisi desa/kelurahan di Indonesia menurut keberadaan agen bahan bakar dan keluarga pengguna listrik.

Link project: 

https://public.tableau.com/views/DashboardInformasiPodesIndonesia/DashboardPodes

## Dokumentasi Proses Pembuatan Dashboard Informasi

### Perancangan

Tahapan dalam pembuatan dashboard ini secara umum ditunjukkan pada diagram alur pada Gambar berikut:

![1. Tahapan penelitian](https://github.com/azahrazhr/uas-visdat/blob/main/images/Gambar1.png?raw=true)

### Pengumpulan Data

Penelitian ini menggunakan data sekunder yang diperoleh dari situs resmi Badan Pusat Statistik (https://www.bps.go.id/), yaitu data Potensi Desa di Indonesia. Data yang dimaksud yaitu data banyaknya desa/kelurahan menurut keberadaan agen/penjual bahan bakar dan keluarga pengguna listrik tahun 2014, 2018, dan 2021. Dataset didapatkan dalam format excel (.xlsx).

Selain data BPS, diambil pula data spasial tentang latitude dan longitude per provinsi yang ada di Indonesia. Data ini diperoleh dari website GADM (https://gadm.org/data.html) dan didapatkan dalam format shapefile (.shp).

### Preprocessing Data

Setelah data dikumpulkan, tahap selanjutnya yaitu melakukan preprocessing data untuk memperbaiki data yang ada. Pada penelitian ini, peneliti melakukan pengolahan data PODES dengan menggunakan Microsoft Excel. Data yang diproses terdiri dari 613 rows dan 5 columns yang terdiri dari provinsi, tahun, kategori, subkategori, dan jumlah/nilai. Adapun detail perubahan data adalah sebagai berikut:

* Perubahan dari tabel 3 dimensi menjadi tabel 2 dimensi
* Menyamakan nama provinsi data PODES dengan data spasial
* Transformasi tahun, kategori, subkategori, dan nilai dari kolom menjadi baris

Data yang diolah akan digunakan dalam visualisasi data menggunakan Tableau. Gambar 2 menunjukkan pengolahan data pada Microsoft Excel.

![2. Pengolahan data pada Microsoft Excel](https://github.com/azahrazhr/uas-visdat/blob/main/images/Gambar2.png?raw=true)

Kemudian, data PODES yang telah diproses dan data spasial dihubungkan ke Tableau. Kedua data tersebut digabung menggunakan inner join berdasarkan provinsinya. Data source yang digunakan dapat terlihat pada Gambar 3.

![3. Tampilan data source di Tableau Public](https://github.com/azahrazhr/uas-visdat/blob/main/images/Gambar3.png?raw=true)

Setelah data diimport, dilakukan perubahan nama salah satu provinsi yaitu Jakarta, dari Jakarta Raya menjadi DKI Jakarta menggunakan fitur Aliases di Tableau.

### Implementasi pada Tableau

Pada tahap ini dilakukan pembuatan visualisasi terhadap data yang sudah diproses dengan menggunakan software Tableau. Visualisasi yang digunakan dalam dashboard ini antara lain adalah bar chart, stacked bar chart, peta choropleth, serta elemen lain yaitu teks. 

* Bar chart menggambarkan urutan provinsi tertinggi ke terendah dengan banyak desa menurut agen bahan bakar dan keluarga pengguna listrik. 
* Stacked bar chart menggambarkan persentase banyaknya desa menurut agen bahan bakar atau keluarga pengguna listrik yang dibedakan berdasarkan tahun dan subkategorinya. 
* Peta choropleth dibuat agar user dapat melihat persebaran dan perbandingan jumlah agen bahan bakar dan keluarga pengguna listrik berdasarkan daerahnya. 
* Teks menampilkan total agen bahan bakar atau keluarga pengguna listrik berdasarkan daerahnya. 

Setelah itu dibuat output akhir berupa **information dashboard** tentang kondisi desa/kelurahan menurut keberadaan agen bahan bakar dan keluarga pengguna listrik dengan menggabungkan chart dan teks yang telah dibuat.  

Berdasarkan pengolahan data yang telah dilakukan di Tableau, maka didapatkan hasil sebagai berikut:

#### A. Bar Chart

Gambar 4 menunjukkan provinsi dengan banyak desa/kelurahan menurut agen bahan bakar dan keluarga pengguna listriknya dalam bentuk bar chart. Hasil diurutkan dari provinsi dengan jumlah tertinggi ke terendah.

![4. Bar Chart](https://github.com/azahrazhr/uas-visdat/blob/main/images/Gambar4.jpg?raw=true)

Keterangan dimensi dan measures yang digunakan adalah:
* Row = nama provinsi
* Column = aggregat dari jumlah agen bahan bakar dan keluarga pengguna listrik
* Measures = aggregat

Fitur:
* Tooltip = keterangan tentang jumlah agen bahan bakar dan keluarga pengguna listrik per provinsi
* Filter berdasarkan provinsi dan tahun

#### B. Stacked Bar Chart

Dua kategori yang digunakan dalam visualisasi stacked bar chart adalah banyaknya desa/kelurahan menurut agen bahan bakar dan keluarga pengguna listrik. 

Gambar 5 merupakan visualisasi berbentuk stacked bar chart dari persentase banyaknya desa menurut agen bahan bakar yang dibedakan berdasarkan tahun, yaitu 2014, 2018, dan 2021. 

![5. Stacked Bar Chart 1](https://github.com/azahrazhr/uas-visdat/blob/main/images/Gambar5.jpg?raw=true)

Keterangan warna berdasarkan sub kategori:
* Merah tua = tidak adanya agen
* Orange tua = minyak tanah
* Orange muda = LPG

Keterangan dimensi dan measures yang digunakan adalah:
* Row = tahun
* Column = jumlah agen bahan bakar 
* Measures = persentase

Fitur:
* Tooltip = keterangan tentang subkategori, tahun, dan persentase
* Filter berdasarkan provinsi dan tahun

Gambar 6 menggambarkan visualisasi berbentuk stacked bar chart dari persentase banyaknya desa menurut keluarga pengguna listrik yang dibedakan berdasarkan tahun, yaitu 2014, 2018, dan 2021. 

![6. Stacked Bar Chart 2](https://github.com/azahrazhr/uas-visdat/blob/main/images/Gambar6.jpg?raw=true)

Keterangan warna berdasarkan sub kategori:
* Biru tua = tidak ada listrik
* Biru agak tua = PLN
* Biru muda = non-PLN

Keterangan dimensi dan measures yang digunakan adalah:
* Row = tahun
* Column = jumlah keluarga pengguna listrik 
* Measures = persentase

Fitur:
* Tooltip = keterangan tentang subkategori, tahun, dan persentase
* Filter berdasarkan provinsi dan tahun

#### C. Peta Choropleth

Pada Gambar 7, persebaran agen bahan bakar dan keluarga pengguna listrik di setiap provinsi di Indonesia ditampilkan dalam bentuk peta choropleth berupa kartogram area, dimana tiap provinsi diwakili oleh banyak desa menurut jumlah agen bahan bakar dan keluarga pengguna listriknya masing-masing. Semakin gelap warna biru yang terdapat pada peta, maka semakin tinggi nilai rata-rata jumlah agen bahan bakar dan keluarga pengguna listrik.

![7. Peta Choropleth](https://github.com/azahrazhr/uas-visdat/blob/main/images/Gambar7.jpg?raw=true)

Keterangan dimensi dan measures yang digunakan adalah:
* Row = latitude
* Column = longitude

Fitur:
* Tooltip = keterangan tentang jumlah keluarga pengguna listrik, agen bahan bakar, dan keseluruhan
* Filter berdasarkan provinsi dan tahun

#### D. Teks

Selain menggunakan chart, teks juga akan digunakan untuk mengetahui total banyak desa/kelurahan menurut agen bahan bakar dan keluarga pengguna listrik.

Gambar 8 menunjukkan total banyak desa menurut agen bahan bakar dalam bentuk teks.

![8. Teks 1](https://github.com/azahrazhr/uas-visdat/blob/main/images/Gambar8.jpg?raw=true)

Fitur:
* Tooltip = keterangan tentang total agen bahan bakar
* Filter berdasarkan provinsi dan tahun

Gambar 9 menunjukkan total banyak desa menurut keluarga pengguna listrik dalam bentuk teks.

![9. Teks 2](https://github.com/azahrazhr/uas-visdat/blob/main/images/Gambar9.jpg?raw=true)

Fitur:
* Tooltip = keterangan tentang total keluarga pengguna listrik
* Filter berdasarkan provinsi dan tahun

#### E. Information Dashboard

Agar representasi lebih efektif dan efisien, grafik dan teks yang telah dibuat digabung pada sebuah dashboard seperti Gambar 10 agar pengguna dapat melihat secara langsung keterkaitan antar grafiknya.

![alt text](https://github.com/azahrazhr/uas-visdat/blob/main/images/Gambar10.jpg?raw=true)

Size dashboard: 1470 px x 785 px

Filter berdasarkan provinsi dapat dilakukan dengan tiga cara. 
1. Mengklik atau melakukan rectangular selection pada provinsi yang diinginkan di peta choropleth
2. Mengklik provinsi yang diinginkan di bar chart
3. Menggunakan filter dropdown yang tersedia di bagian kiri dashboard. 

Fitur:
* Tooltip per masing-masing chart dan teks
* Judul, penjelasan singkat, serta sumber dan pembuat dashboard ditampilkan di bagian kiri dashboard.
