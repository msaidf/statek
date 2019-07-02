# Pengantar Ekonometri



Penggunaan statistik meluas di berbagai bidang pengetahuan. Dalam penerapannya, banyak ditemukan masalah statistik yang cukup spesifik di masing-masing bidang. Karenanya berkembang cabang-cabang statistik untuk menangani masalah spesifik di masing-masing bidang pengetahuan.

Ekonometri merupakan pengembangan statistik yang memenuhi kebutuhan analisis empiris di bidang ekonomi. Bagian terbesar dari ekometri melibatkan analisis **regresi** untuk mengestimasi parameter model matematis yang menspesifikasi hubungan antara variabel-variabel ekonomi.

Regresi dengan sendirinya hanya bisa mengestimasi korelasi antar variabel, tapi tidak bisa memastikan nilai korelasi yang diestimasi memiliki arti kausal (sebab-akibat). Penelitian perlu didesain khusus agar hasil regresi memiliki arti kausal. Namun desain penelitian kausalitas di luar cakupan buku ini.



Sebagaimana dalam statistik inferensi, masalah utama dalam ekonometri adalah memperkirakan nilai parameter regresi pada populasi berdasarkan informasi dari data sampel. Apapun metode estimasi (estimator) yang dipilih, hasil estimasinya akan berubah ketika diterapkan pada sampel berbeda dari populasi yang sama.

Estimator dipilih untuk memaksimalkan dua kriteria, **akurasi** dan **presisi**. Estimator disebut akurat jika rata-rata nilai estimasi parameter dari berbagai sampel mendekati nilai parameter populasi sebenarnya. Estimator disebut presisi jika nilai estimasi parameter dari berbagai sampel tidak menyebar.

Salah satu estimator yang disebut ***Ordinary Least Square*** (OLS) memenuhi dua kriteria tersebut jika data yang dihadapi memenuhi seperangkat **asumsi klasik**.



Pelanggaran sebagian asumsi tersebut hanya berkonsekuensi mengurangi presisi estimasi, namun estimasi parameternya sendiri masih akurat. Sementara pelanggaran lainnnya ada yang bisa membuat estimasi tidak akurat (bias).

Masalah pada presisi mewujud sebagai kenaikan *standard error*. *Standard error* yang keliru dapat mengakibatkan inferensi yang keliru, terutama dalam memutuskan apakah parameter tersebut secara statistik berbeda signifikan dari nol. Ini biasanya untuk mengambil kesimpulan apakah variabel-variabel yang diteliti benar memiliki hubungan, bahwa nilai estimasi bukan hanya dihasilkan secara kebetulan dari keacakan sampel.

Solusi standar bagi masalah presisi adalah koreksi terhadap *standard error* dengan metode tertentu, sesuai dengan penyebab masalah. Ketika masalah presisi ditimbulkan oleh **heteroskedastisitas**, yakni variasi error yang berubah mengikuti perubahan variabel lain, metode White digunakan untuk mengoreksi *standard error*. Sementara jika yang terjadi adalah **korelasi serial**, metode Newey-White digunakan untuk mengoreksi *standard error*. 

