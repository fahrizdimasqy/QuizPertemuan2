```python
import pandas as pd
```


```python
url = 'https://raw.githubusercontent.com/fahrizdimasqy/QuizPertemuan2/main/marvel_clean.csv'
df = pd.read_csv(url)
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Title</th>
      <th>Distributor</th>
      <th>ReleaseDateUS</th>
      <th>Budget</th>
      <th>OpeningWeekendNorthAmerica</th>
      <th>NorthAmerica</th>
      <th>OtherTerritories</th>
      <th>Worldwide</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Howard the Duck</td>
      <td>Universal Pictures</td>
      <td>1986-08-01 00:00:00</td>
      <td>37000000</td>
      <td>5070136</td>
      <td>16295774</td>
      <td>21667000</td>
      <td>37962774</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Blade</td>
      <td>New Line Cinema</td>
      <td>1998-08-21 00:00:00</td>
      <td>45000000</td>
      <td>17073856</td>
      <td>70087718</td>
      <td>61095812</td>
      <td>131183530</td>
    </tr>
    <tr>
      <th>2</th>
      <td>X-Men</td>
      <td>20th Century Fox</td>
      <td>2000-07-14 00:00:00</td>
      <td>75000000</td>
      <td>54471475</td>
      <td>157299717</td>
      <td>139039810</td>
      <td>296339527</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Blade II</td>
      <td>New Line Cinema</td>
      <td>2002-03-22 00:00:00</td>
      <td>54000000</td>
      <td>32528016</td>
      <td>82348319</td>
      <td>72661713</td>
      <td>155010032</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Spider-Man</td>
      <td>Sony Pictures</td>
      <td>2002-05-03 00:00:00</td>
      <td>139000000</td>
      <td>114844116</td>
      <td>403706375</td>
      <td>418002176</td>
      <td>821708551</td>
    </tr>
  </tbody>
</table>
</div>




```python
print(df.dtypes)
```

    Title                         object
    Distributor                   object
    ReleaseDateUS                 object
    Budget                         int64
    OpeningWeekendNorthAmerica     int64
    NorthAmerica                   int64
    OtherTerritories               int64
    Worldwide                      int64
    dtype: object



```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 64 entries, 0 to 63
    Data columns (total 8 columns):
     #   Column                      Non-Null Count  Dtype 
    ---  ------                      --------------  ----- 
     0   Title                       64 non-null     object
     1   Distributor                 64 non-null     object
     2   ReleaseDateUS               64 non-null     object
     3   Budget                      64 non-null     int64 
     4   OpeningWeekendNorthAmerica  64 non-null     int64 
     5   NorthAmerica                64 non-null     int64 
     6   OtherTerritories            64 non-null     int64 
     7   Worldwide                   64 non-null     int64 
    dtypes: int64(5), object(3)
    memory usage: 4.1+ KB



```python
df.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Budget</th>
      <th>OpeningWeekendNorthAmerica</th>
      <th>NorthAmerica</th>
      <th>OtherTerritories</th>
      <th>Worldwide</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>6.400000e+01</td>
      <td>6.400000e+01</td>
      <td>6.400000e+01</td>
      <td>6.400000e+01</td>
      <td>6.400000e+01</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1.481562e+08</td>
      <td>9.014824e+07</td>
      <td>2.470271e+08</td>
      <td>3.820033e+08</td>
      <td>6.290544e+08</td>
    </tr>
    <tr>
      <th>std</th>
      <td>7.053969e+07</td>
      <td>6.741286e+07</td>
      <td>1.845656e+08</td>
      <td>3.422534e+08</td>
      <td>5.152216e+08</td>
    </tr>
    <tr>
      <th>min</th>
      <td>0.000000e+00</td>
      <td>1.500000e+06</td>
      <td>1.521787e+06</td>
      <td>1.330495e+06</td>
      <td>2.852282e+06</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>1.000000e+08</td>
      <td>5.413204e+07</td>
      <td>1.324575e+08</td>
      <td>1.622535e+08</td>
      <td>2.881115e+08</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1.500000e+08</td>
      <td>8.269390e+07</td>
      <td>2.135329e+08</td>
      <td>3.000000e+08</td>
      <td>5.316230e+08</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2.000000e+08</td>
      <td>1.153900e+08</td>
      <td>3.334327e+08</td>
      <td>4.984571e+08</td>
      <td>7.971595e+08</td>
    </tr>
    <tr>
      <th>max</th>
      <td>3.560000e+08</td>
      <td>3.571150e+08</td>
      <td>8.583730e+08</td>
      <td>1.937901e+09</td>
      <td>2.797801e+09</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.count()
```




    Title                         64
    Distributor                   64
    ReleaseDateUS                 64
    Budget                        64
    OpeningWeekendNorthAmerica    64
    NorthAmerica                  64
    OtherTerritories              64
    Worldwide                     64
    dtype: int64




