# Ex02-Outlier


You are given bhp.csv which contains property prices in the city of banglore, India. You need to examine price_per_sqft column and do following,

(1) Remove outliers using IQR

(2) After removing outliers in step 1, you get a new dataframe.

(3) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result

(4) for the data set height_weight.csv find the following

(i) Using IQR detect weight outliers and print them

(ii) Using IQR, detect height outliers and print them

ALGORITHM:

STEP 1:Read the given Data.

STEP 2:Get the information about the data.

STEP 3:Detect the Outliers using IQR method and Z score.

STEP 4:Remove the outliers:

STEP 5:Plot the datas using box plot.

CODE :

S.BARATH
212222230018

```
import pandas as pd
import seaborn as sns
age = [1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
sns.boxplot(data=af)

sns.scatterplot(data=af)

q1=af.quantile(0.25)
q2=af.quantile(0.5)
q3=af.quantile(0.75)
iqr=q3-q1

low=q1-1.5*iqr
low

high=q1+1.5*iqr
high

aq=af[((af>=low)&(af<=high))]
aq.dropna()

sns.boxplot(data=af)

af=af[((af>=low)&(af<=high))]
af.dropna()

sns.boxplot(data=af)

sns.scatterplot(data=af)

import pandas as pd
import numpy as np
import seaborn as sns
from scipy import stats
data = {'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
df=pd.DataFrame(data)
df

sns.boxplot(data=df)

z=np.abs(stats.zscore(df))
print(df[z['weight']>3])

val=[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,69,202,72,75,78,81,84,232,87,90,93,96,99,258]
out=[]
def d_o(val):
  ts=3
  m=np.mean(val)
  sd=np.std(val)
  for i in val:
    z=(i-m)/sd
    if np.abs(z)>ts:
      out.append(i)
  return out
op=d_o(val)
op

import pandas as pd
import numpy as np
import seaborn as sns
from scipy import stats
id=pd.read_csv("iris.csv")
id.head()

sns.boxplot(x='sepal_width',data=id)

c1=id.sepal_width.quantile(0.25)
c3=id.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)

rid=id[((id.sepal_width<(c1-1.5*iq))|(id.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']

delid=id[~((id.sepal_width<(c1-1.5*iq))|(id.sepal_width>(c3+1.5*iq)))]
delid

sns.boxplot(x='sepal_width',data=delid)
```

OUTPUT:

import pandas as pd
import seaborn as sns
age = [1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af

![MODEL](https://github.com/barathsubramani/ODD2023---Datascience---Ex-02/blob/main/Screenshot%202023-09-01%20195107.png)

sns.boxplot(data=af)

![MODEL](https://github.com/barathsubramani/ODD2023---Datascience---Ex-02/blob/main/Screenshot%202023-09-01%20195214.png)

sns.scatterplot(data=af)

![MODEL](https://github.com/barathsubramani/ODD2023---Datascience---Ex-02/blob/main/Screenshot%202023-09-01%20195328.png)

q1=af.quantile(0.25)
q2=af.quantile(0.5)
q3=af.quantile(0.75)
iqr=q3-q1

![MODEL](https://github.com/barathsubramani/ODD2023---Datascience---Ex-02/blob/main/Screenshot%202023-09-01%20195355.png)

low=q1-1.5*iqr
low

![MODEL](https://github.com/barathsubramani/ODD2023---Datascience---Ex-02/blob/main/Screenshot%202023-09-01%20195404.png)

high=q1+1.5*iqr
high

![MODEL](https://github.com/barathsubramani/ODD2023---Datascience---Ex-02/blob/main/Screenshot%202023-09-01%20195421.png)

aq=af[((af>=low)&(af<=high))]
aq.dropna()

![MODEL](https://github.com/barathsubramani/ODD2023---Datascience---Ex-02/blob/main/Screenshot%202023-09-01%20195443.png)

sns.boxplot(data=af)

![MODEL](https://github.com/barathsubramani/ODD2023---Datascience---Ex-02/blob/main/Screenshot%202023-09-01%20195455.png)

af=af[((af>=low)&(af<=high))]
af.dropna()

![MODEL](https://github.com/barathsubramani/ODD2023---Datascience---Ex-02/blob/main/Screenshot%202023-09-01%20195506.png)

sns.boxplot(data=af)

![MODEL](https://github.com/barathsubramani/ODD2023---Datascience---Ex-02/blob/main/Screenshot%202023-09-01%20195519.png)

sns.scatterplot(data=af)

![MODEL](https://github.com/barathsubramani/ODD2023---Datascience---Ex-02/blob/main/Screenshot%202023-09-01%20200214.png)

import pandas as pd
import numpy as np
import seaborn as sns
from scipy import stats
data = {'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
df=pd.DataFrame(data)
df

![MODEL](https://github.com/barathsubramani/ODD2023---Datascience---Ex-02/blob/main/Screenshot%202023-09-01%20200244.png)

sns.boxplot(data=df)

![MODEL](https://github.com/barathsubramani/ODD2023---Datascience---Ex-02/blob/main/Screenshot%202023-09-01%20221437.png)

z=np.abs(stats.zscore(df))
print(df[z['weight']>3])

![MODEL](https://github.com/barathsubramani/ODD2023---Datascience---Ex-02/blob/main/Screenshot%202023-09-01%20221538.png)

val=[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,69,202,72,75,78,81,84,232,87,90,93,96,99,258]
out=[]
def d_o(val):
  ts=3
  m=np.mean(val)
  sd=np.std(val)
  for i in val:
    z=(i-m)/sd
    if np.abs(z)>ts:
      out.append(i)
  return out
op=d_o(val)
op

![MODEL](https://github.com/barathsubramani/ODD2023---Datascience---Ex-02/blob/main/Screenshot%202023-09-01%20221523.png)

import pandas as pd
import numpy as np
import seaborn as sns
from scipy import stats
id=pd.read_csv("iris.csv")
id.head()

![MODEL]()

sns.boxplot(x='sepal_width',data=id)

![MODEL]()

c1=id.sepal_width.quantile(0.25)
c3=id.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)

![MODEL]()

rid=id[((id.sepal_width<(c1-1.5*iq))|(id.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']

![MODEL]()

delid=id[~((id.sepal_width<(c1-1.5*iq))|(id.sepal_width>(c3+1.5*iq)))]
delid

![MODEL]()

sns.boxplot(x='sepal_width',data=delid)


RESULT :

Thus the outliers are detected and removed in the given file and the final data set is saved into the file.





