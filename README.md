# Ex.No.1---Data-Preprocessing
## AIM:

To perform Data preprocessing in a data set downloaded from Kaggle

##REQUIPMENTS REQUIRED:
Hardware – PCs
Anaconda – Python 3.7 Installation / Google Colab /Jupiter Notebook

## RELATED THEORETICAL CONCEPT:

Kaggle :
Kaggle, a subsidiary of Google LLC, is an online community of data scientists and machine learning practitioners. Kaggle allows users to find and publish data sets, explore and build models in a web-based data-science environment, work with other data scientists and machine learning engineers, and enter competitions to solve data science challenges.

Data Preprocessing:

Pre-processing refers to the transformations applied to our data before feeding it to the algorithm. Data Preprocessing is a technique that is used to convert the raw data into a clean data set. In other words, whenever the data is gathered from different sources it is collected in raw format which is not feasible for the analysis.
Data Preprocessing is the process of making data suitable for use while training a machine learning model. The dataset initially provided for training might not be in a ready-to-use state, for e.g. it might not be formatted properly, or may contain missing or null values.Solving all these problems using various methods is called Data Preprocessing, using a properly processed dataset while training will not only make life easier for you but also increase the efficiency and accuracy of your model.

Need of Data Preprocessing :

For achieving better results from the applied model in Machine Learning projects the format of the data has to be in a proper manner. Some specified Machine Learning model needs information in a specified format, for example, Random Forest algorithm does not support null values, therefore to execute random forest algorithm null values have to be managed from the original raw data set.
Another aspect is that the data set should be formatted in such a way that more than one Machine Learning and Deep Learning algorithm are executed in one data set, and best out of them is chosen.


## ALGORITHM:
Importing the libraries
Importing the dataset
Taking care of missing data
Encoding categorical data
Normalizing the data
Splitting the data into test and train

## PROGRAM:
```
import pandas as pd

df = pd.read_csv("Churn_Modelling.csv")

df.head() df.info()

x = df.iloc[:,:-1].values y= df.iloc[:,1].values x y

df.describe()

from sklearn.preprocessing import LabelEncoder le = LabelEncoder()

df1 = df.copy()

df1["Geography"] = le.fit_transform(df1["Geography"]) df1["Gender"] = le.fit_transform(df1["Gender"])

from sklearn.preprocessing import StandardScaler from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler()

df1[["CreditScore","Geography","Age","Tenure","Balance","NumOfProducts","EstimatedSalary"]] = pd.DataFrame(scaler.fit_transform(df1[["CreditScore","Geography","Age","Tenure","Balance","NumOfProducts","EstimatedSalary"]]))

df1.describe()

X = df1[["CreditScore","Geography","Gender","Age","Tenure","Balance","NumOfProducts","HasCrCard","IsActiveMember","EstimatedSalary"]].values print(X)

y = df1.iloc[:,-1].values print(y)

from sklearn.model_selection import train_test_split X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

print(X_train)

print("Size of X_train: ",len(X_train))

print(X_test) print("Size of X_test: ",len(X_test))
```

## OUTPUT:
![image](https://github.com/MaithreyanDinakaran/Ex.No.1---Data-Preprocessing/assets/119104032/5fc94029-6283-48c6-9e3f-02a1a5d28125)
![image](https://github.com/MaithreyanDinakaran/Ex.No.1---Data-Preprocessing/assets/119104032/a24d12d7-ed97-488a-bcb6-e26a65425697)
![image](https://github.com/MaithreyanDinakaran/Ex.No.1---Data-Preprocessing/assets/119104032/34b2e47e-9b5e-4e3f-97db-6d18c6beee1c)
![image](https://github.com/MaithreyanDinakaran/Ex.No.1---Data-Preprocessing/assets/119104032/40d529f1-a4ca-4496-a433-d42638cb9ca7)
![image](https://github.com/MaithreyanDinakaran/Ex.No.1---Data-Preprocessing/assets/119104032/ae3e5390-35ef-461b-8aad-08ad42b78385)
![image](https://github.com/MaithreyanDinakaran/Ex.No.1---Data-Preprocessing/assets/119104032/c13a99fc-9f5d-4b5f-9548-c418b545b2c8)
![image](https://github.com/MaithreyanDinakaran/Ex.No.1---Data-Preprocessing/assets/119104032/72ce0dcf-6cdb-4ca9-af3a-c569effff70f)


## RESULT
Data preprocessing is performed in the given dataset.
