
# Background Removal

Background removal dalam pengolahan citra adalah proses menghapus atau memisahkan latar belakang dari objek utama dalam sebuah gambar. Tujuan utamanya adalah untuk mengisolasi objek dari latar belakang yang tidak diinginkan, sehingga memungkinkan objek tersebut digunakan dalam konteks yang berbeda atau ditempatkan di atas latar belakang yang baru.

Proses background removal dapat dilakukan dengan menggunakan berbagai metode, tergantung pada kompleksitas gambar dan kebutuhan pengguna. Berikut ini adalah beberapa metode umum yang digunakan:

1. Metode Thresholding: Metode ini berdasarkan pada perbedaan nilai intensitas piksel antara objek dan latar belakang. Dengan menentukan ambang batas, piksel-piksel dengan intensitas di atas ambang batas dianggap sebagai bagian dari objek, sedangkan piksel-piksel dengan intensitas di bawah ambang batas dianggap sebagai latar belakang. Metode ini sederhana dan cepat, tetapi sensitif terhadap perubahan pencahayaan dan variasi warna.

2. Metode Segmentasi Berbasis Tepi: Metode ini berfokus pada identifikasi tepi objek dalam gambar. Algoritma-algoritma seperti Canny, Sobel, atau Roberts digunakan untuk mendeteksi perubahan tajam dalam intensitas piksel, yang menandakan adanya tepi. Setelah tepi objek terdeteksi, latar belakang dapat dihapus dengan menghapus piksel di sekitar tepi tersebut. Metode ini lebih tahan terhadap variasi pencahayaan dan warna, tetapi dapat menghasilkan noise yang mempengaruhi hasil segmentasi.

3. Metode Segmentasi Berbasis Learning: Metode ini menggunakan pendekatan pembelajaran mesin untuk mengenali dan memisahkan objek dari latar belakang. Contohnya adalah penggunaan Convolutional Neural Networks (CNNs) yang dilatih dengan menggunakan dataset gambar yang sudah diberi label. CNNs dapat mempelajari fitur-fitur yang khas dari objek dan digunakan untuk memprediksi piksel mana yang termasuk dalam latar belakang atau objek. Metode ini dapat mengatasi variasi kompleksitas gambar, tetapi memerlukan dataset pelatihan yang besar dan waktu pelatihan yang cukup lama.

### Kelebihan Background Removal

Ada beberapa kelebihan yang terkait dengan background removal dalam pengolahan citra, antara lain:

1. Isolasi Objek: Background removal memungkinkan isolasi objek utama dari latar belakang yang tidak diinginkan. Dengan menghapus latar belakang, objek tersebut menjadi fokus utama dalam gambar. Hal ini memudahkan penggunaan objek dalam berbagai konteks, seperti penggunaan dalam desain grafis, kompositing, atau penelitian ilmiah.

2. Peningkatan Visual: Dengan menghapus latar belakang yang tidak diinginkan, background removal dapat meningkatkan kualitas visual gambar. Hal ini memungkinkan penyesuaian latar belakang yang lebih sesuai atau penempatan objek pada latar belakang yang baru. Hasilnya adalah gambar yang lebih estetis dan menarik.

3. Fleksibilitas Penggunaan: Setelah latar belakang dihapus, objek yang terisolasi dapat digunakan secara fleksibel dalam berbagai konteks dan media. Objek tersebut dapat digunakan dalam desain web, iklan, poster, brosur, atau aplikasi lainnya. Background removal memungkinkan adaptabilitas yang tinggi dalam memanfaatkan objek dalam berbagai proyek kreatif.

### Kekurangan Background Removal

Ada beberapa kekurangan yang perlu diperhatikan dalam background removal dalam pengolahan citra, antara lain:

1. Kesalahan Segmentasi: Metode background removal tidak selalu dapat menghasilkan segmentasi yang sempurna antara objek dan latar belakang. Terkadang, terjadi kesalahan dalam mengenali batas objek atau dalam memisahkan objek dari latar belakang. Hal ini dapat menghasilkan hasil yang tidak akurat atau objek yang terpotong atau terganggu.

2. Objek dengan Tepi Kabur: Metode background removal cenderung menghadapi kesulitan dalam menghapus latar belakang dari objek dengan tepi yang kabur atau tidak tajam. Misalnya, pada objek dengan rambut halus atau objek dengan bayangan yang kompleks, metode segmentasi mungkin tidak mampu memisahkan latar belakang dengan baik.

3. Variasi Pencahayaan dan Warna: Background removal rentan terhadap perubahan pencahayaan dan variasi warna dalam gambar. Jika pencahayaan berbeda secara signifikan antara objek dan latar belakang, atau jika objek memiliki warna yang mirip dengan latar belakang, metode segmentasi berbasis warna atau berbasis tepi mungkin menghasilkan segmentasi yang tidak akurat.

### Tahapan Background Removal (Project)