```python
df.describe(include='all')
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Title</th>
      <th>Distributor</th>
      <th>ReleaseDateUS</th>
      <th>Budget</th>
      <th>OpeningWeekendNorthAmerica</th>
      <th>NorthAmerica</th>
      <th>OtherTerritories</th>
      <th>Worldwide</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>64</td>
      <td>64</td>
      <td>64</td>
      <td>6.400000e+01</td>
      <td>6.400000e+01</td>
      <td>6.400000e+01</td>
      <td>6.400000e+01</td>
      <td>6.400000e+01</td>
    </tr>
    <tr>
      <th>unique</th>
      <td>63</td>
      <td>9</td>
      <td>64</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>top</th>
      <td>Fantastic Four</td>
      <td>Walt Disney Studios Motion Pictures</td>
      <td>1986-08-01 00:00:00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>freq</th>
      <td>2</td>
      <td>20</td>
      <td>1</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.481562e+08</td>
      <td>9.014824e+07</td>
      <td>2.470271e+08</td>
      <td>3.820033e+08</td>
      <td>6.290544e+08</td>
    </tr>
    <tr>
      <th>std</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7.053969e+07</td>
      <td>6.741286e+07</td>
      <td>1.845656e+08</td>
      <td>3.422534e+08</td>
      <td>5.152216e+08</td>
    </tr>
    <tr>
      <th>min</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>0.000000e+00</td>
      <td>1.500000e+06</td>
      <td>1.521787e+06</td>
      <td>1.330495e+06</td>
      <td>2.852282e+06</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.000000e+08</td>
      <td>5.413204e+07</td>
      <td>1.324575e+08</td>
      <td>1.622535e+08</td>
      <td>2.881115e+08</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.500000e+08</td>
      <td>8.269390e+07</td>
      <td>2.135329e+08</td>
      <td>3.000000e+08</td>
      <td>5.316230e+08</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.000000e+08</td>
      <td>1.153900e+08</td>
      <td>3.334327e+08</td>
      <td>4.984571e+08</td>
      <td>7.971595e+08</td>
    </tr>
    <tr>
      <th>max</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.560000e+08</td>
      <td>3.571150e+08</td>
      <td>8.583730e+08</td>
      <td>1.937901e+09</td>
      <td>2.797801e+09</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.fillna(0)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Title</th>
      <th>Distributor</th>
      <th>ReleaseDateUS</th>
      <th>Budget</th>
      <th>OpeningWeekendNorthAmerica</th>
      <th>NorthAmerica</th>
      <th>OtherTerritories</th>
      <th>Worldwide</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Howard the Duck</td>
      <td>Universal Pictures</td>
      <td>1986-08-01 00:00:00</td>
      <td>37000000</td>
      <td>5070136</td>
      <td>16295774</td>
      <td>21667000</td>
      <td>37962774</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Blade</td>
      <td>New Line Cinema</td>
      <td>1998-08-21 00:00:00</td>
      <td>45000000</td>
      <td>17073856</td>
      <td>70087718</td>
      <td>61095812</td>
      <td>131183530</td>
    </tr>
    <tr>
      <th>2</th>
      <td>X-Men</td>
      <td>20th Century Fox</td>
      <td>2000-07-14 00:00:00</td>
      <td>75000000</td>
      <td>54471475</td>
      <td>157299717</td>
      <td>139039810</td>
      <td>296339527</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Blade II</td>
      <td>New Line Cinema</td>
      <td>2002-03-22 00:00:00</td>
      <td>54000000</td>
      <td>32528016</td>
      <td>82348319</td>
      <td>72661713</td>
      <td>155010032</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Spider-Man</td>
      <td>Sony Pictures</td>
      <td>2002-05-03 00:00:00</td>
      <td>139000000</td>
      <td>114844116</td>
      <td>403706375</td>
      <td>418002176</td>
      <td>821708551</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>59</th>
      <td>Black Widow</td>
      <td>Walt Disney Studios Motion Pictures</td>
      <td>2021-07-09 00:00:00</td>
      <td>200000000</td>
      <td>80366312</td>
      <td>183651665</td>
      <td>195979696</td>
      <td>379631351</td>
    </tr>
    <tr>
      <th>60</th>
      <td>Shang-Chi and the Legend of the Ten Rings</td>
      <td>Walt Disney Studios Motion Pictures</td>
      <td>2021-09-03 00:00:00</td>
      <td>150000000</td>
      <td>75388688</td>
      <td>224543292</td>
      <td>207700000</td>
      <td>432243292</td>
    </tr>
    <tr>
      <th>61</th>
      <td>Venom: Let There Be Carnage</td>
      <td>Sony Pictures</td>
      <td>2021-10-01 00:00:00</td>
      <td>110000000</td>
      <td>90033210</td>
      <td>213550366</td>
      <td>288500000</td>
      <td>502050366</td>
    </tr>
    <tr>
      <th>62</th>
      <td>Eternals</td>
      <td>Walt Disney Studios Motion Pictures</td>
      <td>2021-11-05 00:00:00</td>
      <td>200000000</td>
      <td>85021497</td>
      <td>164870234</td>
      <td>237194665</td>
      <td>402064899</td>
    </tr>
    <tr>
      <th>63</th>
      <td>Spider-Man: No Way Home</td>
      <td>Sony Pictures</td>
      <td>2021-12-17 00:00:00</td>
      <td>200000000</td>
      <td>260138569</td>
      <td>780418859</td>
      <td>1072000000</td>
      <td>1852418859</td>
    </tr>
  </tbody>
</table>
<p>64 rows × 8 columns</p>
</div>




```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 64 entries, 0 to 63
    Data columns (total 8 columns):
     #   Column                      Non-Null Count  Dtype 
    ---  ------                      --------------  ----- 
     0   Title                       64 non-null     object
     1   Distributor                 64 non-null     object
     2   ReleaseDateUS               64 non-null     object
     3   Budget                      64 non-null     int64 
     4   OpeningWeekendNorthAmerica  64 non-null     int64 
     5   NorthAmerica                64 non-null     int64 
     6   OtherTerritories            64 non-null     int64 
     7   Worldwide                   64 non-null     int64 
    dtypes: int64(5), object(3)
    memory usage: 4.1+ KB



