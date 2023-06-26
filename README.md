<div align="center">

# Set Up


</div>
<img src = 'https://github.com/rijalammar1/uas-big-data-ml-2023/assets/75898886/8fa74c54-dc26-41b4-a6bd-935811bee67c' width=70% height=70%>
 
 ```sh
 Yang pertamna memasukan code yang berfungsi unutk mengkoneksikan google colab dengan drive kita
  ```

<img src = 'https://github.com/rijalammar1/uas-big-data-ml-2023/assets/75898886/abb70dd1-1ffb-4e62-8a22-9bc05bd7d410' width=70% height=70%>

```sh
 kemudian menabahkan code ini yang berfungsi unutk menginstall pysprak di dalam google colab
  ```

<img src = 'https://github.com/rijalammar1/uas-big-data-ml-2023/assets/75898886/b19aa74e-c69c-408f-9fe8-6c318843caa4' width=70% height=70%>

```sh
  Setelah itu memasukan code ini yang berfungsi unutk menginstall library Geopandas
  ```

<img src = 'https://github.com/rijalammar1/uas-big-data-ml-2023/assets/75898886/244453ef-9e25-4de2-ab74-16a371c579c8' width=70% height=70%>

```sh
  Setelah itu melakukan import untuk kebutuhan mengolah data dan menvisulaisai data menjadi cart
  - from pyspark.sql import SparkSession: Ini mengimpor kelas SparkSession yang diperlukan untuk memulai sesi Spark. SparkSession adalah titik masuk utama untuk berinteraksi dengan data dalam Spark.
  - from pyspark.ml.feature import VectorAssembler: Ini mengimpor kelas VectorAssembler yang digunakan untuk menggabungkan beberapa kolom fitur menjadi satu kolom vektor fitur. Ini diperlukan dalam proses pemodelan regresi.
  - from pyspark.ml.regression import LinearRegression: Ini mengimpor kelas LinearRegression yang digunakan untuk membangun model regresi linear.
  - from pyspark.ml.evaluation import RegressionEvaluator: Ini mengimpor kelas RegressionEvaluator yang digunakan untuk mengevaluasi kinerja model regresi.
  - from pyspark.sql.functions import max: Ini mengimpor fungsi max dari modul pyspark.sql.functions. Fungsi ini digunakan untuk menghitung nilai maksimum dalam suatu kolom.
  - import matplotlib.pyplot as plt: Ini mengimpor modul matplotlib.pyplot yang digunakan untuk membuat visualisasi grafik.
  - import geopandas as gpd: Ini mengimpor pustaka geopandas yang digunakan untuk memanipulasi, analisis, dan visualisasi data geografis.
  - from mpl_toolkits.axes_grid1 import make_axes_locatable: Ini mengimpor fungsi make_axes_locatable dari modul mpl_toolkits.axes_grid1. Fungsi ini digunakan untuk membuat objek pembagi pada sumbu yang akan digunakan dalam visualisasi.
  ```

<img src = 'https://github.com/rijalammar1/uas-big-data-ml-2023/assets/75898886/c91279dc-1acd-43c4-be06-76ead10e830f' width=70% height=70%>

```sh
  untuk membuat atau mendapatkan sesi Spark dengan nama aplikasi "MalnutritionAnalysis". SparkSession adalah titik masuk utama untuk berinteraksi dengan data dalam Spark.
  ```

<img src = 'https://github.com/rijalammar1/uas-big-data-ml-2023/assets/75898886/7d8e02eb-8493-4536-9d81-2f1cd5c69837' width=70% height=70%>

```sh
  Code ini untuk membaca file .cvs yang sudah kita upload didalam google drive
  ```

<img src = 'https://github.com/rijalammar1/uas-big-data-ml-2023/assets/75898886/80dfdfe9-3d73-494f-af8d-8bd1aea8a4a1' width=70% height=70%>

```sh
  Code ini berfungsi untuk menselect data yang akan dipakai kemudian merename nama tabel setelah itu menggabungkan data indicator,sex,time period, dan obs value unutk mencari negara mana yang memiliki malnutrisi paling tinggi setelah medapatkannya kemudian data dijadikan bar cart
  ```

<img src = 'https://github.com/rijalammar1/uas-big-data-ml-2023/assets/75898886/3ed904ea-39c3-410c-8b3e-1623408972f5' width=70% height=70%>

```sh
  - Kode pertama memilih kolom-kolom yang akan diproses dari dataset data. Kolom yang dipilih adalah "TIME_PERIOD", "Country", "Sex", "Indicator", dan "OBS_VALUE". Nama kolom-kolom ini kemudian diubah menggunakan fungsi withColumnRenamed.
  - Pada tahap ini, data yang memiliki nilai kosong (null) pada kolom "obs_value" atau memiliki nilai negatif dihapus dari data_new. Hal ini dilakukan dengan menggunakan fungsi filter dan operator logika & (AND).
  - Kolom "time_period" pada data_new dikonversi menjadi tipe data integer menggunakan fungsi withColumn dan cast.
  - max_obs dan data_new digabungkan berdasarkan kolom "indicator", "country", dan "max_obs_value". Ini dilakukan dengan menggunakan fungsi join pada kondisi yang diberikan. Hanya kolom-kolom yang relevan dipilih dalam hasil gabungan menggunakan fungsi select.
  - Kolom-kolom yang akan digunakan sebagai fitur dalam model regresi linier dipilih sebagai input menggunakan VectorAssembler. Input kolom-kolom ini diubah menjadi vektor tunggal dalam kolom baru yang disebut "features".
  - Data yang telah diubah menggunakan VectorAssembler dibagi menjadi data pelatihan (trainingData) dan data pengujian (testData) dalam proporsi 80:20 menggunakan fungsi randomSplit.
  - Model regresi linier dibuat dengan menggunakan LinearRegression dari Spark MLlib. Fitur yang telah dihasilkan dari VectorAssembler dijadikan fitur (featuresCol) dan kolom "max_obs_value" dijadikan label (labelCol) dalam model.
  - Model yang telah dilatih digunakan untuk membuat prediksi pada data pengujian. Hasil prediksi dan nilai aktual ("max_obs_value") diekstrak dari dataframe predictions dan dikonversi menjadi daftar Python menggunakan toPandas(). Nilai prediksi dan aktual ini digunakan untuk membuat scatter plot.
  ```

