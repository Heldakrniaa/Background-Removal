
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

### Tahapan Proses Membuat Background Removal (Project)

1. Pertama , buka terlebih dahulu aplikasi jupyter notebook
2. Lalu add new file phyton pada jupyter tadi 
3. Setelah file phyton terbuka , masukkan perintah : 

       from IPython import display
       from rembg import remove
       from PIL import Image
       import cv2 
       from skimage.io import imread
       import matplotlib.pyplot as plt
       %matplotlib inline

4. Lalu , cari gambar yang akan kita pakai untuk di remove background dan pindahkan kedalam document yang terdapat file jupyter tadi 
5. Jangan lupa untuk me-rename gambar asli dengan nama "cup" beserta "bukti gambar"
6. Selanjutnya , kita buat heading " Open File" dengan jenis Markdown
7. Lalu kita masukkan kembali perintah untuk menampilkan gambar yang telah kita impor kedalam file jupyter nya / program nya

       citra1 = imread(fname='cup.jpeg')
       citra1 = cv2.cvtColor(citra1, cv2.COLOR_RGB2BGR)
       citra2  = imread(fname='bukti foto.jpeg')
       citra2  = cv2.cvtColor(citra2, cv2.COLOR_RGB2BGR)

8. Setelah gambar asli dari cup dan bukti gambar muncul , kita masukkan kembali perintah dibawah ini :

       output_path = "cup-removed-bg.png"

       with open(output_path, 'wb') as f:
       input_pict = open(input_path,'rb').read()
       subject = remove(input_pict) 
       f.write(subject)

       display.Image(output_path)

9. Setelah perintah tersebut kita masukkan , maka akan muncul hasil dari gambar "cup" yang telah di remove background 
10. Jangan lupa untuk nge-running setiap selesai memasukkan semua perintah.

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

