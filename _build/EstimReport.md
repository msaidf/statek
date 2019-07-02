---
redirect_from:
  - "/estimreport"
interact_link: content/EstimReport.ipynb
kernel_name: ir
has_widgets: false
title: 'Estimasi dan Pelaporan'
prev_page:
  url: /IntroMetrics
  title: 'Pengantar Ekonometri'
next_page:
  url: 
  title: ''
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---


# Estimasi dan Pelaporan



## Estimasi Model Regresi



Menjalankan regresi OLS pada R menggunakan perintah `lm`. Berikut adalah regresi tingkat morbiditas terhadap jumlah dokter, bidan, dan pendapatan domestik bruto per kapita di tiap kabupaten, menggunakan data INDO-DAPOER dari World Bank yang sudah disiapkan di bab sebelumnya dan tersimpan di file `datakab.rds`. 

Variabel pendapatan domestik bruto per kapita tidak terdapat di data tersebut, namun dapat dihitung sendiri dengan membagi variabel pendapatan domestik bruto dengan total populasi. Perhitungan itu bisa langsung dilakukan dalam spesifikasi persamaan pada fungsi `lm` dengan menempatkan perhitungan dalam `I()`.



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
library(tidyverse)
datakab = readRDS('datakab.rds')

lm(morbidity_rate ~ number_of_doctors + number_of_midwives + 
                    I(total_gdp_based_on_expenditure/total_population), 
   data = datakab)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_data_text}
```

Call:
lm(formula = morbidity_rate ~ number_of_doctors + number_of_midwives + 
    I(total_gdp_based_on_expenditure/total_population), data = datakab)

Coefficients:
                                       (Intercept)  
                                        28.9713794  
                                 number_of_doctors  
                                        -0.0009816  
                                number_of_midwives  
                                         0.0002814  
I(total_gdp_based_on_expenditure/total_population)  
                                         0.0135187  

```

</div>
</div>
</div>



Jika variabel hasil perhitungan akan digunakan lagi dalam analisis lainnya, lebih baik ditambahkan sebagai variabel baru dalam data.



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab = datakab %>% mutate(gdp_per_capita = total_gdp_based_on_expenditure/total_population)
reg_morbid = lm(morbidity_rate ~ number_of_doctors + number_of_midwives + gdp_per_capita, datakab)
reg_morbid

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_data_text}
```

Call:
lm(formula = morbidity_rate ~ number_of_doctors + number_of_midwives + 
    gdp_per_capita, data = datakab)

Coefficients:
       (Intercept)   number_of_doctors  number_of_midwives      gdp_per_capita  
        28.9713794          -0.0009816           0.0002814           0.0135187  

```

</div>
</div>
</div>



Output fungsi `lm` bisa disimpan menjadi obyek tipe/kelas `lm`, yang bisa digunakan untuk proses analisis berikutnya. 



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
class(reg_morbid)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
'lm'
</div>

</div>
</div>
</div>



Obyek `lm` merupakan kumpulan dari vektor dan matriks yang menyimpan hasil estimasi, nilai residual dan prediksi variabel respon, dan bagian data dari variabel-variabel yang dilibatkan dalam estimasi. 

Komponen obyek `lm` bisa didaftar namanya dengan perintah `names` dan ditampilkan dengan operator `$`.



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
names(reg_morbid) %>% t

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<tbody>
	<tr><td>coefficients </td><td>residuals    </td><td>effects      </td><td>rank         </td><td>fitted.values</td><td>assign       </td><td>qr           </td><td>df.residual  </td><td>na.action    </td><td>xlevels      </td><td>call         </td><td>terms        </td><td>model        </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
reg_morbid$coefficients %>% t

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<thead><tr><th scope="col">(Intercept)</th><th scope="col">number_of_doctors</th><th scope="col">number_of_midwives</th><th scope="col">gdp_per_capita</th></tr></thead>
<tbody>
	<tr><td>28.97138     </td><td>-0.0009816237</td><td>0.0002814264 </td><td>0.01351866   </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