<img src = 'https://github.com/rijalammar1/uas-big-data-ml-2023/assets/75898886/9b7677a4-ae66-4535-aac6-198eea0fa1a0' width=70% height=70%>

```sh
  - Kode pertama memilih kolom-kolom yang akan diproses dari dataset data. Kolom yang dipilih adalah "TIME_PERIOD", "Country", "Sex", "Indicator", dan "OBS_VALUE". Nama kolom-kolom ini kemudian diubah menggunakan fungsi withColumnRenamed.
  - Pada tahap ini, data yang memiliki nilai kosong (null) pada kolom "obs_value" atau memiliki nilai negatif dihapus dari data_new. Hal ini dilakukan dengan menggunakan fungsi filter dan operator logika & (AND).
  - data_new dikelompokkan berdasarkan kolom "country" dan "indicator", dan nilai maksimum dari kolom "obs_value" dihitung menggunakan fungsi groupBy dan agg. Hasilnya disimpan dalam variabel max_obs.
  - max_obs dan data_new digabungkan berdasarkan kolom "indicator", "country", dan "max_obs_value". Ini dilakukan dengan menggunakan fungsi join pada kondisi yang diberikan. Hanya kolom-kolom yang relevan dipilih dalam hasil gabungan menggunakan fungsi select.
  - Kolom-kolom yang akan digunakan sebagai fitur dalam model regresi linier dipilih sebagai input menggunakan VectorAssembler. Input kolom-kolom ini diubah menjadi vektor tunggal dalam kolom baru yang disebut "features".
  - Data yang telah diubah menggunakan VectorAssembler dibagi menjadi data pelatihan (trainingData) dan data pengujian (testData) dalam proporsi 80:20 menggunakan fungsi randomSplit.
  - Model regresi linier dibuat dengan menggunakan LinearRegression dari Spark MLlib. Fitur yang telah dihasilkan dari VectorAssembler dijadikan fitur (featuresCol) dan kolom "max_obs_value" dijadikan label (labelCol) dalam model.
  - Model yang telah dilatih digunakan untuk membuat prediksi pada data pengujian. Hasil prediksi dievaluasi menggunakan RegressionEvaluator dengan membandingkan nilai prediksi dengan nilai aktual ("max_obs_value"). Metrik evaluasi yang digunakan adalah root mean squared error (RMSE). Hasil prediksi dan nilai aktual disimpan dalam dataframe predictions.
  - Dataset geospasial "naturalearth_lowres" diunduh menggunakan gpd.datasets.get_path. Dataset ini digunakan untuk membuat peta dunia. Dataframe predictions digabungkan dengan dataset geospasial berdasarkan kolom "country" dan "name" menggunakan fungsi merge. Hal ini memungkinkan penggabungan prediksi nilai malnutrisi dengan data geospasial untuk menghasilkan visualisasi pada peta dunia.
  - Kolom "prediction" dalam dataframe merged_data diisi dengan nilai 0 untuk negara-negara yang tidak memiliki prediksi. Hal ini dilakukan dengan menggunakan metode fillna pada kolom tersebut.
  - Pengaturan plot dilakukan menggunakan matplotlib. Ukuran plot disesuaikan dengan menggunakan fig, ax = plt.subplots(figsize=(12, 8)). Pembagian warna pada peta menggunakan skala "coolwarm" dan kolom "prediction" dari merged_data sebagai nilai yang digunakan dalam peta. Legend dan colorbar ditambahkan menggunakan legend=True dan cax=cax. Judul plot ditambahkan dengan ax.set_title dan sumbu x dan y dihilangkan dengan ax.axis("off"). Akhirnya, plot ditampilkan menggunakan plt.show().
  ```

<div align="center">

# Flowchart


</div>


<img src = 'https://github.com/rijalammar1/uas-big-data-ml-2023/assets/75898886/8604cd5a-d4eb-4bfc-a2c2-9bf56155f5a7' width=60% height=60%>

```sh
 Flowchart Pre-processing
  ```



<img src = 'https://github.com/rijalammar1/uas-big-data-ml-2023/assets/75898886/0f4859d1-3127-4673-a587-72fa01841475' width=60% height=60%>


```sh
 Flowchart Processing
  ```




<div align="center">

# Hasil Visualisasi


</div>

<img src = 'https://github.com/rijalammar1/uas-big-data-ml-2023/assets/75898886/f665ca21-4a24-4739-80ae-a10f99cc8485' width=65% height=65%>

<img src = 'https://github.com/rijalammar1/uas-big-data-ml-2023/assets/75898886/6876ab1a-e182-42cc-95a1-394a19ded5cc' width=65% height=65%>

<img src = 'https://github.com/rijalammar1/uas-big-data-ml-2023/assets/75898886/ec1047cd-0033-425d-a6f2-cf636f5ef40e' width=65% height=65%>

<div align="center">

# Kelompok

Irba Adika Jaya

Rijal Ammar Irsyadul Ibad

</div>
