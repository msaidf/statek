---
redirect_from:
  - "/menyiapkandata"
interact_link: content/MenyiapkanData.ipynb
kernel_name: ir
has_widgets: false
title: 'Mempersiapkan Data'
prev_page:
  url: /Pendahuluan
  title: 'Pendahuluan'
next_page:
  url: 
  title: ''
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---


# Menyiapkan Data



<h1>Contents<span class="tocSkip"></span></h1>
<div class="toc"><ul class="toc-item"><li><span><a href="#Di-Balik-Layar" data-toc-modified-id="Di-Balik-Layar-1">Di Balik Layar</a></span></li><li><span><a href="#Memperoleh-Data" data-toc-modified-id="Memperoleh-Data-2">Memperoleh Data</a></span></li><li><span><a href="#Memuat-data-dari-file-ke-R" data-toc-modified-id="Memuat-data-dari-file-ke-R-3">Memuat data dari file ke R</a></span></li><li><span><a href="#Mengecek-Data" data-toc-modified-id="Mengecek-Data-4">Mengecek Data</a></span></li><li><span><a href="#Memilih-variabel" data-toc-modified-id="Memilih-variabel-5">Memilih variabel</a></span></li><li><span><a href="#Merubah-Nama-Variabel" data-toc-modified-id="Merubah-Nama-Variabel-6">Merubah Nama Variabel</a></span></li><li><span><a href="#Menggabungkan-data" data-toc-modified-id="Menggabungkan-data-7">Menggabungkan data</a></span></li><li><span><a href="#Menyimpan-dan-Menghapus-Objek" data-toc-modified-id="Menyimpan-dan-Menghapus-Objek-8">Menyimpan dan Menghapus Objek</a></span></li><li><span><a href="#Merubah-Nilai" data-toc-modified-id="Merubah-Nilai-9">Merubah Nilai</a></span></li></ul></div>



## Di Balik Layar
- Proses paling makan waktu
- Sering tidak diajarkan
- Padahal "sampah masuk, sampah keluar"



## Memperoleh Data
- Dari sumber langsung: BI, BPS, World Bank, IMF
- Dari layanan penyedia data: ORBIS, Bloomberg, Quandl
- Dari library R: quandl, bls



## Memuat data dari file ke R



- Dengan library `rio`, kita bisa mengimpor ke R data dari berbagai macam format: `txt`, `csv`, `xls`, `xlsx`, `dbf`, `sav`, `dta`, `sas7.bdat`. 
- Data yang diimpor akan menjadi obyek R tipe `data.frame` 



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
# install.packages('rio')
datakab = rio::import('indo-dapoer_data.csv')

```
</div>

</div>



## Mengecek Data



- Tampilkan keseluruhan data dengan mengenter nama obyek data



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<caption>A data.frame: 12017 × 19</caption>
<thead>
	<tr><th scope=col>Region Name</th><th scope=col>Region Code</th><th scope=col>Series Name</th><th scope=col>Series Code</th><th scope=col>2000 [YR2000]</th><th scope=col>2001 [YR2001]</th><th scope=col>2002 [YR2002]</th><th scope=col>2003 [YR2003]</th><th scope=col>2004 [YR2004]</th><th scope=col>2005 [YR2005]</th><th scope=col>2006 [YR2006]</th><th scope=col>2007 [YR2007]</th><th scope=col>2008 [YR2008]</th><th scope=col>2009 [YR2009]</th><th scope=col>2010 [YR2010]</th><th scope=col>2011 [YR2011]</th><th scope=col>2012 [YR2012]</th><th scope=col>2013 [YR2013]</th><th scope=col>2014 [YR2014]</th></tr>
	<tr><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th></tr>
</thead>
<tbody>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>65.87778</td><td>66.86649</td><td>67.52173</td><td>68.36661</td><td>69.38033</td><td>..      </td><td>..      </td><td>70.95   </td><td>..              </td><td>72.07           </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>29.19532</td><td>..      </td><td>33.22042</td><td>35.90795</td><td>31.811  </td><td>29.2377 </td><td>30.0167 </td><td>33.93033</td><td>30.5736273527145</td><td>29.909548163414 </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>94.65   </td><td>..      </td><td>94.89   </td><td>94.34   </td><td>96.21   </td><td>96.55   </td><td>98.32   </td><td>86.16   </td><td>90.96           </td><td>95.395058       </td><td>97.03 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>74.33   </td><td>..      </td><td>69.13   </td><td>76.71   </td><td>80.7    </td><td>65.59   </td><td>75.62   </td><td>68.52   </td><td>78.25           </td><td>87.201385       </td><td>87.02 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>54.23   </td><td>..      </td><td>52.97   </td><td>61.7    </td><td>62.9    </td><td>65.55   </td><td>67.8    </td><td>65.99   </td><td>60.86           </td><td>63.46043        </td><td>72.64 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>1       </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..</td><td>..</td><td>..</td><td>13      </td><td>..      </td><td>18      </td><td>..      </td><td>..      </td><td>6       </td><td>..      </td><td>..      </td><td>26      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..</td><td>..</td><td>..</td><td>108     </td><td>..      </td><td>97      </td><td>..      </td><td>..      </td><td>96      </td><td>..      </td><td>..      </td><td>191     </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Puskesmas and its line services              </td><td>SH.PUSKESMAS.TOTL</td><td>..</td><td>..</td><td>..</td><td>35      </td><td>..      </td><td>33      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>37      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Polindes (Poliklinik Desa/Village Polyclinic)</td><td>SH.POLINDES.TOTL </td><td>..</td><td>..</td><td>..</td><td>116     </td><td>..      </td><td>107     </td><td>..      </td><td>..      </td><td>75      </td><td>..      </td><td>..      </td><td>19      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at junior secondary level            </td><td>SE.SCHL.JRSEC    </td><td>..</td><td>..</td><td>..</td><td>16      </td><td>..      </td><td>22      </td><td>..      </td><td>..      </td><td>12      </td><td>..      </td><td>..      </td><td>29      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at primary level                     </td><td>SE.SCHL.PRM      </td><td>..</td><td>..</td><td>..</td><td>117     </td><td>..      </td><td>120     </td><td>..      </td><td>..      </td><td>66      </td><td>..      </td><td>..      </td><td>125     </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at Senior Secondary level            </td><td>SE.SCHL.SRSEC    </td><td>..</td><td>..</td><td>..</td><td>10      </td><td>..      </td><td>11      </td><td>..      </td><td>..      </td><td>10      </td><td>..      </td><td>..      </td><td>21      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Line (in IDR)                                  </td><td>SI.POV.NAPL      </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>146135  </td><td>176979  </td><td>198562  </td><td>231460  </td><td>231758  </td><td>252217  </td><td>274089  </td><td>276324          </td><td>283117          </td><td>288713</td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>..</td><td>..</td><td>..</td><td>27.72   </td><td>27.98   </td><td>27.71   </td><td>28.3    </td><td>28.63   </td><td>23.42   </td><td>21.33   </td><td>19.93   </td><td>19.49   </td><td>18.51           </td><td>18.92           </td><td>17.99 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>..</td><td>..</td><td>..</td><td>5.2     </td><td>4.86    </td><td>6.83    </td><td>5.42    </td><td>4.87    </td><td>3.72    </td><td>3.06    </td><td>3.31    </td><td>2.63    </td><td>2.34            </td><td>2.64            </td><td>2.58  </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>..</td><td>..</td><td>..</td><td>115358  </td><td>111366  </td><td>112230  </td><td>119397  </td><td>121302  </td><td>123101  </td><td>124813  </td><td>126036  </td><td>129708  </td><td>132612          </td><td>135385          </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>..</td><td>..</td><td>..</td><td>83.72   </td><td>..      </td><td>80.62   </td><td>..      </td><td>..      </td><td>67.42   </td><td>..      </td><td>..      </td><td>73.28767</td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..</td><td>..</td><td>..</td><td>2.33    </td><td>..      </td><td>4.65    </td><td>..      </td><td>..      </td><td>3.79    </td><td>..      </td><td>..      </td><td>2.739726</td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..</td><td>..</td><td>..</td><td>13.18   </td><td>..      </td><td>14.73   </td><td>..      </td><td>..      </td><td>28.79   </td><td>..      </td><td>..      </td><td>23.9726 </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>66.67713</td><td>67.4358 </td><td>68.08009</td><td>69.28123</td><td>69.66319</td><td>..      </td><td>..      </td><td>71.2    </td><td>..              </td><td>72.24           </td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>..</td><td>..</td><td>..</td><td>20.64202</td><td>32.03152</td><td>..      </td><td>28.0538 </td><td>42.79228</td><td>31.97134</td><td>27.13197</td><td>29.98806</td><td>35.01794</td><td>23.5453695058823</td><td>24.8722642660141</td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>..</td><td>..</td><td>..</td><td>93.51   </td><td>91.74   </td><td>..      </td><td>93.6    </td><td>96.34   </td><td>94.97   </td><td>93.78   </td><td>95.9    </td><td>93.32   </td><td>94.69           </td><td>99.302559       </td><td>99.75 </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>..</td><td>..</td><td>..</td><td>76.44   </td><td>71.35   </td><td>..      </td><td>73.19   </td><td>73      </td><td>61.91   </td><td>79.4    </td><td>74.69   </td><td>73.52   </td><td>79.22           </td><td>77.846069       </td><td>82.33 </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>..</td><td>..</td><td>..</td><td>55.92   </td><td>53.14   </td><td>..      </td><td>56.41   </td><td>60.92   </td><td>65.52   </td><td>65.66   </td><td>69.77   </td><td>70.41   </td><td>67.87           </td><td>71.44487        </td><td>73.09 </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>2 </td><td>..</td><td>..</td><td>1       </td><td>..      </td><td>1       </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>1       </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..</td><td>..</td><td>..</td><td>22      </td><td>..      </td><td>13      </td><td>..      </td><td>..      </td><td>26      </td><td>..      </td><td>..      </td><td>47      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..</td><td>..</td><td>..</td><td>182     </td><td>..      </td><td>127     </td><td>..      </td><td>..      </td><td>168     </td><td>..      </td><td>..      </td><td>237     </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td></tr>
	<tr><td>Yalimo, Kab.                                                                         </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>55.55556</td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.                                                                         </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>29.62963</td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.                                                                         </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>77.42435</td><td>77.69897        </td><td>77.80558</td><td>78.14222</td><td>78.94582</td><td>..      </td><td>..      </td><td>79.89   </td><td>..             </td><td>80.51           </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>40.45922</td><td>35.12418</td><td>36.52309</td><td>38.80893</td><td>45.61763</td><td>38.41948        </td><td>47.55421</td><td>36.85756</td><td>44.32943</td><td>41.70478</td><td>39.83229</td><td>41.60153</td><td>41.320464015007</td><td>39.2568409442902</td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>91.62   </td><td>93.75   </td><td>91.2    </td><td>90      </td><td>92.05   </td><td>92.11           </td><td>91.97   </td><td>92.64   </td><td>91.97   </td><td>90.64   </td><td>96.2    </td><td>92.18   </td><td>92.64          </td><td>98.837814       </td><td>95.37 </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>71.28   </td><td>81.82   </td><td>76.19   </td><td>73.33   </td><td>77      </td><td>81.82           </td><td>72.37   </td><td>76.56   </td><td>76.56   </td><td>78.87   </td><td>73.63   </td><td>63.02   </td><td>75.77          </td><td>87.365013       </td><td>88    </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>62.59   </td><td>57.04   </td><td>70      </td><td>58.32   </td><td>62.79   </td><td>61.7            </td><td>66.3    </td><td>74.12   </td><td>72.04   </td><td>57.14   </td><td>72.45   </td><td>54.35   </td><td>69.73          </td><td>59.754978       </td><td>63.32 </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>11      </td><td>..      </td><td>..      </td><td>11      </td><td>..      </td><td>11              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>14      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..      </td><td>..      </td><td>..      </td><td>286     </td><td>..      </td><td>297             </td><td>..      </td><td>..      </td><td>291     </td><td>..      </td><td>..      </td><td>243     </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..      </td><td>..      </td><td>..      </td><td>66      </td><td>..      </td><td>47              </td><td>..      </td><td>..      </td><td>58      </td><td>..      </td><td>..      </td><td>47      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Puskesmas and its line services              </td><td>SH.PUSKESMAS.TOTL</td><td>32      </td><td>..      </td><td>..      </td><td>30      </td><td>..      </td><td>29              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>29      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Polindes (Poliklinik Desa/Village Polyclinic)</td><td>SH.POLINDES.TOTL </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at junior secondary level            </td><td>SE.SCHL.JRSEC    </td><td>76      </td><td>..      </td><td>..      </td><td>70      </td><td>..      </td><td>66              </td><td>..      </td><td>..      </td><td>63      </td><td>..      </td><td>..      </td><td>63      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at primary level                     </td><td>SE.SCHL.PRM      </td><td>283     </td><td>..      </td><td>..      </td><td>249     </td><td>..      </td><td>245             </td><td>..      </td><td>..      </td><td>205     </td><td>..      </td><td>..      </td><td>176     </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at Senior Secondary level            </td><td>SE.SCHL.SRSEC    </td><td>91      </td><td>..      </td><td>..      </td><td>64      </td><td>..      </td><td>79              </td><td>..      </td><td>..      </td><td>81      </td><td>..      </td><td>..      </td><td>83      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Line (in IDR)                                  </td><td>SI.POV.NAPL      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>214694          </td><td>235801  </td><td>249318  </td><td>263996  </td><td>265168  </td><td>290286  </td><td>314311  </td><td>333232         </td><td>353602          </td><td>366520</td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>..      </td><td>..      </td><td>14.52   </td><td>12.59   </td><td>21.77   </td><td>10.5            </td><td>10.22   </td><td>9.78    </td><td>10.81   </td><td>10.05   </td><td>9.75    </td><td>9.62    </td><td>9.38           </td><td>8.82            </td><td>8.67  </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>..      </td><td>..      </td><td>3.23    </td><td>3.23    </td><td>2.96    </td><td>2.34            </td><td>1.88    </td><td>2.26    </td><td>2.1     </td><td>1.91    </td><td>1.29    </td><td>1.19    </td><td>1.57           </td><td>1.24            </td><td>1.14  </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>397398  </td><td>395775  </td><td>394140  </td><td>392492  </td><td>396238  </td><td>419163.765233477</td><td>445258  </td><td>451118  </td><td>456915  </td><td>462663  </td><td>388627  </td><td>392506  </td><td>397594         </td><td>402679          </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>100     </td><td>..      </td><td>..      </td><td>100     </td><td>..      </td><td>100             </td><td>..      </td><td>..      </td><td>100     </td><td>..      </td><td>..      </td><td>100     </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>                                                                                     </td><td>                         </td><td>                                                       </td><td>                 </td><td>        </td><td>        </td><td>        </td><td>        </td><td>        </td><td>                </td><td>        </td><td>        </td><td>        </td><td>        </td><td>        </td><td>        </td><td>               </td><td>                </td><td>      </td></tr>
	<tr><td>                                                                                     </td><td>                         </td><td>                                                       </td><td>                 </td><td>        </td><td>        </td><td>        </td><td>        </td><td>        </td><td>                </td><td>        </td><td>        </td><td>        </td><td>        </td><td>        </td><td>        </td><td>               </td><td>                </td><td>      </td></tr>
	<tr><td>                                                                                     </td><td>                         </td><td>                                                       </td><td>                 </td><td>        </td><td>        </td><td>        </td><td>        </td><td>        </td><td>                </td><td>        </td><td>        </td><td>        </td><td>        </td><td>        </td><td>        </td><td>               </td><td>                </td><td>      </td></tr>
	<tr><td>Data from database: INDO-DAPOER (Indonesia Database for Policy and Economic Research)</td><td>                         </td><td>                                                       </td><td>                 </td><td>        </td><td>        </td><td>        </td><td>        </td><td>        </td><td>                </td><td>        </td><td>        </td><td>        </td><td>        </td><td>        </td><td>        </td><td>               </td><td>                </td><td>      </td></tr>
	<tr><td>Last Updated: 05/28/2015                                                             </td><td>                         </td><td>                                                       </td><td>                 </td><td>        </td><td>        </td><td>        </td><td>        </td><td>        </td><td>                </td><td>        </td><td>        </td><td>        </td><td>        </td><td>        </td><td>        </td><td>               </td><td>                </td><td>      </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



- Namun untuk data yang besar, ini tidak banyak membantu bahkan bisa makan waktu lama
- Karenanya cek dulu besarnya data dari dimensi matriksnya.



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
dim(datakab)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<ol class=list-inline>
	<li>12017</li>
	<li>19</li>
</ol>

</div>

</div>
</div>
</div>



- `head` dan `tail` menampilkan baris teratas dan terbawah data 
- bisa menyebutkan jumlah baris yang diinginkan.



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
head(datakab); tail(datakab, n = 8)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<caption>A data.frame: 6 × 19</caption>
<thead>
	<tr><th scope=col>Region Name</th><th scope=col>Region Code</th><th scope=col>Series Name</th><th scope=col>Series Code</th><th scope=col>2000 [YR2000]</th><th scope=col>2001 [YR2001]</th><th scope=col>2002 [YR2002]</th><th scope=col>2003 [YR2003]</th><th scope=col>2004 [YR2004]</th><th scope=col>2005 [YR2005]</th><th scope=col>2006 [YR2006]</th><th scope=col>2007 [YR2007]</th><th scope=col>2008 [YR2008]</th><th scope=col>2009 [YR2009]</th><th scope=col>2010 [YR2010]</th><th scope=col>2011 [YR2011]</th><th scope=col>2012 [YR2012]</th><th scope=col>2013 [YR2013]</th><th scope=col>2014 [YR2014]</th></tr>
	<tr><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th></tr>
</thead>
<tbody>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Human Development Index                      </td><td>IDX.HDI         </td><td>..</td><td>..</td><td>..</td><td>..</td><td>65.87778</td><td>66.86649</td><td>67.52173</td><td>68.36661</td><td>69.38033</td><td>..     </td><td>..     </td><td>70.95   </td><td>..              </td><td>72.07          </td><td>..   </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Morbidity Rate (in %)                        </td><td>SH.MORB.ZS      </td><td>..</td><td>..</td><td>..</td><td>..</td><td>29.19532</td><td>..      </td><td>33.22042</td><td>35.90795</td><td>31.811  </td><td>29.2377</td><td>30.0167</td><td>33.93033</td><td>30.5736273527145</td><td>29.909548163414</td><td>..   </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Primary (in %)         </td><td>SE.PRM.NENR.ZS  </td><td>..</td><td>..</td><td>..</td><td>..</td><td>94.65   </td><td>..      </td><td>94.89   </td><td>94.34   </td><td>96.21   </td><td>96.55  </td><td>98.32  </td><td>86.16   </td><td>90.96           </td><td>95.395058      </td><td>97.03</td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Junior Secondary (in %)</td><td>SE.JRSEC.NENR.ZS</td><td>..</td><td>..</td><td>..</td><td>..</td><td>74.33   </td><td>..      </td><td>69.13   </td><td>76.71   </td><td>80.7    </td><td>65.59  </td><td>75.62  </td><td>68.52   </td><td>78.25           </td><td>87.201385      </td><td>87.02</td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Senior Secondary (in %)</td><td>SE.SRSEC.NENR.ZS</td><td>..</td><td>..</td><td>..</td><td>..</td><td>54.23   </td><td>..      </td><td>52.97   </td><td>61.7    </td><td>62.9    </td><td>65.55  </td><td>67.8   </td><td>65.99   </td><td>60.86           </td><td>63.46043       </td><td>72.64</td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of hospitals                          </td><td>SH.HOSP.TOTL    </td><td>..</td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..     </td><td>..     </td><td>1       </td><td>..              </td><td>..             </td><td>..   </td></tr>
</tbody>
</table>

</div>

</div>
</div>
<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<caption>A data.frame: 8 × 19</caption>
<thead>
	<tr><th></th><th scope=col>Region Name</th><th scope=col>Region Code</th><th scope=col>Series Name</th><th scope=col>Series Code</th><th scope=col>2000 [YR2000]</th><th scope=col>2001 [YR2001]</th><th scope=col>2002 [YR2002]</th><th scope=col>2003 [YR2003]</th><th scope=col>2004 [YR2004]</th><th scope=col>2005 [YR2005]</th><th scope=col>2006 [YR2006]</th><th scope=col>2007 [YR2007]</th><th scope=col>2008 [YR2008]</th><th scope=col>2009 [YR2009]</th><th scope=col>2010 [YR2010]</th><th scope=col>2011 [YR2011]</th><th scope=col>2012 [YR2012]</th><th scope=col>2013 [YR2013]</th><th scope=col>2014 [YR2014]</th></tr>
	<tr><th></th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th></tr>
</thead>
<tbody>
	<tr><th scope=row>12010</th><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Dirt (in % of total villages)  </td><td>ROD.VILG.DIRT.ZS </td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td></tr>
	<tr><th scope=row>12011</th><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Gravel (in % of total villages)</td><td>ROD.VILG.GRAVL.ZS</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td></tr>
	<tr><th scope=row>12012</th><td>Yogyakarta, Kota                                                                     </td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Other (in % of total villages) </td><td>ROD.VILG.OTHR.ZS </td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td><td>..</td></tr>
	<tr><th scope=row>12013</th><td>                                                                                     </td><td>                         </td><td>                                                   </td><td>                 </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td></tr>
	<tr><th scope=row>12014</th><td>                                                                                     </td><td>                         </td><td>                                                   </td><td>                 </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td></tr>
	<tr><th scope=row>12015</th><td>                                                                                     </td><td>                         </td><td>                                                   </td><td>                 </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td></tr>
	<tr><th scope=row>12016</th><td>Data from database: INDO-DAPOER (Indonesia Database for Policy and Economic Research)</td><td>                         </td><td>                                                   </td><td>                 </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td></tr>
	<tr><th scope=row>12017</th><td>Last Updated: 05/28/2015                                                             </td><td>                         </td><td>                                                   </td><td>                 </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td><td>  </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



- Lima baris terakhir bukan bagian dari data. Kita bisa gunakan indeks **positif** untuk memilih baris yang **dipertahankan**.



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
tail(datakab[1:12012,]

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<caption>A data.frame: 6 × 19</caption>
<thead>
	<tr><th></th><th scope=col>Region Name</th><th scope=col>Region Code</th><th scope=col>Series Name</th><th scope=col>Series Code</th><th scope=col>2000 [YR2000]</th><th scope=col>2001 [YR2001]</th><th scope=col>2002 [YR2002]</th><th scope=col>2003 [YR2003]</th><th scope=col>2004 [YR2004]</th><th scope=col>2005 [YR2005]</th><th scope=col>2006 [YR2006]</th><th scope=col>2007 [YR2007]</th><th scope=col>2008 [YR2008]</th><th scope=col>2009 [YR2009]</th><th scope=col>2010 [YR2010]</th><th scope=col>2011 [YR2011]</th><th scope=col>2012 [YR2012]</th><th scope=col>2013 [YR2013]</th><th scope=col>2014 [YR2014]</th></tr>
	<tr><th></th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th></tr>
</thead>
<tbody>
	<tr><th scope=row>12007</th><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Total GDP based on expenditure (in IDR Million)     </td><td>NE.GDI.TOTL.CR   </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..              </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..</td></tr>
	<tr><th scope=row>12008</th><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Total Population (in number of people)              </td><td>SP.POP.TOTL      </td><td>397398</td><td>395775</td><td>394140</td><td>392492</td><td>396238</td><td>419163.765233477</td><td>445258</td><td>451118</td><td>456915</td><td>462663</td><td>388627</td><td>392506</td><td>397594</td><td>402679</td><td>..</td></tr>
	<tr><th scope=row>12009</th><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Asphalt (in % of total villages)</td><td>ROD.VILG.ASPH.ZS </td><td>100   </td><td>..    </td><td>..    </td><td>100   </td><td>..    </td><td>100             </td><td>..    </td><td>..    </td><td>100   </td><td>..    </td><td>..    </td><td>100   </td><td>..    </td><td>..    </td><td>..</td></tr>
	<tr><th scope=row>12010</th><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Dirt (in % of total villages)   </td><td>ROD.VILG.DIRT.ZS </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..              </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..</td></tr>
	<tr><th scope=row>12011</th><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Gravel (in % of total villages) </td><td>ROD.VILG.GRAVL.ZS</td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..              </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..</td></tr>
	<tr><th scope=row>12012</th><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Other (in % of total villages)  </td><td>ROD.VILG.OTHR.ZS </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..              </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..</td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



- atau gunakan indeks **negatif** untuk memilih baris yang **dibuang**



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
library(magrittr)
datakab[-12013:-12017,] %>% tail

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<caption>A data.frame: 6 × 19</caption>
<thead>
	<tr><th></th><th scope=col>Region Name</th><th scope=col>Region Code</th><th scope=col>Series Name</th><th scope=col>Series Code</th><th scope=col>2000 [YR2000]</th><th scope=col>2001 [YR2001]</th><th scope=col>2002 [YR2002]</th><th scope=col>2003 [YR2003]</th><th scope=col>2004 [YR2004]</th><th scope=col>2005 [YR2005]</th><th scope=col>2006 [YR2006]</th><th scope=col>2007 [YR2007]</th><th scope=col>2008 [YR2008]</th><th scope=col>2009 [YR2009]</th><th scope=col>2010 [YR2010]</th><th scope=col>2011 [YR2011]</th><th scope=col>2012 [YR2012]</th><th scope=col>2013 [YR2013]</th><th scope=col>2014 [YR2014]</th></tr>
	<tr><th></th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th></tr>
</thead>
<tbody>
	<tr><th scope=row>12007</th><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Total GDP based on expenditure (in IDR Million)     </td><td>NE.GDI.TOTL.CR   </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..              </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..</td></tr>
	<tr><th scope=row>12008</th><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Total Population (in number of people)              </td><td>SP.POP.TOTL      </td><td>397398</td><td>395775</td><td>394140</td><td>392492</td><td>396238</td><td>419163.765233477</td><td>445258</td><td>451118</td><td>456915</td><td>462663</td><td>388627</td><td>392506</td><td>397594</td><td>402679</td><td>..</td></tr>
	<tr><th scope=row>12009</th><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Asphalt (in % of total villages)</td><td>ROD.VILG.ASPH.ZS </td><td>100   </td><td>..    </td><td>..    </td><td>100   </td><td>..    </td><td>100             </td><td>..    </td><td>..    </td><td>100   </td><td>..    </td><td>..    </td><td>100   </td><td>..    </td><td>..    </td><td>..</td></tr>
	<tr><th scope=row>12010</th><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Dirt (in % of total villages)   </td><td>ROD.VILG.DIRT.ZS </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..              </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..</td></tr>
	<tr><th scope=row>12011</th><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Gravel (in % of total villages) </td><td>ROD.VILG.GRAVL.ZS</td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..              </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..</td></tr>
	<tr><th scope=row>12012</th><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Other (in % of total villages)  </td><td>ROD.VILG.OTHR.ZS </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..              </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..</td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



- `%>%` adalah operator pipe dari library `magrittr`, yang mengirimkan output dari fungsi di sebelah kiri untuk menjadi input/argumen dari fungsi sebelah kanan



- Subset juga bisa dibuat dengan memfilter tabel data agar hanya memberikan baris yang nilai variabelnya memenuhi kriteria yang ditetapkan 
- Kita bisa gunakan fungsi `which` untuk menghasilkan indeks baris yang memenuhi kriteria tersebut



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
which(datakab$`Series Code` != "") %>% datakab[.,] %>% tail

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<caption>A data.frame: 6 × 19</caption>
<thead>
	<tr><th></th><th scope=col>Region Name</th><th scope=col>Region Code</th><th scope=col>Series Name</th><th scope=col>Series Code</th><th scope=col>2000 [YR2000]</th><th scope=col>2001 [YR2001]</th><th scope=col>2002 [YR2002]</th><th scope=col>2003 [YR2003]</th><th scope=col>2004 [YR2004]</th><th scope=col>2005 [YR2005]</th><th scope=col>2006 [YR2006]</th><th scope=col>2007 [YR2007]</th><th scope=col>2008 [YR2008]</th><th scope=col>2009 [YR2009]</th><th scope=col>2010 [YR2010]</th><th scope=col>2011 [YR2011]</th><th scope=col>2012 [YR2012]</th><th scope=col>2013 [YR2013]</th><th scope=col>2014 [YR2014]</th></tr>
	<tr><th></th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th></tr>
</thead>
<tbody>
	<tr><th scope=row>12007</th><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Total GDP based on expenditure (in IDR Million)     </td><td>NE.GDI.TOTL.CR   </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..              </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..</td></tr>
	<tr><th scope=row>12008</th><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Total Population (in number of people)              </td><td>SP.POP.TOTL      </td><td>397398</td><td>395775</td><td>394140</td><td>392492</td><td>396238</td><td>419163.765233477</td><td>445258</td><td>451118</td><td>456915</td><td>462663</td><td>388627</td><td>392506</td><td>397594</td><td>402679</td><td>..</td></tr>
	<tr><th scope=row>12009</th><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Asphalt (in % of total villages)</td><td>ROD.VILG.ASPH.ZS </td><td>100   </td><td>..    </td><td>..    </td><td>100   </td><td>..    </td><td>100             </td><td>..    </td><td>..    </td><td>100   </td><td>..    </td><td>..    </td><td>100   </td><td>..    </td><td>..    </td><td>..</td></tr>
	<tr><th scope=row>12010</th><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Dirt (in % of total villages)   </td><td>ROD.VILG.DIRT.ZS </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..              </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..</td></tr>
	<tr><th scope=row>12011</th><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Gravel (in % of total villages) </td><td>ROD.VILG.GRAVL.ZS</td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..              </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..</td></tr>
	<tr><th scope=row>12012</th><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Other (in % of total villages)  </td><td>ROD.VILG.OTHR.ZS </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..              </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..    </td><td>..</td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



- `$` digunakan untuk memilih kolom/variabel `Series Code` yang merupakan komponen dari tabel `datakab`
- nama variabel perlu diapit dengan *backtick* ``` hanya jika mengandung spasi  