> Catatan: Kedua perintah di atas bisa dijalankan tanpa piping ke fungsi transpose ` %>% t`, yang digunakan di sini semata untuk menghemat ruang untuk menampilkan output R dan membuatnya lebih mudah dibaca. 



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
tail(reg_morbid$model)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<thead><tr><th></th><th scope="col">morbidity_rate</th><th scope="col">number_of_doctors</th><th scope="col">number_of_midwives</th><th scope="col">gdp_per_capita</th></tr></thead>
<tbody>
	<tr><th scope="row">7164</th><td>36.17800 </td><td> 798     </td><td> 9243    </td><td>18.509821</td></tr>
	<tr><th scope="row">7167</th><td>27.18699 </td><td>1157     </td><td> 5179    </td><td>23.923051</td></tr>
	<tr><th scope="row">7174</th><td>16.62400 </td><td>2187     </td><td> 8792    </td><td> 8.763994</td></tr>
	<tr><th scope="row">7176</th><td>19.77800 </td><td>2761     </td><td> 7142    </td><td>11.527983</td></tr>
	<tr><th scope="row">7179</th><td>25.19100 </td><td>2442     </td><td>22611    </td><td>16.874743</td></tr>
	<tr><th scope="row">7182</th><td>25.44086 </td><td>2874     </td><td>12420    </td><td>23.762079</td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



## Pelaporan Hasil Regresi



Ada berapa library R yang memudahkan pelaporan hasil regresi beserta statistik terkait, seperti `stargazer` dan `texreg`. Library tersebut juga memfasilitasi perbandingan antar model dengan menampilkan hasil dari beberapa regresi secara berdampingan. 

Untuk menampilkan laporan di console R, gunakan argumen `type = 'text'` di stargazer dan fungsi `screenreg` untuk library `texreg`. 
> Piping hasil `screenreg` ke `print` tidak diperlukan di console, hanya perlu ditambahkan untuk penampilan di jupyter notebook.



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
reg_morbid_2 = lm(morbidity_rate ~ number_of_doctors + number_of_midwives, datakab)

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
list(reg_morbid, reg_morbid_2) %>% texreg::screenreg() %>% print

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```

===========================================
                    Model 1     Model 2    
-------------------------------------------
(Intercept)          28.97 ***    29.11 ***
                     (1.03)       (0.22)   
number_of_doctors    -0.00        -0.00 *  
                     (0.00)       (0.00)   
number_of_midwives    0.00         0.00    
                     (0.00)       (0.00)   
gdp_per_capita        0.01                 
                     (0.04)                
-------------------------------------------
R^2                   0.03         0.00    
Adj. R^2             -0.00         0.00    
Num. obs.           110         1825       
RMSE                  6.71         8.78    
===========================================
*** p < 0.001, ** p < 0.01, * p < 0.05
```
</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
stargazer::stargazer(reg_morbid, reg_morbid_2, type = 'text')

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```

============================================================
                              Dependent variable:           
                    ----------------------------------------
                                 morbidity_rate             
                            (1)                 (2)         
------------------------------------------------------------
number_of_doctors         -0.001              -0.001**      
                          (0.001)             (0.001)       
                                                            
number_of_midwives        0.0003              0.0003*       
                         (0.0002)             (0.0002)      
                                                            
gdp_per_capita             0.014                            
                          (0.039)                           
                                                            
Constant                 28.971***           29.111***      
                          (1.032)             (0.217)       
                                                            
------------------------------------------------------------
Observations                110                1,825        
R2                         0.026               0.002        
Adjusted R2               -0.002               0.001        
Residual Std. Error  6.708 (df = 106)    8.778 (df = 1822)  
F Statistic         0.928 (df = 3; 106) 2.219 (df = 2; 1822)
============================================================
Note:                            *p<0.1; **p<0.05; ***p<0.01
```
</div>
</div>
</div>



`stargazer` dan `texreg` juga menyediakan format output latex dan html.
- untuk output latex, gunakan argumen `type = tex` di fungsi `stargazer`, dan fungsi `texreg` di library `texreg`
- untuk output html, gunakan argumen `type = html` di fungsi `stargazer`, dan fungsi `htmlreg` di library `texreg`



Format latex dan html sulit dibaca di layar. Tampilan di layar perlu disalin dulu ke file dokumen dan ditampilkan sebagai pdf untuk latex atau melalui browser untuk html. Output latex dan html bisa juga langsung disimpan ke file dengan menyebutkan path dan nama file pada argumen `out` untuk `stargazer` dan `file` untuk `texreg`.



`stargazer` otomatis mengenali tipe output yang diinginkan dari ekstensi nama file, sehingga tidak perlu menyebutkan argumen `type` lagi. 



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
texreg::texreg(list(reg_morbid, reg_morbid_2), file = 'reg_morbid.tex')
stargazer::stargazer(reg_morbid, reg_morbid_2, out = 'reg_morbid.html')

