---
redirect_from:
  - "/menyiapkandata"
interact_link: content/MenyiapkanData.ipynb
kernel_name: ir
has_widgets: false
title: 'Menyiapkan Data'
prev_page:
  url: /IntroR
  title: 'Pengenalan R'
next_page:
  url: /Visual
  title: 'Visualisasi Data'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---


# Menyiapkan Data



## Pekerjaan Di Balik Layar
- Menyiapkan data (*data cleaning*) sering menjadi pekerjaan paling memakan waktu
- Metode menyiapkan data jarang diajarkan dalam kelas
- Padahal kesalahan dalam menyiapkan data bisa mengubah hasil analisis



## Memuat data dari file ke R



Dengan library `rio`, kita bisa mengimpor ke R data dari berbagai macam format: `txt`, `csv`, `xls`, `xlsx`, `dbf`, `sav`, `dta`, `sas7.bdat`. Data yang diimpor akan menjadi obyek R tipe `data.frame`.

Install dulu package `rio` jika belum pernah diinstal sebelumnya. Muat package tersebut dengan perintah `library` 



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
# install.packages('rio')
library(rio)
datakab = import('https://raw.githubusercontent.com/msaidf/statek/master/content/indo-dapoer_data.csv')

```
</div>

</div>



## Mengecek Data



Tampilkan keseluruhan data dengan mengenter nama obyek data. Namun untuk data yang besar, ini tidak banyak membantu bahkan bisa makan waktu lama. 



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab

```
</div>

</div>



Perlu dibiasakan untuk mengecek dulu jumlah baris dari tabel data



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
nrow(datakab)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
12017
</div>

</div>
</div>
</div>



<br>Gunakan `head` dan `tail` untuk menampilkan `n` baris teratas dan terbawah 



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
head(datakab, n = 3)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<thead><tr><th scope="col">Region Name</th><th scope="col">Region Code</th><th scope="col">Series Name</th><th scope="col">Series Code</th><th scope="col">2000 [YR2000]</th><th scope="col">2001 [YR2001]</th><th scope="col">2002 [YR2002]</th><th scope="col">2003 [YR2003]</th><th scope="col">2004 [YR2004]</th><th scope="col">2005 [YR2005]</th><th scope="col">2006 [YR2006]</th><th scope="col">2007 [YR2007]</th><th scope="col">2008 [YR2008]</th><th scope="col">2009 [YR2009]</th><th scope="col">2010 [YR2010]</th><th scope="col">2011 [YR2011]</th><th scope="col">2012 [YR2012]</th><th scope="col">2013 [YR2013]</th><th scope="col">2014 [YR2014]</th></tr></thead>
<tbody>
	<tr><td>Aceh Barat Daya, Kab.               </td><td>IDN_Aceh_Barat_Daya_Kab_73623       </td><td>Human Development Index             </td><td>IDX.HDI                             </td><td>..                                  </td><td>..                                  </td><td>..                                  </td><td>..                                  </td><td>65.87778                            </td><td>66.86649                            </td><td>67.52173                            </td><td>68.36661                            </td><td>69.38033                            </td><td>..                                  </td><td>..                                  </td><td>70.95                               </td><td>..                                  </td><td>72.07                               </td><td>..                                  </td></tr>
	<tr><td>Aceh Barat Daya, Kab.               </td><td>IDN_Aceh_Barat_Daya_Kab_73623       </td><td>Morbidity Rate (in %)               </td><td>SH.MORB.ZS                          </td><td>..                                  </td><td>..                                  </td><td>..                                  </td><td>..                                  </td><td>29.19532                            </td><td>..                                  </td><td>33.22042                            </td><td>35.90795                            </td><td>31.811                              </td><td>29.2377                             </td><td>30.0167                             </td><td>33.93033                            </td><td>30.5736273527145                    </td><td>29.909548163414                     </td><td>..                                  </td></tr>
	<tr><td>Aceh Barat Daya, Kab.               </td><td>IDN_Aceh_Barat_Daya_Kab_73623       </td><td>Net Enrollment Ratio: Primary (in %)</td><td>SE.PRM.NENR.ZS                      </td><td>..                                  </td><td>..                                  </td><td>..                                  </td><td>..                                  </td><td>94.65                               </td><td>..                                  </td><td>94.89                               </td><td>94.34                               </td><td>96.21                               </td><td>96.55                               </td><td>98.32                               </td><td>86.16                               </td><td>90.96                               </td><td>95.395058                           </td><td>97.03                               </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



<br>`n` adalah argumen opsional



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
tail(datakab)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<thead><tr><th></th><th scope="col">Region Name</th><th scope="col">Region Code</th><th scope="col">Series Name</th><th scope="col">Series Code</th><th scope="col">2000 [YR2000]</th><th scope="col">2001 [YR2001]</th><th scope="col">2002 [YR2002]</th><th scope="col">2003 [YR2003]</th><th scope="col">2004 [YR2004]</th><th scope="col">2005 [YR2005]</th><th scope="col">2006 [YR2006]</th><th scope="col">2007 [YR2007]</th><th scope="col">2008 [YR2008]</th><th scope="col">2009 [YR2009]</th><th scope="col">2010 [YR2010]</th><th scope="col">2011 [YR2011]</th><th scope="col">2012 [YR2012]</th><th scope="col">2013 [YR2013]</th><th scope="col">2014 [YR2014]</th></tr></thead>
<tbody>
	<tr><th scope="row">12012</th><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983                                                            </td><td>Villages with road: Other (in % of total villages)                                   </td><td>ROD.VILG.OTHR.ZS                                                                     </td><td>..                                                                                   </td><td>..                                                                                   </td><td>..                                                                                   </td><td>..                                                                                   </td><td>..                                                                                   </td><td>..                                                                                   </td><td>..                                                                                   </td><td>..                                                                                   </td><td>..                                                                                   </td><td>..                                                                                   </td><td>..                                                                                   </td><td>..                                                                                   </td><td>..                                                                                   </td><td>..                                                                                   </td><td>..                                                                                   </td></tr>
	<tr><th scope="row">12013</th><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td></tr>
	<tr><th scope="row">12014</th><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td></tr>
	<tr><th scope="row">12015</th><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td></tr>
	<tr><th scope="row">12016</th><td>Data from database: INDO-DAPOER (Indonesia Database for Policy and Economic Research)</td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td></tr>
	<tr><th scope="row">12017</th><td>Last Updated: 05/28/2015                                                             </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td><td>                                                                                     </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