- cara lain untuk memilih baris berdasar kriteria adalah menggunakan fungsi `filter` dari library `dplyr`



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
filter(datakab, `Series Code` != "") 

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<caption>A data.frame: 12012 × 19</caption>
<thead>
	<tr><th scope=col>REGION NAME</th><th scope=col>REGION CODE</th><th scope=col>SERIES NAME</th><th scope=col>Series Code</th><th scope=col>2000 [YR2000]</th><th scope=col>2001 [YR2001]</th><th scope=col>2002 [YR2002]</th><th scope=col>2003 [YR2003]</th><th scope=col>2004 [YR2004]</th><th scope=col>2005 [YR2005]</th><th scope=col>2006 [YR2006]</th><th scope=col>2007 [YR2007]</th><th scope=col>2008 [YR2008]</th><th scope=col>2009 [YR2009]</th><th scope=col>2010 [YR2010]</th><th scope=col>2011 [YR2011]</th><th scope=col>2012 [YR2012]</th><th scope=col>2013 [YR2013]</th><th scope=col>2014 [YR2014]</th></tr>
	<tr><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th></tr>
</thead>
<tbody>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>65.87778</td><td>66.86649</td><td>67.52173</td><td>68.36661</td><td>69.38033</td><td>..      </td><td>..      </td><td>70.95   </td><td>..              </td><td>72.07           </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>29.19532</td><td>..      </td><td>33.22042</td><td>35.90795</td><td>31.811  </td><td>29.2377 </td><td>30.0167 </td><td>33.93033</td><td>30.5736273527145</td><td>29.909548163414 </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>94.65   </td><td>..      </td><td>94.89   </td><td>94.34   </td><td>96.21   </td><td>96.55   </td><td>98.32   </td><td>86.16   </td><td>90.96           </td><td>95.395058       </td><td>97.03 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>74.33   </td><td>..      </td><td>69.13   </td><td>76.71   </td><td>80.7    </td><td>65.59   </td><td>75.62   </td><td>68.52   </td><td>78.25           </td><td>87.201385       </td><td>87.02 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>54.23   </td><td>..      </td><td>52.97   </td><td>61.7    </td><td>62.9    </td><td>65.55   </td><td>67.8    </td><td>65.99   </td><td>60.86           </td><td>63.46043        </td><td>72.64 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>1       </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..</td><td>..</td><td>..</td><td>13      </td><td>..      </td><td>18      </td><td>..      </td><td>..      </td><td>6       </td><td>..      </td><td>..      </td><td>26      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..</td><td>..</td><td>..</td><td>108     </td><td>..      </td><td>97      </td><td>..      </td><td>..      </td><td>96      </td><td>..      </td><td>..      </td><td>191     </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Puskesmas and its line services              </td><td>SH.PUSKESMAS.TOTL</td><td>..</td><td>..</td><td>..</td><td>35      </td><td>..      </td><td>33      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>37      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Polindes (Poliklinik Desa/Village Polyclinic)</td><td>SH.POLINDES.TOTL </td><td>..</td><td>..</td><td>..</td><td>116     </td><td>..      </td><td>107     </td><td>..      </td><td>..      </td><td>75      </td><td>..      </td><td>..      </td><td>19      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at junior secondary level            </td><td>SE.SCHL.JRSEC    </td><td>..</td><td>..</td><td>..</td><td>16      </td><td>..      </td><td>22      </td><td>..      </td><td>..      </td><td>12      </td><td>..      </td><td>..      </td><td>29      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at primary level                     </td><td>SE.SCHL.PRM      </td><td>..</td><td>..</td><td>..</td><td>117     </td><td>..      </td><td>120     </td><td>..      </td><td>..      </td><td>66      </td><td>..      </td><td>..      </td><td>125     </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at Senior Secondary level            </td><td>SE.SCHL.SRSEC    </td><td>..</td><td>..</td><td>..</td><td>10      </td><td>..      </td><td>11      </td><td>..      </td><td>..      </td><td>10      </td><td>..      </td><td>..      </td><td>21      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Line (in IDR)                                  </td><td>SI.POV.NAPL      </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>146135  </td><td>176979  </td><td>198562  </td><td>231460  </td><td>231758  </td><td>252217  </td><td>274089  </td><td>276324          </td><td>283117          </td><td>288713</td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>..</td><td>..</td><td>..</td><td>27.72   </td><td>27.98   </td><td>27.71   </td><td>28.3    </td><td>28.63   </td><td>23.42   </td><td>21.33   </td><td>19.93   </td><td>19.49   </td><td>18.51           </td><td>18.92           </td><td>17.99 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>..</td><td>..</td><td>..</td><td>5.2     </td><td>4.86    </td><td>6.83    </td><td>5.42    </td><td>4.87    </td><td>3.72    </td><td>3.06    </td><td>3.31    </td><td>2.63    </td><td>2.34            </td><td>2.64            </td><td>2.58  </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>..</td><td>..</td><td>..</td><td>115358  </td><td>111366  </td><td>112230  </td><td>119397  </td><td>121302  </td><td>123101  </td><td>124813  </td><td>126036  </td><td>129708  </td><td>132612          </td><td>135385          </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>..</td><td>..</td><td>..</td><td>83.72   </td><td>..      </td><td>80.62   </td><td>..      </td><td>..      </td><td>67.42   </td><td>..      </td><td>..      </td><td>73.28767</td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..</td><td>..</td><td>..</td><td>2.33    </td><td>..      </td><td>4.65    </td><td>..      </td><td>..      </td><td>3.79    </td><td>..      </td><td>..      </td><td>2.739726</td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..</td><td>..</td><td>..</td><td>13.18   </td><td>..      </td><td>14.73   </td><td>..      </td><td>..      </td><td>28.79   </td><td>..      </td><td>..      </td><td>23.9726 </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>66.67713</td><td>67.4358 </td><td>68.08009</td><td>69.28123</td><td>69.66319</td><td>..      </td><td>..      </td><td>71.2    </td><td>..              </td><td>72.24           </td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>..</td><td>..</td><td>..</td><td>20.64202</td><td>32.03152</td><td>..      </td><td>28.0538 </td><td>42.79228</td><td>31.97134</td><td>27.13197</td><td>29.98806</td><td>35.01794</td><td>23.5453695058823</td><td>24.8722642660141</td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>..</td><td>..</td><td>..</td><td>93.51   </td><td>91.74   </td><td>..      </td><td>93.6    </td><td>96.34   </td><td>94.97   </td><td>93.78   </td><td>95.9    </td><td>93.32   </td><td>94.69           </td><td>99.302559       </td><td>99.75 </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>..</td><td>..</td><td>..</td><td>76.44   </td><td>71.35   </td><td>..      </td><td>73.19   </td><td>73      </td><td>61.91   </td><td>79.4    </td><td>74.69   </td><td>73.52   </td><td>79.22           </td><td>77.846069       </td><td>82.33 </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>..</td><td>..</td><td>..</td><td>55.92   </td><td>53.14   </td><td>..      </td><td>56.41   </td><td>60.92   </td><td>65.52   </td><td>65.66   </td><td>69.77   </td><td>70.41   </td><td>67.87           </td><td>71.44487        </td><td>73.09 </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>2 </td><td>..</td><td>..</td><td>1       </td><td>..      </td><td>1       </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>1       </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..</td><td>..</td><td>..</td><td>22      </td><td>..      </td><td>13      </td><td>..      </td><td>..      </td><td>26      </td><td>..      </td><td>..      </td><td>47      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..</td><td>..</td><td>..</td><td>182     </td><td>..      </td><td>127     </td><td>..      </td><td>..      </td><td>168     </td><td>..      </td><td>..      </td><td>237     </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>47.76   </td><td>44.13   </td><td>40.65   </td><td>39.48          </td><td>40.33           </td><td>35.65 </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>5.98    </td><td>9.32    </td><td>7.16    </td><td>7.8            </td><td>7.46            </td><td>6.32  </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>18806   </td><td>50763   </td><td>52623   </td><td>53785          </td><td>54911           </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>14.81481</td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>55.55556</td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>29.62963</td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>77.42435</td><td>77.69897        </td><td>77.80558</td><td>78.14222</td><td>78.94582</td><td>..      </td><td>..      </td><td>79.89   </td><td>..             </td><td>80.51           </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>40.45922</td><td>35.12418</td><td>36.52309</td><td>38.80893</td><td>45.61763</td><td>38.41948        </td><td>47.55421</td><td>36.85756</td><td>44.32943</td><td>41.70478</td><td>39.83229</td><td>41.60153</td><td>41.320464015007</td><td>39.2568409442902</td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>91.62   </td><td>93.75   </td><td>91.2    </td><td>90      </td><td>92.05   </td><td>92.11           </td><td>91.97   </td><td>92.64   </td><td>91.97   </td><td>90.64   </td><td>96.2    </td><td>92.18   </td><td>92.64          </td><td>98.837814       </td><td>95.37 </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>71.28   </td><td>81.82   </td><td>76.19   </td><td>73.33   </td><td>77      </td><td>81.82           </td><td>72.37   </td><td>76.56   </td><td>76.56   </td><td>78.87   </td><td>73.63   </td><td>63.02   </td><td>75.77          </td><td>87.365013       </td><td>88    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>62.59   </td><td>57.04   </td><td>70      </td><td>58.32   </td><td>62.79   </td><td>61.7            </td><td>66.3    </td><td>74.12   </td><td>72.04   </td><td>57.14   </td><td>72.45   </td><td>54.35   </td><td>69.73          </td><td>59.754978       </td><td>63.32 </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>11      </td><td>..      </td><td>..      </td><td>11      </td><td>..      </td><td>11              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>14      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..      </td><td>..      </td><td>..      </td><td>286     </td><td>..      </td><td>297             </td><td>..      </td><td>..      </td><td>291     </td><td>..      </td><td>..      </td><td>243     </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..      </td><td>..      </td><td>..      </td><td>66      </td><td>..      </td><td>47              </td><td>..      </td><td>..      </td><td>58      </td><td>..      </td><td>..      </td><td>47      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Puskesmas and its line services              </td><td>SH.PUSKESMAS.TOTL</td><td>32      </td><td>..      </td><td>..      </td><td>30      </td><td>..      </td><td>29              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>29      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Polindes (Poliklinik Desa/Village Polyclinic)</td><td>SH.POLINDES.TOTL </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at junior secondary level            </td><td>SE.SCHL.JRSEC    </td><td>76      </td><td>..      </td><td>..      </td><td>70      </td><td>..      </td><td>66              </td><td>..      </td><td>..      </td><td>63      </td><td>..      </td><td>..      </td><td>63      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at primary level                     </td><td>SE.SCHL.PRM      </td><td>283     </td><td>..      </td><td>..      </td><td>249     </td><td>..      </td><td>245             </td><td>..      </td><td>..      </td><td>205     </td><td>..      </td><td>..      </td><td>176     </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at Senior Secondary level            </td><td>SE.SCHL.SRSEC    </td><td>91      </td><td>..      </td><td>..      </td><td>64      </td><td>..      </td><td>79              </td><td>..      </td><td>..      </td><td>81      </td><td>..      </td><td>..      </td><td>83      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Line (in IDR)                                  </td><td>SI.POV.NAPL      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>214694          </td><td>235801  </td><td>249318  </td><td>263996  </td><td>265168  </td><td>290286  </td><td>314311  </td><td>333232         </td><td>353602          </td><td>366520</td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>..      </td><td>..      </td><td>14.52   </td><td>12.59   </td><td>21.77   </td><td>10.5            </td><td>10.22   </td><td>9.78    </td><td>10.81   </td><td>10.05   </td><td>9.75    </td><td>9.62    </td><td>9.38           </td><td>8.82            </td><td>8.67  </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>..      </td><td>..      </td><td>3.23    </td><td>3.23    </td><td>2.96    </td><td>2.34            </td><td>1.88    </td><td>2.26    </td><td>2.1     </td><td>1.91    </td><td>1.29    </td><td>1.19    </td><td>1.57           </td><td>1.24            </td><td>1.14  </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>397398  </td><td>395775  </td><td>394140  </td><td>392492  </td><td>396238  </td><td>419163.765233477</td><td>445258  </td><td>451118  </td><td>456915  </td><td>462663  </td><td>388627  </td><td>392506  </td><td>397594         </td><td>402679          </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>100     </td><td>..      </td><td>..      </td><td>100     </td><td>..      </td><td>100             </td><td>..      </td><td>..      </td><td>100     </td><td>..      </td><td>..      </td><td>100     </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