```
</div>

</div>



Untuk menampilkan output di dokumen format doc/docx atau ppt/pptx, bisa dengan menyalin tampilan output html di browser. Output html bisa juga ditampilkan di jupyter notebook dengan bantuan `IRdisplay::display_html`



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
IRdisplay::display_html(file = 'reg_morbid.html')

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">

<table style="text-align:center"><tr><td colspan="3" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left"></td><td colspan="2"><em>Dependent variable:</em></td></tr>
<tr><td></td><td colspan="2" style="border-bottom: 1px solid black"></td></tr>
<tr><td style="text-align:left"></td><td colspan="2">morbidity_rate</td></tr>
<tr><td style="text-align:left"></td><td>(1)</td><td>(2)</td></tr>
<tr><td colspan="3" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left">number_of_doctors</td><td>-0.001</td><td>-0.001<sup>**</sup></td></tr>
<tr><td style="text-align:left"></td><td>(0.001)</td><td>(0.001)</td></tr>
<tr><td style="text-align:left"></td><td></td><td></td></tr>
<tr><td style="text-align:left">number_of_midwives</td><td>0.0003</td><td>0.0003<sup>*</sup></td></tr>
<tr><td style="text-align:left"></td><td>(0.0002)</td><td>(0.0002)</td></tr>
<tr><td style="text-align:left"></td><td></td><td></td></tr>
<tr><td style="text-align:left">gdp_per_capita</td><td>0.014</td><td></td></tr>
<tr><td style="text-align:left"></td><td>(0.039)</td><td></td></tr>
<tr><td style="text-align:left"></td><td></td><td></td></tr>
<tr><td style="text-align:left">Constant</td><td>28.971<sup>***</sup></td><td>29.111<sup>***</sup></td></tr>
<tr><td style="text-align:left"></td><td>(1.032)</td><td>(0.217)</td></tr>
<tr><td style="text-align:left"></td><td></td><td></td></tr>
<tr><td colspan="3" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left">Observations</td><td>110</td><td>1,825</td></tr>
<tr><td style="text-align:left">R<sup>2</sup></td><td>0.026</td><td>0.002</td></tr>
<tr><td style="text-align:left">Adjusted R<sup>2</sup></td><td>-0.002</td><td>0.001</td></tr>
<tr><td style="text-align:left">Residual Std. Error</td><td>6.708 (df = 106)</td><td>8.778 (df = 1822)</td></tr>
<tr><td style="text-align:left">F Statistic</td><td>0.928 (df = 3; 106)</td><td>2.219 (df = 2; 1822)</td></tr>
<tr><td colspan="3" style="border-bottom: 1px solid black"></td></tr><tr><td style="text-align:left"><em>Note:</em></td><td colspan="2" style="text-align:right"><sup>*</sup>p<0.1; <sup>**</sup>p<0.05; <sup>***</sup>p<0.01</td></tr>
</table>

</div>

</div>
</div>
</div>



## *Robust Standar Error*



Tabel hasil regresi dalam jurnal ilmiah biasanya melaporkan standar error yang telah dikoreksi dari masalah heterokesdastisitas dan atau korelasi serial. Standard error yang dikoreksi tersebut bisa dihitung dari obyek `lm` yang sudah ada, lalu digunakan untuk mengganti standard error bawaan OLS. Namun cara yang lebih mudah adalah dengan sejak awal estimasi menggunakan fungsi `lm_robust` dari library `estimatr` yang langsung memberikan standard error yang telah dikoreksi.

Default lm_robust menggunakan metode koreksi `HC2` dari McKinnon-White (1985). Standard error yang dihasilkan opsi robust di software Stata bisa direplikasi dengan menggunakan argumen `se_type = "stata`.

`stargazer` belum bisa melaporkan hasil dari `lm_robust`, namun `texreg` sudah mendukung. Gunakan argumen `include.ci = FALSE` untuk menampilkan standard error, bukan confidence interval yang merupakan tampilan default untuk lm_robust.



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
library(estimatr)
robust_default = lm_robust(morbidity_rate ~ number_of_doctors + number_of_midwives, datakab)
robust_stata = lm_robust(morbidity_rate ~ number_of_doctors + number_of_midwives, datakab, 
                         se_type = 'stata')

list(reg_morbid_2, robust_default, robust_stata) %>% 
texreg::htmlreg(digits = 4, include.ci = FALSE) %>% 
IRdisplay::display_html()

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">

