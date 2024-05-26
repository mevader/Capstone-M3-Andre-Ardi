# Capstone-M3-Andre-Ardi

# **A. BUSINESS UNDERSTANDING DAN PERUMUSAN MASALAH**

Customer Lifetime Values (CLV), dikutip dari crazyegg, secara sederhana dapat didefinisikan sebagai jumlah uang yang dikeluarkan oleh customer untuk bisnis tertentu sepanjang hubungannya dengan bisnis tersebut. CLV tidak hanya penting untuk menunjukkan jumlah uang yag dikeluarkan oleh customer terhadap sebuah bisnis, namun juga menunjukkan future value dari customer tersebut bila dapat terus dipertahankan (retain) oleh sebuah bisnis.

CLV merupakan angka penting bagi perusahaan karena menyiratkan besaran pertumbuhan sebuah perusahaan yang berbasis kepada customer. Selain itu ia juga akan memperlihatkan arti penting dan cara mempertahankan pelanggan lama di samping fitur-fitur penting dalam mendapatkan pelanggan baru.

Menurut Qualtrix, angka CLV dapat diperoleh dari formula dasar: 

        CLV = (customer revenue per year * duration of relationship in years) - total cost of acquiring and serving the customer

Dengan demikian dapat dikatakan bahwa semakin tinggi angka CLV maka akan semakin baik nilai customer tersebut bagi bisnis kita.

Dalam kasus ini, perusahaan 'Purwa Insurance' adalah sebuah perusahaan asuransi yang  dibidang otomotif. Perusahaan ini membutuhkan sebuah model yang dapat memprediksi cara meningkatkan besaran angka CLV-nya. 

Untuk itu disusunlah perumusan masalah bagi model machine learning  yang akan dibuat:

**B.1 Problem:**

Perusahaan Purwa Insurance ingin memiliki model prediksi guna meningkatkan angka Customer Lifetime Value-nya. Hal ini akan membuat upaya perusahaan akan lebih efisien dan efektif dalam mendapatkan (acquitition) dan merawat (retention) customer.

Untuk itu model machine learning diperlukan guna menentukan fitur-fitur penting apa yang diperlukan dalam asesmen customer berdasarkan Customer Lifetime Value-nya.

Degan demikian problem statementnya adalah: Bagaimana model machine learning yang dapat meningkatkan Customer Lifetime Value Purwa Insurance?

**B.2 Data:**

Model machine learning akan memprediksi 'Customer Lifetime Values' sebagai target (variabel y).

Sementara feature-feature (variabel X) yang akan digunakan untuk memprediksi adalah:

- Vehicle Class

- Coverage

- Renew Offer Type

- Employment Status

- Marital Status

- Education

- Number of Policies

- Monthly Premium Auto

- Total Claim Amount

- Income


**B.3 Machine Learning Objectives:**

Menemukan model machine learning yang dapat memprediksi  peningkatan customer lifetime value Purwa Insurance.

Karena target merupakan data yang bersifat numerikal, maka ada empat model yang akan diuji di sini:

1. Lasso regression

1. Decision Tree Regression

1. KNN Regression

1. Model ensemble: Extreme Gradient Boost


**B.4 Action:**

Perusahaan akan berfokus model dan fitur-fitur yang diprediksi memiliki dampak signifikan dalam peningkatan customer lifetime value, terutama terkait dengan customer acquitition dan retention.


**B.5 Value:**

Pada akhirnya diharapkan bahwa peningkatan CLV akan meningkatkan profit perusahaan ke depan. 

## G.1 Kesimpulan

- Pada tahapan benchmarking Model,guna mendapatkan model yang paling akurat dalam prediksi Customer Lifetime Value Purwa Insurance maka dibandingkanlah empat model machine learning yang berbasis regresi, yaitu:
    - Lasso Regression
    - KNN Regression
    - Decision Tree Regression 
    - XGBoost

- Hasil perhitungan mean dan standar deviasi cross validasi di antara keempatnya menunjukkan bahwa XGBoost memiliki tingkat error lebih rendah serta tingkat stabilitas yang lebih tinggi secara signifikan dibandingkan dengan model yang lain.

- Secara umum XGBoosting memang cenderung memiliki keunggulan performa dibandingkan dengan model-model yang lain.

- Selanjutnya pada tahapan evaluasi model untuk menguji train set dan test set serta membandingkannya di saat sebelum dan setelah hyperparameter tuning,hasilnya adalah:
    
    - Pada train set terjadi peningkatan performa (dari -429.35 ke -326.16) dengan menggunakan Mean Absolut Error (MAE) (penggunaan scoring negatif mean absolut error memiliki arti pembacaan MAE menjadi terbalik)

    - Pada test set terjadi peningkatan performa juga melalui pembacaan angka MAE yaitu (dari 412.29 menjadi 347.88)

