# IBM
IBM data-science capstone project, Coursera course

I am going to predict Wine Quality by using Watson Machine Learning.
I selected this example from IBM Call for code challenge:
https://developer.ibm.com/patterns/create-and-deploy-a-scoring-model-to-
predict-heartrate-failure/. This example will follow me on how to create
correct repository and how to deploy application to IBM Watson studio.
This example has all the steps described on how I am going to deploy my
own application I have created specifically for Capstone project

Red Wine Quality dataset was selected as datasource for this task.
https://www.kaggle.com/maitree/wine-quality-selection
This datasource was taken from Kaggle and I would like to say that it is
well organized and all fields are without null and na values so minimum
work is needed on ETL step. This dataset is for beginners so it is easy to
use and it fits perfect for the start.

For the Capstone project I decided to use next technologies:
First of all it will be IBM Watson studio. There I will create Notebook with
support of Python3 and Spark 2.1 together with Python2 and Spark 2.1 for
SytemML.
I decided to use Python since I know this language. Also I will use next
several Python libraries:
1. NumPy
2. Matplotlib
3. Seaborn
4. Scicit learn
5. Pandas
6. Keras
7. SystemMl
8. Apache Spark
9. SystemML

All those technologies makes available to use different approaches for
estimating of quality of wine.

# The results pof the work:

## SystemML (LogisticRegression):
Here I used SystemML framework together with Pandas dataframe. As a
preprocessing I dropped 3 columns: quality, density and pH since those
columns I think does not give many values to the dataset. I decided to do
this based on the ETL step. And quality is a label so I dropped it also. Then
I added new column label with threshold 7, it means that all wines with
quality more than 7 or equal to 7 have 1 and all other wines have 0 in this
column.
I used LogisticRegression classification algorithm in this framework.
Winequality-red dataset is used in this notebook
### Results:
1) LogisticRegression score: 0.861742

## PySpark (LinearRegression):
I tried to use Linear Regression in order to predict Red Wine quality using
Linear Regression library frin PySpark framework and model is not very
good. I think because Linear Regression is not suitable for this kind of
task. I used Apache Spark and pyspark regression algorithm. Normalizer
did not help.
### Results:
1) RMSE: 0.736556
2) r2: 0.176016

## PySpark(Gradient-Boosted Trees (GBTs)):
I tried to use this algorithm and works pretty well. Also Apache Spark was
used together with this classification algorithm. I also used Pipeline with
Normalizer as part of data engineering process.
### Results:
1) F1: 0.8901

## Keras (Deep Learning):
Here I used feed-forward network in order to try to predict quality of wine
itself. I used Pandas and K-fold cross validation algorithm in order to get
correct prediction values. Also I used Standard Scaler in order to
standardize the data. Unfortunately because data is not enough I think the
results are not good:
### Results:
1) MSE: 0.4849
2) MAE: 0.5514
3) R2 score: 0.3619