<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<table cellspacing="0" align="center" style="border: none;">
<caption align="bottom" style="margin-top:0.3em;">Statistical models</caption>
<tr>
<th style="text-align: left; border-top: 2px solid black; border-bottom: 1px solid black; padding-right: 12px;"><b></b></th>
<th style="text-align: left; border-top: 2px solid black; border-bottom: 1px solid black; padding-right: 12px;"><b>Model 1</b></th>
<th style="text-align: left; border-top: 2px solid black; border-bottom: 1px solid black; padding-right: 12px;"><b>Model 2</b></th>
<th style="text-align: left; border-top: 2px solid black; border-bottom: 1px solid black; padding-right: 12px;"><b>Model 3</b></th>
</tr>
<tr>
<td style="padding-right: 12px; border: none;">(Intercept)</td>
<td style="padding-right: 12px; border: none;">29.1109<sup style="vertical-align: 0px;">***</sup></td>
<td style="padding-right: 12px; border: none;">29.1109<sup style="vertical-align: 0px;">***</sup></td>
<td style="padding-right: 12px; border: none;">29.1109<sup style="vertical-align: 0px;">***</sup></td>
</tr>
<tr>
<td style="padding-right: 12px; border: none;"></td>
<td style="padding-right: 12px; border: none;">(0.2166)</td>
<td style="padding-right: 12px; border: none;">(0.2174)</td>
<td style="padding-right: 12px; border: none;">(0.2174)</td>
</tr>
<tr>
<td style="padding-right: 12px; border: none;">number_of_doctors</td>
<td style="padding-right: 12px; border: none;">-0.0013<sup style="vertical-align: 0px;">*</sup></td>
<td style="padding-right: 12px; border: none;">-0.0013<sup style="vertical-align: 0px;">**</sup></td>
<td style="padding-right: 12px; border: none;">-0.0013<sup style="vertical-align: 0px;">**</sup></td>
</tr>
<tr>
<td style="padding-right: 12px; border: none;"></td>
<td style="padding-right: 12px; border: none;">(0.0006)</td>
<td style="padding-right: 12px; border: none;">(0.0004)</td>
<td style="padding-right: 12px; border: none;">(0.0004)</td>
</tr>
<tr>
<td style="padding-right: 12px; border: none;">number_of_midwives</td>
<td style="padding-right: 12px; border: none;">0.0003</td>
<td style="padding-right: 12px; border: none;">0.0003<sup style="vertical-align: 0px;">*</sup></td>
<td style="padding-right: 12px; border: none;">0.0003<sup style="vertical-align: 0px;">*</sup></td>
</tr>
<tr>
<td style="padding-right: 12px; border: none;"></td>
<td style="padding-right: 12px; border: none;">(0.0002)</td>
<td style="padding-right: 12px; border: none;">(0.0001)</td>
<td style="padding-right: 12px; border: none;">(0.0001)</td>
</tr>
<tr>
<td style="border-top: 1px solid black;">R<sup style="vertical-align: 0px;">2</sup></td>
<td style="border-top: 1px solid black;">0.0024</td>
<td style="border-top: 1px solid black;">0.0024</td>
<td style="border-top: 1px solid black;">0.0024</td>
</tr>
<tr>
<td style="padding-right: 12px; border: none;">Adj. R<sup style="vertical-align: 0px;">2</sup></td>
<td style="padding-right: 12px; border: none;">0.0013</td>
<td style="padding-right: 12px; border: none;">0.0013</td>
<td style="padding-right: 12px; border: none;">0.0013</td>
</tr>
<tr>
<td style="padding-right: 12px; border: none;">Num. obs.</td>
<td style="padding-right: 12px; border: none;">1825</td>
<td style="padding-right: 12px; border: none;">1825</td>
<td style="padding-right: 12px; border: none;">1825</td>
</tr>
<tr>
<td style="border-bottom: 2px solid black;">RMSE</td>
<td style="border-bottom: 2px solid black;">8.7776</td>
<td style="border-bottom: 2px solid black;">8.7776</td>
<td style="border-bottom: 2px solid black;">8.7776</td>
</tr>
<tr>
<td style="padding-right: 12px; border: none;" colspan="5"><span style="font-size:0.8em"><sup style="vertical-align: 0px;">***</sup>p &lt; 0.001, <sup style="vertical-align: 0px;">**</sup>p &lt; 0.01, <sup style="vertical-align: 0px;">*</sup>p &lt; 0.05</span></td>
</tr>
</table>

</div>

</div>
</div>
</div>



Bisa dilihat koreksi heterokesdastisitas mengubah nilai standard error dibanding hasil OLS. Akan tetapi tidak nampak ada perbedaan antara metode koreksi bawaan default `lm_robust` dengan metode koreksi opsi robust Stata.