```python
df['Title'] = df['Title'].fillna(0)
df['Distributor'] = df['Distributor'].fillna(0)
df['ReleaseDateUS'] = df['ReleaseDateUS'].fillna(0)
df['Budget'] = df['Budget'].fillna(0)
df['OpeningWeekendNorthAmerica'] = df['OpeningWeekendNorthAmerica'].fillna(0)
df['NorthAmerica'] = df['NorthAmerica'].fillna(0)
df['OtherTerritories'] = df['OtherTerritories'].fillna(0)
df['Worldwide'] = df['Worldwide'].fillna(0)
```


```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 64 entries, 0 to 63
    Data columns (total 8 columns):
     #   Column                      Non-Null Count  Dtype 
    ---  ------                      --------------  ----- 
     0   Title                       64 non-null     object
     1   Distributor                 64 non-null     object
     2   ReleaseDateUS               64 non-null     object
     3   Budget                      64 non-null     int64 
     4   OpeningWeekendNorthAmerica  64 non-null     int64 
     5   NorthAmerica                64 non-null     int64 
     6   OtherTerritories            64 non-null     int64 
     7   Worldwide                   64 non-null     int64 
    dtypes: int64(5), object(3)
    memory usage: 4.1+ KB



```python
df.describe(include='all')
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Title</th>
      <th>Distributor</th>
      <th>ReleaseDateUS</th>
      <th>Budget</th>
      <th>OpeningWeekendNorthAmerica</th>
      <th>NorthAmerica</th>
      <th>OtherTerritories</th>
      <th>Worldwide</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>64</td>
      <td>64</td>
      <td>64</td>
      <td>6.400000e+01</td>
      <td>6.400000e+01</td>
      <td>6.400000e+01</td>
      <td>6.400000e+01</td>
      <td>6.400000e+01</td>
    </tr>
    <tr>
      <th>unique</th>
      <td>63</td>
      <td>9</td>
      <td>64</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>top</th>
      <td>Fantastic Four</td>
      <td>Walt Disney Studios Motion Pictures</td>
      <td>1986-08-01 00:00:00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>freq</th>
      <td>2</td>
      <td>20</td>
      <td>1</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.481562e+08</td>
      <td>9.014824e+07</td>
      <td>2.470271e+08</td>
      <td>3.820033e+08</td>
      <td>6.290544e+08</td>
    </tr>
    <tr>
      <th>std</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7.053969e+07</td>
      <td>6.741286e+07</td>
      <td>1.845656e+08</td>
      <td>3.422534e+08</td>
      <td>5.152216e+08</td>
    </tr>
    <tr>
      <th>min</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>0.000000e+00</td>
      <td>1.500000e+06</td>
      <td>1.521787e+06</td>
      <td>1.330495e+06</td>
      <td>2.852282e+06</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.000000e+08</td>
      <td>5.413204e+07</td>
      <td>1.324575e+08</td>
      <td>1.622535e+08</td>
      <td>2.881115e+08</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.500000e+08</td>
      <td>8.269390e+07</td>
      <td>2.135329e+08</td>
      <td>3.000000e+08</td>
      <td>5.316230e+08</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.000000e+08</td>
      <td>1.153900e+08</td>
      <td>3.334327e+08</td>
      <td>4.984571e+08</td>
      <td>7.971595e+08</td>
    </tr>
    <tr>
      <th>max</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.560000e+08</td>
      <td>3.571150e+08</td>
      <td>8.583730e+08</td>
      <td>1.937901e+09</td>
      <td>2.797801e+09</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.corr()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Budget</th>
      <th>OpeningWeekendNorthAmerica</th>
      <th>NorthAmerica</th>
      <th>OtherTerritories</th>
      <th>Worldwide</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Budget</th>
      <td>1.000000</td>
      <td>0.769557</td>
      <td>0.716768</td>
      <td>0.768289</td>
      <td>0.767265</td>
    </tr>
    <tr>
      <th>OpeningWeekendNorthAmerica</th>
      <td>0.769557</td>
      <td>1.000000</td>
      <td>0.961622</td>
      <td>0.927357</td>
      <td>0.960693</td>
    </tr>
    <tr>
      <th>NorthAmerica</th>
      <td>0.716768</td>
      <td>0.961622</td>
      <td>1.000000</td>
      <td>0.903511</td>
      <td>0.958569</td>
    </tr>
    <tr>
      <th>OtherTerritories</th>
      <td>0.768289</td>
      <td>0.927357</td>
      <td>0.903511</td>
      <td>1.000000</td>
      <td>0.988159</td>
    </tr>
    <tr>
      <th>Worldwide</th>
      <td>0.767265</td>
      <td>0.960693</td>
      <td>0.958569</td>
      <td>0.988159</td>
      <td>1.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