- Pada pembacaan fitur-fitur yang penting (feature importance) pada model XGBoost menunjukkan bahwa jumlah polis (Number of Policy) dan dan besaran pembayaran premi bulanan (Monthly Premium Auto) memiliki nilai importance yang jauh melebihi fitur-fitur yang lain. Pembacaan ini sinkron dengan hasil matrik korelasi pada analisi EDA yang menghubungkan fitur-fitur dengan target (fitur Customer Lifetime Value)

- Sedangkan nilai yang dianggap paling tidak penting dalam model adalah nasabah yang memiliki mobil mewah. Baik sedan maupun SUV mewah memiliki nilai feature importance nol.

- Pola scaterplot residual menunjukkan sedikit kecenderungan ketika nilai prediksi semakin besar maka error-nya pun semakin besar, terutama pada nilai di atas 8000. Meskipun demikian perubahan pola ini terlihat tidak terlalu parah. 

- Secara keseluruhan scatter plot masih menunjukkan konsistensi linear yang dapat terlihat. Hal ini memperlihatkan bahwa tingkat akurasi prediksi pada model masih dapat diandalkan.

## G.2 Rekomendasi 

- Dengan menggunakan model XGBoost ini, perusahaan dapat menggunakan berbagai simulasi guna meningkatkan efektifitas dan efisiensi dari strategi perusahaan untuk meningkatkan Customer Lifetime Value-nya.

- Perusahaan harus fokus kepada fitur-fitur yang paling penting sebagaimana yang ditunjukkan oleh model. 

- Berdasarkan model dan analisis data analisis ada beberapa action yang dapat dilakukan perfitur untuk meningkatkan Customer Lifetime Value:

    1. Jumlah polis nasabah: mengingat secara korelasi terhadap CLV dan feature importance  menempati posisi teratas, maka perusahaan harus meletakkan fokus utamanya kepada fitur ini. Perusahaan harus fokus kepada dua hal: marketing polis baru dan maintaining kepada nasabah lama. Harus diingat bahwa nasabah lama penting loyalitas mereka akan bermakna belanja yang lebih besar terhadap perusahaan dan cost perusahaan yang lebih Kecil dibandingkan dengan marketing kepada nasabah baru. Di samping itu guna meningkatkan engagement terhadap nasabah sekaligus lama perusahaan dapat melakukan program referal yaitu menggunakan nasabah lama untuk mendapatkan nasabah baru dengan memberikan imbal hasil berupa referal fee.

    1. Premi bulanan nasabah: fitur ini menduduki posisi kedua baik dalam korelasi maupun feature importance. Fokus dari action kepada fitur ini adalah maintaining nasabah lama. Dalam hal ini nasabah lama harus lebih banyak didengar dan didekati secara aktif melalui berbagai program yang interaktif. Peningkatan kinerja customer service dan sistem reward bagi para nasabah lama akan lebih meningkatkan loyalitas mereka.

    1. Special treatment dan program kepada nasabah lama dengan membagi segmen mereka berdasarkan fitur-fitur yang berkontribusi signifikan, yaitu:
        - Nasabah yang bekerja
        - Nasabah yang menikah
        - Nasabah yang single
        - Nasabah dengan mobil dua pintu dan mobil keluarga yang mengindikasi kuatnya konstribusi segmen kelas menengah
        - Income Nasabah
        - Tingkat pendidikan nasabah

    1. Nasabah yang pensiun dan nasabah tidak bekerja menurut model juga memiliki konstribusi signifikan. Secara logis hal ini terjadi bila nasabah kehilangan penghasilan maka akan berkontribusi terhadap penurunan CLV.  Untuk itu harus ada program penyelamat yang akan menghindari segmen nasabah ini terputus. Misalnya dengan menawarkan program yang lebih ringan preminya atau yang lainnya.
    
    1. Ada beberapa fitur yang menurut model kurang penting terhadap model yaitu yang terkait dengan segmen kelas atas (ditunjukkan dengan fitur mobil mewah yang dianggap model tidak berkontribusi). Untuk meningkatkan kontribusi mereka, maka perusahaan harus mengembangkan program-progam atau polis-polis khusus bagi segmen kelas ini. Tentunya dengan benefit dan prestise yang menyentuh bagi mereka.

    1. Adapun rekomendasi untuk pengembangan model machine learning yang terkait CLV persahaan dapat dilakukan dengan:
        - Uji coba dengan model machine learning lainnya yang mungkin dapat memberikan nilai prediksi lebih baik
        - Uji coba lebih lanjut dengan hyperparameter tunning  lainnya 
        - Penambahan fitur-fitur baru namun dengan tetap mewaspadai over fitting
