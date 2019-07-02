# Pengenalan R

## Software Statistik

Sebagian besar metode statistik kini bisa dilakukan dengan bantuan program komputer. Penguasaan software statistik menjadi pelengkap wajib dari pengetahuan konsep statistik dan menjadi nilai keunggulan di lapangan kerja.

Banyak macam software yang memiliki program statistik. Sebagian software khusus untuk mengerjakan statistik, seperti SPSS dan Stata. Sebagian lagi bisa digunakan untuk pemrograman matematika secara umum, seperti Matlab, Octave, Gauss dan R. Bahasa pemrograman umum seperti C, Java, Python, dan Julia pun memiliki library statistik. Penerapan statistik di industri teknologi di bawah payung topik *Machine Learning* memunculkan banyak library bahasa pemrograman yang lebih handal dan menerapkan teknik terkini dibanding software khusus statistik. 

**Ringkasan**



- Belajar software statistik adalah bagian tak terpisahkan dari belajar statistik 
- Penguasaan software analisis data adalah skill berharga di lapangan kerja



## Software R

Buku ini mengenalkan software R, yang walau gratis namun fiturnya cukup lengkap, bersaing dengan software statistik komersial yang mahal sekalipun. R bisa diunduh di [CRAN](https://cran.r-project.org), pilih versi sesuai dengan sistem operasi yang digunakan (Windows, MacOS, atau Linux).

R ini pada dasarnya merupakan program yang berjalan dengan kode perintah (*syntax*). Namun R juga bisa digunakan menggunakan tampilan grafis (*GUI*). Software R yang dari CRAN sudah memiliki tampilan grafis sederhana, namun banyak alternatif GUI yang lebih baik. GUI paling populer adalah [RStudio](https://www.rstudio.com), dan versi desktop-nya saya rekomendasikan untuk pemula karena mudah diinstal ke semua sistem operasi. 

Saya sendiri belakangan ini lebih sering menggunakan [Jupyter notebook](https://jupyter.org) yang menggunakan model tampilan *What You See Is What You Get* (WYSYWIG) seperti tampilan pengolah kata MS Word dan Google Docs. Cara termudah untuk menginstall Juypter notebook beserta dengan kernel R adalah dengan menginstal [Miniconda](https://docs.conda.io/en/latest/miniconda.html), lalu jalankan perintah berikut

```
conda install jupyter r-base r-essentials
```

**Ringkasan**

- R program statistik gratis yang lengkap, bersaing dengan software statistik berbayar
- Download installer R di [cran.r-project.org](https://cran.r-project.org)
- Download juga RStudio Desktop di [rstudio.com](https://www.rstudio.com/products/rstudio/download) untuk antarmuka grafis
- Jika sistem operasi masih 32-bit, download versi lama RStudio yang masih mendukung: [Windows](http://download1.rstudio.org/RStudio-1.1.463.exe), [Ubuntu](http://download1.rstudio.org/rstudio-1.1.463-i386.deb), [Red Hat/Fedora](http://download1.rstudio.org/rstudio-1.1.463-i686.rpm), atau [MacOS El Capitan dan sebelumnya](http://download1.rstudio.org/RStudio-1.1.463.dmg)



## R Online

Proses setup software R hingga siap pakai, mencakup program R, GUI dan library yang dibutuhkan memerlukan waktu cukup lama. Berapa lama bergantung pada kecepatan akses internet untuk mengunduh dan kecepatan komputer dalam memproses instalasi. 

Cara yang lebih instan untuk bisa segera memakai R adalah menggunakan layanan software online yang cukup diakses dengan browser internet. Untuk menggunakan layanan ini, pengguna biasanya diharuskan mendaftar akun terlebih dulu. Biasanya ada opsi gratis untuk mencoba; sebagian tetap memberikan fitur penuh namun dibatasi waktu, sebagian lagi tidak membatasi waktu tapi membatasi fitur dan kapasitas pemakaian.

Kebanyakan layanan software statistik online ini menggunakan Jupyter notebook sebagai antarmuka, seperti di [MyBinder](https://mybinder.org). Salah satu penyedia yang menggunakan antarmuka RStudio adalah [RStudio Cloud](https://rstudio.cloud). Ada pula yang memiliki GUI yang dikembangkan sendiri.

**Ringkasan**

- Layanan R online siap pakai segera, tanpa download dan install apapun di komputer lokal
- Bisa dipakai dimana saja, selama ada akses internet
- Beberapa layanan menyediakan akses gratis seperti berikut.
  - [RStudio Cloud](https://rstudio.cloud) dengan antarmuka seperti versi desktopnya
  - [MyBinder](https://mybinder.org) untuk antarmuka jupyter notebook

