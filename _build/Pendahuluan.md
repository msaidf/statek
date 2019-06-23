---
redirect_from:
  - "/pendahuluan"
interact_link: content/Pendahuluan.ipynb
kernel_name: ir
has_widgets: false
title: 'Pendahuluan'
prev_page:
  url: 
  title: ''
next_page:
  url: /MempersiapkanData
  title: 'Mempersiapkan Data'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---


# Statistika Ekonomi dan Keuangan Islam
- Semester Antara 2019



# Pendahuluan



<h1>Contents<span class="tocSkip"></span></h1>
<div class="toc"><ul class="toc-item"><li><span><a href="#Mengapa-Belajar-Statistik?" data-toc-modified-id="Mengapa-Belajar-Statistik?-1">Mengapa Belajar Statistik?</a></span></li><li><span><a href="#Software-Statistik" data-toc-modified-id="Software-Statistik-2">Software Statistik</a></span><ul class="toc-item"><li><span><a href="#Software-R" data-toc-modified-id="Software-R-2.1">Software R</a></span></li><li><span><a href="#R-Online" data-toc-modified-id="R-Online-2.2">R Online</a></span></li></ul></li><li><span><a href="#Pengertian" data-toc-modified-id="Pengertian-3">Pengertian</a></span><ul class="toc-item"><li><span><a href="#Jenis-Statistik" data-toc-modified-id="Jenis-Statistik-3.1">Jenis Statistik</a></span></li><li><span><a href="#Macam-Variabel" data-toc-modified-id="Macam-Variabel-3.2">Macam Variabel</a></span></li><li><span><a href="#Skala-Pengukuran" data-toc-modified-id="Skala-Pengukuran-3.3">Skala Pengukuran</a></span></li></ul></li></ul></div>



## Mengapa Belajar Statistik?
- Banjir informasi, campuran antara yang benar dan keliru
- Tidak cukup melakukan generalisasi atas kejadian anekdotal
- Kita butuh data yang mewakili, dan meringkasnya untuk menjadi informasi yang mudah dimengerti



Masa sekarang, teknologi informasi dan komunikasi berkembang pesat dan semakin menjadi bagian tak terpisahkan dari kehidupan sehari-hari di hampir seluruh lapisan masyarakat. Informasi kini bukan hanya lebih mudah, namun bahkan terlampau mudah hingga membanjir. Tantangan masyarakat di masa ini adalah pada membedakan informasi mana yang benar dari yang keliru dan menyesatkan. 

Istilah *hoax*, kabar palsu, menjadi populer seiring dengan tren ini. Namun kabar palsu tidaklah unik menjadi masalah di masa sekarang. Hanya jumlahnya saja yang semakin banyak seiring dengan banjir informasi. Dari dulu kabar palsu selalu bercampur bersama kabar yang sahih; satu waktu kecil menyelip di antara kabar sahih; di waktu lain justru dominan.

Ketika kita ingin mengambil kesimpulan atas suatu fenomena yang melibatkan banyak kejadian, kita memerlukan cara untuk meringkas informasi yang dikandung oleh berbagai kejadian itu. Kita tidak bisa mengambil kesimpulan untuk fenomena umum hanya berdasarkan informasi dari kejadian-kejadian tunggal (**anekdot**) karena belum tentu anekdot tersebut tepat mewakili fenomena umum itu. Mengambil kesimpulan umum dari bukti anekdotal disebut **generalisasi**.

Karenanya, langkah awal untuk menjawab pertanyaan tentang suatu fenomena adalah memperoleh data terkait segala sesuatu yang terkait fenomena tersebut. Setelah itu, kita perlu suatu metode untuk meringkas data yang melibatkan cukup banyak kejadian sehingga tidak lagi mudah untuk dicerna hanya dengan melihat data satu per satu. Statistik adalah bidang ilmu mengenai cara memperoleh, meringkas dan menyajikan data. 

Banyak dari metode statistik yang hanya memformalisasi cara intuisi kita memproses informasi dalam kehidupan sehari-hari. Misal konsep *modus* yang menyimpulkan kecenderungan berdasarkan pola yang paling banyak muncul, atau *rata-rata* yang menyimpulkan kecenderungan dengan memberi bobot pada tiap kejadian berdasar frekuensi kejadian yang sama atau mirip.



## Software Statistik
- Bagian tak terpisahkan dari belajar statistik 
- Skill berharga di lapangan kerja



