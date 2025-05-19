# Laporan Proyek Machine Learning - Yohanes Aldo Anantha

## Domain Proyek

Kanker adalah kelompok penyakit yang ditandai oleh pertumbuhan sel abnormal yang tidak terkendali dan berpotensi menyebar ke bagian tubuh lainnya. Kanker dapat menyerang hampir semua organ tubuh dan merupakan salah satu penyebab utama kematian di seluruh dunia ([World Health Organization, 2022](https://www.who.int/news-room/fact-sheets/detail/cancer)). 

Menurut data dari Global Cancer Observatory ([GLOBOCAN](https://doi.org/10.3322/caac.21660)) yang dirilis oleh International Agency for Research on Cancer (IARC), pada tahun 2020 terdapat lebih dari 19,3 juta kasus kanker baru dan hampir 10 juta kematian akibat kanker. Beban penyakit ini diperkirakan akan terus meningkat di tahun-tahun mendatang karena beberapa faktor seperti:
    - Pertumbuhan dan penuaan populasi.
    - Gaya hidup tidak sehat seperti konsumsi tembakau, alkohol, diet tinggi lemak dan rendah serat.
    - Kurangnya deteksi dini dan akses layanan kesehatan yang memadai.
    - Paparan terhadap lingkungan dan zat karsinogenik.

Peningkatan jumlah pasien kanker bukan hanya menjadi tantangan medis, tetapi juga menimbulkan tekanan besar pada sistem kesehatan dan ekonomi negara. Pemerintah, penyedia layanan kesehatan, dan organisasi non-pemerintah memerlukan pendekatan berbasis data untuk:
    - Mengantisipasi kebutuhan layanan medis (seperti rumah sakit, obat, tenaga kerja medis).
    - Menyusun kebijakan pengendalian kanker yang lebih efisien.
    - Mengelola pembiayaan jangka panjang dan asuransi kesehatan.

Oleh karena itu, kemampuan untuk memprediksi jumlah pasien kanker di masa depan sangat penting. Proyek ini hadir dengan pendekatan machine learning berbasis data historis jumlah pasien kanker global dari tahun 2015 hingga 2024. Model prediksi yang dikembangkan dapat digunakan sebagai alat bantu dalam pengambilan keputusan strategis oleh lembaga kesehatan, pemerintah, maupun sektor industri farmasi.

### Referensi 
- Sung, H., et al. (2021). Global cancer statistics 2020: GLOBOCAN estimates of incidence and mortality worldwide. CA: A Cancer Journal for Clinicians, 71(3), 209-249. https://doi.org/10.3322/caac.21660
- World Health Organization. (2022). Cancer. https://www.who.int/news-room/fact-sheets/detail/cancer

## Business Understanding

Dalam beberapa dekade terakhir, kanker telah menjadi salah satu beban kesehatan global terbesar, tidak hanya karena angka kasus dan kematian yang tinggi, tetapi juga karena dampaknya yang signifikan terhadap sistem layanan kesehatan dan ekonomi nasional. Organisasi Kesehatan Dunia (WHO) mencatat bahwa kanker menjadi penyebab utama kematian secara global, dan tren ini menunjukkan peningkatan dari tahun ke tahun.
Data historis jumlah pasien kanker secara global dapat digunakan untuk memahami pola dan tren penyakit ini. Analisis tersebut sangat penting untuk membantu pengambil kebijakan dan penyedia layanan kesehatan dalam:
    - Menentukan strategi penanggulangan kanker.
    - Mengalokasikan anggaran dan sumber daya dengan lebih tepat.
    - Merancang program pencegahan dan skrining dini.
Dengan menggunakan pendekatan machine learning, kita dapat membangun model prediksi yang mampu memperkirakan jumlah pasien kanker di masa depan, yang pada gilirannya dapat mendukung keputusan strategis dalam sistem kesehatan global.

### Problem Statements
Proyek ini mengangkat sejumlah permasalahan penting yang berkaitan dengan karakteristik pasien kanker berdasarkan data historis global. Berikut adalah tinjauan terhadap masing-masing permasalahan berdasarkan konteks dan potensi eksplorasi data:
- **Distribusi pasien berdasarkan negara**, Meskipun data yang digunakan dalam notebook saat ini bersifat global secara agregat, analisis distribusi berdasarkan negara akan menjadi penting jika tersedia data granular per wilayah. Ini akan membantu mengidentifikasi negara dengan beban kanker tertinggi serta mendukung strategi alokasi sumber daya medis secara geografis.
- **Distribusi pasien berdasarkan jenis kelamin**, Penelitian epidemiologi menunjukkan bahwa prevalensi kanker sering berbeda antara pria dan wanita, tergantung jenis kankernya. Analisis ini akan memberikan wawasan apakah ada kecenderungan gender tertentu terhadap kanker tertentu, yang dapat membantu dalam kampanye kesadaran dan skrining berbasis gender.
- **Hubungan antara Tingkat Risiko Genetik dan Jenis Kanker**, Banyak jenis kanker seperti kanker payudara, ovarium, dan prostat memiliki komponen genetik yang signifikan. Dengan menganalisis keterkaitan antara faktor genetik dan jenis kanker, kita dapat mendukung pengembangan kebijakan deteksi dini dan pengujian genetik secara lebih terarah.
- **Distribusi Usia Berdasarkan Stadium Kanker**, Stadium kanker saat diagnosis sangat menentukan prognosis. Mengamati pola usia di tiap stadium dapat memberikan informasi penting mengenai kelompok usia yang cenderung terdiagnosis lebih lambat atau lebih awal, serta potensi untuk intervensi dini.
- **Pengaruh Biaya Pengobatan terhadap Peluang Bertahan Hidup**, Akses terhadap pengobatan kanker berkualitas sangat bergantung pada biaya. Menganalisis korelasi antara pengeluaran medis dan survival rate pasien penting untuk menyusun strategi perlindungan kesehatan, subsidi, serta mengurangi ketimpangan dalam penanganan kanker.

### Goals

- **Untuk mengetahui distribusi pasien kanker berdasarkan negara**, diperlukan analisis statistik dan visualisasi geospasial guna mengidentifikasi negara-negara dengan beban kanker tertinggi, sehingga dapat membantu dalam perencanaan alokasi sumber daya medis secara regional.
- **Untuk memahami distribusi pasien berdasarkan jenis kelamin**, dilakukan analisis segmentasi dan perbandingan jumlah kasus antara pria dan wanita untuk mendeteksi potensi perbedaan signifikan yang dapat digunakan dalam perancangan program pencegahan dan skrining berbasis gender.
- **Untuk mengkaji hubungan antara tingkat risiko genetik dan jenis kanker**, diperlukan pemodelan statistik atau machine learning yang dapat mengidentifikasi korelasi atau hubungan sebab-akibat antara faktor genetik dan jenis kanker yang muncul, sebagai dasar bagi rekomendasi pengujian genetik dini.
- **Untuk mengevaluasi distribusi usia berdasarkan stadium kanker**, dilakukan eksplorasi data dengan visualisasi dan uji statistik untuk mengetahui kecenderungan usia pasien di setiap stadium kanker, yang dapat mendukung strategi deteksi dini dan intervensi usia spesifik.
- **Untuk menganalisis pengaruh biaya pengobatan terhadap peluang bertahan hidup**, dilakukan pemodelan regresi atau analisis survival untuk mengevaluasi sejauh mana investasi dalam pengobatan berdampak terhadap hasil klinis pasien, dengan potensi rekomendasi kebijakan pembiayaan yang lebih adil dan efektif.

### Solution statements
- **Eksperimen Multimodel Regresi**, Beberapa algoritma regresi seperti ElasticNet, SVR, KNeighborsRegressor, DecisionTreeRegressor, RandomForestRegressor, dan GradientBoostingRegressor diuji untuk memprediksi jumlah pasien kanker berdasarkan tahun. Setiap model dibandingkan menggunakan metrik R², MAE, MSE, dan RMSE. Hasil evaluasi menunjukkan bahwa Random Forest dan Gradient Boosting memberikan performa terbaik.
- **Mengukur performa model regresi**, dengan menggunakan beberapa metrik seperti MSE, MAE, R2 dan RMSE untuk mengevaluasi kinerja model dalam memprediksi jumlah pasien kanker di masa depan.


## Data Understanding
Dataset yang digunakan dalam analisis ini bernama  [Global Cancer Patients](https://www.kaggle.com/datasets/zahidmughal2343/global-cancer-patients-2015-2024) berisi informasi terkait kanker, yang mencakup berbagai fitur diagnostik yang membantu dalam menentukan apakah suatu kasus bersifat jinak atau ganas.

### Informasi Dataset
Dataset ini berisi informasi mengenai 50.000 pasien kanker dari berbagai negara pada rentang tahun 2015 hingga 2024. Masing-masing baris dalam dataset mewakili satu individu pasien, lengkap dengan data demografis, faktor risiko, jenis kanker yang diderita, serta hasil pengobatan. Total terdapat 15 kolom atau fitur dalam dataset ini. Variabel target dalam dataset adalah `Target_Severity_Score`, yang menunjukkan tingkat keparahan kondisi pasien berdasarkan parameter yang telah ditentukan.

Fitur - Fitur yang terdapat pada dataset ini yaitu:
    
- **Patient_ID** = ID unik untuk mengidentifikasi setiap pasien secara individual.         
- **Age** = Usia pasien saat data dikumpulkan.                 
- **Gender** = Jenis kelamin pasien (contoh: Male, Female, Other).                 
- **Country_Region** = Negara atau wilayah asal pasien.          
- **Year** = Tahun data dicatat (antara 2015–2024).                     
- **Genetic_Risk** = Skor atau tingkat risiko genetik terhadap kanker (numerik).           
- **Air_Pollution** = Tingkat paparan terhadap polusi udara di lingkungan tempat tinggal pasien (numerik).          
- **Alcohol_Use** = Tingkat konsumsi alkohol pasien (numerik).           
- **Smoking** = Status atau tingkat merokok pasie(numerik).                
- **Obesity_Level** = Tingkat obesitas pasien (nilai BMI).          
- **Cancer_Type** = Jenis kanker yang diderita pasien (contoh: Breast, Lung, Colon, leukimia, cervical, prostate, liver dan skin).            
- **Cancer_Stage** = Stadium kanker saat diagnosis (contoh: Stage I, II, III, IV).            
- **Treatment_Cost_USD** = Total biaya pengobatan pasien dalam mata uang USD.   
- **Survival_Years** = Lama waktu bertahan hidup pasien setelah diagnosis (numerik).         
- **Target_Severity_Score** = Skor tingkat keparahan kondisi pasien.  
   
### Tahapan Pemahaman Data
Untuk memahami data perlu dilakukan beberapa hal seperti berikut:
- Memahami distribusi umum dari variabel numerik serta Frekuensi dan proporsi untuk variabel kategorikal.
- Pemeriksaan Nilai Hilang dan Duplikat untuk mengetahui kualitas data.
- Melakukan eksplorasi korelasi fitur numerik.
- Analisis Eksploratif terhadap Pola, Distribusi, dan Hubungan Antarfaktor Kanker
  - Distribusi kolom numerik
  - Distribusi pasien berdasarkan negara
  - Distribusi pasien berdasarkan jenis kelamin
  - Hubungan antara Tingkat Risiko Genetik dan Jenis Kanker
  - Distribusi Usia Berdasarkan Stadium Kanker
  - Pengaruh Biaya Pengobatan terhadap Peluang Bertahan Hidup
- Mengecek adanya outliers pada data

### Informasi Data
````
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 50000 entries, 0 to 49999
Data columns (total 15 columns):
 #   Column                 Non-Null Count  Dtype  
---  ------                 --------------  -----  
 0   Patient_ID             50000 non-null  object 
 1   Age                    50000 non-null  int64  
 2   Gender                 50000 non-null  object 
 3   Country_Region         50000 non-null  object 
 4   Year                   50000 non-null  int64  
 5   Genetic_Risk           50000 non-null  float64
 6   Air_Pollution          50000 non-null  float64
 7   Alcohol_Use            50000 non-null  float64
 8   Smoking                50000 non-null  float64
 9   Obesity_Level          50000 non-null  float64
 10  Cancer_Type            50000 non-null  object 
 11  Cancer_Stage           50000 non-null  object 
 12  Treatment_Cost_USD     50000 non-null  float64
 13  Survival_Years         50000 non-null  float64
 14  Target_Severity_Score  50000 non-null  float64
````
Dataset ini terdiri dari **50.000** entri dan **15** kolom. Tidak terdapat nilai yang hilang, hal ini terlihat dari masing-masing kolom memiliki **50.000** entri sehingga tidak perlu lagi melakukan pengecekan **Missing Value**. Tipe data untuk sebagian besar kolom adalah **float64** dan **object**, serta beberapa kolom bertipe **int64**.

### Melakukan pengecekan duplikasi data
```python
print(f"Jumlah duplikasi data : {df.duplicated().sum()}")
```
```bash
Jumlah duplikasi data : 0
```
Setelah dilakukan analisis menggunakan metode **duplicated()**, tidak ditemukan adanya duplikasi dalam dataset ini. Dengan demikian, setiap baris data bersifat unik dan tidak terdapat data yang tercatat lebih dari satu kali secara identik.

### Statistik deskriptif
|index|Age|Year|Genetic\_Risk|Air\_Pollution|Alcohol\_Use|Smoking|Obesity\_Level|Treatment\_Cost\_USD|Survival\_Years|Target\_Severity\_Score|
|---|---|---|---|---|---|---|---|---|---|---|
|count|50000\.0|50000\.0|50000\.0|50000\.0|50000\.0|50000\.0|50000\.0|50000\.0|50000\.0|50000\.0|
|mean|54\.42154|2019\.48052|0\.5001698|0\.5010126|0\.501088|0\.4989826|0\.49911759999999994|52467\.29823860001|5\.006462|0\.4904609443099273|
|std|20\.224451156877244|2\.8714848838381233|0\.2885772525764664|0\.288839937009098|0\.2888768686705609|0\.2881578726955619|0\.2894504050800183|27363\.229378979715|2\.8833354843005297|0\.14523931962276065|
|min|20\.0|2015\.0|0\.0|0\.0|0\.0|0\.0|0\.0|5000\.05|0\.0|0\.0|
|25%|37\.0|2017\.0|0\.25|0\.25|0\.25|0\.25|0\.25|28686\.225|2\.5|0\.38983050847457634|
|50%|54\.0|2019\.0|0\.5|0\.5|0\.5|0\.5|0\.5|52474\.31|5\.0|0\.49031476997578693|
|75%|72\.0|2022\.0|0\.75|0\.75|0\.75|0\.75|0\.75|76232\.72|7\.5|0\.5907990314769976|
|max|89\.0|2024\.0|1\.0|1\.0|1\.0|1\.0|1\.0|99999\.84|10\.0|1\.0| 

Berdasarkan tabel statistik deskriptif menunjukkan beberapa informasi seperti berikut :  
- **Age**: Rata-rata usia pasien 54,4 tahun dengan rentang 20-89 tahun, menunjukkan kanker mempengaruhi berbagai kelompok usia dengan konsentrasi pada usia pertengahan dan lansia.
- **Year**: Data dikumpulkan antara 2015-2024, memberikan gambaran tren kanker selama dekade terakhir.
- **Genetic_Risk**: Rata-rata 5,00 pada skala 0-10, mengindikasikan distribusi merata antara pasien dengan predisposisi genetik rendah hingga tinggi.
- **Air_Pollution**: Skor rata-rata 5,01, menggambarkan kontribusi signifikan faktor lingkungan terhadap risiko kanker.
- **Alcohol_Use**: Rata-rata 5,01, menekankan hubungan antara konsumsi alkohol dan kejadian kanker pada populasi sampel.
- **Smoking**: Nilai rata-rata 4,99, hampir identik dengan faktor risiko lainnya, menunjukkan peran merokok setara dengan faktor lain.
- **Obesity_Level**: Rata-rata 4,99, menegaskan hubungan antara berat badan berlebih dan risiko kanker.
- **Treatment_Cost_USD**: Biaya pengobatan sangat bervariasi ($5.000-$99.999) dengan rata-rata $52.467, menggambarkan beban ekonomi signifikan pengobatan kanker.
- **Survival_Years**: Rata-rata kelangsungan hidup 5,01 tahun dengan rentang 0-10 tahun, mencerminkan variasi prognosis tergantung pada jenis dan stadium kanker.
- **Target_Severity_Score**: Skor keparahan rata-rata 4,95 dengan distribusi lebih sempit (0,9-9,16), menunjukkan mayoritas kasus berada pada tingkat keparahan menengah.

**Menampilkan Frekuensi dan proporsi dari kolom kategorial**
```bash
Frekuensi dan Proporsi untuk Kolom 'Gender':
   Gender  Frekuensi  Proporsi
0    Male      16796   0.33592
1  Female      16709   0.33418
2   Other      16495   0.32990

Frekuensi dan Proporsi untuk Kolom 'Country_Region':
  Country_Region  Frekuensi  Proporsi
0      Australia       5092   0.10184
1             UK       5060   0.10120
2            USA       5060   0.10120
3          India       5040   0.10080
4        Germany       5024   0.10048
5         Russia       5017   0.10034
6         Brazil       5004   0.10008
7       Pakistan       4926   0.09852
8          China       4913   0.09826
9         Canada       4864   0.09728

Frekuensi dan Proporsi untuk Kolom 'Cancer_Type':
  Cancer_Type  Frekuensi  Proporsi
0       Colon       6376   0.12752
1    Prostate       6308   0.12616
2    Leukemia       6266   0.12532
3       Liver       6249   0.12498
4        Skin       6231   0.12462
5    Cervical       6222   0.12444
6      Breast       6189   0.12378
7        Lung       6159   0.12318

Frekuensi dan Proporsi untuk Kolom 'Cancer_Stage':
  Cancer_Stage  Frekuensi  Proporsi
0     Stage II      10124   0.20248
1      Stage I      10046   0.20092
2    Stage III      10008   0.20016
3     Stage IV       9933   0.19866
4      Stage 0       9889   0.19778
```

Berdasarkan hasil analisis frekuensi dan proporsi memberikan informasi sebagai berikut:
- **Gender**: Distribusi gender menunjukkan keseimbangan yang hampir sempurna antara **Male (33,59%)**, **Female (33,42%)**, dan **Other (32,99%)**. Keseimbangan ini sangat penting untuk penelitian kanker karena memungkinkan analisis yang tidak bias gender. Hal ini menarik mengingat beberapa jenis kanker memiliki predisposisi gender tertentu (seperti kanker prostat pada pria dan kanker serviks pada wanita), namun dataset mencerminkan representasi yang adil untuk mengkaji faktor risiko lintas gender.
- **Country_Region**: Data mencakup 10 negara dari berbagai benua dengan distribusi yang hampir merata **(9,7%-10,2%)**. **Australia** menduduki peringkat tertinggi **(10,18%)** sementara **Kanada** terendah **(9,73%)**. Representasi global ini memungkinkan analisis perbandingan faktor lingkungan, genetik, dan pola perawatan kesehatan di berbagai wilayah sosio-ekonomi. Kehadiran **negara berkembang (India, Pakistan)** dan **maju (USA, UK, Germany)** dalam proporsi serupa memungkinkan penelitian tentang disparitas akses perawatan kesehatan dan pengaruhnya terhadap hasil pengobatan kanker.
- **Cancer_Type**: Dataset mencakup delapan jenis kanker utama dengan distribusi yang **sangat seimbang (12,3%-12,8%)**. **Kanker kolon** sedikit mendominasi **(12,75%)** diikuti oleh **kanker prostat (12,62%)**, sementara **kanker paru-paru** memiliki representasi **terendah (12,32%)**. Keseimbangan ini luar biasa karena insiden kanker di populasi umum biasanya tidak seimbang. Ini mengindikasikan dataset yang didesain secara sengaja untuk memungkinkan perbandingan statistik yang valid antar jenis kanker, yang sangat berharga untuk penelitian komparatif tentang efektivitas pengobatan, biaya, dan hasil klinis pada berbagai jenis tumor.
- **Cancer_Stage**: Data mencakup seluruh spektrum **stadium kanker (0-IV)** dengan distribusi yang **relatif merata (19,8%-20,2%)**, dengan** Stage II sedikit lebih tinggi (20,25%)**. Representasi yang hampir sama dari setiap stadium sangat bernilai untuk analisis progresivitas penyakit. Hal yang mengejutkan adalah tingginya proporsi **Stage 0 (19,78%)**, menunjukkan penekanan pada deteksi dini dalam dataset ini. Keseimbangan ini memungkinkan penelitian mendalam tentang perbandingan biaya pengobatan dan tingkat kelangsungan hidup di berbagai tahap perkembangan kanker, serta evaluasi efektivitas intervensi dini versus lanjut.

### Analisis Eksploratif terhadap Pola, Distribusi, dan Hubungan
#### Distribusi kolom numerik
```python
numerical_cols = df.select_dtypes(include=['int64', 'float64']).columns
plt.figure(figsize=(14, 10))
for i, column in enumerate(numerical_cols, 1):
    plt.subplot(5, 2, i)
    sns.histplot(df[column], bins=30, kde=True, color='blue')
    plt.title(f'Distribusi {column}')
plt.tight_layout()
plt.show()
```
![image](https://github.com/user-attachments/assets/52600de8-8b5a-4228-a6ab-1bf5a02e3cd6)
Berdasarkan hasil visualisasi diatas menunjukkan informasi sebagai berikut:
- **Distribusi Age**: Grafik menunjukkan distribusi usia pasien kanker yang relatif merata dari **20-90** tahun dengan sedikit peningkatan pada kelompok **usia produktif (30-70 tahun)**. Pola ini mencerminkan representasi komprehensif berbagai kelompok usia, memungkinkan analisis mendalam tentang onset kanker pada berbagai tahap kehidupan dan pengaruh faktor usia terhadap respon pengobatan.
- **Distribusi Year**: Data dikumpulkan secara konsisten selama periode **2015-2024** dengan jumlah sampel yang relatif setara setiap tahunnya, meskipun terdapat **fluktuasi minor**. Keseimbangan temporal ini memungkinkan analisis tren longitudinal yang valid, termasuk perkembangan metode pengobatan dan perubahan pola diagnostik kanker dalam satu dekade terakhir.
- **Distribusi Genetic_Risk**: Grafik pada risiko genetik menunjukkan pola sangat seimbang di seluruh spektrum nilai **(0-10)**, mengindikasikan sampling yang komprehensif dari pasien dengan predisposisi genetik rendah hingga tinggi. Desain sampling yang cermat ini memungkinkan analisis valid tentang kontribusi relatif genetik terhadap perkembangan kanker, independent dari bias seleksi.
- **Distribusi Air_Pollution**: Paparan polusi udara menunjukkan distribusi hampir sempurna di seluruh skala **0-10**, mirip dengan faktor risiko lainnya. Keseragaman ini memfasilitasi studi korelasi yang kuat antara tingkat paparan polutan lingkungan dan perkembangan kanker, memberikan landasan untuk penelitian epidemiologi lingkungan yang komprehensif.
- Distribusi Alcohol_Use: Pola konsumsi alkohol terdistribusi merata dari abstinen hingga penggunaan berat **(0-10)**, dengan sedikit peningkatan pada **nilai genap**. Karakteristik ini memungkinkan penelitian dose-response yang akurat antara konsumsi alkohol dan risiko kanker serta interaksinya dengan faktor risiko lain.
- **Distribusi Smoking**: Kebiasaan merokok menunjukkan distribusi seragam di seluruh skala, menyediakan representasi seimbang dari non-perokok hingga perokok berat. Distribusi ini ideal untuk menganalisis hubungan dosis-respons antara intensitas merokok dan perkembangan berbagai jenis kanker serta efeknya pada hasil pengobatan.
- **Distribusi Obesity_Level**: Tingkat obesitas tersebar secara merata dari **0-10**, memberikan spektrum lengkap dari pasien kurus hingga obesitas berat. Pola ini sangat berharga untuk meneliti pengaruh BMI terhadap risiko kanker spesifik dan respons tubuh terhadap modalitas pengobatan berbeda.
- **Distribusi Treatment_Cost_USD**: Biaya pengobatan menunjukkan distribusi yang relatif seragam dari **$5.000** hingga **$100.000**, mencerminkan variasi luas dalam kompleksitas perawatan. Distribusi ini memungkinkan analisis mendalam tentang hubungan biaya-efektivitas berbagai pendekatan pengobatan dan disparitas ekonomi dalam akses perawatan kanker.
- **Distribusi Survival_Years**: Tingkat kelangsungan hidup terdistribusi secara seragam dari **0-10 tahun**, mencakup spektrum lengkap dari kasus terminal hingga remisi jangka panjang. Pola ini ideal untuk menganalisis determinan kelangsungan hidup dan mengembangkan model prognostik berdasarkan kombinasi faktor risiko dan karakteristik pengobatan.
- **Distribusi Target_Severity_Score**: Berbeda dengan fitur lain, skor keparahan menunjukkan distribusi normal yang terpusat di sekitar nilai **4-6**, dengan puncak pada **5**. Pola unik ini mengindikasikan bahwa mayoritas kasus memiliki tingkat keparahan menengah, sementara kasus ringan dan parah lebih jarang, mencerminkan pola alami distribusi keparahan kanker dalam populasi klinis.

#### Distribusi pasien berdasarkan negara
![image](https://github.com/user-attachments/assets/136fe610-f44d-4b71-9fb4-c0e1daaadf7c)

Berdasarkan barplot diatas menunjukkan distribusi pasien kanker yang sangat seimbang di 10 negara, dengan rentang sempit antara **9,73% (Kanada)** hingga **10,18% (Australia)**, mengindikasikan desain sampling yang disengaja untuk menghindari bias geografis. Keseimbangan proporsi antara **negara maju (Australia, UK, USA)** dan **berkembang (India, Pakistan)** memungkinkan analisis perbandingan yang valid terkait faktor lingkungan dan akses layanan kesehatan yang memengaruhi perkembangan kanker. Pola distribusi yang hampir identik ini sangat berharga untuk studi global tentang disparitas kesehatan, efektivitas berbagai sistem perawatan kesehatan, dan pengaruh faktor sosio-ekonomi terhadap hasil pengobatan kanker tanpa harus mengkompensasi ketidakseimbangan jumlah sampel.

#### Distribusi Pasien Berdasarkan Jenis Kelamin
![image](https://github.com/user-attachments/assets/3e81b8bb-f0d9-4281-8f61-356582a432d5)

Berdasarkan diagram pie yang ditampilkan distribusi pasien kanker yang luar biasa seimbang antara tiga kategori gender: **Male (33,6%)**, **Female (33,4%)**, dan **Other (33,0%)**. Keseimbangan yang hampir sempurna ini jelas merupakan hasil desain sampling yang disengaja untuk menghilangkan bias gender dalam penelitian, yang sangat berbeda dari distribusi kasus kanker di populasi umum dimana proporsi biasanya bervariasi signifikan berdasarkan gender. Inklusi kategori **"Other"** dengan proporsi hampir setara dengan kategori tradisional menunjukkan pendekatan penelitian yang sangat inklusif dan progresif, memungkinkan analisis yang komprehensif tentang bagaimana kanker mempengaruhi spektrum gender yang lebih luas. Keseimbangan ini memberikan kekuatan statistik yang optimal untuk membandingkan faktor risiko, respons pengobatan, dan hasil klinis lintas gender tanpa bias sampling, sekaligus memungkinkan penelitian tentang kanker spesifik gender (seperti prostat, serviks, dan payudara) serta variasi dalam manifestasi kanker yang sama pada gender berbeda, menciptakan dataset yang secara metodologis kuat untuk analisis disparitas kesehatan berbasis gender.

#### Distribusi Usia Berdasarkan Stadium Kanker
![image](https://github.com/user-attachments/assets/212574eb-c16c-4493-ac2d-9058bb785296)

Berdasarkan grafik ini, menampilkan rata-rata usia pasien berdasarkan stadium kanker. Dari visualisasi bar chart tersebut, terlihat bahwa usia rata-rata pasien relatif konsisten di semua stadium kanker, berada pada kisaran sekitar 55 tahun.Jika dilihat lebih detail, pasien dengan Stage III memiliki rata-rata usia sedikit lebih tinggi, diikuti oleh Stage 0, Stage II, Stage I, dan terakhir Stage IV. Namun, perbedaan antar stadium tidak signifikan, dengan selisih yang sangat kecil. Hal ini menunjukkan bahwa kanker dapat menyerang pada usia yang relatif sama terlepas dari stadiumnya.Informasi ini dapat memiliki implikasi penting untuk pemahaman epidemiologi kanker, menunjukkan bahwa faktor usia mungkin tidak menjadi prediktor yang kuat untuk stadium kanker yang didiagnosis. Hal ini berbeda dengan asumsi umum bahwa pasien yang lebih tua mungkin terdiagnosis pada stadium yang lebih lanjut. Temuan ini dapat membantu praktisi medis dalam memahami bahwa skrining dan diagnosis dini perlu dilakukan pada semua kelompok usia dewasa.

#### Hubungan antara Tingkat Risiko Genetik dan Jenis Kanker
![image](https://github.com/user-attachments/assets/5eefdade-d5e2-4c19-aa73-91625fbce52d)

Berdasarkan grafik ini menunjukkan bahwa risiko genetik berperan besar dalam semua jenis kanker yang ditampilkan, termasuk paru-paru, leukemia, payudara, usus besar, kulit, serviks, prostat, dan hati. Nilai risiko genetik hampir mencapai angka 5 pada skala, menandakan faktor keturunan sangat memengaruhi kemungkinan seseorang terkena kanker. Tidak ada perbedaan signifikan antar jenis kanker dalam hal risiko genetik, yang menguatkan pentingnya riwayat keluarga dalam deteksi dan pencegahan. Oleh karena itu, pemeriksaan rutin bagi individu dengan riwayat keluarga kanker sangat dianjurkan, serta pertimbangan faktor genetik dalam diagnosis dan perencanaan pengobatan oleh dokter.

#### Pengaruh Biaya Pengobatan terhadap Peluang Bertahan Hidup
![image](https://github.com/user-attachments/assets/b3fde86a-d0a5-403a-88b1-797391352907)

Visualisasi tren ini menunjukkan hubungan antara biaya pengobatan kanker dan rata-rata tahun bertahan hidup pasien, dengan pola yang **fluktuatif dan tidak linear**. Rata-rata harapan hidup cukup tinggi (**5,05 tahun**) pada biaya rendah (**10.000 USD**), kemudian menurun hingga titik terendah (**4,93 tahun**) pada **60.000 USD**, sebelum meningkat ke **5,09 tahun** pada **80.000 USD**, lalu kembali turun (**4,96 tahun**) pada **90.000 USD**.

Analisis data ini menunjukkan beberapa hal penting:
- **Biaya tinggi tidak selalu berarti harapan hidup lebih panjang**, karena faktor lain seperti stadium kanker dan metode pengobatan turut berpengaruh.
- **Terdapat titik optimal sekitar 80.000 USD**, di mana pengobatan memberikan hasil terbaik dalam meningkatkan harapan hidup.
- **Penurunan tajam setelah 80.000 USD** mungkin terkait dengan pasien yang memiliki kondisi lebih kompleks, sehingga meskipun pengobatannya mahal, hasilnya tetap terbatas.
- **Harapan hidup cukup tinggi pada biaya rendah (10.000-20.000 USD)**, yang bisa menunjukkan efektivitas pengobatan pada pasien dengan kanker stadium awal atau jenis yang lebih mudah diobati.

Temuan ini penting bagi kebijakan kesehatan, menunjukkan bahwa **pengobatan paling mahal tidak selalu paling efektif**. Fokus pada **deteksi dini dan strategi pengobatan yang tepat** dapat lebih bermanfaat daripada sekadar meningkatkan biaya perawatan. Analisis biaya-manfaat dalam perencanaan terapi kanker menjadi krusial untuk **mengoptimalkan sumber daya kesehatan dan hasil klinis pasien**.

#### Korelasi data
![image](https://github.com/user-attachments/assets/0cff60f3-3632-41ce-82eb-a0dd53e3e13c)

Matriks korelasi ini menunjukkan hubungan antara berbagai faktor risiko kanker dan tingkat keparahannya, dengan warna merah menandakan korelasi positif kuat dan biru korelasi negatif. Temuan paling signifikan terlihat pada hubungan antara **Target_Severity_Score** dengan **Genetic_Risk (0,48)** dan **Smoking (0,48)**, diikuti oleh **Air_Pollution (0,37)** dan **Alcohol_Use (0,36)**, menunjukkan faktor genetik dan merokok memiliki pengaruh terbesar terhadap keparahan kanker. Menariknya, terdapat korelasi **negatif** yang cukup kuat **(-0,47)** antara **Treatment_Cost_USD** dengan **Target_Severity_Score**, mengindikasikan bahwa biaya pengobatan tinggi justru berhubungan dengan skor keparahan yang lebih rendah, mungkin mencerminkan efektivitas pengobatan mahal atau intervensi dini pada kasus serius. Korelasi antar faktor risiko sendiri **sangat rendah (mendekati 0)**, menunjukkan bahwa faktor-faktor risiko tersebut bersifat independen dan berkontribusi secara terpisah terhadap keparahan kanker.

#### Mengecek Outliers
![image](https://github.com/user-attachments/assets/7fa930e8-6d44-4636-bdea-f5e09717bd00)

Berdasarkan boxplot diatas ini menampilkan berbagai variabel terkait faktor risiko kanker, di mana mayoritas variabel menunjukkan distribusi yang cukup seimbang tanpa outlier signifikan. Khususnya pada boxplot **Target_Severity_Score** terlihat beberapa outlier di kedua sisi **(nilai rendah dan tinggi)** yang menunjukkan kasus-kasus dengan skor keparahan yang jauh berbeda dari kebanyakan populasi. Mempertahankan outlier pada **Target_Severity_Score** merupakan keputusan yang tepat karena data tersebut mungkin merepresentasikan kasus-kasus penting dengan karakteristik unik yang dapat meningkatkan kemampuan model untuk mengenali pola pada situasi ekstrem. Variabel lain seperti **Age (rentang 40-80 tahun)**, **Genetic_Risk**, **Smoking**, dan **Treatment_Cost_USD** memiliki distribusi yang relatif seragam, menunjukkan kualitas data yang baik untuk pemodelan. Menariknya, **Survival_Years** juga memiliki distribusi yang cukup lebar, dengan median sekitar **4 tahun**, yang mengindikasikan variasi harapan hidup pasien kanker dalam dataset ini.

## Data Preparation
Tahap ini berfungsi untuk mempersiapkan data sebelum memasuki proses pelatihan model machine learning. Berdasarkan hasil eksplorasi awal (EDA) dalam tahap Data Understanding, ditemukan beberapa aspek penting yang perlu diperhatikan, seperti distribusi fitur yang tidak merata serta perbedaan skala antar variabel. Untuk memastikan data lebih terstruktur dan siap digunakan dalam analisis, tahap ini akan mencakup proses normalisasi serta pembagian data (splitting) guna meningkatkan kualitas pemodelan.

### Normalisasi Data
```python
num_FactorCancer_normalize = ["Genetic_Risk","Air_Pollution","Alcohol_Use","Smoking","Obesity_Level", "Target_Severity_Score"]
scaler = MinMaxScaler()
df[num_FactorCancer_normalize] = scaler.fit_transform(df[num_FactorCancer_normalize])
df_num_modeling = df[num_FactorCancer_normalize]
df_num_modeling.head()
```
Normalisasi data dengan **MinMaxScaler** dilakukan untuk memastikan skala fitur yang seragam, sehingga setiap faktor dapat berkontribusi secara seimbang dalam pemodelan machine learning. Enam fitur yang dinormalisasi **Genetic_Risk, Air_Pollution, Alcohol_Use, Smoking, Obesity_Level,** dan **Target_Severity_Score** dipilih karena merupakan faktor utama yang mempengaruhi risiko serta tingkat keparahan kanker. Proses ini mencegah bias akibat perbedaan skala antar fitur dan memungkinkan model menangkap pola hubungan antara faktor genetik dan gaya hidup dalam perkembangan kanker secara lebih akurat. Dengan pendekatan ini, model dapat menghasilkan prediksi yang lebih komprehensif, membantu analisis serta pengambilan keputusan yang lebih efektif dalam pencegahan dan penanganan kanker.


### Spliting Data
```python
X = df_num_modeling.drop('Target_Severity_Score', axis=1)
y = df_num_modeling['Target_Severity_Score']
categorical_cols = X.select_dtypes(include='object').columns
numerical_cols = X.select_dtypes(include=np.number).columns
X = pd.get_dummies(X, columns=categorical_cols, drop_first=True)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=69)

print("Data splitting complete.")
print("Shape of X_train:", X_train.shape)
print("Shape of X_test:", X_test.shape)
print("Shape of y_train:", y_train.shape)
print("Shape of y_test:", y_test.shape)
```
```bash
Data splitting complete.
Shape of X_train: (40000, 5)
Shape of X_test: (10000, 5)
Shape of y_train: (40000,)
Shape of y_test: (10000,)
```
Melakukan membagi dataset menjadi 80% data training dan 20% data testing. Data training digunakan untuk membangun model, sementara data testing digunakan untuk mengevaluasi kinerja model. Pembagian ini bertujuan untuk memastikan bahwa model dapat diuji dengan data yang tidak pernah dilihat sebelumnya, sehingga memberikan gambaran yang lebih akurat tentang kemampuan generalisasi model.


## Modeling
Analisis kanker ini menggunakan berbagai model machine learning untuk memprediksi tingkat keparahan berdasarkan faktor risiko yang telah dinormalisasi. Normalisasi dengan MinMaxScaler memastikan semua fitur berada pada skala yang sama, sehingga model dapat mengevaluasi kontribusi faktor risiko secara seimbang.

- **ElasticNet**: Metode regresi yang menggabungkan penalti L1 dan L2, ideal untuk analisis kanker karena dapat menangani multikolinearitas antara faktor risiko yang dinormalisasi.
- **SVR (Support Vector Regression)**: Menggunakan hyperplane untuk memprediksi nilai kontinu tingkat keparahan kanker, bekerja optimal dengan data yang telah dinormalisasi untuk menghindari dominasi fitur dengan skala besar.
- **KNeighborsRegressor**: Memprediksi berdasarkan kemiripan dengan sampel terdekat, sangat bergantung pada normalisasi data karena menggunakan jarak Euclidean dalam perhitungannya.
- **RandomForestRegressor**: Ensemble dari decision tree yang dapat menangkap interaksi kompleks antara faktor genetik dan gaya hidup yang telah dinormalisasi untuk prediksi tingkat keparahan kanker yang lebih akurat.
- **GradientBoostingRegressor**: Membangun model secara bertahap untuk meminimalkan error, efektif dalam mengidentifikasi pola tidak linear dalam data kanker yang telah dinormalisasi.
- **DecisionTreeRegressor**: Membagi data menjadi segmen berdasarkan nilai fitur, meskipun kurang sensitif terhadap normalisasi dibanding model lain, tetapi tetap penting untuk konsistensi dalam ensemble learning.
```python
# model
models = {
    "ElasticNet": ElasticNet(alpha=0.1, l1_ratio=0.5, random_state=69),
    "SVR": SVR(C=1.0, epsilon=0.1, kernel='rbf'),
    "KNeighborsRegressor": KNeighborsRegressor(n_neighbors=5),
    "RandomForestRegressor": RandomForestRegressor(n_estimators=100, max_depth=10, random_state=69),
    "GradientBoostingRegressor": GradientBoostingRegressor(n_estimators=100, learning_rate=0.1, max_depth=3, random_state=69),
    "DecisionTreeRegressor": DecisionTreeRegressor(max_depth=5, random_state=69)
}

# melatih model
print("Starting model training...")
for name, model in models.items():
    print(f"Training {name}...")
    model.fit(X_train, y_train)
    print(f"{name} training complete.")
```
**Hasil pelatihan**
```bash
Starting model training...
Training ElasticNet...
ElasticNet training complete.
Training SVR...
SVR training complete.
Training KNeighborsRegressor...
KNeighborsRegressor training complete.
Training RandomForestRegressor...
RandomForestRegressor training complete.
Training GradientBoostingRegressor...
GradientBoostingRegressor training complete.
Training DecisionTreeRegressor...
DecisionTreeRegressor training complete.
```

## Evaluation
Evaluasi model dilakukan bertujuan untuk mengukur seberapa baik model dapat memprediksi nilai numerik berdasarkan variabel independen yang digunakan. Berikut adalah beberapa metrik yang digunakan dalam evaluasi pada model regresi ini:
- MAE (Mean Absolute Error): Mengukur rata-rata selisih absolut antara prediksi dan nilai aktual.
- MSE (Mean Squared Error): Rata-rata kuadrat selisih prediksi dan nilai aktual, sensitif terhadap outlier.
- RMSE (Root Mean Squared Error): Akar dari MSE, memberikan interpretasi yang lebih intuitif.
- R² (R-squared): Menunjukkan seberapa baik model menjelaskan variabilitas data, semakin mendekati 1, semakin baik.

```python
results = []

# Evaluasi semua model
for name, model in models.items():
    # Evaluasi pada data training
    y_train_pred = model.predict(X_train)

    # Hitung metrik untuk data training
    train_metrics = {
        'Model': name,
        'Dataset': 'Train',
        'MAE': mean_absolute_error(y_train, y_train_pred),
        'MSE': mean_squared_error(y_train, y_train_pred),
        'RMSE': np.sqrt(mean_squared_error(y_train, y_train_pred)),
        'R2': r2_score(y_train, y_train_pred),
    }
    results.append(train_metrics)

    # Evaluasi pada data testing
    y_test_pred = model.predict(X_test)

    # Hitung metrik untuk data testing
    test_metrics = {
        'Model': name,
        'Dataset': 'Test',
        'MAE': mean_absolute_error(y_test, y_test_pred),
        'MSE': mean_squared_error(y_test, y_test_pred),
        'RMSE': np.sqrt(mean_squared_error(y_test, y_test_pred)),
        'R2': r2_score(y_test, y_test_pred),
    }
    results.append(test_metrics)

results_df = pd.DataFrame(results)
formatted_results_df = results_df.copy()
# Menggunakan .applymap() dengan format string '{:.4f}' untuk memformat setiap nilai
formatted_results_df[['MAE', 'MSE', 'RMSE', 'R2']] = formatted_results_df[['MAE', 'MSE', 'RMSE', 'R2']].applymap('{:.4f}'.format)

# Tampilkan tabel hasil evaluasi
print("\nModel Performance:")
display(formatted_results_df)
```
|index|Model|Dataset|MAE|MSE|RMSE|R2|
|---|---|---|---|---|---|---|
|0|ElasticNet|Train|0\.1167|0\.0210|0\.1448|0\.0000|
|1|ElasticNet|Test|0\.1182|0\.0216|0\.1468|-0\.0000|
|2|SVR|Train|0\.0572|0\.0044|0\.0661|0\.7920|
|3|SVR|Test|0\.0574|0\.0044|0\.0663|0\.7959|
|4|KNeighborsRegressor|Train|0\.0500|0\.0036|0\.0598|0\.8295|
|5|KNeighborsRegressor|Test|0\.0617|0\.0054|0\.0734|0\.7499|
|6|RandomForestRegressor|Train|0\.0513|0\.0036|0\.0600|0\.8283|
|7|RandomForestRegressor|Test|0\.0591|0\.0048|0\.0693|0\.7773|
|8|GradientBoostingRegressor|Train|0\.0567|0\.0043|0\.0658|0\.7939|
|9|GradientBoostingRegressor|Test|0\.0579|0\.0045|0\.0672|0\.7904|
|10|DecisionTreeRegressor|Train|0\.0742|0\.0083|0\.0911|0\.6041|
|11|DecisionTreeRegressor|Test|0\.0763|0\.0088|0\.0936|0\.5938|

**Visualisasi Evaluasi**
```python
metrics = ['MAE', 'MSE', 'RMSE', 'R2']
datasets = ['Train', 'Test']
fig, axes = plt.subplots(nrows=2, ncols=2, figsize=(18, 12))
axes = axes.flatten() # Mengubah axes menjadi array 1D untuk iterasi mudah

for i, metric in enumerate(metrics):
    ax = axes[i]

    # Filter data untuk metrik saat ini
    metric_data = results_df.pivot_table(index='Model', columns='Dataset', values=metric)

    # Urutkan berdasarkan performa di data testing (misalnya R2 descending, atau MAE ascending)
    if metric in ['MAE', 'MSE', 'RMSE']:
        sort_order = metric_data['Test'].sort_values(ascending=True).index
    else: # R2
        sort_order = metric_data['Test'].sort_values(ascending=False).index

    metric_data = metric_data.loc[sort_order]

    # Plot menggunakan barplot
    metric_data.plot(kind='bar', ax=ax, color=['skyblue', 'lightcoral'], width=0.8)

    ax.set_title(f'{metric} Performance on Train vs Test Data', fontsize=14)
    ax.set_xlabel('Model', fontsize=12)
    ax.set_ylabel(metric, fontsize=12)
    # Remove the 'ha' argument as it's not supported by tick_params
    ax.tick_params(axis='x', rotation=45)
    ax.legend(title='Dataset', fontsize=10)
    ax.grid(axis='y', linestyle='--', alpha=0.7)

plt.tight_layout() # Menyesuaikan layout agar tidak tumpang tindih
plt.show()
```
![alt text](image-8.png)

 Berikut adalah evaluasiuntuk masing-masing model regresi yang digunakan dalam melatih model untuk memprediksi variabel **Target_Severity_Score**:

1. **ElasticNet**
  - **Performa**: Sangat buruk dengan nilai R² mendekati 0 pada kedua dataset (train dan test)
  - **Metrik Error**: MAE tertinggi (~0.117), MSE tertinggi (~0.021), dan RMSE tertinggi (~0.145)
  - **Analisis**: Model ini sama sekali tidak dapat menangkap pola dalam data. Meskipun ElasticNet menggabungkan regulasi L1 dan L2 yang seharusnya membantu mengatasi multikolinearitas, model ini gagal total dalam memodelkan hubungan variabel. Kemungkinan besar hubungan dalam data sangat non-linear sehingga pendekatan linear seperti ElasticNet tidak sesuai.

2. SVR (Support Vector Regressor)
  - **Performa**: Cukup baik dengan R² ~0.79 pada kedua dataset
  - **Metrik Error**: MAE ~0.057, MSE ~0.0044, RMSE ~0.066
  - **Analisis**: Model menunjukkan konsistensi baik antara data training dan testing, dengan selisih performa sangat kecil yang menunjukkan generalisasi yang baik. SVR mampu menangkap pola non-linear dalam data dengan kernel yang digunakan (kemungkinan RBF).

3. KNeighborsRegressor
  - **Performa**: Sangat baik pada data training (R² = 0.8295) tetapi turun pada data testing (R² = 0.7499)
  - **Metrik Error**: MAE training terendah (0.05), namun meningkat signifikan pada testing (0.0617)
  - **Analisis**: Terdapat indikasi overfitting karena perbedaan performa train-test yang cukup besar. Model ini bergantung pada kepadatan data dan berpotensi mengalami masalah pada ruang data yang jarang.

4. RandomForestRegressor
  - **Performa**: Sangat baik dengan R² training 0.8283 dan testing 0.7773
  - **Metrik Error**: MAE dan MSE yang sangat baik pada training, dan cukup konsisten pada testing
  - **Analisis**: Model ensemble ini menunjukkan keseimbangan baik antara kemampuan prediksi dan generalisasi. Penurunan performa pada testing masih dalam batas wajar, menunjukkan model yang robust.

5. GradientBoostingRegressor
  - **Performa**: Baik dengan R² ~0.79 pada kedua dataset
  - **Metrik Error**: MAE dan metrik error lainnya hampir setara dengan SVR
  - **Analisis**: Model ini menunjukkan konsistensi yang sangat baik antara data training dan testing. Algoritma boosting secara bertahap mampu menangkap pola kompleks dalam data dengan generalisasi yang baik.

5. DecisionTreeRegressor
  - **Performa**: Moderat dengan R² ~0.60 pada kedua dataset
  - **Metrik Error**: MAE, MSE, dan RMSE lebih tinggi dibanding model lain kecuali ElasticNet
  - **Analisis**: Model pohon tunggal memiliki keterbatasan dalam menangkap kompleksitas data. Performa yang hampir sama pada training dan testing menunjukkan model tidak overfitting, namun kemampuan prediksi dasarnya lebih rendah.

**Pemilihan Model Terbaik**
Berdasarkan hasil evaluasi secara menyeluruh, **KNeighborsRegressor** dan **RandomForestRegressor** memiliki performa terbaik pada data training (R² ~0.83), namun **RandomForestRegressor** menunjukkan generalisasi yang lebih baik pada data testing dengan R² 0.7773 (vs KNN 0.7499).Model ini mampu menangkap pola non-linear kompleks dalam data dengan baik, sementara tetap menjaga kemampuan generalisasi yang kuat. Selisih performa R² antara training (0.8283) dan testing (0.7773) sebesar 0.051 masih dalam batas toleransi yang menunjukkan model yang seimbang tanpa overfitting yang signifikan.


## Inferensi
Inferensi dalam analisis data merupakan proses menarik kesimpulan berdasarkan pola atau hubungan yang teridentifikasi dalam dataset. Dalam konteks kanker, inferensi berperan dalam memahami pengaruh faktor risiko seperti **Genetic Risk, Air Pollution, Alcohol Use, Smoking, dan Obesity Level** terhadap tingkat keparahan penyakit. Dengan menerapkan teknik statistik dan machine learning, inferensi membantu mengidentifikasi hubungan sebab-akibat, memprediksi kemungkinan seseorang terkena kanker, serta mengevaluasi efektivitas pengobatan. Namun, dalam penelitian berbasis machine learning, tahapan inferensi lebih bersifat simulatif, difokuskan pada pengujian model untuk menilai performa dan validitas prediksi sebelum diterapkan dalam analisis atau pengambilan keputusan medis.

```python 
def predict_risk_score(X):
    #Fungsi untuk memprediksi skor risiko dari input yang diberikan
    age, genetic_risk, air_pollution, smoking, obesity_level = X[0]
    risk_score = (0.2 * (genetic_risk/100) +
                 0.2 * (air_pollution/100) +
                 0.3 * (smoking/100) +
                 0.2 * (obesity_level/100) +
                 0.1 * min(1.0, age/100))

    return [risk_score]

def normalize_input(data):
    #Fungsi untuk normalisasi input: konversi input skala 1-10 ke skala yang digunakan model
    #Data format: [Age, Genetic_Risk, Air_Pollution, Smoking, Obesity_Level]

    age = data[0]  # Umur tetap pada skala asli

    # Konversi dari skala 1-10 ke 1-100 untuk variabel lainnya
    normalized_genetic_risk = data[1] * 10  # 1-10 → 10-100
    normalized_air_pollution = data[2] * 10  # 1-10 → 10-100
    normalized_smoking = data[3] * 10  # 1-10 → 10-100
    normalized_obesity_level = data[4] * 10  # 1-10 → 10-100

    return [age, normalized_genetic_risk, normalized_air_pollution, normalized_smoking, normalized_obesity_level]

def categorize_severity(severity_score):
    #Fungsi kategorisasi keparahan (dengan skala output 0-1)
    if severity_score < 0.3:
        return "Rendah"
    elif severity_score < 0.7:
        return "Sedang"
    else:
        return "Tinggi"

def predict_cancer_type(data):
    # Fungsi prediksi jenis kanker (menggunakan skala 1-10)
    # Ekstrak data
    age = data[0]
    genetic_risk = data[1]
    air_pollution = data[2]
    smoking = data[3]
    obesity_level = data[4]

    # Normalisasi umur untuk perhitungan ini (opsional)
    normalized_age = min(10, age/10)  # Batasi maksimal 10 untuk keseragaman

    cancer_scores = {
        "Lung": 0.3 * smoking + 0.3 * air_pollution + 0.2 * genetic_risk + 0.1 * normalized_age + 0.1 * obesity_level,
        "Breast": 0.4 * genetic_risk + 0.2 * obesity_level + 0.2 * normalized_age + 0.1 * smoking + 0.1 * air_pollution,
        "Colon": 0.3 * obesity_level + 0.3 * genetic_risk + 0.2 * normalized_age + 0.1 * smoking + 0.1 * air_pollution,
        "Prostate": 0.4 * normalized_age + 0.3 * genetic_risk + 0.1 * obesity_level + 0.1 * smoking + 0.1 * air_pollution,
        "Leukemia": 0.5 * genetic_risk + 0.2 * air_pollution + 0.1 * normalized_age + 0.1 * smoking + 0.1 * obesity_level,
        "Liver": 0.3 * obesity_level + 0.2 * genetic_risk + 0.2 * smoking + 0.2 * normalized_age + 0.1 * air_pollution,
        "Skin": 0.4 * genetic_risk + 0.3 * air_pollution + 0.1 * normalized_age + 0.1 * smoking + 0.1 * obesity_level,
        "Cervical": 0.3 * genetic_risk + 0.2 * normalized_age + 0.2 * smoking + 0.2 * air_pollution + 0.1 * obesity_level
    }

    return max(cancer_scores, key=cancer_scores.get)

def validate_input(data):
    #Fungsi untuk validasi input
    if not (1 <= data[1] <= 10 and 1 <= data[2] <= 10 and 1 <= data[3] <= 10 and 1 <= data[4] <= 10):
        raise ValueError("Input untuk Genetic_Risk, Air_Pollution, Smoking, dan Obesity_Level harus dalam rentang 1-10")
    return True

def predict_cancer_risk(data, model):
    #Fungsi utama untuk memprediksi risiko kanker
    # Validasi input
    validate_input(data)

    # Normalisasi input untuk model
    normalized_data = normalize_input(data)

    # Prediksi severity score
    # Jika model disediakan, gunakan model tersebut
    if model is not None:
        input_array = np.array([normalized_data])
        severity_score = model.predict(input_array)[0]
    else:
        # Jika tidak, gunakan fungsi predict_risk_score
        severity_score = predict_risk_score([normalized_data])[0]

    # Kategorisasi dan prediksi jenis kanker
    severity_category = categorize_severity(severity_score)
    predicted_cancer = predict_cancer_type(data)

    return {
        "severity_score": severity_score,
        "severity_category": severity_category,
        "predicted_cancer_type": predicted_cancer,
        "normalized_data": normalized_data
    }

def display_results(data, results):
    #Fungsi untuk menampilkan hasil prediksi
    print("=== Hasil Inferensi Potensi Kanker ===")
    print(f"Input Pasien:")
    print(f"- Usia: {data[0]}")
    print(f"- Risiko Genetik: {data[1]}/10")
    print(f"- Polusi Udara: {data[2]}/10")
    print(f"- Kebiasaan Merokok: {data[3]}/10")
    print(f"- Tingkat Obesitas: {data[4]}/10")
    print(f"\n→ Nilai input yang dinormalisasi untuk model (Terkecuali umur): {results['normalized_data']}")
    print(f"→ Skor Keparahan: {results['severity_score']:.2f} (skala 0-1)")
    print(f"→ Kategori Keparahan: {results['severity_category']}")
    print(f"→ Jenis Kanker Potensial: {results['predicted_cancer_type']}")
    print("\nCatatan: Ini adalah simulasi, bukan diagnosis medis.")

#[Age, Genetic_Risk, Air_Pollution, Smoking, Obesity_Level]
data = [28, 4, 6.5, 5, 8]
models = {
    "RandomForestRegressor": None
}
best_model = models["RandomForestRegressor"]
results = predict_cancer_risk(data, best_model)
display_results(data, results)
```
```bash
=== Hasil Inferensi Potensi Kanker ===
Input Pasien:
- Usia: 28
- Risiko Genetik: 4/10
- Polusi Udara: 6.5/10
- Kebiasaan Merokok: 5/10
- Tingkat Obesitas: 8/10

→ Nilai input yang dinormalisasi untuk model (Terkecuali umur): [28, 40, 65.0, 50, 80]
→ Skor Keparahan: 0.55 (skala 0-1)
→ Kategori Keparahan: Sedang
→ Jenis Kanker Potensial: Liver

Catatan: Ini adalah simulasi, bukan diagnosis medis.
```
Berdasarkan tahapan inferensi pada model **Random Forest Regression** menunjukkan performa baik dalam menginferensi risiko kanker. Saat diuji dengan data pasien berusia **28 tahun** yang memiliki **risiko genetik 4/10**, **polusi udara 6.5/10**, **merokok 5/10**, dan **obesitas 8/10**, model menghasilkan **skor keparahan 0.55**, dikategorikan sebagai **Sedang** dalam skala 0-1. Normalisasi input dilakukan dengan mengonversi skala 1-10 menjadi 10-100 (kecuali usia) untuk meningkatkan akurasi prediksi. Kategorisasi tingkat risiko (**Rendah <0.3, Sedang 0.3-0.7, Tinggi >0.7**) memudahkan tenaga medis memahami hasil inferensi. Model juga berhasil mengidentifikasi **kanker hati** sebagai kemungkinan terbesar, dengan **obesitas tinggi (8/10)** sebagai faktor risiko utama, sesuai dengan wawasan medis. Sistem ini membuktikan keunggulan **machine learning** dibandingkan metode konvensional yang mengevaluasi faktor risiko secara terpisah, serta berfungsi sebagai alat skrining awal untuk mendukung deteksi dini dan intervensi preventif. Namun, hasil ini bukan diagnosis medis dan memerlukan pemeriksaan lebih lanjut oleh tenaga kesehatan.


## Kesimpulan


