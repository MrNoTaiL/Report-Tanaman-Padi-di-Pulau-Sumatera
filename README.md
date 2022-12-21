# Report-Tanaman-Padi-di-Sumatera
Halo !! Selamat datang di repositori ini !! Tujuan dari project ini adalah menganalisa data yang bersumber dari website kaggle.com tentang Dataset Tanaman Padi di Sumatera,Indonesia dan melihat <i>insight</i> yang dihasilkan dari proses analisis data tersebut. 

## Sumber Data
![header](https://user-images.githubusercontent.com/98092595/208815878-21a86f4b-6427-4452-8587-344ae1baaf31.jpg)
Pengambilan data diperoleh melalui website BPS pada kategori tanaman pangan utama dari 8 provinsi di pulau Sumatera yaitu Nanggroe Aceh Darussalam (NAD), Sumatera Utara, Riau, Jambi, Sumatera Selatan, Bengkulu dan Lampung. Data yang digunakan adalah data dari tahun 1993 hingga tahun 2020 untuk dataset padi. Data memuat hasil produksi tahunan dan luas panen atau luas lahan. Kemudian data perubahan cuaca diperoleh melalui website BMKG untuk data harian curah hujan, kelembapan, dan temperatur rata-rata atau suhu rata-rata dari tahun 1993 hingga tahun 2020. Pengambilan data juga berasal dari website kaggle pada bagian data set tranding atau bisa <a href="https://www.kaggle.com/datasets/ardikasatria/datasettanamanpadisumatera">disini</a>.

## Latar Belakang
Fokus pada satu komoditi yaitu Padi yang merupakan komoditi utama. Diharapkan dapat menjadi komoditi yang bisa memenuhi kebutuhan pangan masyarakat sumatera dan dapat meningkatkan sektor pertanian di sumatera.

## Rumusan Masalah
1. Apakah terdapat korelasi variabel yang lain terhadap variabel produksi padi ?
2. Provinsi mana yang memiliki produksi padi tertinggi dan terendah di pulau sumatera ?
3. Bagaimana pertumbuhan produksi padi dari tahun 1993 sampai 2020 ?

## Pembahasan
<p>Bagian 1 - Preparation Data:</p>
Pertama yang dilakukan dalam menganalisis data adalah tahap preparation data. load data pada python menggunakan syntax pandas. Dapat dilihat terdapat variabel Provinsi, Tahun, Produksi, Luas Panen, Curah hujan, Kelembapan, Suhu rata-rata.
<br>
(img1)
<br><br>
<p>Bagian 2 - Data Cleansing:</p>
Pada bagian ini, hal yang dilakukan adalah melihat dataset Tanaman Padi Sumatera,Indonesia sudah sesuai dengan type data tersebut.
<br>
Dari informasi dibawah ini, bisa dilihat masing-masing variabel sudah sesuai dengan tipe dari data
<br>
(img2)
<br>
Proses selanjutnya melihat missing value, dalam hal ini data terlihat lengkap dan terlihat dari tidak adanya missing value yang ditunjukan
<br>
(img3)
<br>
Proses selanjutnya adalah melihat outlier. outlier merupakan nilai ekstrim atau nilai berbeda dengan pengamatan yang dilakukan. nilai ini muncul akibat perbedaan satuan atau nilai asli dari kodisi sebenarnya.
<br>
Menggunakan 3 cara untuk melihat, yaitu dengan melihat nilai minimal dan maksimal di setiap variabelnya
<br>
(img4)
<br>
Dengan menggunakan histogram, dapat mengetahui visualisasi dari outlier tersebut.
<br>
(img5)
<br>
Menggunakan boxplot , juga bisa mengetahui outlier dengan memvisualisasikannya.
<br>
(img6)
<br>
Hasilnya dapat diketahui jika variabel Luas Panen terdapat outlier. Nilai outlier yang terdapat di variabel Luas Panen kemungkinan berasal dari perbedaan wilayah tiap provinsi.
<br>
Setelah melihat adanya outlier pada variabel Luas Panen, proses selanjutnya adalah memperbaiki atau <i>manipulation data</i> dengan metode IQR. Setelah dilakukan proses IQR, menghasilkan variabel baru yaitu Luas Panen yang sudah di hitung. Dapat dilihat hasilnya tidak terdapat lagi outlier pada variabel tersebut.
<br>
(img7)