<br>Lima baris terakhir tabel bukan merupakan data, sehingga perlu kita keluarkan. Kita bisa gunakan indeks **positif** untuk memilih baris yang **dipertahankan**,



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
tail(datakab[1:12012,], 2)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<thead><tr><th></th><th scope="col">Region Name</th><th scope="col">Region Code</th><th scope="col">Series Name</th><th scope="col">Series Code</th><th scope="col">2000 [YR2000]</th><th scope="col">2001 [YR2001]</th><th scope="col">2002 [YR2002]</th><th scope="col">2003 [YR2003]</th><th scope="col">2004 [YR2004]</th><th scope="col">2005 [YR2005]</th><th scope="col">2006 [YR2006]</th><th scope="col">2007 [YR2007]</th><th scope="col">2008 [YR2008]</th><th scope="col">2009 [YR2009]</th><th scope="col">2010 [YR2010]</th><th scope="col">2011 [YR2011]</th><th scope="col">2012 [YR2012]</th><th scope="col">2013 [YR2013]</th><th scope="col">2014 [YR2014]</th></tr></thead>
<tbody>
	<tr><th scope="row">12011</th><td>Yogyakarta, Kota                                   </td><td>IDN_Yogyakarta_Kota_17983                          </td><td>Villages with road: Gravel (in % of total villages)</td><td>ROD.VILG.GRAVL.ZS                                  </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td></tr>
	<tr><th scope="row">12012</th><td>Yogyakarta, Kota                                   </td><td>IDN_Yogyakarta_Kota_17983                          </td><td>Villages with road: Other (in % of total villages) </td><td>ROD.VILG.OTHR.ZS                                   </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



<br> atau gunakan indeks **negatif** untuk memilih baris yang **dibuang**.
> R memproses fungsi dari dalam ke luar. Namun penulisan seperti ini sulit dibaca dan diikuti urutan prosesnya. Karenanya, kini pemrograman R banyak menggunakan operator *piping* `%>%` dari library `magrittr`. `f() %>% g()` berarti output dari fungsi `f` akan menjadi argumen pertama dari fungsi `g`



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
library(magrittr)
datakab[-12013:-12017,] %>% tail(3)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<thead><tr><th></th><th scope="col">Region Name</th><th scope="col">Region Code</th><th scope="col">Series Name</th><th scope="col">Series Code</th><th scope="col">2000 [YR2000]</th><th scope="col">2001 [YR2001]</th><th scope="col">2002 [YR2002]</th><th scope="col">2003 [YR2003]</th><th scope="col">2004 [YR2004]</th><th scope="col">2005 [YR2005]</th><th scope="col">2006 [YR2006]</th><th scope="col">2007 [YR2007]</th><th scope="col">2008 [YR2008]</th><th scope="col">2009 [YR2009]</th><th scope="col">2010 [YR2010]</th><th scope="col">2011 [YR2011]</th><th scope="col">2012 [YR2012]</th><th scope="col">2013 [YR2013]</th><th scope="col">2014 [YR2014]</th></tr></thead>
<tbody>
	<tr><th scope="row">12010</th><td>Yogyakarta, Kota                                   </td><td>IDN_Yogyakarta_Kota_17983                          </td><td>Villages with road: Dirt (in % of total villages)  </td><td>ROD.VILG.DIRT.ZS                                   </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td></tr>
	<tr><th scope="row">12011</th><td>Yogyakarta, Kota                                   </td><td>IDN_Yogyakarta_Kota_17983                          </td><td>Villages with road: Gravel (in % of total villages)</td><td>ROD.VILG.GRAVL.ZS                                  </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td></tr>
	<tr><th scope="row">12012</th><td>Yogyakarta, Kota                                   </td><td>IDN_Yogyakarta_Kota_17983                          </td><td>Villages with road: Other (in % of total villages) </td><td>ROD.VILG.OTHR.ZS                                   </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



<br>Subset juga bisa dibuat dengan memfilter tabel data agar hanya memberikan baris yang nilai variabelnya memenuhi kriteria yang ditetapkan. Kita bisa gunakan fungsi `which` untuk menghasilkan indeks baris yang memenuhi kriteria tersebut.