pip install seaborn
```

    Requirement already satisfied: seaborn in /opt/conda/lib/python3.9/site-packages (0.11.2)
    Requirement already satisfied: matplotlib>=2.2 in /opt/conda/lib/python3.9/site-packages (from seaborn) (3.5.1)
    Requirement already satisfied: scipy>=1.0 in /opt/conda/lib/python3.9/site-packages (from seaborn) (1.8.0)
    Requirement already satisfied: numpy>=1.15 in /opt/conda/lib/python3.9/site-packages (from seaborn) (1.22.2)
    Requirement already satisfied: pandas>=0.23 in /opt/conda/lib/python3.9/site-packages (from seaborn) (1.4.1)
    Requirement already satisfied: python-dateutil>=2.7 in /opt/conda/lib/python3.9/site-packages (from matplotlib>=2.2->seaborn) (2.8.2)
    Requirement already satisfied: cycler>=0.10 in /opt/conda/lib/python3.9/site-packages (from matplotlib>=2.2->seaborn) (0.11.0)
    Requirement already satisfied: pyparsing>=2.2.1 in /opt/conda/lib/python3.9/site-packages (from matplotlib>=2.2->seaborn) (3.0.7)
    Requirement already satisfied: kiwisolver>=1.0.1 in /opt/conda/lib/python3.9/site-packages (from matplotlib>=2.2->seaborn) (1.3.2)
    Requirement already satisfied: pillow>=6.2.0 in /opt/conda/lib/python3.9/site-packages (from matplotlib>=2.2->seaborn) (9.0.1)
    Requirement already satisfied: fonttools>=4.22.0 in /opt/conda/lib/python3.9/site-packages (from matplotlib>=2.2->seaborn) (4.29.1)
    Requirement already satisfied: packaging>=20.0 in /opt/conda/lib/python3.9/site-packages (from matplotlib>=2.2->seaborn) (21.3)
    Requirement already satisfied: pytz>=2020.1 in /opt/conda/lib/python3.9/site-packages (from pandas>=0.23->seaborn) (2021.3)
    Requirement already satisfied: six>=1.5 in /opt/conda/lib/python3.9/site-packages (from python-dateutil>=2.7->matplotlib>=2.2->seaborn) (1.16.0)
    Note: you may need to restart the kernel to use updated packages.



```python
import matplotlib.pyplot as plt
import seaborn as sns

korelasi = df.corr()
plt.figure(figsize=(15, 10))
sns.heatmap(korelasi[(korelasi >= 0.5) | (korelasi <= -0.4)], cmap='viridis', vmax=1.0, vmin=-1.0, linewidths=0.1, 
            annot=True, annot_kws={"size": 8}, square=True).set_title('Korelasi Antar Variabel')
plt.show()
```


    
![png](output_15_0.png)
    



```python
bud_total = df.groupby("Title")["Budget"].sum().sort_values()
bud_total.plot(kind="barh", fontsize=10, figsize=(8,40), title='Budget Terbesar')
plt.show()

```


    
![png](output_16_0.png)
    



```python

```
