# Automated Scoring System With ALS Pyspark

This notebook implements an automated scoring system using PySpark. Initially, various PySpark libraries such as `SparkSession`, `functions`, and `ml` components are imported to facilitate data manipulation, transformations, and the creation of machine learning pipelines. A Spark session is then created with the application name "task automated scoring system," which is used to load and process the data.

The dataset, stored in a CSV file, is loaded using `spark.read.csv()` and displayed using `df.show()`. It contains columns such as `npm`, `nama_peserta`, `jawaban`, `soal`, and `skor_per_soal`. The dataset is filtered to retain only relevant columns (`npm`, `jawaban`, `soal`, and `skor_per_soal`), and a new column, `HashValue`, is created by hashing the `jawaban` column to generate unique identifiers for each response.

The dataset is then split into training and testing sets using the `randomSplit()` method, with an 80% allocation for training and 20% for testing. The target variable, `skor_per_soal`, is renamed as `label` in the training data and `trueLabel` in the testing data. The number of rows in each dataset is printed to verify the distribution.

The model's performance is evaluated using key metrics. The results indicate excellent predictive accuracy, with a Root Mean Square Error (RMSE) of 4.167 × 10⁻⁵, a Mean Absolute Error (MAE) of 3.977 × 10⁻⁵, and an R-squared (R²) value of 0.9999999999818238, demonstrating near-perfect fit and minimal error. This highlights the effectiveness of the system in scoring responses based on the prepared data.