> - Tanda titik dalam fungsi subset `[.,]` digunakan untuk memandu operator pipe bahwa input dari fungsi sebelumnya menjadi argumen di lokasi titik tersebut
> - `$` digunakan untuk memilih kolom/variabel `Series Code` yang merupakan komponen dari tabel `datakab`
> - nama variabel perlu diapit dengan *backtick* (```) hanya jika mengandung spasi  



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
which(datakab$`Series Code` != "") %>% datakab[.,] %>% tail(2)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<thead><tr><th></th><th scope="col">Region Name</th><th scope="col">Region Code</th><th scope="col">Series Name</th><th scope="col">Series Code</th><th scope="col">2000 [YR2000]</th><th scope="col">2001 [YR2001]</th><th scope="col">2002 [YR2002]</th><th scope="col">2003 [YR2003]</th><th scope="col">2004 [YR2004]</th><th scope="col">2005 [YR2005]</th><th scope="col">2006 [YR2006]</th><th scope="col">2007 [YR2007]</th><th scope="col">2008 [YR2008]</th><th scope="col">2009 [YR2009]</th><th scope="col">2010 [YR2010]</th><th scope="col">2011 [YR2011]</th><th scope="col">2012 [YR2012]</th><th scope="col">2013 [YR2013]</th><th scope="col">2014 [YR2014]</th></tr></thead>
<tbody>
	<tr><th scope="row">12011</th><td>Yogyakarta, Kota                                   </td><td>IDN_Yogyakarta_Kota_17983                          </td><td>Villages with road: Gravel (in % of total villages)</td><td>ROD.VILG.GRAVL.ZS                                  </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td></tr>
	<tr><th scope="row">12012</th><td>Yogyakarta, Kota                                   </td><td>IDN_Yogyakarta_Kota_17983                          </td><td>Villages with road: Other (in % of total villages) </td><td>ROD.VILG.OTHR.ZS                                   </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



<br>Cara lain untuk memilih baris berdasar kriteria adalah menggunakan fungsi `filter` dari library `dplyr`. 
> - Kita bisa menggunakan fungsi dari suatu library tanpa memuatnya terlebih dulu dengan menggunakan `::`
> - Bandingkan hasil perintah di bawah jika dijalankan tanpa awalan `dplyr::`
> - Perbedaan tersebut terjadi karena fungsi `filter` yang digunakan berasal dari package lain
> - Jika ada lebih dari satu fungsi yang bernama sama, R akan memprioritaskan fungsi dari library yang dimuat paling akhir.



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
dplyr::filter(datakab, `Series Code` != "")  %>% tail(2)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<thead><tr><th></th><th scope="col">Region Name</th><th scope="col">Region Code</th><th scope="col">Series Name</th><th scope="col">Series Code</th><th scope="col">2000 [YR2000]</th><th scope="col">2001 [YR2001]</th><th scope="col">2002 [YR2002]</th><th scope="col">2003 [YR2003]</th><th scope="col">2004 [YR2004]</th><th scope="col">2005 [YR2005]</th><th scope="col">2006 [YR2006]</th><th scope="col">2007 [YR2007]</th><th scope="col">2008 [YR2008]</th><th scope="col">2009 [YR2009]</th><th scope="col">2010 [YR2010]</th><th scope="col">2011 [YR2011]</th><th scope="col">2012 [YR2012]</th><th scope="col">2013 [YR2013]</th><th scope="col">2014 [YR2014]</th></tr></thead>
<tbody>
	<tr><th scope="row">12011</th><td>Yogyakarta, Kota                                   </td><td>IDN_Yogyakarta_Kota_17983                          </td><td>Villages with road: Gravel (in % of total villages)</td><td>ROD.VILG.GRAVL.ZS                                  </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td></tr>
	<tr><th scope="row">12012</th><td>Yogyakarta, Kota                                   </td><td>IDN_Yogyakarta_Kota_17983                          </td><td>Villages with road: Other (in % of total villages) </td><td>ROD.VILG.OTHR.ZS                                   </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



<br>Jika sudah yakin indeks menghasilkan subset yang diinginkan, simpan subset tersebut menjadi objek. Jangan sertakan `tail` karena yang ingin disimpan adalah keseluruhan data, bukan cuma baris terbawah saja. 



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab = dplyr::filter(datakab, `Series Code` != "") 

```
</div>

</div>



## Memilih variabel




Seperti memilih baris, kita bisa memilih variabel menggunakan indeks kolom yang terletak setelah koma di fungsi subset `[]`



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
c(1, 3:5, ncol(datakab)) %>% datakab[, .] %>% tail(4)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<thead><tr><th></th><th scope="col">Region Name</th><th scope="col">Series Name</th><th scope="col">Series Code</th><th scope="col">2000 [YR2000]</th><th scope="col">2014 [YR2014]</th></tr></thead>
<tbody>
	<tr><th scope="row">12009</th><td>Yogyakarta, Kota                                    </td><td>Villages with road: Asphalt (in % of total villages)</td><td>ROD.VILG.ASPH.ZS                                    </td><td>100                                                 </td><td>..                                                  </td></tr>
	<tr><th scope="row">12010</th><td>Yogyakarta, Kota                                    </td><td>Villages with road: Dirt (in % of total villages)   </td><td>ROD.VILG.DIRT.ZS                                    </td><td>..                                                  </td><td>..                                                  </td></tr>
	<tr><th scope="row">12011</th><td>Yogyakarta, Kota                                    </td><td>Villages with road: Gravel (in % of total villages) </td><td>ROD.VILG.GRAVL.ZS                                   </td><td>..                                                  </td><td>..                                                  </td></tr>
	<tr><th scope="row">12012</th><td>Yogyakarta, Kota                                    </td><td>Villages with road: Other (in % of total villages)  </td><td>ROD.VILG.OTHR.ZS                                    </td><td>..                                                  </td><td>..                                                  </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



<br>Indeks kolom angka bisa digantikan dengan vektor nama variabel 



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab[,c('Region Code', 'Series Name')] %>% tail

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<thead><tr><th></th><th scope="col">Region Code</th><th scope="col">Series Name</th></tr></thead>
<tbody>
	<tr><th scope="row">12007</th><td>IDN_Yogyakarta_Kota_17983                           </td><td>Total GDP based on expenditure (in IDR Million)     </td></tr>
	<tr><th scope="row">12008</th><td>IDN_Yogyakarta_Kota_17983                           </td><td>Total Population (in number of people)              </td></tr>
	<tr><th scope="row">12009</th><td>IDN_Yogyakarta_Kota_17983                           </td><td>Villages with road: Asphalt (in % of total villages)</td></tr>
	<tr><th scope="row">12010</th><td>IDN_Yogyakarta_Kota_17983                           </td><td>Villages with road: Dirt (in % of total villages)   </td></tr>
	<tr><th scope="row">12011</th><td>IDN_Yogyakarta_Kota_17983                           </td><td>Villages with road: Gravel (in % of total villages) </td></tr>
	<tr><th scope="row">12012</th><td>IDN_Yogyakarta_Kota_17983                           </td><td>Villages with road: Other (in % of total villages)  </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



<br>Pemilihan variabel juga bisa menggunakan `dplyr::select`. Namun kali ini lebih baik `dplyr` dimuat dulu agar semua fungsi pembantunya bisa ikut digunakan. 
> Ketika memuat `dplyr` akan ada pesan peringatan fungsi-fungsi dari package lain yang ditutupi oleh fungsi-fungsi `dplyr`. Fungsi `dplyr` itu sendiri akan berjalan baik, tapi penggunaan fungsi yang ditutupi kini perlu menyertakan prefix package asalnya.



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
library(dplyr)

```
</div>

</div>



Berapa ketentuan dalam pemilihan variabel di fungsi `select`:
- Nama variabel yang mengandung spasi harus diapit tanda kutip 
- Pilih sejumlah variabel yang berurutan cukup sebutkan variabel di pinggir, `var_kiri:var_kanan` 
- Pilih semua variabel yang namanya memiliki kesamaan pola, baik diawali (`starts_with`), diakhiri (`ends_with`), atau mengandung (`contains`) karakter tertentu 
- Gunakan tanda minus (`-`) untuk mengecualikan variabel 
- Urutan kolom tabel baru mengikuti urutan variabel dalam `select`
- Mengganti nama variabel yang dipilih, `nama_baru = nama_lama`



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
select(datakab, 'Region Code':'Series Code', -'Series Name', 
       region_name = 'Region Name', contains('YR'), -contains('YR201')) %>% tail(4)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<thead><tr><th></th><th scope="col">Region Code</th><th scope="col">Series Code</th><th scope="col">region_name</th><th scope="col">2000 [YR2000]</th><th scope="col">2001 [YR2001]</th><th scope="col">2002 [YR2002]</th><th scope="col">2003 [YR2003]</th><th scope="col">2004 [YR2004]</th><th scope="col">2005 [YR2005]</th><th scope="col">2006 [YR2006]</th><th scope="col">2007 [YR2007]</th><th scope="col">2008 [YR2008]</th><th scope="col">2009 [YR2009]</th></tr></thead>
<tbody>
	<tr><th scope="row">12009</th><td>IDN_Yogyakarta_Kota_17983</td><td>ROD.VILG.ASPH.ZS         </td><td>Yogyakarta, Kota         </td><td>100                      </td><td>..                       </td><td>..                       </td><td>100                      </td><td>..                       </td><td>100                      </td><td>..                       </td><td>..                       </td><td>100                      </td><td>..                       </td></tr>
	<tr><th scope="row">12010</th><td>IDN_Yogyakarta_Kota_17983</td><td>ROD.VILG.DIRT.ZS         </td><td>Yogyakarta, Kota         </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td></tr>
	<tr><th scope="row">12011</th><td>IDN_Yogyakarta_Kota_17983</td><td>ROD.VILG.GRAVL.ZS        </td><td>Yogyakarta, Kota         </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td></tr>
	<tr><th scope="row">12012</th><td>IDN_Yogyakarta_Kota_17983</td><td>ROD.VILG.OTHR.ZS         </td><td>Yogyakarta, Kota         </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td><td>..                       </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



## Merubah Nama Variabel



Jika hanya ingin mengganti nama sejumlah variabel, tanpa merubah struktur tabel data, gunakan `dplyr::rename`
> hasil dari `rename` adalah tabel data, sehingga bisa langsung disubset dengan `[]` tanpa menggunakan *piping* `%>%`



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
rename(datakab, region_name = 'Region Name', series_code = 'Series Code') [100:102,]

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<thead><tr><th></th><th scope="col">region_name</th><th scope="col">Region Code</th><th scope="col">Series Name</th><th scope="col">series_code</th><th scope="col">2000 [YR2000]</th><th scope="col">2001 [YR2001]</th><th scope="col">2002 [YR2002]</th><th scope="col">2003 [YR2003]</th><th scope="col">2004 [YR2004]</th><th scope="col">2005 [YR2005]</th><th scope="col">2006 [YR2006]</th><th scope="col">2007 [YR2007]</th><th scope="col">2008 [YR2008]</th><th scope="col">2009 [YR2009]</th><th scope="col">2010 [YR2010]</th><th scope="col">2011 [YR2011]</th><th scope="col">2012 [YR2012]</th><th scope="col">2013 [YR2013]</th><th scope="col">2014 [YR2014]</th></tr></thead>
<tbody>
	<tr><th scope="row">100</th><td>Aceh Selatan, Kab.                         </td><td>IDN_Aceh_Selatan_Kab_73626                 </td><td>Number of schools at primary level         </td><td>SE.SCHL.PRM                                </td><td>333                                        </td><td>..                                         </td><td>..                                         </td><td>211                                        </td><td>..                                         </td><td>223                                        </td><td>..                                         </td><td>..                                         </td><td>128                                        </td><td>..                                         </td><td>..                                         </td><td>232                                        </td><td>..                                         </td><td>..                                         </td><td>..                                         </td></tr>
	<tr><th scope="row">101</th><td>Aceh Selatan, Kab.                         </td><td>IDN_Aceh_Selatan_Kab_73626                 </td><td>Number of schools at Senior Secondary level</td><td>SE.SCHL.SRSEC                              </td><td>25                                         </td><td>..                                         </td><td>..                                         </td><td>21                                         </td><td>..                                         </td><td>25                                         </td><td>..                                         </td><td>..                                         </td><td>15                                         </td><td>..                                         </td><td>..                                         </td><td>40                                         </td><td>..                                         </td><td>..                                         </td><td>..                                         </td></tr>
	<tr><th scope="row">102</th><td>Aceh Selatan, Kab.                         </td><td>IDN_Aceh_Selatan_Kab_73626                 </td><td>Poverty Line (in IDR)                      </td><td>SI.POV.NAPL                                </td><td>..                                         </td><td>..                                         </td><td>..                                         </td><td>..                                         </td><td>..                                         </td><td>171815                                     </td><td>186227                                     </td><td>196167                                     </td><td>203761                                     </td><td>236741                                     </td><td>257640                                     </td><td>278854                                     </td><td>281158                                     </td><td>283446                                     </td><td>285301                                     </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



<br>Merubah nama bisa pula dilakukan dengan meng-*assign* vektor nama baru dengan panjang sama seperti nama yang hendak digantikan



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
names(datakab)[1:3] = names(datakab)[1:3] %>% toupper
names(datakab) %>% t

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<tbody>
	<tr><td>REGION NAME  </td><td>REGION CODE  </td><td>SERIES NAME  </td><td>Series Code  </td><td>2000 [YR2000]</td><td>2001 [YR2001]</td><td>2002 [YR2002]</td><td>2003 [YR2003]</td><td>2004 [YR2004]</td><td>2005 [YR2005]</td><td>2006 [YR2006]</td><td>2007 [YR2007]</td><td>2008 [YR2008]</td><td>2009 [YR2009]</td><td>2010 [YR2010]</td><td>2011 [YR2011]</td><td>2012 [YR2012]</td><td>2013 [YR2013]</td><td>2014 [YR2014]</td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



Format penulisan nama-nama variabel di atas akan mempersulit penulisan program selanjutnya.  Fungsi `clean_names` dari package `janitor` bisa merubah sekaligus seluruh nama variabel dalam data agar mengikuti gaya penulisan nama variabel yang banyak disarankan.



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab = janitor::clean_names(datakab)
names(datakab) %>% t

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<tbody>
	<tr><td>region_name </td><td>region_code </td><td>series_name </td><td>series_code </td><td>x2000_yr2000</td><td>x2001_yr2001</td><td>x2002_yr2002</td><td>x2003_yr2003</td><td>x2004_yr2004</td><td>x2005_yr2005</td><td>x2006_yr2006</td><td>x2007_yr2007</td><td>x2008_yr2008</td><td>x2009_yr2009</td><td>x2010_yr2010</td><td>x2011_yr2011</td><td>x2012_yr2012</td><td>x2013_yr2013</td><td>x2014_yr2014</td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



Kita bisa sederhanakan lagi nama-nama variabel tahun dengan hanya mengambil karakter setelah garis bawah ( _ ). Kita gunakan fungsi `str_replace` dari library `stringr` untuk mendeteksi pola karakter yang ingin dihapus, yakni diganti dengan karakter kosong (`''`)



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab %<>% rename_at(vars(starts_with('x20')), 
                       funs(stringr::str_replace(., 'x20[0-9][0-9]_', ''))) 
datakab %>% names %>% t

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<tbody>
	<tr><td>region_name</td><td>region_code</td><td>series_name</td><td>series_code</td><td>yr2000     </td><td>yr2001     </td><td>yr2002     </td><td>yr2003     </td><td>yr2004     </td><td>yr2005     </td><td>yr2006     </td><td>yr2007     </td><td>yr2008     </td><td>yr2009     </td><td>yr2010     </td><td>yr2011     </td><td>yr2012     </td><td>yr2013     </td><td>yr2014     </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



## Menggabungkan data



Untuk keperluan latihan penggabungan, datakab dipecah menjadi dua data dengan variabel berbeda kecuali variabel ID



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
data1 = datakab %>% select(region_name:series_code, contains('201'))
names(data1) %>% t

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<tbody>
	<tr><td>region_name</td><td>region_code</td><td>series_name</td><td>series_code</td><td>yr2010     </td><td>yr2011     </td><td>yr2012     </td><td>yr2013     </td><td>yr2014     </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
data2 = datakab %>% select(-contains('201'))
names(data2) %>% t

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<tbody>
	<tr><td>region_name</td><td>region_code</td><td>series_name</td><td>series_code</td><td>yr2000     </td><td>yr2001     </td><td>yr2002     </td><td>yr2003     </td><td>yr2004     </td><td>yr2005     </td><td>yr2006     </td><td>yr2007     </td><td>yr2008     </td><td>yr2009     </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



<br>Lalu gabungkan dua data tersebut menggunakan  `merge` dari base R, atau seri fungsi 
`_join` dari `dplyr`. Penggabungan baris berdasar variabel ID dalam argumen `by`. Jika ada variabel bernama sama tapi tidak menjadi argumen `by`, maka di data baru variabel tersebut akan ditambahi akhiran `.x` dan `.y`



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
merge(data1, data2, by = c('region_code', 'series_code')) %>% tail(3)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<thead><tr><th></th><th scope="col">region_code</th><th scope="col">series_code</th><th scope="col">region_name.x</th><th scope="col">series_name.x</th><th scope="col">yr2010</th><th scope="col">yr2011</th><th scope="col">yr2012</th><th scope="col">yr2013</th><th scope="col">yr2014</th><th scope="col">region_name.y</th><th scope="col">...</th><th scope="col">yr2000</th><th scope="col">yr2001</th><th scope="col">yr2002</th><th scope="col">yr2003</th><th scope="col">yr2004</th><th scope="col">yr2005</th><th scope="col">yr2006</th><th scope="col">yr2007</th><th scope="col">yr2008</th><th scope="col">yr2009</th></tr></thead>
<tbody>
	<tr><th scope="row">12010</th><td>IDN_Yogyakarta_Kota_17983             </td><td>SI.POV.NAPR.ZS                        </td><td>Yogyakarta, Kota                      </td><td>Poverty Rate (in % of population)     </td><td>9.75                                  </td><td>9.62                                  </td><td>9.38                                  </td><td>8.82                                  </td><td>8.67                                  </td><td>Yogyakarta, Kota                      </td><td>...                                   </td><td>..                                    </td><td>..                                    </td><td>14.52                                 </td><td>12.59                                 </td><td>21.77                                 </td><td>10.5                                  </td><td>10.22                                 </td><td>9.78                                  </td><td>10.81                                 </td><td>10.05                                 </td></tr>
	<tr><th scope="row">12011</th><td>IDN_Yogyakarta_Kota_17983             </td><td>SI.POV.NGAP                           </td><td>Yogyakarta, Kota                      </td><td>Poverty Gap (index)                   </td><td>1.29                                  </td><td>1.19                                  </td><td>1.57                                  </td><td>1.24                                  </td><td>1.14                                  </td><td>Yogyakarta, Kota                      </td><td>...                                   </td><td>..                                    </td><td>..                                    </td><td>3.23                                  </td><td>3.23                                  </td><td>2.96                                  </td><td>2.34                                  </td><td>1.88                                  </td><td>2.26                                  </td><td>2.1                                   </td><td>1.91                                  </td></tr>
	<tr><th scope="row">12012</th><td>IDN_Yogyakarta_Kota_17983             </td><td>SP.POP.TOTL                           </td><td>Yogyakarta, Kota                      </td><td>Total Population (in number of people)</td><td>388627                                </td><td>392506                                </td><td>397594                                </td><td>402679                                </td><td>..                                    </td><td>Yogyakarta, Kota                      </td><td>...                                   </td><td>397398                                </td><td>395775                                </td><td>394140                                </td><td>392492                                </td><td>396238                                </td><td>419163.765233477                      </td><td>445258                                </td><td>451118                                </td><td>456915                                </td><td>462663                                </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



<br>Jika variabel id berbeda nama di kedua data, pasangkan variabel id dari kedua data dengan tanda `=`, dengan format 
```
by = c("ID1_data1" = "ID1_data2", "ID2_data1" = "ID2_data2")
```
Jika tidak ada argumen `by`, penggabungan dilakukan dengan semua variabel bernama sama



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
dplyr::inner_join(data1, data2) %>% tail(3)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<thead><tr><th></th><th scope="col">region_name</th><th scope="col">region_code</th><th scope="col">series_name</th><th scope="col">series_code</th><th scope="col">yr2010</th><th scope="col">yr2011</th><th scope="col">yr2012</th><th scope="col">yr2013</th><th scope="col">yr2014</th><th scope="col">yr2000</th><th scope="col">yr2001</th><th scope="col">yr2002</th><th scope="col">yr2003</th><th scope="col">yr2004</th><th scope="col">yr2005</th><th scope="col">yr2006</th><th scope="col">yr2007</th><th scope="col">yr2008</th><th scope="col">yr2009</th></tr></thead>
<tbody>
	<tr><th scope="row">12010</th><td>Yogyakarta, Kota                                   </td><td>IDN_Yogyakarta_Kota_17983                          </td><td>Villages with road: Dirt (in % of total villages)  </td><td>ROD.VILG.DIRT.ZS                                   </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td></tr>
	<tr><th scope="row">12011</th><td>Yogyakarta, Kota                                   </td><td>IDN_Yogyakarta_Kota_17983                          </td><td>Villages with road: Gravel (in % of total villages)</td><td>ROD.VILG.GRAVL.ZS                                  </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td></tr>
	<tr><th scope="row">12012</th><td>Yogyakarta, Kota                                   </td><td>IDN_Yogyakarta_Kota_17983                          </td><td>Villages with road: Other (in % of total villages) </td><td>ROD.VILG.OTHR.ZS                                   </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td><td>..                                                 </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



Secara default, hasil merge hanya mempertahankan baris dengan ID yang terdapat di kedua data yang digabungkan. Hasil default merge ini ekuivalen dengan hasil dari `dplyr::inner_join`

Jika ingin semua baris dipertahankan walau ID hanya terdapat di salah satu data, maka gunakan argumen `all = TRUE`. Ini ekuivalen dengan hasil dari `dplyr::all_join`

Jika hanya ingin mempertahankan semua baris dari salah satu data 
  - data I gunakan `all.x = TRUE`, ekuivalen dengan `dplyr::left_join`
  - data II gunakan `all.y = TRUE`, ekuivalen dengan `dplyr::right_join`



## Merubah Nilai



Data dalam tabel bisa dirubah dengan meng-*assign* nilai baru ke lokasi baris dan kolom yang ingin dirubah. Dimensi nilai yang di-*assign* harus sama dengan dimensi data yang dirubah. Berikut ini data di baris kedua dan kolom kelima `datakab` diganti dari karakter ".." menjadi `NA`
> `NA`, kependekan dari *Not Available*, adalah cara R mengeksplisitkan bagian data yang tidak memiliki nilai (*missing values*). Sel yang tampak kosong di R adalah karakter kosong yang dianggap ada datanya, yakni observasi yang valid.



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab[2,5]

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
'..'
</div>

</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
(datakab[2,5] = NA)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
&lt;NA&gt;
</div>

</div>
</div>
</div>



Di bawah ini bisa dilihat bahwa variabel-variabel tahun didominasi dengan karakter ".." yang sebenarnya mewakili *missing values*. Karena di atas kita telah mengganti satu observasi menjadi `NA` dalam kolom ke-5 data, yakni variabel `yr2000`,  maka variabel tersebut tidak lagi valid 100%. 



> `dfSummary` dari package `summarytools` menampilkan ringkasan karakteristik data. Argumen `graph.col = F` digunakan karena informasi pada histogram sudah diwakili oleh kolom frekuensi `Freqs`. Demikian pula `na.col` yang mengandung jumlah dan persentase *missing values* adalah kebalikan dari kolom `Valid`. 



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab %>% select(yr2000, yr2001) %>% 
            summarytools::dfSummary(graph.col = F, na.col = F) %>% 
            print

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
Data Frame Summary     
N: 12012   
--------------------------------------------------------------------
No   Variable      Stats / Values    Freqs (% of Valid)   Valid     
---- ------------- ----------------- -------------------- ----------
1    yr2000        1. ..             7343 (61.1%)         12011     
     [character]   2. 1              85 ( 0.7%)           (99.99%)  
                   3. 2              79 ( 0.7%)                     
                   4. 4              49 ( 0.4%)                     
                   5. 3              47 ( 0.4%)                     
                   6. 100            31 ( 0.3%)                     
                   7. 5              26 ( 0.2%)                     
                   8. 7              21 ( 0.2%)                     
                   9. 6              20 ( 0.2%)                     
                   10. 26            18 ( 0.1%)                     
                   [ 2901 others ]   4292 (40.2%)                   

2    yr2001        1. ..             10189 (84.8%)        12012     
     [character]   2. 94.52          4 ( 0.0%)            (100%)    
                   3. 90.77          3 ( 0.0%)                      
                   4. 90.92          3 ( 0.0%)                      
                   5. 92.16          3 ( 0.0%)                      
                   6. 93.44          3 ( 0.0%)                      
                   7. 93.53          3 ( 0.0%)                      
                   8. 93.58          3 ( 0.0%)                      
                   9. 93.69          3 ( 0.0%)                      
                   10. 94.03         3 ( 0.0%)                      
                   [ 1724 others ]   1795 (17.9%)                   
--------------------------------------------------------------------
```
</div>
</div>
</div>



Salah satu unsur penyiapan data untuk analisis adalah mengeksplisitkan seluruh *missing values* pada data menjadi `NA` agar diproses secara benar dalam analisis berikutnya. Untuk keperluan ini,  kombinasi `dplyr::mutate` dan  `ifelse` bisa digunakan untuk merubah seluruh nilai variabel ".." menjadi `NA`.
> `ifelse` akan memberikan nilai argumen kedua jika ekspresi di argumen pertamanya benar, dan memberikan nilai argumen ketiga jika ekspresi tersebut salah. Uji kesamaan di R menggunakan simbol `==`, bukan `=`. Ketidaksamaan menggunakan simbol `!=`. Sementara relasi lainnya menggunakan simbol matematika seperti umumnya, `<`, `>`, `<=`, dan `>=`. 



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab %>% mutate(yr2000 = ifelse(yr2000 == '..', NA, yr2000),
                   yr2001 = ifelse(yr2001 == '..', NA, yr2001)) %>% 
            select(yr2000:yr2002) %>% 
            summarytools::dfSummary(graph.col = F, na.col = F) %>% 
            print

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
Data Frame Summary     
N: 12012   
--------------------------------------------------------------------
No   Variable      Stats / Values    Freqs (% of Valid)   Valid     
---- ------------- ----------------- -------------------- ----------
1    yr2000        1. 1              85 ( 1.8%)           4668      
     [character]   2. 2              79 ( 1.7%)           (38.86%)  
                   3. 4              49 ( 1.0%)                     
                   4. 3              47 ( 1.0%)                     
                   5. 100            31 ( 0.7%)                     
                   6. 5              26 ( 0.6%)                     
                   7. 7              21 ( 0.4%)                     
                   8. 6              20 ( 0.4%)                     
                   9. 26             18 ( 0.4%)                     
                   10. 11            17 ( 0.4%)                     
                   [ 2900 others ]   4275 (87.3%)                   

2    yr2001        1. 94.52          4 ( 0.2%)            1823      
     [character]   2. 90.77          3 ( 0.2%)            (15.18%)  
                   3. 90.92          3 ( 0.2%)                      
                   4. 92.16          3 ( 0.2%)                      
                   5. 93.44          3 ( 0.2%)                      
                   6. 93.53          3 ( 0.2%)                      
                   7. 93.58          3 ( 0.2%)                      
                   8. 93.69          3 ( 0.2%)                      
                   9. 94.03          3 ( 0.2%)                      
                   10. 94.07         3 ( 0.2%)                      
                   [ 1723 others ]   1792 (90.3%)                   

3    yr2002        1. ..             9487 (79.0%)         12012     
     [character]   2. 4.34           5 ( 0.0%)            (100%)    
                   3. 2.19           4 ( 0.0%)                      
                   4. 2.33           4 ( 0.0%)                      
                   5. 2.34           4 ( 0.0%)                      
                   6. 2.53           4 ( 0.0%)                      
                   7. 0.65           3 ( 0.0%)                      
                   8. 0.86           3 ( 0.0%)                      
                   9. 0.97           3 ( 0.0%)                      
                   10. 0.98          3 ( 0.0%)                      
                   [ 2273 others ]   2492 (24.7%)                   
--------------------------------------------------------------------
```
</div>
</div>
</div>



Gunakan `mutate_at` untuk memutasi sekaligus semua variabel yang dipilih dengan fungsi yang sama, tanpa harus mengulang satu per satu. Agar perintah mutasi bisa diterapkan ke semua variabel, nama variabel diganti dengan titik (`.`) dalam argumen `funs`



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab %<>% mutate_at(vars(starts_with("yr20")), funs(ifelse(. == '..', NA, .))) 

```
</div>

</div>



Data pada variabel-variabel yang diawali `yr` pada dasarnya merupakan variabel angka, sehingga lebih baik dikonversi menjadi tipe angka dengan `as.numeric`.



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab %<>% mutate_at(vars(starts_with("yr20")), as.numeric)

```
</div>

</div>



`dfSummary` kini dapat menyajikan statitik yang meringkas variabel angka, bukan hanya frekuensi tiap nilai uniknya.



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab %>% select(starts_with("yr201")) %>%
            summarytools::dfSummary(graph.col = F, na.col = F) %>% 
            print

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
Data Frame Summary     
N: 12012   
------------------------------------------------------------------------------------------
No   Variable    Stats / Values                          Freqs (% of Valid)     Valid     
---- ----------- --------------------------------------- ---------------------- ----------
1    yr2010      mean (sd) : 1360005.99 (24387637.53)    3776 distinct values   4305      
     [numeric]   min < med < max :                                              (35.84%)  
                 0.19 < 59.02 < 862158976                                                 
                 IQR (CV) : 42791.39 (17.93)                                              

2    yr2011      mean (sd) : 329813.33 (11716890.33)     5981 distinct values   10396     
     [numeric]   min < med < max :                                              (86.55%)  
                 0 < 57 < 982540032                                                       
                 IQR (CV) : 80.45 (35.53)                                                 

3    yr2012      mean (sd) : 150075.75 (1148162.6)       3720 distinct values   4273      
     [numeric]   min < med < max :                                              (35.57%)  
                 0 < 61.9 < 44643586                                                      
                 IQR (CV) : 78.08 (7.65)                                                  

4    yr2013      mean (sd) : 137749.78 (1099946.11)      4373 distinct values   4778      
     [numeric]   min < med < max :                                              (39.78%)  
                 0 < 69.12 < 45340799                                                     
                 IQR (CV) : 74.97 (7.99)                                                  

5    yr2014      mean (sd) : 52560.86 (120968.25)        2582 distinct values   3180      
     [numeric]   min < med < max :                                              (26.47%)  
                 0.2 < 68.97 < 657702                                                     
                 IQR (CV) : 85.91 (2.3)                                                   
------------------------------------------------------------------------------------------
```
</div>
</div>
</div>



## Pivot Tabel



- Tahun pada dasarnya bukan nama variabel, sehingga bisa dikumpulkan menjadi satu kolom/variabel dengan menggunakan `dplyr::gather`



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab %<>% gather(year, val, starts_with('yr'))  
datakab %>% head(2)

```
</div>

</div>



Kolom `series_code` dan `series_name` sebenarnya berisikan nama-nama variabel. Agar data rapi, siap analisis, nama-nama variabel dalam kolom tersebut perlu dijadikan sebagai nama kolom. 

`dplyr::spread` bisa digunakan untuk keperluan ini. Dalam menerapkannya, salah satu dari `series_code` atau `series_name` perlu dibuang dulu karena redundan dan justru membuat hasilnya tak sesuai harapan.



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab %<>% mutate(year = str_replace(year, 'yr', '') %>% 
                          as.integer) %>% 
            select(-series_code) %>% 
            spread(key = series_name, value = val)
datakab %>% head(2)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<thead><tr><th scope="col">region_name</th><th scope="col">region_code</th><th scope="col">year</th><th scope="col">Human Development Index</th><th scope="col">Morbidity Rate (in %)</th><th scope="col">Net Enrollment Ratio: Junior Secondary (in %)</th><th scope="col">Net Enrollment Ratio: Primary (in %)</th><th scope="col">Net Enrollment Ratio: Senior Secondary (in %)</th><th scope="col">Number of Doctors</th><th scope="col">Number of hospitals</th><th scope="col">...</th><th scope="col">Number of schools at Senior Secondary level</th><th scope="col">Poverty Gap (index)</th><th scope="col">Poverty Line (in IDR)</th><th scope="col">Poverty Rate (in % of population)</th><th scope="col">Total GDP based on expenditure (in IDR Million)</th><th scope="col">Total Population (in number of people)</th><th scope="col">Villages with road: Asphalt (in % of total villages)</th><th scope="col">Villages with road: Dirt (in % of total villages)</th><th scope="col">Villages with road: Gravel (in % of total villages)</th><th scope="col">Villages with road: Other (in % of total villages)</th></tr></thead>
<tbody>
	<tr><td>Aceh Barat Daya, Kab.        </td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>2000                         </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>...                          </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td></tr>
	<tr><td>Aceh Barat Daya, Kab.        </td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>2001                         </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>...                          </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td><td>NA                           </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



Nama kolom-kolom baru ini tidak memenuhi gaya standar. `janitor::clean_names` bisa digunakan lagi untuk menstandarisasi nama. Dan sekedar untuk menyingkat nama variabel, bagian  nama yang menjelaskan unit pengukuran bisa dihapus dengan bantuan fungsi `str_replace_all` dari library `stringr`.
> `str_replace` dan `str_detect` mencari urutan karakter yang memenuhi pola yang dispesifikasi menggunakan syntax [regular expression](https://regex101.com).



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab %<>% janitor::clean_names()
names(datakab) %<>% str_replace_all('_in_.+$', '') %>% t
datakab %>% names %>% t

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<tbody>
	<tr><td>region_name                                </td><td>region_code                                </td><td>year                                       </td><td>human_development_index                    </td><td>morbidity_rate                             </td><td>net_enrollment_ratio_junior_secondary      </td><td>net_enrollment_ratio_primary               </td><td>net_enrollment_ratio_senior_secondary      </td><td>number_of_doctors                          </td><td>number_of_hospitals                        </td><td>...                                        </td><td>number_of_schools_at_senior_secondary_level</td><td>poverty_gap_index                          </td><td>poverty_line                               </td><td>poverty_rate                               </td><td>total_gdp_based_on_expenditure             </td><td>total_population                           </td><td>villages_with_road_asphalt                 </td><td>villages_with_road_dirt                    </td><td>villages_with_road_gravel                  </td><td>villages_with_road_other                   </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



## Menyimpan dan Menghapus Objek



- simpan semua objek R di memori ke file dengan perintah `save.image`
- gunakan `save` jika hanya sebagian objek yang ingin disimpan  
- simpan image dengan nama `.RData` jika ingin otomatis dimuat ke memori tiap awal menjalankan R dari direktori tersebut



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
save.image(file = ".RData")
save(datakab, file = "datakab.rda")

```
</div>

</div>



- hapus objek R dari memori dengan `rm`



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
rm(data1, data2)
ls()

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
'datakab'
</div>

</div>
</div>
</div>



- `ls` memberikan vektor nama semua objek yang ada di memori



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
rm(list = ls())
ls()

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">

</div>

</div>
</div>
</div>



- gunakan `load` untuk memuat semua objek dalam file image ke memori



- saat dimuat kembali dari file image, nama objek akan sama dengan saat disimpan 
- untuk bisa bebas memberikan nama baru pada objek saat dimuat kembali, simpan dengan `saveRDS` dan muat dengan `readRDS`
- kedua perintah ini hanya bisa menyimpan dan memuat satu objek



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
load('datakab.rda')
ls()

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
'datakab'
</div>

</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
saveRDS(datakab, file = "datakab.rds")
indodapoer = readRDS('datakab.rds')
ls()

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<ol class=list-inline>
	<li>'datakab'</li>
	<li>'indodapoer'</li>
</ol>

</div>

</div>
</div>
</div>

