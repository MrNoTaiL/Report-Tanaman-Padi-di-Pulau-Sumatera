# Report - Produksi Padi di Sumatera Tahun 1993-2020
Halo !! Selamat datang di repositori ini !! Tujuan dari project ini adalah menganalisa data yang bersumber dari website kaggle.com tentang Dataset Tanaman Padi di Sumatera,Indonesia dan melihat <i>insight</i> yang dihasilkan dari proses analisis data tersebut. 

## Sumber Data
![header](https://user-images.githubusercontent.com/98092595/208815878-21a86f4b-6427-4452-8587-344ae1baaf31.jpg)
<p align="justify">Pengambilan data diperoleh melalui website BPS pada kategori tanaman pangan utama dari 8 provinsi di pulau Sumatera yaitu Nanggroe Aceh Darussalam (NAD), Sumatera Utara, Riau, Jambi, Sumatera Selatan, Bengkulu dan Lampung. Data yang digunakan adalah data dari tahun 1993 hingga tahun 2020 untuk dataset padi. Data memuat hasil produksi tahunan dan luas panen atau luas lahan. Kemudian data perubahan cuaca diperoleh melalui website BMKG untuk data harian curah hujan, kelembapan, dan temperatur rata-rata atau suhu rata-rata dari tahun 1993 hingga tahun 2020. Pengambilan data juga berasal dari website kaggle pada bagian data set tranding atau bisa <a href="https://www.kaggle.com/datasets/ardikasatria/datasettanamanpadisumatera">disini</a>.</p>

## Latar Belakang
<p align="justify">Fokus pada satu komoditi yaitu Padi yang merupakan komoditi utama. Diharapkan dapat menjadi komoditi yang bisa memenuhi kebutuhan pangan masyarakat sumatera dan dapat meningkatkan sektor pertanian di sumatera.</p>

## Rumusan Masalah
1. Apakah terdapat korelasi variabel yang lain terhadap variabel produksi padi ?
2. Berapa nilai produksi padi di tiap provinsi ?
3. Bagaimana pertumbuhan produksi padi dari tahun 1993-2020 ?

## Pembahasan
<h3>Bagian 1 - Preparation Data:</h3>
<p align="justify">Pertama yang dilakukan dalam menganalisis data adalah tahap preparation data. load data pada python menggunakan syntax pandas. Dapat dilihat terdapat variabel Provinsi, Tahun, Produksi, Luas Panen, Curah hujan, Kelembapan, Suhu rata-rata.</p>

<img src="https://github.com/MrNoTaiL/Report-Tanaman-Padi-di-Pulau-Sumatera/blob/main/img/1.jpg?raw=true"></img>

<h3>Bagian 2 - Data Cleansing:</h3>
<p align="justify">Pada bagian ini, hal yang dilakukan adalah melihat dataset Tanaman Padi Sumatera,Indonesia sudah sesuai dengan type data tersebut. Dari informasi dibawah ini, bisa dilihat masing-masing variabel sudah sesuai dengan tipe dari data.</p>

<img src="https://github.com/MrNoTaiL/Report-Tanaman-Padi-di-Pulau-Sumatera/blob/main/img/2.jpg?raw=true"></img>

<p align="justify">Proses selanjutnya melihat missing value, dalam hal ini data terlihat lengkap dan terlihat dari tidak adanya missing value yang ditunjukan.</p>

<img src="https://github.com/MrNoTaiL/Report-Tanaman-Padi-di-Pulau-Sumatera/blob/main/img/3.jpg?raw=true"></img>

<p align="justify">Proses selanjutnya adalah melihat outlier. outlier merupakan nilai ekstrim atau nilai berbeda dengan pengamatan yang dilakukan. nilai ini muncul akibat perbedaan satuan atau nilai asli dari kodisi sebenarnya.</p>
<br>
<p>Menggunakan 3 cara untuk melihat, yaitu dengan melihat nilai minimal dan maksimal di setiap variabelnya.</p>

<img src="https://github.com/MrNoTaiL/Report-Tanaman-Padi-di-Pulau-Sumatera/blob/main/img/4.jpg?raw=true"></img>

<p>Dengan menggunakan histogram, dapat mengetahui visualisasi dari outlier tersebut.</p>

<img src="https://github.com/MrNoTaiL/Report-Tanaman-Padi-di-Pulau-Sumatera/blob/main/img/5.jpg?raw=true"></img>

<p>Menggunakan boxplot , juga bisa mengetahui outlier dengan memvisualisasikannya.</p>

<img src="https://github.com/MrNoTaiL/Report-Tanaman-Padi-di-Pulau-Sumatera/blob/main/img/6.jpg?raw=true"></img>

<p align="justify">Hasilnya dapat diketahui jika variabel Luas Panen terdapat outlier. Nilai outlier yang terdapat di variabel Luas Panen kemungkinan berasal dari perbedaan wilayah tiap provinsi.</p>
<p align="justify">Setelah melihat adanya outlier pada variabel Luas Panen, proses selanjutnya adalah memperbaiki atau <i>manipulation data</i> dengan metode IQR. Setelah dilakukan proses IQR, menghasilkan variabel baru yaitu Luas Panen yang sudah di hitung. Dapat dilihat hasilnya tidak terdapat lagi outlier pada variabel tersebut.</p>

<img src="https://github.com/MrNoTaiL/Report-Tanaman-Padi-di-Pulau-Sumatera/blob/main/img/7.jpg?raw=true"></img>

<h3>Bagian 3 - Exploratory Data:</h3>
<p align="justify">Pada bagian ini, data akan di <i>explore</i> untuk menjawab 3 pertanyaan pada rumusan masalah. Rumusan pertanyaan yang pertama adalah apakah terdapat korelasi antara variabel lain dengan variabel produksi. Cara menjawabnya dengan menggunakan <i>syntax correlation</i> dapat mengetahui vairabel mana saja yang akan mempengaruhi Produksi.</p>
<p align="justify">Seperti gambar dibawah ini, Adanya korelasi variabel antara vairabel hanya ditunjukan dengan variabel Luas Panen saja. Variabel curah hujan, kelembapan, dan suhu rata-rata tidak menunjukan korelasi. Luas Panen merupakan gambaran pengukuran subjektif, seperti penggunaan benih, penggunaan air untuk irigasi (blok pengairan), informasi dari petani dan aparat desa, serta pengamatannya dengan pandangan mata (eye estimate). Sehingga dalam pengamatan database ini Luas Panen memiliki korelasi dengan produksi padi. </p>

<img src="https://github.com/MrNoTaiL/Report-Tanaman-Padi-di-Pulau-Sumatera/blob/main/img/8.jpg?raw=true"></img>

<p align="justify">Hal ini juga diperkuat dengan adanya visualisasi menggunakan seaborn regplot yang menunjukan adanya nilai yang mendekati tren line.</p>

<img src="https://github.com/MrNoTaiL/Report-Tanaman-Padi-di-Pulau-Sumatera/blob/main/img/9.jpg?raw=true"></img>

<p align="justify">Pada pertanyaan nilai produksi padi tiap provinsi. Dapat dijawab dengan menggunakan data produksi padi tertinggi di sepanjang tahun 1993-2020. Hasilnya adalah produksi padi di provinsi Aceh sebesar 461.060 Ton, Sumatera Utara sebesar 847.610 Ton, Sumatera barat sebesar 507.454 Ton, Riau 156.088 Ton, Jambi sebesar 215.975 Ton, Sumatera Selatan sebesar 872.737 Ton, Bengkulu sebesar 147.680 Ton, dan Lampung sebesar 707.266 Ton.</p>
<p align="justify">Kemudian untuk produksi terendah di tiap provinsinya dapat dijawab dengan menggunakan produksi padi terendah di sepanjang tahun 1993-2020. Hasilnya produksi padi di provinsi Aceh sebesar 293.067 Ton, Sumatera Utara sebesar 388.591 Ton, Sumatera barat sebesar 222.021 Ton, Riau 63.142 Ton, Jambi sebesar 69.536 Ton, Sumatera Selatan sebesar 422.109 Ton, Bengkulu sebesar 64.137 Ton, dan Lampung sebesar 390.799 Ton.</p>
<p align="justify">Kemudian untuk pertumbuhan produksi padi di sepanjang tahun 1993-2020 dapat di visualisasikan pada gambar dibawah ini.</p>

<img src="https://github.com/MrNoTaiL/Report-Tanaman-Padi-di-Pulau-Sumatera/blob/main/img/10.jpg?raw=true"></img>

<p align="justify">Pada pertumbuhan produksi padi di sumatera, tahun 2018-2020 mengalami penurunan. Seperti pada data visualisasi dibawah ini. dapat dilihat adanya penurunan produksi padi di tahun 2018-2020. Hal ini disebabkan adanya virus covid-19 yang sedang melanda dunia dan dampaknya juga dirasakan oleh masyarakat di Indonesia.</p>

<img src="https://github.com/MrNoTaiL/Report-Tanaman-Padi-di-Pulau-Sumatera/blob/main/img/11.jpg?raw=true"></img>

## Kesimpulan
Dari analisis diatas dapat disimpilkan:
<p align="justify">1. Adanya korelasi variabel. Variabel Luas Panen dengan Produksi. Hal ini ditunjukan dengan nilai 1.00 yang artinya ada korelasi variabel.</p> 
<p align="justify">2. Nilai produksi padi di tunjukan dengan nilai maksimal dan minimal di setiap provinsi. Hal ini dapat dilihat, Provinsi Sumatera Selatan memiliki produksi padi yang besar ketimbang provinsi lainnya di pulau Sumatera. Kemudian produksi padi terendah berada di provinsi Jambi.</p>
<p align="justify">3. Pertumbuhan produksi padi dari tahun 1993-2017 mengalami kenaikan, akan tetapi di tahun 2018-2020 mengalami penurunan. Penurunan ini diakibatkan adanya virus corona yang melanda Indonesia, bahkan dunia. Sehingga, berdampak pada produksi padi di Sumatera</p>