Sebagian besar metode statistik kini bisa dilakukan dengan bantuan program komputer. Penguasaan software statistik menjadi pelengkap wajib dari pengetahuan konsep statistik dan menjadi nilai keunggulan di lapangan kerja.

Banyak macam software yang memiliki program statistik. Sebagian software khusus untuk mengerjakan statistik, seperti SPSS dan Stata. Sebagian lagi bisa digunakan untuk pemrograman matematika secara umum, seperti Matlab, Octave, Gauss dan R. Bahasa pemrograman umum seperti C, Java, Python, dan Julia pun memiliki library statistik. Penerapan statistik di industri teknologi di bawah payung topik *Machine Learning* memunculkan banyak library bahasa pemrograman yang lebih handal dan menerapkan teknik terkini dibanding software khusus statistik.



### Software R
- Gratis dan lengkap, bersaing dengan software statistik berbayar
- Download installer R di [cran.r-project.org](https://cran.r-project.org)
- Download juga RStudio Desktop di [rstudio.com](https://www.rstudio.com/products/rstudio/download) untuk antarmuka grafis



Kelas ini akan menggunakan software R, karena gratis dan lengkap, cukup bersaing dengan software statistik komersial yang mahal sekalipun. R bisa diunduh di [CRAN](https://cran.r-project.org), pilih versi sesuai dengan sistem operasi yang digunakan (Windows, MacOS, atau Linux).

R ini pada dasarnya merupakan program yang berjalan dengan kode perintah (*syntax*). Namun R juga bisa digunakan menggunakan tampilan grafis (*GUI*). Software R yang dari CRAN sudah memiliki tampilan grafis sederhana, namun banyak alternatif GUI yang lebih baik. GUI paling populer adalah [RStudio](https://www.rstudio.com), dan versi desktop-nya saya rekomendasikan untuk siswa karena mudah diinstal ke semua sistem operasi. Saya sendiri akan lebih sering menggunakan Jupyter notebook yang menggunakan model tampilan *What You See Is What You Get* (WYSYWIG) seperti tampilan pengolah kata MS Word dan Google Docs. 



### R Online
- Siap pakai segera, tidak perlu menginstal apapun
- Bisa dipakai dimana saja, selama ada akses internet
- *Freemium*: bisa akses gratis dengan fitur dan kapasitas terbatas
- [RStudio Cloud](https://cloud.rstudio.com) dengan antarmuka seperti versi desktopnya
- [MyBinder](https://mybinder.org) untuk antarmuka jupyter notebook



Proses setup software R hingga siap pakai, mencakup program R, GUI dan library yang dibutuhkan memerlukan waktu cukup lama. Berapa lama bergantung pada kecepatan akses internet untuk mengunduh dan kecepatan komputer dalam memproses instalasi. 

Cara yang lebih instan untuk bisa segera memakai R adalah menggunakan layanan software online yang cukup diakses dengan browser internet. Untuk menggunakan layanan ini, pengguna biasanya diharuskan mendaftar akun terlebih dulu. Biasanya ada opsi gratis untuk mencoba; sebagian tetap memberikan fitur penuh namun dibatasi waktu, sebagian lagi tidak membatasi waktu tapi membatasi fitur dan kapasitas pemakaian.

Kebanyakan layanan software statistik online ini menggunakan Jupyter notebook sebagai antarmuka, seperti di [MyBinder](https://mybinder.org). Salah satu penyedia yang menggunakan antarmuka RStudio adalah [RStudio Cloud](https://cloud.rstudio.com). Sebagian lagi memiliki GUI yang dikembangkan sendiri.



## Pengertian



### Jenis Statistik
- **Statistik Deskriptif**: mengumpulkan, meringkas, dan menyajikan data
- **Statistik Inferensial**: estimasi, prediksi, generalisasi mengenai satu populasi berdasarkan sampel
    - **populasi**: kumpulan individu atau pengukuran yang jadi ketertarikan
    - **sampel**: bagian dari populasi ketertarikan yang menjadi dasar inferensi



### Macam Variabel
- **Kualitatif**: non angka
- **Kuantitatif**: angka
    - Diskrit: bulat, tidak bisa dipecah
    - Kontinyu: bisa dipecah hingga sekecil-kecilnya



### Skala Pengukuran
- **Nominal**: tak bisa diurutkan
- **Ordinal**: urut, selisih tidak tentu
- **Interval**: urut, selisih bisa dihitung, rasio tak tentu
- **Rasio**: urut, selisih dan rasio bisa dihitung

