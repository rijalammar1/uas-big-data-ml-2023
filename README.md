<div align="center">

# Set Up


</div>
<img src = 'https://github.com/rijalammar1/uas-big-data-ml-2023/assets/75898886/8fa74c54-dc26-41b4-a6bd-935811bee67c' width=70% height=70%>
 
 ```sh
  Code ini berfungsi unutk mengkoneksikan google colab dengan drive kita
  ```

<img src = 'https://github.com/rijalammar1/uas-big-data-ml-2023/assets/75898886/abb70dd1-1ffb-4e62-8a22-9bc05bd7d410' width=70% height=70%>

```sh
  Code ini berfungsi unutk menginstall pysprak di dalam google colab
  ```

<img src = 'https://github.com/rijalammar1/uas-big-data-ml-2023/assets/75898886/b19aa74e-c69c-408f-9fe8-6c318843caa4' width=70% height=70%>

```sh
  Code ini berfungsi unutk menginstall library Geopandas
  ```

<img src = 'https://github.com/rijalammar1/uas-big-data-ml-2023/assets/75898886/244453ef-9e25-4de2-ab74-16a371c579c8' width=70% height=70%>

```sh
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

<div align="center">

# Hasil Visualisasi


</div>

<img src = 'https://github.com/rijalammar1/uas-big-data-ml-2023/assets/75898886/f665ca21-4a24-4739-80ae-a10f99cc8485' width=70% height=70%>

<div align="center">

# Hasil Visualisasi

Irba Adika Jaya

Rijal Ammar Irsyadul Ibad

</div>
