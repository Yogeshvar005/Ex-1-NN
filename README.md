<H3>ENTER YOUR NAME: YOGESHVAR M </H3>
<H3>ENTER YOUR REGISTER NO: 212222230180</H3>
<H3>EX. NO.1</H3>
<H3>DATE: 22.08.2024 </H3>
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
```python
import pandas as pd
import io
from sklearn.preprocessing import StandardScaler
from sklearn.model_selection import train_test_split
```
```python
df=pd.read_csv("/content/Churn_Modelling.csv", index_col="RowNumber")
df
```
```python
df.drop(['CustomerId'],axis=1,inplace=True)
df.drop(['Surname'],axis=1,inplace=True)
df.drop('Age',axis=1,inplace=True)
df.drop('Geography',axis=1,inplace=True)
df.drop('Gender',axis=1,inplace=True)
df
```
```python
df.isnull().sum()
```
```python
df.duplicated()
```
```python
df.describe()
```
```python
scaler=StandardScaler()
df1=pd.DataFrame(scaler.fit_transform(df))
df1
```
```python
x=df1.iloc[:,:-1].values
x
y=df1.iloc[:,-1].values
y
```
```python
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2)
print(x_train)
print(len(x_train))
print(x_test)
print(len(x_test))
```
## OUTPUT:
#### DATASET:

![image](https://github.com/user-attachments/assets/b307ad72-2227-40f9-a01f-ea29f5ce9a97)


#### DROPPING THE UNWANTED DATASET:

![image](https://github.com/user-attachments/assets/3dba3b07-09f9-49db-a55a-99b2faf06c90)


#### CHECKING NULL VALUES:

![image](https://github.com/user-attachments/assets/d3c1fce1-752c-4fde-a516-9df764d0d480)


#### CHECKING FOR DUPLICATION:

![image](https://github.com/user-attachments/assets/48106b0f-bcfd-4935-9c50-99826fd24377)

#### DESCRIBING THE DATASET:

![image](https://github.com/user-attachments/assets/8458a45b-0d8a-4bbb-80b9-e5084cb711ad)

#### SCALING THE DATASET:

![image](https://github.com/user-attachments/assets/ff631792-e764-4331-998b-ec2c75079c9f)

#### X FEATURES:

![image](https://github.com/user-attachments/assets/9153bdee-74b3-41f2-aa60-f7ab4d361cb5)

#### Y FEATURES:

![image](https://github.com/user-attachments/assets/9597d125-20f2-4959-aa6c-73867f95925d)

#### SPLITTING THE TRAINING AND TESTING DATASET:

![image](https://github.com/user-attachments/assets/0d84d561-5ac7-43d6-871d-ac66b127df80)

## RESULT:
Thus, Implementation of Data Preprocessing is done in python  using a data set downloaded from Kaggle.