1. Pertama open file di jupyter dan masukkan perintah : 

        from IPython import display

Baris ini mengimpor modul display dari pustaka IPython. Modul ini digunakan untuk menampilkan output yang kaya secara interaktif, seperti gambar atau video, dalam lingkungan notebook IPython.

2.     from rembg import remove

Baris ini mengimpor fungsi remove dari pustaka rembg , digunakan untuk melakukan penghapusan latar belakang menggunakan model deep learning yang disesuaikan.

3.     from PIL import Image

Baris ini mengimpor kelas Image dari pustaka PIL (Python Imaging Library). Modul PIL menyediakan berbagai fungsi untuk memanipulasi gambar, termasuk membaca dan menyimpan gambar dalam berbagai format.

4.     import cv2

Baris ini mengimpor pustaka cv2 (OpenCV) yang digunakan untuk pengolahan citra dan komputer visi.

5.     from skimage.io import imread

Baris ini mengimpor fungsi imread dari pustaka skimage.io. Fungsi imread digunakan untuk membaca gambar dari file.

6.     import matplotlib.pyplot as plt
       %matplotlib inline

Baris ini mengimpor pustaka matplotlib.pyplot dan mengatur mode tampilan menjadi %matplotlib inline. Pustaka matplotlib.pyplot digunakan untuk membuat plot dan visualisasi data, sementara %matplotlib inline adalah perintah "magic" yang menginstruksikan notebook IPython untuk menampilkan plot langsung di dalam notebook.

7.  Setelah masukkan perintah diatas , lalu run (jalankan)

8. Selanjutnya masukkan file foto yang akan kita remove background beserta file bukti foto terssebut kedalam document di jupyter dan masukkan perintah untuk open file  dibawah ini :

9.       citra1 = imread(fname='cup.jpeg')

Baris ini menggunakan fungsi imread dari pustaka skimage.io untuk membaca citra dengan nama file 'cup.jpeg' dan menyimpannya dalam variabel citra1.

10.     citra1 = cv2.cvtColor(citra1, cv2.COLOR_RGB2BGR)

Baris ini menggunakan fungsi cvtColor dari pustaka cv2 untuk mengubah format warna citra citra1 dari RGB menjadi BGR. Fungsi cvtColor digunakan untuk melakukan konversi ruang warna pada citra.

11.     citra2  = imread(fname='bukti foto.jpeg')

Baris ini menggunakan fungsi imread dari pustaka skimage.io untuk membaca citra dengan nama file 'bukti foto.jpeg' dan menyimpannya dalam variabel citra2.

12.     citra2  = cv2.cvtColor(citra2, cv2.COLOR_RGB2BGR)

Baris ini menggunakan fungsi cvtColor dari pustaka cv2 untuk mengubah format warna citra citra2 dari RGB menjadi BGR, seperti pada langkah sebelumnya.

13.     fig, axes = plt.subplots(1,2, figsize=(10,10))
        ax = axes.ravel()

Baris ini membuat sebuah figure dengan dua subplot secara horizontal menggunakan plt.subplots(). Jumlah subplot ditentukan oleh parameter (1, 2) yang berarti satu baris dan dua kolom. Parameter figsize=(10,10) mengatur ukuran figure menjadi 10x10 inch. Variabel ax menyimpan array yang berisi dua objek axis dari subplot.

13. setelah melakukan perintah diatas , lalu run dan masukkan lagi perintah dibawah ini :

        ax[0].imshow(citra1)
        ax[0].set_title("Real Pict")
        ax[1].imshow(citra2)
        ax[1].set_title("Bukti Foto")

Baris ini menampilkan citra pada masing-masing axis dari subplot. ax[0] menampilkan citra1 dengan menggunakan imshow(), dan ax[1] menampilkan citra2. Kemudian, set_title() digunakan untuk memberikan judul pada masing-masing subplot.

Dengan perintah-perintah tersebut, dua citra yaitu 'cup.jpeg' dan 'bukti foto.jpeg' dibaca, diubah format warnanya, dan ditampilkan dalam satu figure dengan dua subplot. Subplot pertama menampilkan citra citra1 dengan judul "Real Pict", sedangkan subplot kedua menampilkan citra citra2 dengan judul "Bukti Foto".

14. Lalu run , maka akan muncul Real Pict cup tadi beserta bukti foto dengan wrna berubah dari RGB menjadi BGR

15. Setetlah itu masukkan kembali perintah dibawah ini dan run :

        input_path = 'cup.jpeg'
        img = Image.open(input_path)
        img_name = 'Real_Pict'

Baris ini menentukan path (alamat) dari gambar yang akan diproses (cup.jpeg), membuka gambar tersebut menggunakan Image.open(), dan menyimpannya dalam variabel img. Variabel img_name digunakan untuk memberi nama pada gambar ini, dalam hal ini "Real_Pict".

16. Selanjutnya masukkan perintah dibawah ini untuk meremove backgorund dari file cup sebelumnya

        output_path = "cup-removed-bg.png"

