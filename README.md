# EX-05-Feature-Generation


## AIM
To read the given data and perform Feature Generation process and save the data to a file. 

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature Generation techniques to all the feature of the data set
### STEP 4
Save the data to the file


# 1.FEATURE GENERATION FOR Data.csv
## CODE FOR FEATURE ENCODING AND FEATURE SCALING:
import pandas as pd
df=pd.read_csv("data.csv")
df
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
temp=["Cold","Warm","Hot","Very Hot"]
enc=OrdinalEncoder(categories=[temp])
df["Ord_1"]=enc.fit_transform(df[["Ord_1"]])
df
education=["High School","Diploma","Bachelors","Masters","PhD"]
ed=OrdinalEncoder(categories=[education])
df["Ord_2"]=ed.fit_transform(df[["Ord_2"]])
df
pip install category_encoders
from category_encoders import BinaryEncoder
be=BinaryEncoder()
be.fit_transform(df["bin_1"])
df["bin_1"]=be.fit_transform(df[["bin_1"]])
df
be1=BinaryEncoder()
be1.fit_transform(df["bin_2"])
df["bin_2"]=be1.fit_transform(df[["bin_2"]])
df
from sklearn.preprocessing import OneHotEncoder
ohe=OneHotEncoder(sparse=False)
ohe.fit_transform(df[["City"]])
from category_encoders import TargetEncoder
te=TargetEncoder()
te.fit_transform(X=df['Ord_1'],y=df["Target"])
le=LabelEncoder()
df["City"]=le.fit_transform(df[["City"]])
df

from sklearn.preprocessing import StandardScaler
sc=StandardScaler()
df1=pd.DataFrame(sc.fit_transform(df),columns=['id','bin_1','bin_2','City','Ord_1','Ord_2','Target'])
df1

from sklearn.preprocessing import MaxAbsScaler
mas=MaxAbsScaler()
df2=pd.DataFrame(mas.fit_transform(df),columns=['id','bin_1','bin_2','City','Ord_1','Ord_2','Target'])
df2

from sklearn.preprocessing import MinMaxScaler
mms=MinMaxScaler()
df3=pd.DataFrame(mms.fit_transform(df),columns=['id','bin_1','bin_2','City','Ord_1','Ord_2','Target'])
df3