- Uups, hasilnya tidak seperti yang diinginkan
- Ternyata kita belum memuat library `dplyr` sehingga fungsi `filter` yang digunakan di atas berasal dari library lain
- Jika ada lebih dari satu fungsi yang bernama sama, R akan memprioritaskan fungsi dari library yang dimuat paling akhir.



- Kita bisa memastikan fungsi `filter` yang digunakan adalah dari `dplyr`, walau kita belum memuatnya, dengan didului `dplyr::`



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
dplyr::filter(datakab, `Series Code` != "") 

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<caption>A data.frame: 12012 × 19</caption>
<thead>
	<tr><th scope=col>Region Name</th><th scope=col>Region Code</th><th scope=col>Series Name</th><th scope=col>Series Code</th><th scope=col>2000 [YR2000]</th><th scope=col>2001 [YR2001]</th><th scope=col>2002 [YR2002]</th><th scope=col>2003 [YR2003]</th><th scope=col>2004 [YR2004]</th><th scope=col>2005 [YR2005]</th><th scope=col>2006 [YR2006]</th><th scope=col>2007 [YR2007]</th><th scope=col>2008 [YR2008]</th><th scope=col>2009 [YR2009]</th><th scope=col>2010 [YR2010]</th><th scope=col>2011 [YR2011]</th><th scope=col>2012 [YR2012]</th><th scope=col>2013 [YR2013]</th><th scope=col>2014 [YR2014]</th></tr>
	<tr><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th></tr>
</thead>
<tbody>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>65.87778</td><td>66.86649</td><td>67.52173</td><td>68.36661</td><td>69.38033</td><td>..      </td><td>..      </td><td>70.95   </td><td>..              </td><td>72.07           </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>29.19532</td><td>..      </td><td>33.22042</td><td>35.90795</td><td>31.811  </td><td>29.2377 </td><td>30.0167 </td><td>33.93033</td><td>30.5736273527145</td><td>29.909548163414 </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>94.65   </td><td>..      </td><td>94.89   </td><td>94.34   </td><td>96.21   </td><td>96.55   </td><td>98.32   </td><td>86.16   </td><td>90.96           </td><td>95.395058       </td><td>97.03 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>74.33   </td><td>..      </td><td>69.13   </td><td>76.71   </td><td>80.7    </td><td>65.59   </td><td>75.62   </td><td>68.52   </td><td>78.25           </td><td>87.201385       </td><td>87.02 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>54.23   </td><td>..      </td><td>52.97   </td><td>61.7    </td><td>62.9    </td><td>65.55   </td><td>67.8    </td><td>65.99   </td><td>60.86           </td><td>63.46043        </td><td>72.64 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>1       </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..</td><td>..</td><td>..</td><td>13      </td><td>..      </td><td>18      </td><td>..      </td><td>..      </td><td>6       </td><td>..      </td><td>..      </td><td>26      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..</td><td>..</td><td>..</td><td>108     </td><td>..      </td><td>97      </td><td>..      </td><td>..      </td><td>96      </td><td>..      </td><td>..      </td><td>191     </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Puskesmas and its line services              </td><td>SH.PUSKESMAS.TOTL</td><td>..</td><td>..</td><td>..</td><td>35      </td><td>..      </td><td>33      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>37      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Polindes (Poliklinik Desa/Village Polyclinic)</td><td>SH.POLINDES.TOTL </td><td>..</td><td>..</td><td>..</td><td>116     </td><td>..      </td><td>107     </td><td>..      </td><td>..      </td><td>75      </td><td>..      </td><td>..      </td><td>19      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at junior secondary level            </td><td>SE.SCHL.JRSEC    </td><td>..</td><td>..</td><td>..</td><td>16      </td><td>..      </td><td>22      </td><td>..      </td><td>..      </td><td>12      </td><td>..      </td><td>..      </td><td>29      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at primary level                     </td><td>SE.SCHL.PRM      </td><td>..</td><td>..</td><td>..</td><td>117     </td><td>..      </td><td>120     </td><td>..      </td><td>..      </td><td>66      </td><td>..      </td><td>..      </td><td>125     </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at Senior Secondary level            </td><td>SE.SCHL.SRSEC    </td><td>..</td><td>..</td><td>..</td><td>10      </td><td>..      </td><td>11      </td><td>..      </td><td>..      </td><td>10      </td><td>..      </td><td>..      </td><td>21      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Line (in IDR)                                  </td><td>SI.POV.NAPL      </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>146135  </td><td>176979  </td><td>198562  </td><td>231460  </td><td>231758  </td><td>252217  </td><td>274089  </td><td>276324          </td><td>283117          </td><td>288713</td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>..</td><td>..</td><td>..</td><td>27.72   </td><td>27.98   </td><td>27.71   </td><td>28.3    </td><td>28.63   </td><td>23.42   </td><td>21.33   </td><td>19.93   </td><td>19.49   </td><td>18.51           </td><td>18.92           </td><td>17.99 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>..</td><td>..</td><td>..</td><td>5.2     </td><td>4.86    </td><td>6.83    </td><td>5.42    </td><td>4.87    </td><td>3.72    </td><td>3.06    </td><td>3.31    </td><td>2.63    </td><td>2.34            </td><td>2.64            </td><td>2.58  </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>..</td><td>..</td><td>..</td><td>115358  </td><td>111366  </td><td>112230  </td><td>119397  </td><td>121302  </td><td>123101  </td><td>124813  </td><td>126036  </td><td>129708  </td><td>132612          </td><td>135385          </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>..</td><td>..</td><td>..</td><td>83.72   </td><td>..      </td><td>80.62   </td><td>..      </td><td>..      </td><td>67.42   </td><td>..      </td><td>..      </td><td>73.28767</td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..</td><td>..</td><td>..</td><td>2.33    </td><td>..      </td><td>4.65    </td><td>..      </td><td>..      </td><td>3.79    </td><td>..      </td><td>..      </td><td>2.739726</td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..</td><td>..</td><td>..</td><td>13.18   </td><td>..      </td><td>14.73   </td><td>..      </td><td>..      </td><td>28.79   </td><td>..      </td><td>..      </td><td>23.9726 </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>66.67713</td><td>67.4358 </td><td>68.08009</td><td>69.28123</td><td>69.66319</td><td>..      </td><td>..      </td><td>71.2    </td><td>..              </td><td>72.24           </td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>..</td><td>..</td><td>..</td><td>20.64202</td><td>32.03152</td><td>..      </td><td>28.0538 </td><td>42.79228</td><td>31.97134</td><td>27.13197</td><td>29.98806</td><td>35.01794</td><td>23.5453695058823</td><td>24.8722642660141</td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>..</td><td>..</td><td>..</td><td>93.51   </td><td>91.74   </td><td>..      </td><td>93.6    </td><td>96.34   </td><td>94.97   </td><td>93.78   </td><td>95.9    </td><td>93.32   </td><td>94.69           </td><td>99.302559       </td><td>99.75 </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>..</td><td>..</td><td>..</td><td>76.44   </td><td>71.35   </td><td>..      </td><td>73.19   </td><td>73      </td><td>61.91   </td><td>79.4    </td><td>74.69   </td><td>73.52   </td><td>79.22           </td><td>77.846069       </td><td>82.33 </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>..</td><td>..</td><td>..</td><td>55.92   </td><td>53.14   </td><td>..      </td><td>56.41   </td><td>60.92   </td><td>65.52   </td><td>65.66   </td><td>69.77   </td><td>70.41   </td><td>67.87           </td><td>71.44487        </td><td>73.09 </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>2 </td><td>..</td><td>..</td><td>1       </td><td>..      </td><td>1       </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>1       </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..</td><td>..</td><td>..</td><td>22      </td><td>..      </td><td>13      </td><td>..      </td><td>..      </td><td>26      </td><td>..      </td><td>..      </td><td>47      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..</td><td>..</td><td>..</td><td>182     </td><td>..      </td><td>127     </td><td>..      </td><td>..      </td><td>168     </td><td>..      </td><td>..      </td><td>237     </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>47.76   </td><td>44.13   </td><td>40.65   </td><td>39.48          </td><td>40.33           </td><td>35.65 </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>5.98    </td><td>9.32    </td><td>7.16    </td><td>7.8            </td><td>7.46            </td><td>6.32  </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>18806   </td><td>50763   </td><td>52623   </td><td>53785          </td><td>54911           </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>14.81481</td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>55.55556</td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>29.62963</td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>77.42435</td><td>77.69897        </td><td>77.80558</td><td>78.14222</td><td>78.94582</td><td>..      </td><td>..      </td><td>79.89   </td><td>..             </td><td>80.51           </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>40.45922</td><td>35.12418</td><td>36.52309</td><td>38.80893</td><td>45.61763</td><td>38.41948        </td><td>47.55421</td><td>36.85756</td><td>44.32943</td><td>41.70478</td><td>39.83229</td><td>41.60153</td><td>41.320464015007</td><td>39.2568409442902</td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>91.62   </td><td>93.75   </td><td>91.2    </td><td>90      </td><td>92.05   </td><td>92.11           </td><td>91.97   </td><td>92.64   </td><td>91.97   </td><td>90.64   </td><td>96.2    </td><td>92.18   </td><td>92.64          </td><td>98.837814       </td><td>95.37 </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>71.28   </td><td>81.82   </td><td>76.19   </td><td>73.33   </td><td>77      </td><td>81.82           </td><td>72.37   </td><td>76.56   </td><td>76.56   </td><td>78.87   </td><td>73.63   </td><td>63.02   </td><td>75.77          </td><td>87.365013       </td><td>88    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>62.59   </td><td>57.04   </td><td>70      </td><td>58.32   </td><td>62.79   </td><td>61.7            </td><td>66.3    </td><td>74.12   </td><td>72.04   </td><td>57.14   </td><td>72.45   </td><td>54.35   </td><td>69.73          </td><td>59.754978       </td><td>63.32 </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>11      </td><td>..      </td><td>..      </td><td>11      </td><td>..      </td><td>11              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>14      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..      </td><td>..      </td><td>..      </td><td>286     </td><td>..      </td><td>297             </td><td>..      </td><td>..      </td><td>291     </td><td>..      </td><td>..      </td><td>243     </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..      </td><td>..      </td><td>..      </td><td>66      </td><td>..      </td><td>47              </td><td>..      </td><td>..      </td><td>58      </td><td>..      </td><td>..      </td><td>47      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Puskesmas and its line services              </td><td>SH.PUSKESMAS.TOTL</td><td>32      </td><td>..      </td><td>..      </td><td>30      </td><td>..      </td><td>29              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>29      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Polindes (Poliklinik Desa/Village Polyclinic)</td><td>SH.POLINDES.TOTL </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at junior secondary level            </td><td>SE.SCHL.JRSEC    </td><td>76      </td><td>..      </td><td>..      </td><td>70      </td><td>..      </td><td>66              </td><td>..      </td><td>..      </td><td>63      </td><td>..      </td><td>..      </td><td>63      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at primary level                     </td><td>SE.SCHL.PRM      </td><td>283     </td><td>..      </td><td>..      </td><td>249     </td><td>..      </td><td>245             </td><td>..      </td><td>..      </td><td>205     </td><td>..      </td><td>..      </td><td>176     </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at Senior Secondary level            </td><td>SE.SCHL.SRSEC    </td><td>91      </td><td>..      </td><td>..      </td><td>64      </td><td>..      </td><td>79              </td><td>..      </td><td>..      </td><td>81      </td><td>..      </td><td>..      </td><td>83      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Line (in IDR)                                  </td><td>SI.POV.NAPL      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>214694          </td><td>235801  </td><td>249318  </td><td>263996  </td><td>265168  </td><td>290286  </td><td>314311  </td><td>333232         </td><td>353602          </td><td>366520</td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>..      </td><td>..      </td><td>14.52   </td><td>12.59   </td><td>21.77   </td><td>10.5            </td><td>10.22   </td><td>9.78    </td><td>10.81   </td><td>10.05   </td><td>9.75    </td><td>9.62    </td><td>9.38           </td><td>8.82            </td><td>8.67  </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>..      </td><td>..      </td><td>3.23    </td><td>3.23    </td><td>2.96    </td><td>2.34            </td><td>1.88    </td><td>2.26    </td><td>2.1     </td><td>1.91    </td><td>1.29    </td><td>1.19    </td><td>1.57           </td><td>1.24            </td><td>1.14  </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>397398  </td><td>395775  </td><td>394140  </td><td>392492  </td><td>396238  </td><td>419163.765233477</td><td>445258  </td><td>451118  </td><td>456915  </td><td>462663  </td><td>388627  </td><td>392506  </td><td>397594         </td><td>402679          </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>100     </td><td>..      </td><td>..      </td><td>100     </td><td>..      </td><td>100             </td><td>..      </td><td>..      </td><td>100     </td><td>..      </td><td>..      </td><td>100     </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