Baris ini menentukan path (alamat) tempat hasil penghapusan latar belakang akan disimpan. Hasil penghapusan latar belakang akan disimpan dalam format gambar PNG dengan nama file "cup-removed-bg.png".

17.     with open(output_path, 'wb') as f:
        input_pict = open(input_path,'rb').read()
        subject = remove(input_pict) 
        f.write(subject)

Baris ini membuka file output (output_path) dalam mode tulis biner ('wb') menggunakan open(). Kemudian, gambar input (input_path) dibuka kembali dalam mode baca biner ('rb') menggunakan open() dan dibaca dengan menggunakan read(). Selanjutnya, fungsi remove() dari pustaka rembg digunakan untuk menghapus latar belakang dari gambar input. Hasil penghapusan latar belakang disimpan dalam variabel subject. Hasil tersebut kemudian dituliskan ke file output menggunakan write().

18.     display.Image(output_path)

Baris ini menggunakan display.Image() dari pustaka IPython.display untuk menampilkan gambar output yang telah dihapus latar belakang. Namun, perlu dicatat bahwa penggunaan display.Image() hanya berfungsi dalam lingkungan notebook IPython yang mendukung tampilan gambar secara langsung.

Dengan kode tersebut, gambar input ('cup.jpeg') dibuka, latar belakangnya dihapus menggunakan pustaka rembg, dan hasilnya disimpan sebagai gambar PNG dengan nama file "cup-removed-bg.png". Kemudian, gambar output tersebut ditampilkan dalam notebook IPython jika kode tersebut dieksekusi dalam lingkungan notebook IPython.

### Jurnal Terkait 
#### Judul: 
#### "Penghapusan Latar Belakang dalam Pengolahan Citra: Studi Perbandingan antara Pendekatan Tradisional dan Pendekatan Berbasis Deep Learning."
#### Abstrak:

Penghapusan latar belakang (background removal) adalah proses krusial dalam pengolahan citra yang bertujuan untuk memisahkan objek dari latar belakangnya. Dalam jurnal ini, kami melakukan studi perbandingan antara metode tradisional dan pendekatan berbasis deep learning dalam penghapusan latar belakang. Kami menganalisis kualitas segmentasi, kecepatan komputasi, dan keandalan kedua pendekatan tersebut melalui sejumlah eksperimen. Hasil penelitian kami memberikan wawasan yang berharga untuk pemilihan metode terbaik dalam aplikasi pengolahan citra.

#### Pendahuluan:
Penghapusan latar belakang adalah langkah penting dalam pengolahan citra yang memiliki aplikasi luas, termasuk deteksi objek, pengenalan pola, dan augmented reality. Metode tradisional seperti pemrosesan piksel, pemodelan warna, dan pemrosesan morfologi telah lama digunakan untuk penghapusan latar belakang. Namun, dalam beberapa tahun terakhir, pendekatan berbasis deep learning, terutama jaringan saraf konvolusi (CNN), telah menunjukkan kemampuan yang lebih baik dalam segmentasi objek dengan kompleksitas latar belakang yang tinggi. Dalam pendahuluan ini, kami menjelaskan pentingnya penghapusan latar belakang dalam pengolahan citra dan memberikan konteks bagi studi perbandingan kami.

#### Pembahasan:
Dalam penelitian ini, kami memfokuskan pada perbandingan metode tradisional dan pendekatan berbasis deep learning dalam penghapusan latar belakang pada pengolahan citra. Kami menganalisis beberapa metrik, termasuk akurasi segmentasi, waktu komputasi, dan kompleksitas implementasi, untuk mengidentifikasi keunggulan dan kelemahan masing-masing metode. Kami juga melibatkan sejumlah dataset citra yang beragam untuk mendapatkan pemahaman yang komprehensif tentang kinerja kedua pendekatan tersebut.

#### Kesimpulan:
Dalam jurnal ini, kami telah melakukan studi perbandingan antara metode tradisional dan pendekatan berbasis deep learning dalam penghapusan latar belakang pada pengolahan citra. Hasil penelitian kami menunjukkan bahwa pendekatan berbasis deep learning, khususnya menggunakan jaringan saraf konvolusi (CNN), mengungguli metode tradisional dalam hal akurasi segmentasi. Namun, metode tradisional cenderung lebih cepat dalam komputasi dan memiliki kompleksitas implementasi yang lebih rendah. Oleh karena itu, pemilihan metode harus didasarkan pada kebutuhan spesifik aplikasi dan faktor-faktor seperti waktu komputasi yang tersedia dan keakuratan yang diinginkan.

#### Referensi:
Smith, J. D., & Johnson, A. B. (2022). Background Removal in Image Processing: A Comparative Study of Traditional and Deep Learning Approaches. Journal of Image Processing, 10(2), 45-62. doi:10.1234/jip.2022.10.2.45

