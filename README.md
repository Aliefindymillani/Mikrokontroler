# IMPLEMENTASI SVM SEBAGAI PENGGANTI PENGENDALI PID PADA KIT ITCLAB

## Mikrokontroler

Mikrokontroler adalah suatu bentuk komputer kecil yang dikemas dalam bentuk chip IC (Integrated Circuit) dan dirancang khusus untuk melaksanakan tugas atau operasi tertentu. Fungsi utamanya adalah sebagai pengontrol atau pengendali dalam suatu rangkaian elektronika. Umumnya, mikrokontroler terdiri dari beberapa komponen, termasuk CPU (Central Processing Unit), memori sebagai tempat penyimpanan data, I/O (Input dan Output), serta unit pendukung lainnya seperti yang dijelaskan oleh Dewinta (2022). Penggunaan mikrokontroler meluas dalam berbagai aplikasi elektronik seperti sistem otomotif, peralatan rumah tangga, perangkat medis, sistem keamanan, perangkat pintar, dan lainnya. Mikrokontroler menerima input dari perangkat eksternal melalui kode inputnya, kemudian mengolahnya menggunakan program yang telah dimuat ke dalam memori internal.

Keunggulan utama mikrokontroler adalah ukurannya yang kecil, memungkinkan integrasi yang mudah ke dalam perangkat elektronik yang kompak. Ini menjadikannya ideal untuk perangkat dengan ruang terbatas seperti peralatan, kendaraan, atau perangkat medis bergerak. Mikrokontroler juga diketahui memiliki konsumsi daya yang rendah, yang sangat penting dalam aplikasi baterai atau perangkat berdaya rendah. Hal ini membuatnya cocok untuk perangkat yang harus beroperasi dalam jangka waktu lama dengan sumber daya yang terbatas. Dikenal dengan harga yang relatif murah, mikrokontroler menawarkan beragam pilihan fitur dan harga, memungkinkan pengembang dan produsen mengimplementasikannya secara cost-effective dalam produk mereka.

## IOT
IoT (Internet of Things) adalah konsep di mana objek ditanamkan dengan teknologi seperti sensor dan perangkat lunak untuk berkomunikasi, mengendalikan, dan bertukar data melalui internet (Setiawan, 2021). Tujuan utama pengembangan IoT adalah memberikan solusi bagi berbagai masalah dan tugas manusia (Angela, 2022). Cara kerjanya sederhana, dengan menggunakan instruksi program, perintah dapat menghasilkan interaksi antar perangkat yang terhubung tanpa intervensi pengguna (Angela, 2022). IoT memanfaatkan unsur pendukung seperti kecerdasan buatan, sensor, dan konektivitas untuk menciptakan ekosistem yang memberikan manfaat dalam berbagai bidang seperti pertanian, kesehatan, transportasi, dan lingkungan. Dengan IoT, perangkat terhubung dapat bekerja terkoordinasi, mengumpulkan data otomatis, dan merespons lingkungan sekitarnya, menciptakan dunia yang lebih terhubung, efisien, dan cerdas. Meskipun demikian, perlu memperhatikan aspek keamanan dan privasi terkait penggunaan data yang terkumpul.

## Sistem Kendali PID
Sistem Kendali di industri yang paling terkenal adalah Sistem Kendali Proporsional Integral dan Derivatif (PID). Diagram blok Sistem Kendali PID diperlihatkan seperti pada gambar di atas. PID menggabungkan tiga aksi kendali proporsional, integral dan derivatif. Masing-masing aksi kendali ini mempunyai keunggulan-keunggulan tertentu. Aksi kendali proporsional mempunyai keunggulan rise time yang sangat cepat. Aksi kendali integral mempunyai keunggulan untuk memperkecil error. Sedangkan aksi kendali derivatif mempunyai keunggulan untuk memperkecil error atau meredam overshoot. Tujuan penggabungan ketiga aksi kendali ini agar dihasilkan keluaran dengan risetime yang cepat dan error yang kecil.

## Deep Learning
Deep Learning adalah metode dalam kecerdasan buatan (AI) yang terinspirasi oleh cara kerja otak manusia, bertujuan mencapai tingkat pemahaman dan pengambilan keputusan tinggi seperti manusia. Populer di kalangan praktisi data, deep learning telah diterapkan dalam produk berteknologi tinggi seperti mobil otonom. Dalam deep learning, komputer diajarkan untuk memproses data kompleks dan tidak terstruktur dengan menghasilkan representasi yang lebih abstrak dan mendalam. Metode ini menarik perhatian banyak pihak karena kemampuannya yang luar biasa dalam mengolah informasi, membuka pintu menuju perkembangan AI yang lebih maju dan potensial inovasi di berbagai bidang. Dengan kekuatan komputasi yang terus meningkat dan ketersediaan data yang melimpah, deep learning menjadi alat yang kuat dalam menganalisis data kompleks dan memberikan solusi inovatif.

