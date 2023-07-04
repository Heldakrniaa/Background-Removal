
# Background Removal

Background removal dalam pengolahan citra adalah proses menghapus latar belakang dari sebuah citra atau gambar digital untuk mengisolasi objek utama yang ada di dalamnya. Tujuan utamanya adalah untuk memisahkan objek dari latar belakangnya sehingga objek tersebut dapat digunakan secara terpisah atau ditempatkan di latar belakang yang berbeda. Pengolahan citra untuk background removal melibatkan berbagai teknik dan algoritma.
  
Berikut ini beberapa metode umum yang sering digunakan:
1. Metode Berbasis Tepi 
Metode ini melibatkan deteksi tepi pada citra untuk memisahkan objek dari latar belakang. Algoritma seperti Canny Edge Detection atau Sobel Operator dapat digunakan untuk mengidentifikasi tepi 
objek dengan akurasi tinggi.

2. Metode Berbasis Warna 
Metode ini memanfaatkan perbedaan warna antara objek dan latar belakang untuk memisahkannya. Algoritma seperti Chroma Keying atau Color Thresholding digunakan untuk mengidentifikasi dan menghapus piksel dengan rentang warna yang ditentukan sebagai latar belakang.

3. Metode Segmentasi 
Metode ini melibatkan segmentasi citra untuk memisahkan objek dan latar belakang. Algoritma seperti K-Means Clustering, GrabCut, atau Watershed Transformation digunakan untuk mempartisi citra menjadi area yang berbeda berdasarkan intensitas, warna, atau tekstur piksel.

4. Metode Machine Learning 
Metode ini menggunakan teknik pembelajaran mesin, seperti Convolutional Neural Networks (CNN) atau Deep Learning, untuk mengidentifikasi dan memisahkan objek dari latar belakang. Model yang dilatih dengan dataset citra yang telah di-label akan mampu mengenali objek dan melakukan background removal secara otomatis. 

Ada beberapa alasan mengapa seseorang mungkin perlu menggunakan background removal. Salah satu alasan utama adalah untuk keperluan desain grafis, seperti membuat logo, poster, atau iklan di mana objek perlu dipisahkan dan ditempatkan di latar belakang yang berbeda. Background removal juga sering digunakan dalam e-commerce, di mana gambar produk perlu dipisahkan dari latar belakangnya agar tampil lebih profesional dan menarik.

### Tahapan Cara Penyelesaian  

1. Langkah pertama yang dilakukan yaitu buka file baru di jupyter notebook , lalu masukkan perintah :
2.     pip install rembg --user
3. Perintah tersebut akan menggunakan pip untuk menginstal paket rembg dengan opsi "--user" . Opsi "--user" digunakan untuk menginstal paket .
4. Tunggu hingga proses instalasi selesai. Pip akan mengunduh dan menginstal paket rembg beserta dependensinya.
5. Setelah instalasi selesai , pilih gambar yang nantinya akan di hapus background dan pindahkan ke folder document yang terdapat file jupyter tadi
6. Selanjutnya , masukkan perintah :
7.     from remb import remove 
8. Untuk mengimpor fungsi remove dari modul rembg, yang akan digunakan untuk menghapus latar belakang gambar. 
9.     from PIL import image
10. Untuk mengimpor modul Image dari PIL, yang akan digunakan untuk membaca dan menyimpan gambar.
11.     input_path = 'cup.jpg'
12. Maksud dari input ini yaitu untuk memasukan nama file gambar yang akan kita hapus background nanti nya
13.     output_path = 'cup2.png'
14. Nah sedangkan perintah output_path yang berfungsi untuk mengeluarkan hasil dari input tadi dan diubah dari jpg menjadi png , jangan lupa untuk memberi beda nama file gambar tadi 
15.     input = Image.open(input_path)
16. Fungsi Image.open() dari PIL digunakan untuk membaca gambar input dari jalur file yang ditentukan. Gambar input akan disimpan dalam variabel input.
17.     output = remove(input)
18. Fungsi remove dari paket rembg untuk menghapus latar belakang gambar input. Hasil dari background removal akan disimpan dalam variabel output.
19.     output.save(output_path)
20. Fungsi save() dari objek gambar output digunakan untuk menyimpan gambar hasil removal ke jalur file yang ditentukan sebagai file PNG. Anda juga dapat mengatur format file yang diinginkan jika format PNG tidak diinginkan.

 Setelah menjalankan kode ini, gambar dengan latar belakang yang dihapus akan disimpan di file output yang ditentukan. 

### Jurnal Terkait Removal Background

 Judul: A Comparative Study of Background Removal Techniques for Image Processing

Abstrak: 
Penghapusan Latar belakang atau "background removal" adalah proses penting dalam pengolahan citra yang bertujuan untuk mengisolasi objek utama dari latar belakangnya. Dalam jurnal ini, kami melakukan studi perbandingan terhadap berbagai teknik penghapusan latar belakang yang umum digunakan dalam pengolahan citra. Kami menganalisis dan membandingkan kinerja teknik-teknik tersebut berdasarkan beberapa metrik evaluasi yang mencakup presisi, kecepatan, dan kehandalan.

Penjelasan : 
Metode yang kami teliti meliputi metode berbasis pemisahan warna (color-based), metode berbasis model, dan metode berbasis pembelajaran mesin (machine learning). Kami menerapkan teknik-teknik ini pada berbagai jenis citra dengan latar belakang yang kompleks dan berbeda-beda. Selanjutnya, kami melakukan perbandingan kualitatif dan kuantitatif berdasarkan hasil penghapusan latar belakang yang diperoleh. Hasil eksperimen menunjukkan bahwa teknik penghapusan latar belakang berbasis pembelajaran mesin memberikan hasil terbaik dalam sebagian besar kasus, dengan tingkat presisi yang tinggi dan waktu komputasi yang relatif cepat. Namun, kami juga mengidentifikasi beberapa kelemahan dan tantangan yang terkait dengan metode ini, seperti kebutuhan akan kumpulan data pelatihan yang besar dan kompleksitas pemrosesan yang lebih tinggi.

Kesimpulannya : 
Dalam jurnal ini kami menyajikan studi perbandingan yang komprehensif tentang teknik penghapusan latar belakang dalam pengolahan citra. Hasil penelitian ini dapat menjadi panduan praktis bagi peneliti dan praktisi di bidang pengolahan citra untuk memilih teknik yang paling sesuai dengan kebutuhan aplikasi mereka.

Kata kunci: pengolahan citra, penghapusan latar belakang, pemrosesan warna, model berbasis, pembelajaran mesin.







### 🚀 About Me
Im a student of Institut Teknologi PLN...
 


### Acknowledgements

 - [Awesome Readme Templates](https://awesomeopensource.com/project/elangosundar/awesome-README-templates)
 - [Awesome README](https://github.com/matiassingers/awesome-readme)
 - [How to write a Good readme](https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project)


### Features

- Light/dark mode toggle
- Live previews
- Fullscreen mode
- Cross platform


### Support

For support, email hkrniaa@gmail.com or join our Slack channel.

