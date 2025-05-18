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





## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

## Evaluation
Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.