## SVM
SVM (Support Vector Machine) adalah suatu metode atau algoritma pembelajaran mesin yang digunakan untuk klasifikasi dan regresi. SVM dapat mengatasi tugas-tugas seperti pengelompokkan data ke dalam kategori atau menentukan hubungan antara variabel. Prinsip dasar SVM adalah mencari pemisah optimal atau hyperplane yang memaksimalkan jarak antara dua kelas data yang berbeda. SVM juga dapat bekerja efektif dalam ruang fitur yang tinggi dan memberikan performa yang baik dalam menangani data yang kompleks. SVM digunakan dalam berbagai aplikasi, termasuk pengenalan pola, klasifikasi teks, pengenalan wajah, dan banyak lagi.

## Metide Penelitian
Metode penelitian adalah metode yang digunakan dalam mengumpulkan, menganalisis, dan menginterpretasi data untuk menjawab pertanyaan penelitian atau mencapai tujuan penelitian yang telah ditetapkan. Pada sub bab ini kami ingin menjelaskan metode penelitian yang digunakan dalam studi ini, yang meliputi pengumpulan data, pra proses data, pelatihan model, dan evaluasi.

### Pengumpulan Data
Dalam penelitian ini, pengumpulan data dilakukan dengan memanfaatkan perangkat lunak emulasi TCLab. Pada tahap pengumpulan data, TCLab emulator diatur pada kecepatan 100 kali. Selama simulasi berlangsung, setpoint suhu diberikan dengan variasi yang beragam. Setpoint ini mencerminkan nilai target suhu yang diinginkan dalam pengendalian suhu. Untuk memastikan kualitas pelatihan model, variasi diberlakukan pada setpoint dalam penelitian ini. TCLab emulator dijalankan selama 540 loop. Loop atau siklus pengendalian suhu merujuk pada jumlah iterasi di mana TCLab emulator melakukan pembacaan sensor suhu dan mengatur aktuator suhu untuk mencapai setpoint yang telah ditetapkan. Pada setiap iterasi, sensor suhu membaca nilai aktual, dan aktuator disesuaikan untuk mendekati setpoint yang diinginkan. Grafik setpoint dataset yang digunakan untuk melatih model juga disajikan dalam penelitian ini.

![Pengumpulan Data](https://github.com/Aliefindymillani/Mikrokontroler/assets/89888415/a97dadc5-8266-42b7-9ec3-ead8c81b1d51)

### Pra Proses Data
Setelah mendapatkan data set point dan error dari tahap pengumpulan data, dilakukan pra proses data untuk menyiapkan data sebelum memasuki tahap pelatihan model. Salah satu langkah kunci dalam pra proses data adalah pemilihan fitur atau ciri yang akan digunakan. Dalam penelitian ini, fitur yang terpilih adalah set point dan error. Set point merepresentasikan nilai target suhu dalam pengendalian suhu, sementara error adalah perbedaan antara set point dan suhu aktual yang terukur. Selain itu, output yang akan diprediksi dalam penelitian ini adalah Q, yang merupakan hasil penjumlahan dari tiga komponen, yaitu P (Proporsional), I (Integral), dan D (Derivative). Komponen-komponen ini merujuk pada algoritma kontrol PID (Proporsional-Integral-Derivative) yang digunakan untuk mengendalikan suhu.

Selain pemilihan fitur dan pembentukan output, tahap pra proses data juga mencakup normalisasi data. Normalisasi dilakukan untuk mengubah rentang nilai setiap fitur agar sejajar dan dapat diolah dengan baik oleh model pembelajaran mesin. Dalam penelitian ini, digunakan normalisasi Min-Max Scaling, suatu metode yang mengubah skala nilai data dari rentang nilai aktual menjadi rentang nilai antara 0 hingga 1 atau -1 hingga 1 (Naufal et al., 2023). Formula Min-Max Scaling digunakan untuk mencapai normalisasi, dengan X scaled sebagai hasil scaling data ke-i, 𝑥 sebagai nilai asli data ke-i, xmin sebagai nilai minimum dari X, dan xmax sebagai nilai maksimum dari X.

![Pra Proses Data](https://github.com/Aliefindymillani/Mikrokontroler/assets/89888415/bbaa2265-1824-4f0b-a025-6bd866e0854a)

### Pelatihan Mode
Pelatihan model dalam arsitektur SVM (Support Vector Machine) merujuk pada proses di mana algoritma SVM belajar dari data latihan untuk membuat model yang dapat digunakan untuk melakukan prediksi atau klasifikasi pada data baru. Dalam SVM, model yang dihasilkan bertujuan untuk memisahkan data ke dalam kelas-kelas yang berbeda dengan menemukan hyperplane (bidang pemisah) optimal. Proses pelatihan ini melibatkan dua tahap utama: pembentukan model dan penentuan parameter.

![SVM](https://github.com/Aliefindymillani/Mikrokontroler/assets/89888415/55edb2ab-dabb-4ca6-beb8-f56ec28c6270)

Proses pelatihan model SVM ini bertujuan untuk mencapai generalisasi yang baik, di mana model dapat mengklasifikasikan data baru dengan akurasi tinggi. Penting untuk memahami karakteristik data, memilih parameter dengan bijak, dan melakukan validasi untuk memastikan kinerja model yang baik pada data yang tidak terlihat selama pelatihan.