- jika sudah yakin indeks menghasilkan subset yang diinginkan, simpan subset tersebut menjadi objek 



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab = .Last.value

```
</div>

</div>



- nilai dari perintah yang dijalankan terakhir  bisa dimuat kembali dengan `.Last.value`



## Memilih variabel




- seperti memilih baris, kita bisa memilih variabel menggunakan indeks kolom yang terletak setelah koma di fungsi subset `[]`



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab[,c(1, 3:5, ncol(datakab))]

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<caption>A data.frame: 12012 × 5</caption>
<thead>
	<tr><th scope=col>Region Name</th><th scope=col>Series Name</th><th scope=col>Series Code</th><th scope=col>2000 [YR2000]</th><th scope=col>2014 [YR2014]</th></tr>
	<tr><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th></tr>
</thead>
<tbody>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..</td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>..</td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>..</td><td>97.03 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>..</td><td>87.02 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>..</td><td>72.64 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>..</td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..</td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..</td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Number of Puskesmas and its line services              </td><td>SH.PUSKESMAS.TOTL</td><td>..</td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Number of Polindes (Poliklinik Desa/Village Polyclinic)</td><td>SH.POLINDES.TOTL </td><td>..</td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Number of schools at junior secondary level            </td><td>SE.SCHL.JRSEC    </td><td>..</td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Number of schools at primary level                     </td><td>SE.SCHL.PRM      </td><td>..</td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Number of schools at Senior Secondary level            </td><td>SE.SCHL.SRSEC    </td><td>..</td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Poverty Line (in IDR)                                  </td><td>SI.POV.NAPL      </td><td>..</td><td>288713</td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>..</td><td>17.99 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>..</td><td>2.58  </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..</td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>..</td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>..</td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..</td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..</td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..</td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..</td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>..</td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>..</td><td>99.75 </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>..</td><td>82.33 </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>..</td><td>73.09 </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>2 </td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..</td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..</td><td>..    </td></tr>
	<tr><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td></tr>
	<tr><td>Yalimo, Kab.    </td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>..      </td><td>35.65 </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>..      </td><td>6.32  </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..      </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>..      </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>..      </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..      </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..      </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..      </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..      </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>40.45922</td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>91.62   </td><td>95.37 </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>71.28   </td><td>88    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>62.59   </td><td>63.32 </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>11      </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..      </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..      </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Number of Puskesmas and its line services              </td><td>SH.PUSKESMAS.TOTL</td><td>32      </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Number of Polindes (Poliklinik Desa/Village Polyclinic)</td><td>SH.POLINDES.TOTL </td><td>..      </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Number of schools at junior secondary level            </td><td>SE.SCHL.JRSEC    </td><td>76      </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Number of schools at primary level                     </td><td>SE.SCHL.PRM      </td><td>283     </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Number of schools at Senior Secondary level            </td><td>SE.SCHL.SRSEC    </td><td>91      </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Poverty Line (in IDR)                                  </td><td>SI.POV.NAPL      </td><td>..      </td><td>366520</td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>..      </td><td>8.67  </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>..      </td><td>1.14  </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..      </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>397398  </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>100     </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..      </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..      </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..      </td><td>..    </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



- indeks kolom angka bisa digantikan dengan vektor nama variabel 



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab[,c('Region Code', 'Series Name')]

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<caption>A data.frame: 12012 × 2</caption>
<thead>
	<tr><th scope=col>Region Code</th><th scope=col>Series Name</th></tr>
	<tr><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th></tr>
</thead>
<tbody>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Human Development Index                                </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Morbidity Rate (in %)                                  </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Primary (in %)                   </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of hospitals                                    </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Doctors                                      </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Midwives                                     </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Puskesmas and its line services              </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Polindes (Poliklinik Desa/Village Polyclinic)</td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at junior secondary level            </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at primary level                     </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at Senior Secondary level            </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Line (in IDR)                                  </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Rate (in % of population)                      </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Gap (index)                                    </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Total GDP based on expenditure (in IDR Million)        </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Total Population (in number of people)                 </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Asphalt (in % of total villages)   </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Dirt (in % of total villages)      </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Gravel (in % of total villages)    </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Other (in % of total villages)     </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>Human Development Index                                </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>Morbidity Rate (in %)                                  </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Primary (in %)                   </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of hospitals                                    </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of Doctors                                      </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of Midwives                                     </td></tr>
	<tr><td>⋮</td><td>⋮</td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>Poverty Rate (in % of population)                      </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>Poverty Gap (index)                                    </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>Total GDP based on expenditure (in IDR Million)        </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>Total Population (in number of people)                 </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>Villages with road: Asphalt (in % of total villages)   </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>Villages with road: Dirt (in % of total villages)      </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>Villages with road: Gravel (in % of total villages)    </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>Villages with road: Other (in % of total villages)     </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Human Development Index                                </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Morbidity Rate (in %)                                  </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Primary (in %)                   </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Number of hospitals                                    </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Doctors                                      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Midwives                                     </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Puskesmas and its line services              </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Polindes (Poliklinik Desa/Village Polyclinic)</td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at junior secondary level            </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at primary level                     </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at Senior Secondary level            </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Line (in IDR)                                  </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Rate (in % of population)                      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Gap (index)                                    </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Total GDP based on expenditure (in IDR Million)        </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Total Population (in number of people)                 </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Asphalt (in % of total villages)   </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Dirt (in % of total villages)      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Gravel (in % of total villages)    </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Other (in % of total villages)     </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



- Pemilihan variabel juga bisa menggunakan `dplyr::select`



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
library(dplyr); select(datakab, 'Region Code':'Series Code', -'Series Name', 
                       region_name = 'Region Name', contains('YR'), -contains('YR201'))

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<caption>A data.frame: 12012 × 13</caption>
<thead>
	<tr><th scope=col>Region Code</th><th scope=col>Series Code</th><th scope=col>region_name</th><th scope=col>2000 [YR2000]</th><th scope=col>2001 [YR2001]</th><th scope=col>2002 [YR2002]</th><th scope=col>2003 [YR2003]</th><th scope=col>2004 [YR2004]</th><th scope=col>2005 [YR2005]</th><th scope=col>2006 [YR2006]</th><th scope=col>2007 [YR2007]</th><th scope=col>2008 [YR2008]</th><th scope=col>2009 [YR2009]</th></tr>
	<tr><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th></tr>
</thead>
<tbody>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>IDX.HDI          </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>..      </td><td>65.87778</td><td>66.86649</td><td>67.52173</td><td>68.36661</td><td>69.38033</td><td>..      </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SH.MORB.ZS       </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>..      </td><td>29.19532</td><td>..      </td><td>33.22042</td><td>35.90795</td><td>31.811  </td><td>29.2377 </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SE.PRM.NENR.ZS   </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>..      </td><td>94.65   </td><td>..      </td><td>94.89   </td><td>94.34   </td><td>96.21   </td><td>96.55   </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SE.JRSEC.NENR.ZS </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>..      </td><td>74.33   </td><td>..      </td><td>69.13   </td><td>76.71   </td><td>80.7    </td><td>65.59   </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SE.SRSEC.NENR.ZS </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>..      </td><td>54.23   </td><td>..      </td><td>52.97   </td><td>61.7    </td><td>62.9    </td><td>65.55   </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SH.HOSP.TOTL     </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SH.DR.TOTL       </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>13      </td><td>..      </td><td>18      </td><td>..      </td><td>..      </td><td>6       </td><td>..      </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SH.MED.MWIV.TOTL </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>108     </td><td>..      </td><td>97      </td><td>..      </td><td>..      </td><td>96      </td><td>..      </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SH.PUSKESMAS.TOTL</td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>35      </td><td>..      </td><td>33      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SH.POLINDES.TOTL </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>116     </td><td>..      </td><td>107     </td><td>..      </td><td>..      </td><td>75      </td><td>..      </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SE.SCHL.JRSEC    </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>16      </td><td>..      </td><td>22      </td><td>..      </td><td>..      </td><td>12      </td><td>..      </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SE.SCHL.PRM      </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>117     </td><td>..      </td><td>120     </td><td>..      </td><td>..      </td><td>66      </td><td>..      </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SE.SCHL.SRSEC    </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>10      </td><td>..      </td><td>11      </td><td>..      </td><td>..      </td><td>10      </td><td>..      </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SI.POV.NAPL      </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>146135  </td><td>176979  </td><td>198562  </td><td>231460  </td><td>231758  </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SI.POV.NAPR.ZS   </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>27.72   </td><td>27.98   </td><td>27.71   </td><td>28.3    </td><td>28.63   </td><td>23.42   </td><td>21.33   </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SI.POV.NGAP      </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>5.2     </td><td>4.86    </td><td>6.83    </td><td>5.42    </td><td>4.87    </td><td>3.72    </td><td>3.06    </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>NE.GDI.TOTL.CR   </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SP.POP.TOTL      </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>115358  </td><td>111366  </td><td>112230  </td><td>119397  </td><td>121302  </td><td>123101  </td><td>124813  </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>ROD.VILG.ASPH.ZS </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>83.72   </td><td>..      </td><td>80.62   </td><td>..      </td><td>..      </td><td>67.42   </td><td>..      </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>ROD.VILG.DIRT.ZS </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>2.33    </td><td>..      </td><td>4.65    </td><td>..      </td><td>..      </td><td>3.79    </td><td>..      </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>ROD.VILG.GRAVL.ZS</td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>13.18   </td><td>..      </td><td>14.73   </td><td>..      </td><td>..      </td><td>28.79   </td><td>..      </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>ROD.VILG.OTHR.ZS </td><td>Aceh Barat Daya, Kab.</td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>IDX.HDI          </td><td>Aceh Barat, Kab.     </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>66.67713</td><td>67.4358 </td><td>68.08009</td><td>69.28123</td><td>69.66319</td><td>..      </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>SH.MORB.ZS       </td><td>Aceh Barat, Kab.     </td><td>..</td><td>..</td><td>..</td><td>20.64202</td><td>32.03152</td><td>..      </td><td>28.0538 </td><td>42.79228</td><td>31.97134</td><td>27.13197</td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>SE.PRM.NENR.ZS   </td><td>Aceh Barat, Kab.     </td><td>..</td><td>..</td><td>..</td><td>93.51   </td><td>91.74   </td><td>..      </td><td>93.6    </td><td>96.34   </td><td>94.97   </td><td>93.78   </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>SE.JRSEC.NENR.ZS </td><td>Aceh Barat, Kab.     </td><td>..</td><td>..</td><td>..</td><td>76.44   </td><td>71.35   </td><td>..      </td><td>73.19   </td><td>73      </td><td>61.91   </td><td>79.4    </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>SE.SRSEC.NENR.ZS </td><td>Aceh Barat, Kab.     </td><td>..</td><td>..</td><td>..</td><td>55.92   </td><td>53.14   </td><td>..      </td><td>56.41   </td><td>60.92   </td><td>65.52   </td><td>65.66   </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>SH.HOSP.TOTL     </td><td>Aceh Barat, Kab.     </td><td>2 </td><td>..</td><td>..</td><td>1       </td><td>..      </td><td>1       </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>SH.DR.TOTL       </td><td>Aceh Barat, Kab.     </td><td>..</td><td>..</td><td>..</td><td>22      </td><td>..      </td><td>13      </td><td>..      </td><td>..      </td><td>26      </td><td>..      </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>SH.MED.MWIV.TOTL </td><td>Aceh Barat, Kab.     </td><td>..</td><td>..</td><td>..</td><td>182     </td><td>..      </td><td>127     </td><td>..      </td><td>..      </td><td>168     </td><td>..      </td></tr>
	<tr><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>SI.POV.NAPR.ZS   </td><td>Yalimo, Kab.    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>47.76   </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>SI.POV.NGAP      </td><td>Yalimo, Kab.    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>5.98    </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>NE.GDI.TOTL.CR   </td><td>Yalimo, Kab.    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>SP.POP.TOTL      </td><td>Yalimo, Kab.    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>18806   </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>ROD.VILG.ASPH.ZS </td><td>Yalimo, Kab.    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>ROD.VILG.DIRT.ZS </td><td>Yalimo, Kab.    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>ROD.VILG.GRAVL.ZS</td><td>Yalimo, Kab.    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>ROD.VILG.OTHR.ZS </td><td>Yalimo, Kab.    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>IDX.HDI          </td><td>Yogyakarta, Kota</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>77.42435</td><td>77.69897        </td><td>77.80558</td><td>78.14222</td><td>78.94582</td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SH.MORB.ZS       </td><td>Yogyakarta, Kota</td><td>40.45922</td><td>35.12418</td><td>36.52309</td><td>38.80893</td><td>45.61763</td><td>38.41948        </td><td>47.55421</td><td>36.85756</td><td>44.32943</td><td>41.70478</td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SE.PRM.NENR.ZS   </td><td>Yogyakarta, Kota</td><td>91.62   </td><td>93.75   </td><td>91.2    </td><td>90      </td><td>92.05   </td><td>92.11           </td><td>91.97   </td><td>92.64   </td><td>91.97   </td><td>90.64   </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SE.JRSEC.NENR.ZS </td><td>Yogyakarta, Kota</td><td>71.28   </td><td>81.82   </td><td>76.19   </td><td>73.33   </td><td>77      </td><td>81.82           </td><td>72.37   </td><td>76.56   </td><td>76.56   </td><td>78.87   </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SE.SRSEC.NENR.ZS </td><td>Yogyakarta, Kota</td><td>62.59   </td><td>57.04   </td><td>70      </td><td>58.32   </td><td>62.79   </td><td>61.7            </td><td>66.3    </td><td>74.12   </td><td>72.04   </td><td>57.14   </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SH.HOSP.TOTL     </td><td>Yogyakarta, Kota</td><td>11      </td><td>..      </td><td>..      </td><td>11      </td><td>..      </td><td>11              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SH.DR.TOTL       </td><td>Yogyakarta, Kota</td><td>..      </td><td>..      </td><td>..      </td><td>286     </td><td>..      </td><td>297             </td><td>..      </td><td>..      </td><td>291     </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SH.MED.MWIV.TOTL </td><td>Yogyakarta, Kota</td><td>..      </td><td>..      </td><td>..      </td><td>66      </td><td>..      </td><td>47              </td><td>..      </td><td>..      </td><td>58      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SH.PUSKESMAS.TOTL</td><td>Yogyakarta, Kota</td><td>32      </td><td>..      </td><td>..      </td><td>30      </td><td>..      </td><td>29              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SH.POLINDES.TOTL </td><td>Yogyakarta, Kota</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SE.SCHL.JRSEC    </td><td>Yogyakarta, Kota</td><td>76      </td><td>..      </td><td>..      </td><td>70      </td><td>..      </td><td>66              </td><td>..      </td><td>..      </td><td>63      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SE.SCHL.PRM      </td><td>Yogyakarta, Kota</td><td>283     </td><td>..      </td><td>..      </td><td>249     </td><td>..      </td><td>245             </td><td>..      </td><td>..      </td><td>205     </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SE.SCHL.SRSEC    </td><td>Yogyakarta, Kota</td><td>91      </td><td>..      </td><td>..      </td><td>64      </td><td>..      </td><td>79              </td><td>..      </td><td>..      </td><td>81      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SI.POV.NAPL      </td><td>Yogyakarta, Kota</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>214694          </td><td>235801  </td><td>249318  </td><td>263996  </td><td>265168  </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SI.POV.NAPR.ZS   </td><td>Yogyakarta, Kota</td><td>..      </td><td>..      </td><td>14.52   </td><td>12.59   </td><td>21.77   </td><td>10.5            </td><td>10.22   </td><td>9.78    </td><td>10.81   </td><td>10.05   </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SI.POV.NGAP      </td><td>Yogyakarta, Kota</td><td>..      </td><td>..      </td><td>3.23    </td><td>3.23    </td><td>2.96    </td><td>2.34            </td><td>1.88    </td><td>2.26    </td><td>2.1     </td><td>1.91    </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>NE.GDI.TOTL.CR   </td><td>Yogyakarta, Kota</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SP.POP.TOTL      </td><td>Yogyakarta, Kota</td><td>397398  </td><td>395775  </td><td>394140  </td><td>392492  </td><td>396238  </td><td>419163.765233477</td><td>445258  </td><td>451118  </td><td>456915  </td><td>462663  </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>ROD.VILG.ASPH.ZS </td><td>Yogyakarta, Kota</td><td>100     </td><td>..      </td><td>..      </td><td>100     </td><td>..      </td><td>100             </td><td>..      </td><td>..      </td><td>100     </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>ROD.VILG.DIRT.ZS </td><td>Yogyakarta, Kota</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>ROD.VILG.GRAVL.ZS</td><td>Yogyakarta, Kota</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>ROD.VILG.OTHR.ZS </td><td>Yogyakarta, Kota</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



- Nama variabel yang mengandung spasi harus diapit tanda kutip 
- Pilih sejumlah variabel yang berurutan cukup sebutkan variabel di pinggir, `var_kiri:var_kanan` 
- Pilih semua variabel yang namanya memiliki kesamaan pola, baik diawali (`starts_with`), diakhiri (`ends_with`), atau mengandung (`contains`) karakter tertentu 
- Gunakan tanda minus (`-`) untuk mengecualikan variabel 
- Urutan kolom tabel baru mengikuti urutan variabel dalam `select`
- Mengganti nama variabel yang dipilih, `nama_baru = nama_lama`



## Merubah Nama Variabel



- jika hanya ingin mengganti nama sejumlah variabel, tanpa merubah struktur tabel data, gunakan `dplyr::rename`



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
rename(datakab, region_name = 'Region Name', series_code = 'Series Code') [100:103,]

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<caption>A data.frame: 4 × 19</caption>
<thead>
	<tr><th></th><th scope=col>region_name</th><th scope=col>Region Code</th><th scope=col>Series Name</th><th scope=col>series_code</th><th scope=col>2000 [YR2000]</th><th scope=col>2001 [YR2001]</th><th scope=col>2002 [YR2002]</th><th scope=col>2003 [YR2003]</th><th scope=col>2004 [YR2004]</th><th scope=col>2005 [YR2005]</th><th scope=col>2006 [YR2006]</th><th scope=col>2007 [YR2007]</th><th scope=col>2008 [YR2008]</th><th scope=col>2009 [YR2009]</th><th scope=col>2010 [YR2010]</th><th scope=col>2011 [YR2011]</th><th scope=col>2012 [YR2012]</th><th scope=col>2013 [YR2013]</th><th scope=col>2014 [YR2014]</th></tr>
	<tr><th></th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th></tr>
</thead>
<tbody>
	<tr><th scope=row>100</th><td>Aceh Selatan, Kab.</td><td>IDN_Aceh_Selatan_Kab_73626</td><td>Number of schools at primary level         </td><td>SE.SCHL.PRM   </td><td>333</td><td>..</td><td>..   </td><td>211  </td><td>..   </td><td>223   </td><td>..    </td><td>..    </td><td>128   </td><td>..    </td><td>..    </td><td>232   </td><td>..    </td><td>..    </td><td>..    </td></tr>
	<tr><th scope=row>101</th><td>Aceh Selatan, Kab.</td><td>IDN_Aceh_Selatan_Kab_73626</td><td>Number of schools at Senior Secondary level</td><td>SE.SCHL.SRSEC </td><td>25 </td><td>..</td><td>..   </td><td>21   </td><td>..   </td><td>25    </td><td>..    </td><td>..    </td><td>15    </td><td>..    </td><td>..    </td><td>40    </td><td>..    </td><td>..    </td><td>..    </td></tr>
	<tr><th scope=row>102</th><td>Aceh Selatan, Kab.</td><td>IDN_Aceh_Selatan_Kab_73626</td><td>Poverty Line (in IDR)                      </td><td>SI.POV.NAPL   </td><td>.. </td><td>..</td><td>..   </td><td>..   </td><td>..   </td><td>171815</td><td>186227</td><td>196167</td><td>203761</td><td>236741</td><td>257640</td><td>278854</td><td>281158</td><td>283446</td><td>285301</td></tr>
	<tr><th scope=row>103</th><td>Aceh Selatan, Kab.</td><td>IDN_Aceh_Selatan_Kab_73626</td><td>Poverty Rate (in % of population)          </td><td>SI.POV.NAPR.ZS</td><td>.. </td><td>..</td><td>28.28</td><td>29.25</td><td>27.56</td><td>26.43 </td><td>24.58 </td><td>24.72 </td><td>19.4  </td><td>17.5  </td><td>15.93 </td><td>15.52 </td><td>14.81 </td><td>13.44 </td><td>12.79 </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



- fungsi subset `[]` bisa langsung digunakan tanpa piping  `%>%` setelah fungsi yang menghasilkan objek yang bisa di-subset



- merubah nama bisa pula dilakukan dengan meng-*assign* vektor nama baru dengan panjang sama seperti nama yang hendak digantikan



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
names(datakab)[1:3] = names(datakab)[1:3] %>% toupper
names(datakab)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<ol class=list-inline>
	<li>'REGION NAME'</li>
	<li>'REGION CODE'</li>
	<li>'SERIES NAME'</li>
	<li>'Series Code'</li>
	<li>'2000 [YR2000]'</li>
	<li>'2001 [YR2001]'</li>
	<li>'2002 [YR2002]'</li>
	<li>'2003 [YR2003]'</li>
	<li>'2004 [YR2004]'</li>
	<li>'2005 [YR2005]'</li>
	<li>'2006 [YR2006]'</li>
	<li>'2007 [YR2007]'</li>
	<li>'2008 [YR2008]'</li>
	<li>'2009 [YR2009]'</li>
	<li>'2010 [YR2010]'</li>
	<li>'2011 [YR2011]'</li>
	<li>'2012 [YR2012]'</li>
	<li>'2013 [YR2013]'</li>
	<li>'2014 [YR2014]'</li>
</ol>

</div>

</div>
</div>
</div>



- `janitor::clean_names` merubah nama variabel agar mengikuti gaya standar 



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab = janitor::clean_names(datakab)
names(datakab)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<ol class=list-inline>
	<li>'region_name'</li>
	<li>'region_code'</li>
	<li>'series_name'</li>
	<li>'series_code'</li>
	<li>'x2000_yr2000'</li>
	<li>'x2001_yr2001'</li>
	<li>'x2002_yr2002'</li>
	<li>'x2003_yr2003'</li>
	<li>'x2004_yr2004'</li>
	<li>'x2005_yr2005'</li>
	<li>'x2006_yr2006'</li>
	<li>'x2007_yr2007'</li>
	<li>'x2008_yr2008'</li>
	<li>'x2009_yr2009'</li>
	<li>'x2010_yr2010'</li>
	<li>'x2011_yr2011'</li>
	<li>'x2012_yr2012'</li>
	<li>'x2013_yr2013'</li>
	<li>'x2014_yr2014'</li>
</ol>

</div>

</div>
</div>
</div>



## Menggabungkan data



- Untuk keperluan latihan penggabungan, datakab dipecah menjadi dua data dengan variabel berbeda kecuali variabel ID



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
(data1 = datakab %>% select(region_name:series_code, contains('201')))

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<caption>A data.frame: 12012 × 9</caption>
<thead>
	<tr><th scope=col>region_name</th><th scope=col>region_code</th><th scope=col>series_name</th><th scope=col>series_code</th><th scope=col>x2010_yr2010</th><th scope=col>x2011_yr2011</th><th scope=col>x2012_yr2012</th><th scope=col>x2013_yr2013</th><th scope=col>x2014_yr2014</th></tr>
	<tr><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th></tr>
</thead>
<tbody>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..      </td><td>70.95   </td><td>..              </td><td>72.07           </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>30.0167 </td><td>33.93033</td><td>30.5736273527145</td><td>29.909548163414 </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>98.32   </td><td>86.16   </td><td>90.96           </td><td>95.395058       </td><td>97.03 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>75.62   </td><td>68.52   </td><td>78.25           </td><td>87.201385       </td><td>87.02 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>67.8    </td><td>65.99   </td><td>60.86           </td><td>63.46043        </td><td>72.64 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>..      </td><td>1       </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..      </td><td>26      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..      </td><td>191     </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Puskesmas and its line services              </td><td>SH.PUSKESMAS.TOTL</td><td>..      </td><td>37      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Polindes (Poliklinik Desa/Village Polyclinic)</td><td>SH.POLINDES.TOTL </td><td>..      </td><td>19      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at junior secondary level            </td><td>SE.SCHL.JRSEC    </td><td>..      </td><td>29      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at primary level                     </td><td>SE.SCHL.PRM      </td><td>..      </td><td>125     </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at Senior Secondary level            </td><td>SE.SCHL.SRSEC    </td><td>..      </td><td>21      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Line (in IDR)                                  </td><td>SI.POV.NAPL      </td><td>252217  </td><td>274089  </td><td>276324          </td><td>283117          </td><td>288713</td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>19.93   </td><td>19.49   </td><td>18.51           </td><td>18.92           </td><td>17.99 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>3.31    </td><td>2.63    </td><td>2.34            </td><td>2.64            </td><td>2.58  </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..      </td><td>..      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>126036  </td><td>129708  </td><td>132612          </td><td>135385          </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>..      </td><td>73.28767</td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..      </td><td>2.739726</td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..      </td><td>23.9726 </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..      </td><td>..      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..      </td><td>71.2    </td><td>..              </td><td>72.24           </td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>29.98806</td><td>35.01794</td><td>23.5453695058823</td><td>24.8722642660141</td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>95.9    </td><td>93.32   </td><td>94.69           </td><td>99.302559       </td><td>99.75 </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>74.69   </td><td>73.52   </td><td>79.22           </td><td>77.846069       </td><td>82.33 </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>69.77   </td><td>70.41   </td><td>67.87           </td><td>71.44487        </td><td>73.09 </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>..      </td><td>1       </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..      </td><td>47      </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..      </td><td>237     </td><td>..              </td><td>..              </td><td>..    </td></tr>
	<tr><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>44.13   </td><td>40.65   </td><td>39.48          </td><td>40.33           </td><td>35.65 </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>9.32    </td><td>7.16    </td><td>7.8            </td><td>7.46            </td><td>6.32  </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>50763   </td><td>52623   </td><td>53785          </td><td>54911           </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>..      </td><td>14.81481</td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..      </td><td>55.55556</td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..      </td><td>29.62963</td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..      </td><td>79.89   </td><td>..             </td><td>80.51           </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>39.83229</td><td>41.60153</td><td>41.320464015007</td><td>39.2568409442902</td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>96.2    </td><td>92.18   </td><td>92.64          </td><td>98.837814       </td><td>95.37 </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>73.63   </td><td>63.02   </td><td>75.77          </td><td>87.365013       </td><td>88    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>72.45   </td><td>54.35   </td><td>69.73          </td><td>59.754978       </td><td>63.32 </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>..      </td><td>14      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..      </td><td>243     </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..      </td><td>47      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Puskesmas and its line services              </td><td>SH.PUSKESMAS.TOTL</td><td>..      </td><td>29      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Polindes (Poliklinik Desa/Village Polyclinic)</td><td>SH.POLINDES.TOTL </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at junior secondary level            </td><td>SE.SCHL.JRSEC    </td><td>..      </td><td>63      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at primary level                     </td><td>SE.SCHL.PRM      </td><td>..      </td><td>176     </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at Senior Secondary level            </td><td>SE.SCHL.SRSEC    </td><td>..      </td><td>83      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Line (in IDR)                                  </td><td>SI.POV.NAPL      </td><td>290286  </td><td>314311  </td><td>333232         </td><td>353602          </td><td>366520</td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>9.75    </td><td>9.62    </td><td>9.38           </td><td>8.82            </td><td>8.67  </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>1.29    </td><td>1.19    </td><td>1.57           </td><td>1.24            </td><td>1.14  </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>388627  </td><td>392506  </td><td>397594         </td><td>402679          </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>..      </td><td>100     </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
(data2 = datakab %>% select(-contains('201')))

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<caption>A data.frame: 12012 × 14</caption>
<thead>
	<tr><th scope=col>region_name</th><th scope=col>region_code</th><th scope=col>series_name</th><th scope=col>series_code</th><th scope=col>x2000_yr2000</th><th scope=col>x2001_yr2001</th><th scope=col>x2002_yr2002</th><th scope=col>x2003_yr2003</th><th scope=col>x2004_yr2004</th><th scope=col>x2005_yr2005</th><th scope=col>x2006_yr2006</th><th scope=col>x2007_yr2007</th><th scope=col>x2008_yr2008</th><th scope=col>x2009_yr2009</th></tr>
	<tr><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th></tr>
</thead>
<tbody>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>65.87778</td><td>66.86649</td><td>67.52173</td><td>68.36661</td><td>69.38033</td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>29.19532</td><td>..      </td><td>33.22042</td><td>35.90795</td><td>31.811  </td><td>29.2377 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>94.65   </td><td>..      </td><td>94.89   </td><td>94.34   </td><td>96.21   </td><td>96.55   </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>74.33   </td><td>..      </td><td>69.13   </td><td>76.71   </td><td>80.7    </td><td>65.59   </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>54.23   </td><td>..      </td><td>52.97   </td><td>61.7    </td><td>62.9    </td><td>65.55   </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..</td><td>..</td><td>..</td><td>13      </td><td>..      </td><td>18      </td><td>..      </td><td>..      </td><td>6       </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..</td><td>..</td><td>..</td><td>108     </td><td>..      </td><td>97      </td><td>..      </td><td>..      </td><td>96      </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Puskesmas and its line services              </td><td>SH.PUSKESMAS.TOTL</td><td>..</td><td>..</td><td>..</td><td>35      </td><td>..      </td><td>33      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Polindes (Poliklinik Desa/Village Polyclinic)</td><td>SH.POLINDES.TOTL </td><td>..</td><td>..</td><td>..</td><td>116     </td><td>..      </td><td>107     </td><td>..      </td><td>..      </td><td>75      </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at junior secondary level            </td><td>SE.SCHL.JRSEC    </td><td>..</td><td>..</td><td>..</td><td>16      </td><td>..      </td><td>22      </td><td>..      </td><td>..      </td><td>12      </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at primary level                     </td><td>SE.SCHL.PRM      </td><td>..</td><td>..</td><td>..</td><td>117     </td><td>..      </td><td>120     </td><td>..      </td><td>..      </td><td>66      </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at Senior Secondary level            </td><td>SE.SCHL.SRSEC    </td><td>..</td><td>..</td><td>..</td><td>10      </td><td>..      </td><td>11      </td><td>..      </td><td>..      </td><td>10      </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Line (in IDR)                                  </td><td>SI.POV.NAPL      </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>146135  </td><td>176979  </td><td>198562  </td><td>231460  </td><td>231758  </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>..</td><td>..</td><td>..</td><td>27.72   </td><td>27.98   </td><td>27.71   </td><td>28.3    </td><td>28.63   </td><td>23.42   </td><td>21.33   </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>..</td><td>..</td><td>..</td><td>5.2     </td><td>4.86    </td><td>6.83    </td><td>5.42    </td><td>4.87    </td><td>3.72    </td><td>3.06    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>..</td><td>..</td><td>..</td><td>115358  </td><td>111366  </td><td>112230  </td><td>119397  </td><td>121302  </td><td>123101  </td><td>124813  </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>..</td><td>..</td><td>..</td><td>83.72   </td><td>..      </td><td>80.62   </td><td>..      </td><td>..      </td><td>67.42   </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..</td><td>..</td><td>..</td><td>2.33    </td><td>..      </td><td>4.65    </td><td>..      </td><td>..      </td><td>3.79    </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..</td><td>..</td><td>..</td><td>13.18   </td><td>..      </td><td>14.73   </td><td>..      </td><td>..      </td><td>28.79   </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>66.67713</td><td>67.4358 </td><td>68.08009</td><td>69.28123</td><td>69.66319</td><td>..      </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>..</td><td>..</td><td>..</td><td>20.64202</td><td>32.03152</td><td>..      </td><td>28.0538 </td><td>42.79228</td><td>31.97134</td><td>27.13197</td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>..</td><td>..</td><td>..</td><td>93.51   </td><td>91.74   </td><td>..      </td><td>93.6    </td><td>96.34   </td><td>94.97   </td><td>93.78   </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>..</td><td>..</td><td>..</td><td>76.44   </td><td>71.35   </td><td>..      </td><td>73.19   </td><td>73      </td><td>61.91   </td><td>79.4    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>..</td><td>..</td><td>..</td><td>55.92   </td><td>53.14   </td><td>..      </td><td>56.41   </td><td>60.92   </td><td>65.52   </td><td>65.66   </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>2 </td><td>..</td><td>..</td><td>1       </td><td>..      </td><td>1       </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..</td><td>..</td><td>..</td><td>22      </td><td>..      </td><td>13      </td><td>..      </td><td>..      </td><td>26      </td><td>..      </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..</td><td>..</td><td>..</td><td>182     </td><td>..      </td><td>127     </td><td>..      </td><td>..      </td><td>168     </td><td>..      </td></tr>
	<tr><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>47.76   </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>5.98    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>18806   </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>77.42435</td><td>77.69897        </td><td>77.80558</td><td>78.14222</td><td>78.94582</td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>40.45922</td><td>35.12418</td><td>36.52309</td><td>38.80893</td><td>45.61763</td><td>38.41948        </td><td>47.55421</td><td>36.85756</td><td>44.32943</td><td>41.70478</td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>91.62   </td><td>93.75   </td><td>91.2    </td><td>90      </td><td>92.05   </td><td>92.11           </td><td>91.97   </td><td>92.64   </td><td>91.97   </td><td>90.64   </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>71.28   </td><td>81.82   </td><td>76.19   </td><td>73.33   </td><td>77      </td><td>81.82           </td><td>72.37   </td><td>76.56   </td><td>76.56   </td><td>78.87   </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>62.59   </td><td>57.04   </td><td>70      </td><td>58.32   </td><td>62.79   </td><td>61.7            </td><td>66.3    </td><td>74.12   </td><td>72.04   </td><td>57.14   </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>11      </td><td>..      </td><td>..      </td><td>11      </td><td>..      </td><td>11              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..      </td><td>..      </td><td>..      </td><td>286     </td><td>..      </td><td>297             </td><td>..      </td><td>..      </td><td>291     </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..      </td><td>..      </td><td>..      </td><td>66      </td><td>..      </td><td>47              </td><td>..      </td><td>..      </td><td>58      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Puskesmas and its line services              </td><td>SH.PUSKESMAS.TOTL</td><td>32      </td><td>..      </td><td>..      </td><td>30      </td><td>..      </td><td>29              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Polindes (Poliklinik Desa/Village Polyclinic)</td><td>SH.POLINDES.TOTL </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at junior secondary level            </td><td>SE.SCHL.JRSEC    </td><td>76      </td><td>..      </td><td>..      </td><td>70      </td><td>..      </td><td>66              </td><td>..      </td><td>..      </td><td>63      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at primary level                     </td><td>SE.SCHL.PRM      </td><td>283     </td><td>..      </td><td>..      </td><td>249     </td><td>..      </td><td>245             </td><td>..      </td><td>..      </td><td>205     </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at Senior Secondary level            </td><td>SE.SCHL.SRSEC    </td><td>91      </td><td>..      </td><td>..      </td><td>64      </td><td>..      </td><td>79              </td><td>..      </td><td>..      </td><td>81      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Line (in IDR)                                  </td><td>SI.POV.NAPL      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>214694          </td><td>235801  </td><td>249318  </td><td>263996  </td><td>265168  </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>..      </td><td>..      </td><td>14.52   </td><td>12.59   </td><td>21.77   </td><td>10.5            </td><td>10.22   </td><td>9.78    </td><td>10.81   </td><td>10.05   </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>..      </td><td>..      </td><td>3.23    </td><td>3.23    </td><td>2.96    </td><td>2.34            </td><td>1.88    </td><td>2.26    </td><td>2.1     </td><td>1.91    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>397398  </td><td>395775  </td><td>394140  </td><td>392492  </td><td>396238  </td><td>419163.765233477</td><td>445258  </td><td>451118  </td><td>456915  </td><td>462663  </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>100     </td><td>..      </td><td>..      </td><td>100     </td><td>..      </td><td>100             </td><td>..      </td><td>..      </td><td>100     </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



- gabungkan dua data tersebut menggunakan  `merge` dari base R, atau seri fungsi `_join` dari `dplyr`



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
merge(data1, data2, by = c('region_code', 'series_code'))

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<caption>A data.frame: 12012 × 21</caption>
<thead>
	<tr><th scope=col>region_code</th><th scope=col>series_code</th><th scope=col>region_name.x</th><th scope=col>series_name.x</th><th scope=col>x2010_yr2010</th><th scope=col>x2011_yr2011</th><th scope=col>x2012_yr2012</th><th scope=col>x2013_yr2013</th><th scope=col>x2014_yr2014</th><th scope=col>region_name.y</th><th scope=col>⋯</th><th scope=col>x2000_yr2000</th><th scope=col>x2001_yr2001</th><th scope=col>x2002_yr2002</th><th scope=col>x2003_yr2003</th><th scope=col>x2004_yr2004</th><th scope=col>x2005_yr2005</th><th scope=col>x2006_yr2006</th><th scope=col>x2007_yr2007</th><th scope=col>x2008_yr2008</th><th scope=col>x2009_yr2009</th></tr>
	<tr><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>⋯</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th></tr>
</thead>
<tbody>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>IDX.HDI          </td><td>Aceh Barat Daya, Kab.</td><td>Human Development Index                                </td><td>..     </td><td>70.95   </td><td>..              </td><td>72.07          </td><td>..    </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>..    </td><td>65.87778</td><td>66.86649</td><td>67.52173</td><td>68.36661</td><td>69.38033</td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>NE.GDI.TOTL.CR   </td><td>Aceh Barat Daya, Kab.</td><td>Total GDP based on expenditure (in IDR Million)        </td><td>..     </td><td>..      </td><td>..              </td><td>..             </td><td>..    </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>..    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>ROD.VILG.ASPH.ZS </td><td>Aceh Barat Daya, Kab.</td><td>Villages with road: Asphalt (in % of total villages)   </td><td>..     </td><td>73.28767</td><td>..              </td><td>..             </td><td>..    </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>83.72 </td><td>..      </td><td>80.62   </td><td>..      </td><td>..      </td><td>67.42   </td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>ROD.VILG.DIRT.ZS </td><td>Aceh Barat Daya, Kab.</td><td>Villages with road: Dirt (in % of total villages)      </td><td>..     </td><td>2.739726</td><td>..              </td><td>..             </td><td>..    </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>2.33  </td><td>..      </td><td>4.65    </td><td>..      </td><td>..      </td><td>3.79    </td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>ROD.VILG.GRAVL.ZS</td><td>Aceh Barat Daya, Kab.</td><td>Villages with road: Gravel (in % of total villages)    </td><td>..     </td><td>23.9726 </td><td>..              </td><td>..             </td><td>..    </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>13.18 </td><td>..      </td><td>14.73   </td><td>..      </td><td>..      </td><td>28.79   </td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>ROD.VILG.OTHR.ZS </td><td>Aceh Barat Daya, Kab.</td><td>Villages with road: Other (in % of total villages)     </td><td>..     </td><td>..      </td><td>..              </td><td>..             </td><td>..    </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>..    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SE.JRSEC.NENR.ZS </td><td>Aceh Barat Daya, Kab.</td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>75.62  </td><td>68.52   </td><td>78.25           </td><td>87.201385      </td><td>87.02 </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>..    </td><td>74.33   </td><td>..      </td><td>69.13   </td><td>76.71   </td><td>80.7    </td><td>65.59  </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SE.PRM.NENR.ZS   </td><td>Aceh Barat Daya, Kab.</td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>98.32  </td><td>86.16   </td><td>90.96           </td><td>95.395058      </td><td>97.03 </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>..    </td><td>94.65   </td><td>..      </td><td>94.89   </td><td>94.34   </td><td>96.21   </td><td>96.55  </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SE.SCHL.JRSEC    </td><td>Aceh Barat Daya, Kab.</td><td>Number of schools at junior secondary level            </td><td>..     </td><td>29      </td><td>..              </td><td>..             </td><td>..    </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>16    </td><td>..      </td><td>22      </td><td>..      </td><td>..      </td><td>12      </td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SE.SCHL.PRM      </td><td>Aceh Barat Daya, Kab.</td><td>Number of schools at primary level                     </td><td>..     </td><td>125     </td><td>..              </td><td>..             </td><td>..    </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>117   </td><td>..      </td><td>120     </td><td>..      </td><td>..      </td><td>66      </td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SE.SCHL.SRSEC    </td><td>Aceh Barat Daya, Kab.</td><td>Number of schools at Senior Secondary level            </td><td>..     </td><td>21      </td><td>..              </td><td>..             </td><td>..    </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>10    </td><td>..      </td><td>11      </td><td>..      </td><td>..      </td><td>10      </td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SE.SRSEC.NENR.ZS </td><td>Aceh Barat Daya, Kab.</td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>67.8   </td><td>65.99   </td><td>60.86           </td><td>63.46043       </td><td>72.64 </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>..    </td><td>54.23   </td><td>..      </td><td>52.97   </td><td>61.7    </td><td>62.9    </td><td>65.55  </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SH.DR.TOTL       </td><td>Aceh Barat Daya, Kab.</td><td>Number of Doctors                                      </td><td>..     </td><td>26      </td><td>..              </td><td>..             </td><td>..    </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>13    </td><td>..      </td><td>18      </td><td>..      </td><td>..      </td><td>6       </td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SH.HOSP.TOTL     </td><td>Aceh Barat Daya, Kab.</td><td>Number of hospitals                                    </td><td>..     </td><td>1       </td><td>..              </td><td>..             </td><td>..    </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>..    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SH.MED.MWIV.TOTL </td><td>Aceh Barat Daya, Kab.</td><td>Number of Midwives                                     </td><td>..     </td><td>191     </td><td>..              </td><td>..             </td><td>..    </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>108   </td><td>..      </td><td>97      </td><td>..      </td><td>..      </td><td>96      </td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SH.MORB.ZS       </td><td>Aceh Barat Daya, Kab.</td><td>Morbidity Rate (in %)                                  </td><td>30.0167</td><td>33.93033</td><td>30.5736273527145</td><td>29.909548163414</td><td>..    </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>..    </td><td>29.19532</td><td>..      </td><td>33.22042</td><td>35.90795</td><td>31.811  </td><td>29.2377</td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SH.POLINDES.TOTL </td><td>Aceh Barat Daya, Kab.</td><td>Number of Polindes (Poliklinik Desa/Village Polyclinic)</td><td>..     </td><td>19      </td><td>..              </td><td>..             </td><td>..    </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>116   </td><td>..      </td><td>107     </td><td>..      </td><td>..      </td><td>75      </td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SH.PUSKESMAS.TOTL</td><td>Aceh Barat Daya, Kab.</td><td>Number of Puskesmas and its line services              </td><td>..     </td><td>37      </td><td>..              </td><td>..             </td><td>..    </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>35    </td><td>..      </td><td>33      </td><td>..      </td><td>..      </td><td>..      </td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SI.POV.NAPL      </td><td>Aceh Barat Daya, Kab.</td><td>Poverty Line (in IDR)                                  </td><td>252217 </td><td>274089  </td><td>276324          </td><td>283117         </td><td>288713</td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>..    </td><td>..      </td><td>146135  </td><td>176979  </td><td>198562  </td><td>231460  </td><td>231758 </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SI.POV.NAPR.ZS   </td><td>Aceh Barat Daya, Kab.</td><td>Poverty Rate (in % of population)                      </td><td>19.93  </td><td>19.49   </td><td>18.51           </td><td>18.92          </td><td>17.99 </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>27.72 </td><td>27.98   </td><td>27.71   </td><td>28.3    </td><td>28.63   </td><td>23.42   </td><td>21.33  </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SI.POV.NGAP      </td><td>Aceh Barat Daya, Kab.</td><td>Poverty Gap (index)                                    </td><td>3.31   </td><td>2.63    </td><td>2.34            </td><td>2.64           </td><td>2.58  </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>5.2   </td><td>4.86    </td><td>6.83    </td><td>5.42    </td><td>4.87    </td><td>3.72    </td><td>3.06   </td></tr>
	<tr><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>SP.POP.TOTL      </td><td>Aceh Barat Daya, Kab.</td><td>Total Population (in number of people)                 </td><td>126036 </td><td>129708  </td><td>132612          </td><td>135385         </td><td>..    </td><td>Aceh Barat Daya, Kab.</td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>115358</td><td>111366  </td><td>112230  </td><td>119397  </td><td>121302  </td><td>123101  </td><td>124813 </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>IDX.HDI          </td><td>Aceh Barat, Kab.     </td><td>Human Development Index                                </td><td>..     </td><td>71.2    </td><td>..              </td><td>72.24          </td><td>..    </td><td>Aceh Barat, Kab.     </td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>..    </td><td>66.67713</td><td>67.4358 </td><td>68.08009</td><td>69.28123</td><td>69.66319</td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>NE.GDI.TOTL.CR   </td><td>Aceh Barat, Kab.     </td><td>Total GDP based on expenditure (in IDR Million)        </td><td>..     </td><td>..      </td><td>..              </td><td>..             </td><td>..    </td><td>Aceh Barat, Kab.     </td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>..    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>ROD.VILG.ASPH.ZS </td><td>Aceh Barat, Kab.     </td><td>Villages with road: Asphalt (in % of total villages)   </td><td>..     </td><td>52.8125 </td><td>..              </td><td>..             </td><td>..    </td><td>Aceh Barat, Kab.     </td><td>⋯</td><td>47.69</td><td>..</td><td>..</td><td>43.1  </td><td>..      </td><td>40      </td><td>..      </td><td>..      </td><td>40      </td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>ROD.VILG.DIRT.ZS </td><td>Aceh Barat, Kab.     </td><td>Villages with road: Dirt (in % of total villages)      </td><td>..     </td><td>2.1875  </td><td>..              </td><td>..             </td><td>..    </td><td>Aceh Barat, Kab.     </td><td>⋯</td><td>18.04</td><td>..</td><td>..</td><td>12.07 </td><td>..      </td><td>16.56   </td><td>..      </td><td>..      </td><td>15      </td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>ROD.VILG.GRAVL.ZS</td><td>Aceh Barat, Kab.     </td><td>Villages with road: Gravel (in % of total villages)    </td><td>..     </td><td>45      </td><td>..              </td><td>..             </td><td>..    </td><td>Aceh Barat, Kab.     </td><td>⋯</td><td>31.75</td><td>..</td><td>..</td><td>42.76 </td><td>..      </td><td>40.31   </td><td>..      </td><td>..      </td><td>44.38   </td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>ROD.VILG.OTHR.ZS </td><td>Aceh Barat, Kab.     </td><td>Villages with road: Other (in % of total villages)     </td><td>..     </td><td>..      </td><td>..              </td><td>..             </td><td>..    </td><td>Aceh Barat, Kab.     </td><td>⋯</td><td>0.7  </td><td>..</td><td>..</td><td>..    </td><td>..      </td><td>0.94    </td><td>..      </td><td>..      </td><td>..      </td><td>..     </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>SE.JRSEC.NENR.ZS </td><td>Aceh Barat, Kab.     </td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>74.69  </td><td>73.52   </td><td>79.22           </td><td>77.846069      </td><td>82.33 </td><td>Aceh Barat, Kab.     </td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>76.44 </td><td>71.35   </td><td>..      </td><td>73.19   </td><td>73      </td><td>61.91   </td><td>79.4   </td></tr>
	<tr><td>IDN_Aceh_Barat_Kab_73624     </td><td>SE.PRM.NENR.ZS   </td><td>Aceh Barat, Kab.     </td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>95.9   </td><td>93.32   </td><td>94.69           </td><td>99.302559      </td><td>99.75 </td><td>Aceh Barat, Kab.     </td><td>⋯</td><td>..   </td><td>..</td><td>..</td><td>93.51 </td><td>91.74   </td><td>..      </td><td>93.6    </td><td>96.34   </td><td>94.97   </td><td>93.78  </td></tr>
	<tr><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋱</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>SH.MED.MWIV.TOTL </td><td>Yalimo, Kab.    </td><td>Number of Midwives                                     </td><td>..      </td><td>25      </td><td>..              </td><td>..              </td><td>..    </td><td>Yalimo, Kab.    </td><td>⋯</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>SH.MORB.ZS       </td><td>Yalimo, Kab.    </td><td>Morbidity Rate (in %)                                  </td><td>43.24022</td><td>15.14103</td><td>7.99950882792473</td><td>11.1413404345512</td><td>..    </td><td>Yalimo, Kab.    </td><td>⋯</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>50.21875</td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>SH.POLINDES.TOTL </td><td>Yalimo, Kab.    </td><td>Number of Polindes (Poliklinik Desa/Village Polyclinic)</td><td>..      </td><td>1       </td><td>..              </td><td>..              </td><td>..    </td><td>Yalimo, Kab.    </td><td>⋯</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>SH.PUSKESMAS.TOTL</td><td>Yalimo, Kab.    </td><td>Number of Puskesmas and its line services              </td><td>..      </td><td>19      </td><td>..              </td><td>..              </td><td>..    </td><td>Yalimo, Kab.    </td><td>⋯</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>SI.POV.NAPL      </td><td>Yalimo, Kab.    </td><td>Poverty Line (in IDR)                                  </td><td>201665  </td><td>219074  </td><td>232140          </td><td>246035          </td><td>253293</td><td>Yalimo, Kab.    </td><td>⋯</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>185425  </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>SI.POV.NAPR.ZS   </td><td>Yalimo, Kab.    </td><td>Poverty Rate (in % of population)                      </td><td>44.13   </td><td>40.65   </td><td>39.48           </td><td>40.33           </td><td>35.65 </td><td>Yalimo, Kab.    </td><td>⋯</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>47.76   </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>SI.POV.NGAP      </td><td>Yalimo, Kab.    </td><td>Poverty Gap (index)                                    </td><td>9.32    </td><td>7.16    </td><td>7.8             </td><td>7.46            </td><td>6.32  </td><td>Yalimo, Kab.    </td><td>⋯</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>5.98    </td></tr>
	<tr><td>IDN_Yalimo_18307         </td><td>SP.POP.TOTL      </td><td>Yalimo, Kab.    </td><td>Total Population (in number of people)                 </td><td>50763   </td><td>52623   </td><td>53785           </td><td>54911           </td><td>..    </td><td>Yalimo, Kab.    </td><td>⋯</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>18806   </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>IDX.HDI          </td><td>Yogyakarta, Kota</td><td>Human Development Index                                </td><td>..      </td><td>79.89   </td><td>..              </td><td>80.51           </td><td>..    </td><td>Yogyakarta, Kota</td><td>⋯</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>77.42435</td><td>77.69897        </td><td>77.80558</td><td>78.14222</td><td>78.94582</td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>NE.GDI.TOTL.CR   </td><td>Yogyakarta, Kota</td><td>Total GDP based on expenditure (in IDR Million)        </td><td>..      </td><td>..      </td><td>..              </td><td>..              </td><td>..    </td><td>Yogyakarta, Kota</td><td>⋯</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>ROD.VILG.ASPH.ZS </td><td>Yogyakarta, Kota</td><td>Villages with road: Asphalt (in % of total villages)   </td><td>..      </td><td>100     </td><td>..              </td><td>..              </td><td>..    </td><td>Yogyakarta, Kota</td><td>⋯</td><td>100     </td><td>..      </td><td>..      </td><td>100     </td><td>..      </td><td>100             </td><td>..      </td><td>..      </td><td>100     </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>ROD.VILG.DIRT.ZS </td><td>Yogyakarta, Kota</td><td>Villages with road: Dirt (in % of total villages)      </td><td>..      </td><td>..      </td><td>..              </td><td>..              </td><td>..    </td><td>Yogyakarta, Kota</td><td>⋯</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>ROD.VILG.GRAVL.ZS</td><td>Yogyakarta, Kota</td><td>Villages with road: Gravel (in % of total villages)    </td><td>..      </td><td>..      </td><td>..              </td><td>..              </td><td>..    </td><td>Yogyakarta, Kota</td><td>⋯</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>ROD.VILG.OTHR.ZS </td><td>Yogyakarta, Kota</td><td>Villages with road: Other (in % of total villages)     </td><td>..      </td><td>..      </td><td>..              </td><td>..              </td><td>..    </td><td>Yogyakarta, Kota</td><td>⋯</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SE.JRSEC.NENR.ZS </td><td>Yogyakarta, Kota</td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>73.63   </td><td>63.02   </td><td>75.77           </td><td>87.365013       </td><td>88    </td><td>Yogyakarta, Kota</td><td>⋯</td><td>71.28   </td><td>81.82   </td><td>76.19   </td><td>73.33   </td><td>77      </td><td>81.82           </td><td>72.37   </td><td>76.56   </td><td>76.56   </td><td>78.87   </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SE.PRM.NENR.ZS   </td><td>Yogyakarta, Kota</td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>96.2    </td><td>92.18   </td><td>92.64           </td><td>98.837814       </td><td>95.37 </td><td>Yogyakarta, Kota</td><td>⋯</td><td>91.62   </td><td>93.75   </td><td>91.2    </td><td>90      </td><td>92.05   </td><td>92.11           </td><td>91.97   </td><td>92.64   </td><td>91.97   </td><td>90.64   </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SE.SCHL.JRSEC    </td><td>Yogyakarta, Kota</td><td>Number of schools at junior secondary level            </td><td>..      </td><td>63      </td><td>..              </td><td>..              </td><td>..    </td><td>Yogyakarta, Kota</td><td>⋯</td><td>76      </td><td>..      </td><td>..      </td><td>70      </td><td>..      </td><td>66              </td><td>..      </td><td>..      </td><td>63      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SE.SCHL.PRM      </td><td>Yogyakarta, Kota</td><td>Number of schools at primary level                     </td><td>..      </td><td>176     </td><td>..              </td><td>..              </td><td>..    </td><td>Yogyakarta, Kota</td><td>⋯</td><td>283     </td><td>..      </td><td>..      </td><td>249     </td><td>..      </td><td>245             </td><td>..      </td><td>..      </td><td>205     </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SE.SCHL.SRSEC    </td><td>Yogyakarta, Kota</td><td>Number of schools at Senior Secondary level            </td><td>..      </td><td>83      </td><td>..              </td><td>..              </td><td>..    </td><td>Yogyakarta, Kota</td><td>⋯</td><td>91      </td><td>..      </td><td>..      </td><td>64      </td><td>..      </td><td>79              </td><td>..      </td><td>..      </td><td>81      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SE.SRSEC.NENR.ZS </td><td>Yogyakarta, Kota</td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>72.45   </td><td>54.35   </td><td>69.73           </td><td>59.754978       </td><td>63.32 </td><td>Yogyakarta, Kota</td><td>⋯</td><td>62.59   </td><td>57.04   </td><td>70      </td><td>58.32   </td><td>62.79   </td><td>61.7            </td><td>66.3    </td><td>74.12   </td><td>72.04   </td><td>57.14   </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SH.DR.TOTL       </td><td>Yogyakarta, Kota</td><td>Number of Doctors                                      </td><td>..      </td><td>243     </td><td>..              </td><td>..              </td><td>..    </td><td>Yogyakarta, Kota</td><td>⋯</td><td>..      </td><td>..      </td><td>..      </td><td>286     </td><td>..      </td><td>297             </td><td>..      </td><td>..      </td><td>291     </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SH.HOSP.TOTL     </td><td>Yogyakarta, Kota</td><td>Number of hospitals                                    </td><td>..      </td><td>14      </td><td>..              </td><td>..              </td><td>..    </td><td>Yogyakarta, Kota</td><td>⋯</td><td>11      </td><td>..      </td><td>..      </td><td>11      </td><td>..      </td><td>11              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SH.MED.MWIV.TOTL </td><td>Yogyakarta, Kota</td><td>Number of Midwives                                     </td><td>..      </td><td>47      </td><td>..              </td><td>..              </td><td>..    </td><td>Yogyakarta, Kota</td><td>⋯</td><td>..      </td><td>..      </td><td>..      </td><td>66      </td><td>..      </td><td>47              </td><td>..      </td><td>..      </td><td>58      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SH.MORB.ZS       </td><td>Yogyakarta, Kota</td><td>Morbidity Rate (in %)                                  </td><td>39.83229</td><td>41.60153</td><td>41.320464015007 </td><td>39.2568409442902</td><td>..    </td><td>Yogyakarta, Kota</td><td>⋯</td><td>40.45922</td><td>35.12418</td><td>36.52309</td><td>38.80893</td><td>45.61763</td><td>38.41948        </td><td>47.55421</td><td>36.85756</td><td>44.32943</td><td>41.70478</td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SH.POLINDES.TOTL </td><td>Yogyakarta, Kota</td><td>Number of Polindes (Poliklinik Desa/Village Polyclinic)</td><td>..      </td><td>..      </td><td>..              </td><td>..              </td><td>..    </td><td>Yogyakarta, Kota</td><td>⋯</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SH.PUSKESMAS.TOTL</td><td>Yogyakarta, Kota</td><td>Number of Puskesmas and its line services              </td><td>..      </td><td>29      </td><td>..              </td><td>..              </td><td>..    </td><td>Yogyakarta, Kota</td><td>⋯</td><td>32      </td><td>..      </td><td>..      </td><td>30      </td><td>..      </td><td>29              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SI.POV.NAPL      </td><td>Yogyakarta, Kota</td><td>Poverty Line (in IDR)                                  </td><td>290286  </td><td>314311  </td><td>333232          </td><td>353602          </td><td>366520</td><td>Yogyakarta, Kota</td><td>⋯</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>214694          </td><td>235801  </td><td>249318  </td><td>263996  </td><td>265168  </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SI.POV.NAPR.ZS   </td><td>Yogyakarta, Kota</td><td>Poverty Rate (in % of population)                      </td><td>9.75    </td><td>9.62    </td><td>9.38            </td><td>8.82            </td><td>8.67  </td><td>Yogyakarta, Kota</td><td>⋯</td><td>..      </td><td>..      </td><td>14.52   </td><td>12.59   </td><td>21.77   </td><td>10.5            </td><td>10.22   </td><td>9.78    </td><td>10.81   </td><td>10.05   </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SI.POV.NGAP      </td><td>Yogyakarta, Kota</td><td>Poverty Gap (index)                                    </td><td>1.29    </td><td>1.19    </td><td>1.57            </td><td>1.24            </td><td>1.14  </td><td>Yogyakarta, Kota</td><td>⋯</td><td>..      </td><td>..      </td><td>3.23    </td><td>3.23    </td><td>2.96    </td><td>2.34            </td><td>1.88    </td><td>2.26    </td><td>2.1     </td><td>1.91    </td></tr>
	<tr><td>IDN_Yogyakarta_Kota_17983</td><td>SP.POP.TOTL      </td><td>Yogyakarta, Kota</td><td>Total Population (in number of people)                 </td><td>388627  </td><td>392506  </td><td>397594          </td><td>402679          </td><td>..    </td><td>Yogyakarta, Kota</td><td>⋯</td><td>397398  </td><td>395775  </td><td>394140  </td><td>392492  </td><td>396238  </td><td>419163.765233477</td><td>445258  </td><td>451118  </td><td>456915  </td><td>462663  </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



- Penggabungan baris berdasar variabel ID dalam argumen `by`
- jika ada variabel bernama sama tapi tidak menjadi argumen `by`, maka di data baru akan ditambahi akhiran `.x` dan `.y`
- jika variabel id berbeda nama di kedua data, 
  
  `by = c("id1_I" = "id1_II", "id2_I" = "id2_II")`
- jika tidak ada argumen `by`, penggabungan dilakukan dengan semua variabel bernama sama



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
dplyr::inner_join(data1, data2)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<table>
<caption>A data.frame: 12012 × 19</caption>
<thead>
	<tr><th scope=col>region_name</th><th scope=col>region_code</th><th scope=col>series_name</th><th scope=col>series_code</th><th scope=col>x2010_yr2010</th><th scope=col>x2011_yr2011</th><th scope=col>x2012_yr2012</th><th scope=col>x2013_yr2013</th><th scope=col>x2014_yr2014</th><th scope=col>x2000_yr2000</th><th scope=col>x2001_yr2001</th><th scope=col>x2002_yr2002</th><th scope=col>x2003_yr2003</th><th scope=col>x2004_yr2004</th><th scope=col>x2005_yr2005</th><th scope=col>x2006_yr2006</th><th scope=col>x2007_yr2007</th><th scope=col>x2008_yr2008</th><th scope=col>x2009_yr2009</th></tr>
	<tr><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th></tr>
</thead>
<tbody>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..      </td><td>70.95   </td><td>..              </td><td>72.07           </td><td>..    </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>65.87778</td><td>66.86649</td><td>67.52173</td><td>68.36661</td><td>69.38033</td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>30.0167 </td><td>33.93033</td><td>30.5736273527145</td><td>29.909548163414 </td><td>..    </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>29.19532</td><td>..      </td><td>33.22042</td><td>35.90795</td><td>31.811  </td><td>29.2377 </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>98.32   </td><td>86.16   </td><td>90.96           </td><td>95.395058       </td><td>97.03 </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>94.65   </td><td>..      </td><td>94.89   </td><td>94.34   </td><td>96.21   </td><td>96.55   </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>75.62   </td><td>68.52   </td><td>78.25           </td><td>87.201385       </td><td>87.02 </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>74.33   </td><td>..      </td><td>69.13   </td><td>76.71   </td><td>80.7    </td><td>65.59   </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>67.8    </td><td>65.99   </td><td>60.86           </td><td>63.46043        </td><td>72.64 </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>54.23   </td><td>..      </td><td>52.97   </td><td>61.7    </td><td>62.9    </td><td>65.55   </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>..      </td><td>1       </td><td>..              </td><td>..              </td><td>..    </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..      </td><td>26      </td><td>..              </td><td>..              </td><td>..    </td><td>..</td><td>..</td><td>..</td><td>13      </td><td>..      </td><td>18      </td><td>..      </td><td>..      </td><td>6       </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..      </td><td>191     </td><td>..              </td><td>..              </td><td>..    </td><td>..</td><td>..</td><td>..</td><td>108     </td><td>..      </td><td>97      </td><td>..      </td><td>..      </td><td>96      </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Puskesmas and its line services              </td><td>SH.PUSKESMAS.TOTL</td><td>..      </td><td>37      </td><td>..              </td><td>..              </td><td>..    </td><td>..</td><td>..</td><td>..</td><td>35      </td><td>..      </td><td>33      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of Polindes (Poliklinik Desa/Village Polyclinic)</td><td>SH.POLINDES.TOTL </td><td>..      </td><td>19      </td><td>..              </td><td>..              </td><td>..    </td><td>..</td><td>..</td><td>..</td><td>116     </td><td>..      </td><td>107     </td><td>..      </td><td>..      </td><td>75      </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at junior secondary level            </td><td>SE.SCHL.JRSEC    </td><td>..      </td><td>29      </td><td>..              </td><td>..              </td><td>..    </td><td>..</td><td>..</td><td>..</td><td>16      </td><td>..      </td><td>22      </td><td>..      </td><td>..      </td><td>12      </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at primary level                     </td><td>SE.SCHL.PRM      </td><td>..      </td><td>125     </td><td>..              </td><td>..              </td><td>..    </td><td>..</td><td>..</td><td>..</td><td>117     </td><td>..      </td><td>120     </td><td>..      </td><td>..      </td><td>66      </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Number of schools at Senior Secondary level            </td><td>SE.SCHL.SRSEC    </td><td>..      </td><td>21      </td><td>..              </td><td>..              </td><td>..    </td><td>..</td><td>..</td><td>..</td><td>10      </td><td>..      </td><td>11      </td><td>..      </td><td>..      </td><td>10      </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Line (in IDR)                                  </td><td>SI.POV.NAPL      </td><td>252217  </td><td>274089  </td><td>276324          </td><td>283117          </td><td>288713</td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>146135  </td><td>176979  </td><td>198562  </td><td>231460  </td><td>231758  </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>19.93   </td><td>19.49   </td><td>18.51           </td><td>18.92           </td><td>17.99 </td><td>..</td><td>..</td><td>..</td><td>27.72   </td><td>27.98   </td><td>27.71   </td><td>28.3    </td><td>28.63   </td><td>23.42   </td><td>21.33   </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>3.31    </td><td>2.63    </td><td>2.34            </td><td>2.64            </td><td>2.58  </td><td>..</td><td>..</td><td>..</td><td>5.2     </td><td>4.86    </td><td>6.83    </td><td>5.42    </td><td>4.87    </td><td>3.72    </td><td>3.06    </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..      </td><td>..      </td><td>..              </td><td>..              </td><td>..    </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>126036  </td><td>129708  </td><td>132612          </td><td>135385          </td><td>..    </td><td>..</td><td>..</td><td>..</td><td>115358  </td><td>111366  </td><td>112230  </td><td>119397  </td><td>121302  </td><td>123101  </td><td>124813  </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>..      </td><td>73.28767</td><td>..              </td><td>..              </td><td>..    </td><td>..</td><td>..</td><td>..</td><td>83.72   </td><td>..      </td><td>80.62   </td><td>..      </td><td>..      </td><td>67.42   </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..      </td><td>2.739726</td><td>..              </td><td>..              </td><td>..    </td><td>..</td><td>..</td><td>..</td><td>2.33    </td><td>..      </td><td>4.65    </td><td>..      </td><td>..      </td><td>3.79    </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..      </td><td>23.9726 </td><td>..              </td><td>..              </td><td>..    </td><td>..</td><td>..</td><td>..</td><td>13.18   </td><td>..      </td><td>14.73   </td><td>..      </td><td>..      </td><td>28.79   </td><td>..      </td></tr>
	<tr><td>Aceh Barat Daya, Kab.</td><td>IDN_Aceh_Barat_Daya_Kab_73623</td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..      </td><td>..      </td><td>..              </td><td>..              </td><td>..    </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..      </td><td>71.2    </td><td>..              </td><td>72.24           </td><td>..    </td><td>..</td><td>..</td><td>..</td><td>..      </td><td>66.67713</td><td>67.4358 </td><td>68.08009</td><td>69.28123</td><td>69.66319</td><td>..      </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>29.98806</td><td>35.01794</td><td>23.5453695058823</td><td>24.8722642660141</td><td>..    </td><td>..</td><td>..</td><td>..</td><td>20.64202</td><td>32.03152</td><td>..      </td><td>28.0538 </td><td>42.79228</td><td>31.97134</td><td>27.13197</td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>95.9    </td><td>93.32   </td><td>94.69           </td><td>99.302559       </td><td>99.75 </td><td>..</td><td>..</td><td>..</td><td>93.51   </td><td>91.74   </td><td>..      </td><td>93.6    </td><td>96.34   </td><td>94.97   </td><td>93.78   </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>74.69   </td><td>73.52   </td><td>79.22           </td><td>77.846069       </td><td>82.33 </td><td>..</td><td>..</td><td>..</td><td>76.44   </td><td>71.35   </td><td>..      </td><td>73.19   </td><td>73      </td><td>61.91   </td><td>79.4    </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>69.77   </td><td>70.41   </td><td>67.87           </td><td>71.44487        </td><td>73.09 </td><td>..</td><td>..</td><td>..</td><td>55.92   </td><td>53.14   </td><td>..      </td><td>56.41   </td><td>60.92   </td><td>65.52   </td><td>65.66   </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>..      </td><td>1       </td><td>..              </td><td>..              </td><td>..    </td><td>2 </td><td>..</td><td>..</td><td>1       </td><td>..      </td><td>1       </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..      </td><td>47      </td><td>..              </td><td>..              </td><td>..    </td><td>..</td><td>..</td><td>..</td><td>22      </td><td>..      </td><td>13      </td><td>..      </td><td>..      </td><td>26      </td><td>..      </td></tr>
	<tr><td>Aceh Barat, Kab.     </td><td>IDN_Aceh_Barat_Kab_73624     </td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..      </td><td>237     </td><td>..              </td><td>..              </td><td>..    </td><td>..</td><td>..</td><td>..</td><td>182     </td><td>..      </td><td>127     </td><td>..      </td><td>..      </td><td>168     </td><td>..      </td></tr>
	<tr><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>44.13   </td><td>40.65   </td><td>39.48          </td><td>40.33           </td><td>35.65 </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>47.76   </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>9.32    </td><td>7.16    </td><td>7.8            </td><td>7.46            </td><td>6.32  </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>5.98    </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>50763   </td><td>52623   </td><td>53785          </td><td>54911           </td><td>..    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>18806   </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>..      </td><td>14.81481</td><td>..             </td><td>..              </td><td>..    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..      </td><td>55.55556</td><td>..             </td><td>..              </td><td>..    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..      </td><td>29.62963</td><td>..             </td><td>..              </td><td>..    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yalimo, Kab.    </td><td>IDN_Yalimo_18307         </td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Human Development Index                                </td><td>IDX.HDI          </td><td>..      </td><td>79.89   </td><td>..             </td><td>80.51           </td><td>..    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>77.42435</td><td>77.69897        </td><td>77.80558</td><td>78.14222</td><td>78.94582</td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Morbidity Rate (in %)                                  </td><td>SH.MORB.ZS       </td><td>39.83229</td><td>41.60153</td><td>41.320464015007</td><td>39.2568409442902</td><td>..    </td><td>40.45922</td><td>35.12418</td><td>36.52309</td><td>38.80893</td><td>45.61763</td><td>38.41948        </td><td>47.55421</td><td>36.85756</td><td>44.32943</td><td>41.70478</td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Primary (in %)                   </td><td>SE.PRM.NENR.ZS   </td><td>96.2    </td><td>92.18   </td><td>92.64          </td><td>98.837814       </td><td>95.37 </td><td>91.62   </td><td>93.75   </td><td>91.2    </td><td>90      </td><td>92.05   </td><td>92.11           </td><td>91.97   </td><td>92.64   </td><td>91.97   </td><td>90.64   </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Junior Secondary (in %)          </td><td>SE.JRSEC.NENR.ZS </td><td>73.63   </td><td>63.02   </td><td>75.77          </td><td>87.365013       </td><td>88    </td><td>71.28   </td><td>81.82   </td><td>76.19   </td><td>73.33   </td><td>77      </td><td>81.82           </td><td>72.37   </td><td>76.56   </td><td>76.56   </td><td>78.87   </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Net Enrollment Ratio: Senior Secondary (in %)          </td><td>SE.SRSEC.NENR.ZS </td><td>72.45   </td><td>54.35   </td><td>69.73          </td><td>59.754978       </td><td>63.32 </td><td>62.59   </td><td>57.04   </td><td>70      </td><td>58.32   </td><td>62.79   </td><td>61.7            </td><td>66.3    </td><td>74.12   </td><td>72.04   </td><td>57.14   </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of hospitals                                    </td><td>SH.HOSP.TOTL     </td><td>..      </td><td>14      </td><td>..             </td><td>..              </td><td>..    </td><td>11      </td><td>..      </td><td>..      </td><td>11      </td><td>..      </td><td>11              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Doctors                                      </td><td>SH.DR.TOTL       </td><td>..      </td><td>243     </td><td>..             </td><td>..              </td><td>..    </td><td>..      </td><td>..      </td><td>..      </td><td>286     </td><td>..      </td><td>297             </td><td>..      </td><td>..      </td><td>291     </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Midwives                                     </td><td>SH.MED.MWIV.TOTL </td><td>..      </td><td>47      </td><td>..             </td><td>..              </td><td>..    </td><td>..      </td><td>..      </td><td>..      </td><td>66      </td><td>..      </td><td>47              </td><td>..      </td><td>..      </td><td>58      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Puskesmas and its line services              </td><td>SH.PUSKESMAS.TOTL</td><td>..      </td><td>29      </td><td>..             </td><td>..              </td><td>..    </td><td>32      </td><td>..      </td><td>..      </td><td>30      </td><td>..      </td><td>29              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of Polindes (Poliklinik Desa/Village Polyclinic)</td><td>SH.POLINDES.TOTL </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at junior secondary level            </td><td>SE.SCHL.JRSEC    </td><td>..      </td><td>63      </td><td>..             </td><td>..              </td><td>..    </td><td>76      </td><td>..      </td><td>..      </td><td>70      </td><td>..      </td><td>66              </td><td>..      </td><td>..      </td><td>63      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at primary level                     </td><td>SE.SCHL.PRM      </td><td>..      </td><td>176     </td><td>..             </td><td>..              </td><td>..    </td><td>283     </td><td>..      </td><td>..      </td><td>249     </td><td>..      </td><td>245             </td><td>..      </td><td>..      </td><td>205     </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Number of schools at Senior Secondary level            </td><td>SE.SCHL.SRSEC    </td><td>..      </td><td>83      </td><td>..             </td><td>..              </td><td>..    </td><td>91      </td><td>..      </td><td>..      </td><td>64      </td><td>..      </td><td>79              </td><td>..      </td><td>..      </td><td>81      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Line (in IDR)                                  </td><td>SI.POV.NAPL      </td><td>290286  </td><td>314311  </td><td>333232         </td><td>353602          </td><td>366520</td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>214694          </td><td>235801  </td><td>249318  </td><td>263996  </td><td>265168  </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Rate (in % of population)                      </td><td>SI.POV.NAPR.ZS   </td><td>9.75    </td><td>9.62    </td><td>9.38           </td><td>8.82            </td><td>8.67  </td><td>..      </td><td>..      </td><td>14.52   </td><td>12.59   </td><td>21.77   </td><td>10.5            </td><td>10.22   </td><td>9.78    </td><td>10.81   </td><td>10.05   </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Poverty Gap (index)                                    </td><td>SI.POV.NGAP      </td><td>1.29    </td><td>1.19    </td><td>1.57           </td><td>1.24            </td><td>1.14  </td><td>..      </td><td>..      </td><td>3.23    </td><td>3.23    </td><td>2.96    </td><td>2.34            </td><td>1.88    </td><td>2.26    </td><td>2.1     </td><td>1.91    </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Total GDP based on expenditure (in IDR Million)        </td><td>NE.GDI.TOTL.CR   </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Total Population (in number of people)                 </td><td>SP.POP.TOTL      </td><td>388627  </td><td>392506  </td><td>397594         </td><td>402679          </td><td>..    </td><td>397398  </td><td>395775  </td><td>394140  </td><td>392492  </td><td>396238  </td><td>419163.765233477</td><td>445258  </td><td>451118  </td><td>456915  </td><td>462663  </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Asphalt (in % of total villages)   </td><td>ROD.VILG.ASPH.ZS </td><td>..      </td><td>100     </td><td>..             </td><td>..              </td><td>..    </td><td>100     </td><td>..      </td><td>..      </td><td>100     </td><td>..      </td><td>100             </td><td>..      </td><td>..      </td><td>100     </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Dirt (in % of total villages)      </td><td>ROD.VILG.DIRT.ZS </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Gravel (in % of total villages)    </td><td>ROD.VILG.GRAVL.ZS</td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
	<tr><td>Yogyakarta, Kota</td><td>IDN_Yogyakarta_Kota_17983</td><td>Villages with road: Other (in % of total villages)     </td><td>ROD.VILG.OTHR.ZS </td><td>..      </td><td>..      </td><td>..             </td><td>..              </td><td>..    </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td><td>..              </td><td>..      </td><td>..      </td><td>..      </td><td>..      </td></tr>
</tbody>
</table>

</div>

</div>
</div>
</div>



- Secara default, hasil merge hanya mempertahankan baris dengan ID yang terdapat di kedua data yang digabungkan. Hasil default merge ini ekuivalen dengan hasil dari `dplyr::inner_join`
- jika ingin semua baris dipertahankan walau ID hanya terdapat di salah satu data, maka gunakan argumen `all = TRUE`. Ini ekuivalen dengan hasil dari `dplyr::all_join`
- jika hanya ingin mempertahankan semua baris dari salah satu data 
  - data I gunakan `all.x = TRUE`, ekuivalen dengan `dplyr::left_join`
  - data II gunakan `all.y = TRUE`, ekuivalen dengan `dplyr::right_join`



## Menyimpan dan Menghapus Objek



- simpan semua objek R di memori ke file dengan perintah `save.image`
- gunakan `save` jika hanya sebagian objek yang ingin disimpan  
- simpan image dengan nama `.RData` jika ingin otomatis dimuat ke memori tiap awal menjalankan R dari direktori tersebut



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
save(datakab,data1, data2, file = "datakab.rda")
save.image(file = ".RData")

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

</div>



- `ls` memberikan vektor nama semua objek yang ada di memori



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
rm(list = ls())
load('datakab.rda')

```
</div>

</div>



- gunakan `load` untuk memuat semua objek dalam file image ke memori



- saat dimuat kembali dari file image, nama objek akan sama dengan saat disimpan 
- untuk bisa bebas memberikan nama baru pada objek saat dimuat kembali, simpan dengan `saveRDS` dan muat dengan `readRDS`
- kedua perintah ini hanya bisa menyimpan dan memuat satu objek



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
saveRDS(datakab, file = "datakab.rds")
indo_dapoer = readRDS('datakab.rds')

```
</div>

</div>



## Merubah Nilai



- Bisa merubah nilai sel tertentu dengan menunjukkan lokasi baris dan kolomnya



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
datakab[2,3]
datakab[2,3] = 'Morbidity Rate (%)'
datakab[2,3]

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
'Morbidity Rate (in %)'
</div>

</div>
</div>
<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
'Morbidity Rate (%)'
</div>

</div>
</div>
</div>



- Gunakan conditional `ifelse` untuk merubah semua baris atau kolom dengan nilai tertentu.



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```R
mutate_ stringr::str_detect(names(datakab), "x200[0-9].+")] = stringr::str_replace(names(datakab), "x(200[0-9]).+", "\\1")]

```
</div>

</div>