from sklearn.preprocessing import RobustScaler
rs=RobustScaler()
df4=pd.DataFrame(rs.fit_transform(df),columns=['id','bin_1','bin_2','City','Ord_1','Ord_2','Target'])
df4
# OUTPUT:
## Given DataFrame
![1 give](https://user-images.githubusercontent.com/94187572/166731875-91b971d1-029c-49cb-8226-b021719c4ad4.png)


## Feature encoding using Ordinal Encoder
![1 ori](https://user-images.githubusercontent.com/94187572/166732115-ee5394c4-715f-463b-ae72-3625a13cf8df.png)
![1 ori(](https://user-images.githubusercontent.com/94187572/166732190-3f518c4a-359d-4e89-ba4b-fdc9a911d2ac.png)


## Feature encoding using Binary Encoder
![1 bin](https://user-images.githubusercontent.com/94187572/166732386-34eac5d2-03ad-4584-8b06-33b13d9a3b7f.png)
![1 bin(](https://user-images.githubusercontent.com/94187572/166732459-2f452436-a353-4c7a-be02-23655bd93dd9.png)

## Feature encoding using One Hot Encoder
![1 onehot](https://user-images.githubusercontent.com/94187572/166732620-9189abd3-2932-4c54-b148-6e53000ea0dd.png)
 
## Feature encoding using Target Encoder
![1 tar](https://user-images.githubusercontent.com/94187572/166732898-35a104d3-8c9e-4e3e-8fe5-3028470f0418.png)

## Feature encoding using Label Encoder
![1 last](https://user-images.githubusercontent.com/94187572/166733020-aef78867-7f4b-4d66-bc87-8a07d6899edb.png)
## Feature scaling using Standard Scaler
![1 stand](https://user-images.githubusercontent.com/94187572/166733184-9a2aecc7-3aba-4fbb-9b5c-523be3844f25.png)


## Feature scaling using MaxAbs Scaler
![1 max](https://user-images.githubusercontent.com/94187572/166733327-de31ea0e-6698-4b27-834e-e11b1c05d2c9.png)


## Feature scaling using MinMax Scaler
![1 min](https://user-images.githubusercontent.com/94187572/166733440-abb00da3-3908-4cb9-8269-e87ec49ac52b.png)


## Feature scaling using Robust Scaler
![1 rob](https://user-images.githubusercontent.com/94187572/166733596-b7111e7b-5368-445d-affb-3962d0d73eb2.png)


# 2.FEATURE GENERATION FOR Encoding.csv
## CODE FOR FEATURE ENCODING AND FEATURE SCALING:
```
import pandas as pd
df=pd.read_csv("Encoding Data.csv")
df
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
temp=["Cold","Warm","Hot"]
enc=OrdinalEncoder(categories=[temp])
df["ord_2"]=enc.fit_transform(df[["ord_2"]])
df
from category_encoders import BinaryEncoder
be=BinaryEncoder()
df['bin_1']=be.fit_transform(df[['bin_1']])
df
be1=BinaryEncoder()
df['bin_2']=be1.fit_transform(df[['bin_2']])
df
from sklearn.preprocessing import OneHotEncoder
ohe=OneHotEncoder(sparse=False)
ohe.fit_transform(df[["nom_0"]])
le=LabelEncoder()
df["nom_0"]=le.fit_transform(df[["nom_0"]])
df

from sklearn.preprocessing import StandardScaler
sc=StandardScaler()
df1=pd.DataFrame(sc.fit_transform(df),columns=['id','bin_1','bin_2','nom_0','Ord_2'])
df1

from sklearn.preprocessing import MinMaxScaler
mms=MinMaxScaler()
df2=pd.DataFrame(mms.fit_transform(df),columns=['id','bin_1','bin_2','nom_0','Ord_2'])
df2

from sklearn.preprocessing import MaxAbsScaler mas=MaxAbsScaler()
df3=pd.DataFrame(mas.fit_transform(df),columns=['id','bin_1','bin_2','nom_0','Ord_2'])
df3

from sklearn.preprocessing import RobustScaler
rs=RobustScaler()
df4=pd.DataFrame(rs.fit_transform(df),columns=['id','bin_1','bin_2','nom_0','Ord_2'])
df4
```
# OUTPUT:
## Given DataFrame
![2 give](https://user-images.githubusercontent.com/94187572/166734059-862c812a-6136-471b-82b3-5076fd8f5da8.png)

## Feature encoding using Ordinal Encoder
![2 ori](https://user-images.githubusercontent.com/94187572/166734203-2dac3a2b-e435-4492-af25-ad05255c0653.png)

## Feature encoding using Binary Encoder
![2 bin](https://user-images.githubusercontent.com/94187572/166734367-5b2a131f-8458-4cb3-8e2e-ce121e8847e3.png)


## Feature encoding using One Hot Encoder
![2 oneshot](https://user-images.githubusercontent.com/94187572/166734562-fbe44a6f-25d1-48ff-929b-810ab5bbd3cf.png)

## Feature scaling using Standard Scaler
![2 stand](https://user-images.githubusercontent.com/94187572/166735414-41658ab2-dc7b-4954-b1de-21ef18e1d9d5.png)

## Feature scaling using MinMax Scaler
![2 min](https://user-images.githubusercontent.com/94187572/166735575-112abe35-0325-426f-b406-0b97c0a7b309.png)


## Feature scaling using MaxAbs Scaler
![2 max](https://user-images.githubusercontent.com/94187572/166735708-ed7f1695-37ce-4d16-9943-3309d68aec98.png)

## Feature scaling using Robust Scaler
![2 rob](https://user-images.githubusercontent.com/94187572/166735840-e000f057-bb67-4ec9-a38b-50a41d13c676.png)


# 3.FEATURE GENERATION FOR titanic_dataset.csv
## CODE FOR FEATURE ENCODING AND FEATURE SCALING:
import pandas as pd
df=pd.read_csv("titanic_dataset.csv")
df
df.isnull().sum()
df["Age"]=df["Age"].fillna(df["Age"].median())
df["Embarked"]=df["Embarked"].fillna(df["Embarked"].mode()[0])
df
df.drop("Cabin",axis=1,inplace=True)
df.drop("Ticket",axis=1,inplace=True)
df.drop("Name",axis=1,inplace=True)
df.isnull().sum()
df
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
embark=["C","S","Q"]
emb=OrdinalEncoder(categories=[embark])
df["Embarked"]=emb.fit_transform(df[["Embarked"]])
df
from category_encoders import BinaryEncoder
be=BinaryEncoder()
df["Sex"]=be.fit_transform(df[["Sex"]])
df

from sklearn.preprocessing import StandardScaler
ss=StandardScaler()
df1=pd.DataFrame(ss.fit_transform(df),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked','PClass'])
df1

from sklearn.preprocessing import MinMaxScaler
mms=MinMaxScaler()
df2=pd.DataFrame(mms.fit_transform(df),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked','PClass'])
df2

from sklearn.preprocessing import MaxAbsScaler
mas=MaxAbsScaler()
df3=pd.DataFrame(mas.fit_transform(df),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked','PClass'])
df3

from sklearn.preprocessing import RobustScaler
rs = RobustScaler()
df4=pd.DataFrame(rs.fit_transform(df),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked','PClass'])
df4
# OUTPUT:
## Given DataFrame
![3 give](https://user-images.githubusercontent.com/94187572/166736320-b170e8c5-3f0d-452d-aebf-f80512efe95d.png)

## Resolving null value data
![3 null](https://user-images.githubusercontent.com/94187572/166736465-45b82161-7d59-4460-b613-c57234b4a171.png)

## Dropping unnecessary columns
![3 rr](https://user-images.githubusercontent.com/94187572/166736672-cea43c83-7fe1-44be-ba3e-02127d983931.png)

## Feature encoding using Ordinal Encoder
![3 ori](https://user-images.githubusercontent.com/94187572/166737678-225e4d87-6d88-479e-b3a3-a84926f4a33e.png)


## Feature encoding using Binary Encoder
![3 bin](https://user-images.githubusercontent.com/94187572/166737514-f63ffd9b-6306-4b80-99f6-d06d3c371813.png)


## Feature scaling using Standard Scaler
![3 stand](https://user-images.githubusercontent.com/94187572/166737283-fa9bb6ac-a3b0-4cb2-9fa4-403dd93d68c5.png)

## Feature scaling using MinMax Scaler
![3 min](https://user-images.githubusercontent.com/94187572/166737146-ec8024ff-2a0a-4d1a-afa7-92867e460ef8.png)


## Feature scaling using MaxAbs Scaler
![3 max](https://user-images.githubusercontent.com/94187572/166737000-4ad887fa-b7c8-4b46-9140-de92f30ad067.png)


## Feature scaling using Robust Scaler
![3 rob](https://user-images.githubusercontent.com/94187572/166736891-3da94964-c6b9-44fa-b24a-65832e596929.png)


# RESULT:
Feature Encoding process and Feature Scaling process is applied to the given data frame sucessfully.
