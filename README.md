<H3>ENTER YOUR NAME : VIDHIYA LAKSHMI S</H3>
<H3>ENTER YOUR REGISTER NO: 212223230238</H3>
<H3>EX. NO.1</H3>
<H3>DATE1: 07/03/2025</H3>
<H1 ALIGN =CENTER> Introduction to Kaggle and Data preprocessing</H1>

## AIM:

To perform Data preprocessing in a data set downloaded from Kaggle

## EQUIPMENTS REQUIRED:
Hardware – PCs
Anaconda – Python 3.7 Installation / Google Colab /Jupiter Notebook

## RELATED THEORETICAL CONCEPT:

**Kaggle :**
Kaggle, a subsidiary of Google LLC, is an online community of data scientists and machine learning practitioners. Kaggle allows users to find and publish data sets, explore and build models in a web-based data-science environment, work with other data scientists and machine learning engineers, and enter competitions to solve data science challenges.

**Data Preprocessing:**

Pre-processing refers to the transformations applied to our data before feeding it to the algorithm. Data Preprocessing is a technique that is used to convert the raw data into a clean data set. In other words, whenever the data is gathered from different sources it is collected in raw format which is not feasible for the analysis.
Data Preprocessing is the process of making data suitable for use while training a machine learning model. The dataset initially provided for training might not be in a ready-to-use state, for e.g. it might not be formatted properly, or may contain missing or null values.Solving all these problems using various methods is called Data Preprocessing, using a properly processed dataset while training will not only make life easier for you but also increase the efficiency and accuracy of your model.

**Need of Data Preprocessing :**

For achieving better results from the applied model in Machine Learning projects the format of the data has to be in a proper manner. Some specified Machine Learning model needs information in a specified format, for example, Random Forest algorithm does not support null values, therefore to execute random forest algorithm null values have to be managed from the original raw data set.
Another aspect is that the data set should be formatted in such a way that more than one Machine Learning and Deep Learning algorithm are executed in one data set, and best out of them is chosen.


## ALGORITHM:
STEP 1:Importing the libraries<BR>
STEP 2:Importing the dataset<BR>
STEP 3:Taking care of missing data<BR>
STEP 4:Encoding categorical data<BR>
STEP 5:Normalizing the data<BR>
STEP 6:Splitting the data into test and train<BR>

##  PROGRAM:
```
import pandas as pd
import io
from sklearn.preprocessing import StandardScaler
from sklearn.model_selection import train_test_split
```
## Reading the dataset
```
df=pd.read_csv("/content/Churn_Modelling.csv", index_col="RowNumber")
df
```
![image](https://github.com/user-attachments/assets/759d3626-5ef1-4102-bffe-7a6dff4d4fe6)

## Dropping the unwanted Columns

```
df.drop(['CustomerId'],axis=1,inplace=True)
df.drop(['Surname'],axis=1,inplace=True)
df.drop('Age',axis=1,inplace=True)
df.drop('Geography',axis=1,inplace=True)
df.drop('Gender',axis=1,inplace=True)
df
```
![image](https://github.com/user-attachments/assets/a409a9fd-5655-4fdd-a897-f3444bc4728d)

## Checking for null values
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/143b3730-44a1-460d-a4e1-652bf98cb899)

## Checking for duplicate values and Describing the dataset

```
df.describe()
df.duplicated()
```
![image](https://github.com/user-attachments/assets/a0d68f2b-f8f1-481b-8ec0-c696a7c221bf)

## Scaling the dataset
```
scaler=StandardScaler()
df1=pd.DataFrame(scaler.fit_transform(df))
df1
```
![image](https://github.com/user-attachments/assets/402e1b43-9e22-4594-a01f-15b588d93af9)

## Allocating X and Y attributes
```
x=df1.iloc[:,:-1].values
x
y=df1.iloc[:,-1].values
y
```
![image](https://github.com/user-attachments/assets/ccbb5067-df8d-4ffc-a03f-6854e196c002)

## Splitting the data into training and testing dataset
```
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2)
print(x_train)
print(len(x_train))
print(x_test)
print(len(x_test))
```
![image](https://github.com/user-attachments/assets/1f2e7fa4-af2a-454f-a823-4179e8425b62)


## RESULT:
Thus, Implementation of Data Preprocessing is done in python  using a data set downloaded from Kaggle.


