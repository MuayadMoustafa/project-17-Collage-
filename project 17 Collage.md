```python
import pandas as pd 
import numpy as np 
```


```python
df = pd.read_csv("D:Courses/Projects/Collage.txt")
df 
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
      <th>Unnamed: 0</th>
      <th>Private</th>
      <th>Apps</th>
      <th>Accept</th>
      <th>Enroll</th>
      <th>Top10perc</th>
      <th>Top25perc</th>
      <th>F.Undergrad</th>
      <th>P.Undergrad</th>
      <th>Outstate</th>
      <th>Room.Board</th>
      <th>Books</th>
      <th>Personal</th>
      <th>PhD</th>
      <th>Terminal</th>
      <th>S.F.Ratio</th>
      <th>perc.alumni</th>
      <th>Expend</th>
      <th>Grad.Rate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Abilene Christian University</td>
      <td>Yes</td>
      <td>1660</td>
      <td>1232</td>
      <td>721</td>
      <td>23</td>
      <td>52</td>
      <td>2885</td>
      <td>537</td>
      <td>7440</td>
      <td>3300</td>
      <td>450</td>
      <td>2200</td>
      <td>70</td>
      <td>78</td>
      <td>18.1</td>
      <td>12</td>
      <td>7041</td>
      <td>60</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Adelphi University</td>
      <td>Yes</td>
      <td>2186</td>
      <td>1924</td>
      <td>512</td>
      <td>16</td>
      <td>29</td>
      <td>2683</td>
      <td>1227</td>
      <td>12280</td>
      <td>6450</td>
      <td>750</td>
      <td>1500</td>
      <td>29</td>
      <td>30</td>
      <td>12.2</td>
      <td>16</td>
      <td>10527</td>
      <td>56</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Adrian College</td>
      <td>Yes</td>
      <td>1428</td>
      <td>1097</td>
      <td>336</td>
      <td>22</td>
      <td>50</td>
      <td>1036</td>
      <td>99</td>
      <td>11250</td>
      <td>3750</td>
      <td>400</td>
      <td>1165</td>
      <td>53</td>
      <td>66</td>
      <td>12.9</td>
      <td>30</td>
      <td>8735</td>
      <td>54</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Agnes Scott College</td>
      <td>Yes</td>
      <td>417</td>
      <td>349</td>
      <td>137</td>
      <td>60</td>
      <td>89</td>
      <td>510</td>
      <td>63</td>
      <td>12960</td>
      <td>5450</td>
      <td>450</td>
      <td>875</td>
      <td>92</td>
      <td>97</td>
      <td>7.7</td>
      <td>37</td>
      <td>19016</td>
      <td>59</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Alaska Pacific University</td>
      <td>Yes</td>
      <td>193</td>
      <td>146</td>
      <td>55</td>
      <td>16</td>
      <td>44</td>
      <td>249</td>
      <td>869</td>
      <td>7560</td>
      <td>4120</td>
      <td>800</td>
      <td>1500</td>
      <td>76</td>
      <td>72</td>
      <td>11.9</td>
      <td>2</td>
      <td>10922</td>
      <td>15</td>
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
      <td>...</td>
      <td>...</td>
      <td>...</td>
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
      <th>772</th>
      <td>Worcester State College</td>
      <td>No</td>
      <td>2197</td>
      <td>1515</td>
      <td>543</td>
      <td>4</td>
      <td>26</td>
      <td>3089</td>
      <td>2029</td>
      <td>6797</td>
      <td>3900</td>
      <td>500</td>
      <td>1200</td>
      <td>60</td>
      <td>60</td>
      <td>21.0</td>
      <td>14</td>
      <td>4469</td>
      <td>40</td>
    </tr>
    <tr>
      <th>773</th>
      <td>Xavier University</td>
      <td>Yes</td>
      <td>1959</td>
      <td>1805</td>
      <td>695</td>
      <td>24</td>
      <td>47</td>
      <td>2849</td>
      <td>1107</td>
      <td>11520</td>
      <td>4960</td>
      <td>600</td>
      <td>1250</td>
      <td>73</td>
      <td>75</td>
      <td>13.3</td>
      <td>31</td>
      <td>9189</td>
      <td>83</td>
    </tr>
    <tr>
      <th>774</th>
      <td>Xavier University of Louisiana</td>
      <td>Yes</td>
      <td>2097</td>
      <td>1915</td>
      <td>695</td>
      <td>34</td>
      <td>61</td>
      <td>2793</td>
      <td>166</td>
      <td>6900</td>
      <td>4200</td>
      <td>617</td>
      <td>781</td>
      <td>67</td>
      <td>75</td>
      <td>14.4</td>
      <td>20</td>
      <td>8323</td>
      <td>49</td>
    </tr>
    <tr>
      <th>775</th>
      <td>Yale University</td>
      <td>Yes</td>
      <td>10705</td>
      <td>2453</td>
      <td>1317</td>
      <td>95</td>
      <td>99</td>
      <td>5217</td>
      <td>83</td>
      <td>19840</td>
      <td>6510</td>
      <td>630</td>
      <td>2115</td>
      <td>96</td>
      <td>96</td>
      <td>5.8</td>
      <td>49</td>
      <td>40386</td>
      <td>99</td>
    </tr>
    <tr>
      <th>776</th>
      <td>York College of Pennsylvania</td>
      <td>Yes</td>
      <td>2989</td>
      <td>1855</td>
      <td>691</td>
      <td>28</td>
      <td>63</td>
      <td>2988</td>
      <td>1726</td>
      <td>4990</td>
      <td>3560</td>
      <td>500</td>
      <td>1250</td>
      <td>75</td>
      <td>75</td>
      <td>18.1</td>
      <td>28</td>
      <td>4509</td>
      <td>99</td>
    </tr>
  </tbody>
</table>
<p>777 rows × 19 columns</p>
</div>




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
      <th>Apps</th>
      <th>Accept</th>
      <th>Enroll</th>
      <th>Top10perc</th>
      <th>Top25perc</th>
      <th>F.Undergrad</th>
      <th>P.Undergrad</th>
      <th>Outstate</th>
      <th>Room.Board</th>
      <th>Books</th>
      <th>Personal</th>
      <th>PhD</th>
      <th>Terminal</th>
      <th>S.F.Ratio</th>
      <th>perc.alumni</th>
      <th>Expend</th>
      <th>Grad.Rate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>777.000000</td>
      <td>777.000000</td>
      <td>777.000000</td>
      <td>777.000000</td>
      <td>777.000000</td>
      <td>777.000000</td>
      <td>777.000000</td>
      <td>777.000000</td>
      <td>777.000000</td>
      <td>777.000000</td>
      <td>777.000000</td>
      <td>777.000000</td>
      <td>777.000000</td>
      <td>777.000000</td>
      <td>777.000000</td>
      <td>777.000000</td>
      <td>777.00000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>3001.638353</td>
      <td>2018.804376</td>
      <td>779.972973</td>
      <td>27.558559</td>
      <td>55.796654</td>
      <td>3699.907336</td>
      <td>855.298584</td>
      <td>10440.669241</td>
      <td>4357.526384</td>
      <td>549.380952</td>
      <td>1340.642214</td>
      <td>72.660232</td>
      <td>79.702703</td>
      <td>14.089704</td>
      <td>22.743887</td>
      <td>9660.171171</td>
      <td>65.46332</td>
    </tr>
    <tr>
      <th>std</th>
      <td>3870.201484</td>
      <td>2451.113971</td>
      <td>929.176190</td>
      <td>17.640364</td>
      <td>19.804778</td>
      <td>4850.420531</td>
      <td>1522.431887</td>
      <td>4023.016484</td>
      <td>1096.696416</td>
      <td>165.105360</td>
      <td>677.071454</td>
      <td>16.328155</td>
      <td>14.722359</td>
      <td>3.958349</td>
      <td>12.391801</td>
      <td>5221.768440</td>
      <td>17.17771</td>
    </tr>
    <tr>
      <th>min</th>
      <td>81.000000</td>
      <td>72.000000</td>
      <td>35.000000</td>
      <td>1.000000</td>
      <td>9.000000</td>
      <td>139.000000</td>
      <td>1.000000</td>
      <td>2340.000000</td>
      <td>1780.000000</td>
      <td>96.000000</td>
      <td>250.000000</td>
      <td>8.000000</td>
      <td>24.000000</td>
      <td>2.500000</td>
      <td>0.000000</td>
      <td>3186.000000</td>
      <td>10.00000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>776.000000</td>
      <td>604.000000</td>
      <td>242.000000</td>
      <td>15.000000</td>
      <td>41.000000</td>
      <td>992.000000</td>
      <td>95.000000</td>
      <td>7320.000000</td>
      <td>3597.000000</td>
      <td>470.000000</td>
      <td>850.000000</td>
      <td>62.000000</td>
      <td>71.000000</td>
      <td>11.500000</td>
      <td>13.000000</td>
      <td>6751.000000</td>
      <td>53.00000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1558.000000</td>
      <td>1110.000000</td>
      <td>434.000000</td>
      <td>23.000000</td>
      <td>54.000000</td>
      <td>1707.000000</td>
      <td>353.000000</td>
      <td>9990.000000</td>
      <td>4200.000000</td>
      <td>500.000000</td>
      <td>1200.000000</td>
      <td>75.000000</td>
      <td>82.000000</td>
      <td>13.600000</td>
      <td>21.000000</td>
      <td>8377.000000</td>
      <td>65.00000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>3624.000000</td>
      <td>2424.000000</td>
      <td>902.000000</td>
      <td>35.000000</td>
      <td>69.000000</td>
      <td>4005.000000</td>
      <td>967.000000</td>
      <td>12925.000000</td>
      <td>5050.000000</td>
      <td>600.000000</td>
      <td>1700.000000</td>
      <td>85.000000</td>
      <td>92.000000</td>
      <td>16.500000</td>
      <td>31.000000</td>
      <td>10830.000000</td>
      <td>78.00000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>48094.000000</td>
      <td>26330.000000</td>
      <td>6392.000000</td>
      <td>96.000000</td>
      <td>100.000000</td>
      <td>31643.000000</td>
      <td>21836.000000</td>
      <td>21700.000000</td>
      <td>8124.000000</td>
      <td>2340.000000</td>
      <td>6800.000000</td>
      <td>103.000000</td>
      <td>100.000000</td>
      <td>39.800000</td>
      <td>64.000000</td>
      <td>56233.000000</td>
      <td>118.00000</td>
    </tr>
  </tbody>
</table>
</div>




```python
 df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 777 entries, 0 to 776
    Data columns (total 19 columns):
     #   Column       Non-Null Count  Dtype  
    ---  ------       --------------  -----  
     0   Unnamed: 0   777 non-null    object 
     1   Private      777 non-null    object 
     2   Apps         777 non-null    int64  
     3   Accept       777 non-null    int64  
     4   Enroll       777 non-null    int64  
     5   Top10perc    777 non-null    int64  
     6   Top25perc    777 non-null    int64  
     7   F.Undergrad  777 non-null    int64  
     8   P.Undergrad  777 non-null    int64  
     9   Outstate     777 non-null    int64  
     10  Room.Board   777 non-null    int64  
     11  Books        777 non-null    int64  
     12  Personal     777 non-null    int64  
     13  PhD          777 non-null    int64  
     14  Terminal     777 non-null    int64  
     15  S.F.Ratio    777 non-null    float64
     16  perc.alumni  777 non-null    int64  
     17  Expend       777 non-null    int64  
     18  Grad.Rate    777 non-null    int64  
    dtypes: float64(1), int64(16), object(2)
    memory usage: 115.5+ KB
    


```python
df.dtypes
```




    Unnamed: 0      object
    Private         object
    Apps             int64
    Accept           int64
    Enroll           int64
    Top10perc        int64
    Top25perc        int64
    F.Undergrad      int64
    P.Undergrad      int64
    Room.Board       int64
    Books            int64
    Personal         int64
    PhD              int64
    Terminal         int64
    S.F.Ratio      float64
    perc.alumni      int64
    Expend           int64
    Grad.Rate        int64
    dtype: object




```python
df.groupby("Accept").Apps.mean()
```




    Accept
    72          81.0
    90         100.0
    118        141.0
    128        152.0
    130        158.5
              ...   
    13007    20192.0
    13243    16587.0
    15096    18114.0
    18744    21804.0
    26330    48094.0
    Name: Apps, Length: 693, dtype: float64




```python
df.groupby("Enroll").Accept.mean()
```




    Enroll
    35         90.0
    46        130.0
    51         72.0
    55        132.0
    63        165.0
             ...   
    5705    11652.0
    5873    13243.0
    5874    18744.0
    6180    15096.0
    6392    10519.0
    Name: Accept, Length: 581, dtype: float64




```python
df.drop(columns='Enroll', inplace=True)
df 
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
      <th>Unnamed: 0</th>
      <th>Private</th>
      <th>Apps</th>
      <th>Accept</th>
      <th>Top10perc</th>
      <th>Top25perc</th>
      <th>F.Undergrad</th>
      <th>P.Undergrad</th>
      <th>Room.Board</th>
      <th>Books</th>
      <th>Personal</th>
      <th>PhD</th>
      <th>Terminal</th>
      <th>S.F.Ratio</th>
      <th>perc.alumni</th>
      <th>Expend</th>
      <th>Grad.Rate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Abilene Christian University</td>
      <td>Yes</td>
      <td>1660</td>
      <td>1232</td>
      <td>23</td>
      <td>52</td>
      <td>2885</td>
      <td>537</td>
      <td>3300</td>
      <td>450</td>
      <td>2200</td>
      <td>70</td>
      <td>78</td>
      <td>18.1</td>
      <td>12</td>
      <td>7041</td>
      <td>60</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Adelphi University</td>
      <td>Yes</td>
      <td>2186</td>
      <td>1924</td>
      <td>16</td>
      <td>29</td>
      <td>2683</td>
      <td>1227</td>
      <td>6450</td>
      <td>750</td>
      <td>1500</td>
      <td>29</td>
      <td>30</td>
      <td>12.2</td>
      <td>16</td>
      <td>10527</td>
      <td>56</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Adrian College</td>
      <td>Yes</td>
      <td>1428</td>
      <td>1097</td>
      <td>22</td>
      <td>50</td>
      <td>1036</td>
      <td>99</td>
      <td>3750</td>
      <td>400</td>
      <td>1165</td>
      <td>53</td>
      <td>66</td>
      <td>12.9</td>
      <td>30</td>
      <td>8735</td>
      <td>54</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Agnes Scott College</td>
      <td>Yes</td>
      <td>417</td>
      <td>349</td>
      <td>60</td>
      <td>89</td>
      <td>510</td>
      <td>63</td>
      <td>5450</td>
      <td>450</td>
      <td>875</td>
      <td>92</td>
      <td>97</td>
      <td>7.7</td>
      <td>37</td>
      <td>19016</td>
      <td>59</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Alaska Pacific University</td>
      <td>Yes</td>
      <td>193</td>
      <td>146</td>
      <td>16</td>
      <td>44</td>
      <td>249</td>
      <td>869</td>
      <td>4120</td>
      <td>800</td>
      <td>1500</td>
      <td>76</td>
      <td>72</td>
      <td>11.9</td>
      <td>2</td>
      <td>10922</td>
      <td>15</td>
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
      <td>...</td>
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
      <th>772</th>
      <td>Worcester State College</td>
      <td>No</td>
      <td>2197</td>
      <td>1515</td>
      <td>4</td>
      <td>26</td>
      <td>3089</td>
      <td>2029</td>
      <td>3900</td>
      <td>500</td>
      <td>1200</td>
      <td>60</td>
      <td>60</td>
      <td>21.0</td>
      <td>14</td>
      <td>4469</td>
      <td>40</td>
    </tr>
    <tr>
      <th>773</th>
      <td>Xavier University</td>
      <td>Yes</td>
      <td>1959</td>
      <td>1805</td>
      <td>24</td>
      <td>47</td>
      <td>2849</td>
      <td>1107</td>
      <td>4960</td>
      <td>600</td>
      <td>1250</td>
      <td>73</td>
      <td>75</td>
      <td>13.3</td>
      <td>31</td>
      <td>9189</td>
      <td>83</td>
    </tr>
    <tr>
      <th>774</th>
      <td>Xavier University of Louisiana</td>
      <td>Yes</td>
      <td>2097</td>
      <td>1915</td>
      <td>34</td>
      <td>61</td>
      <td>2793</td>
      <td>166</td>
      <td>4200</td>
      <td>617</td>
      <td>781</td>
      <td>67</td>
      <td>75</td>
      <td>14.4</td>
      <td>20</td>
      <td>8323</td>
      <td>49</td>
    </tr>
    <tr>
      <th>775</th>
      <td>Yale University</td>
      <td>Yes</td>
      <td>10705</td>
      <td>2453</td>
      <td>95</td>
      <td>99</td>
      <td>5217</td>
      <td>83</td>
      <td>6510</td>
      <td>630</td>
      <td>2115</td>
      <td>96</td>
      <td>96</td>
      <td>5.8</td>
      <td>49</td>
      <td>40386</td>
      <td>99</td>
    </tr>
    <tr>
      <th>776</th>
      <td>York College of Pennsylvania</td>
      <td>Yes</td>
      <td>2989</td>
      <td>1855</td>
      <td>28</td>
      <td>63</td>
      <td>2988</td>
      <td>1726</td>
      <td>3560</td>
      <td>500</td>
      <td>1250</td>
      <td>75</td>
      <td>75</td>
      <td>18.1</td>
      <td>28</td>
      <td>4509</td>
      <td>99</td>
    </tr>
  </tbody>
</table>
<p>777 rows × 17 columns</p>
</div>




```python
print(df.groupby('Enroll').Accept.max())
```

    Enroll
    35         90
    46        130
    51         72
    55        146
    63        165
            ...  
    5705    11652
    5873    13243
    5874    18744
    6180    15096
    6392    10519
    Name: Accept, Length: 581, dtype: int64
    


```python
df.groupby('Unnamed: 0').Accept.agg(['min', 'max'])
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
      <th>min</th>
      <th>max</th>
    </tr>
    <tr>
      <th>Unnamed: 0</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Abilene Christian University</th>
      <td>1232</td>
      <td>1232</td>
    </tr>
    <tr>
      <th>Adelphi University</th>
      <td>1924</td>
      <td>1924</td>
    </tr>
    <tr>
      <th>Adrian College</th>
      <td>1097</td>
      <td>1097</td>
    </tr>
    <tr>
      <th>Agnes Scott College</th>
      <td>349</td>
      <td>349</td>
    </tr>
    <tr>
      <th>Alaska Pacific University</th>
      <td>146</td>
      <td>146</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>Worcester State College</th>
      <td>1515</td>
      <td>1515</td>
    </tr>
    <tr>
      <th>Xavier University</th>
      <td>1805</td>
      <td>1805</td>
    </tr>
    <tr>
      <th>Xavier University of Louisiana</th>
      <td>1915</td>
      <td>1915</td>
    </tr>
    <tr>
      <th>Yale University</th>
      <td>2453</td>
      <td>2453</td>
    </tr>
    <tr>
      <th>York College of Pennsylvania</th>
      <td>1855</td>
      <td>1855</td>
    </tr>
  </tbody>
</table>
<p>777 rows × 2 columns</p>
</div>




```python
df[["Unnamed: 0","Apps","Accept","Enroll"]].head()
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
      <th>Unnamed: 0</th>
      <th>Apps</th>
      <th>Accept</th>
      <th>Enroll</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Abilene Christian University</td>
      <td>1660</td>
      <td>1232</td>
      <td>721</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Adelphi University</td>
      <td>2186</td>
      <td>1924</td>
      <td>512</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Adrian College</td>
      <td>1428</td>
      <td>1097</td>
      <td>336</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Agnes Scott College</td>
      <td>417</td>
      <td>349</td>
      <td>137</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Alaska Pacific University</td>
      <td>193</td>
      <td>146</td>
      <td>55</td>
    </tr>
  </tbody>
</table>
</div>




```python
df[["Unnamed: 0","Apps","Accept","Enroll"]].tail()
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
      <th>Unnamed: 0</th>
      <th>Apps</th>
      <th>Accept</th>
      <th>Enroll</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>772</th>
      <td>Worcester State College</td>
      <td>2197</td>
      <td>1515</td>
      <td>543</td>
    </tr>
    <tr>
      <th>773</th>
      <td>Xavier University</td>
      <td>1959</td>
      <td>1805</td>
      <td>695</td>
    </tr>
    <tr>
      <th>774</th>
      <td>Xavier University of Louisiana</td>
      <td>2097</td>
      <td>1915</td>
      <td>695</td>
    </tr>
    <tr>
      <th>775</th>
      <td>Yale University</td>
      <td>10705</td>
      <td>2453</td>
      <td>1317</td>
    </tr>
    <tr>
      <th>776</th>
      <td>York College of Pennsylvania</td>
      <td>2989</td>
      <td>1855</td>
      <td>691</td>
    </tr>
  </tbody>
</table>
</div>




```python
print(len(df.columns))
```

    19
    


```python
print(len(df.Apps))
```

    777
    


```python
df["Enroll"]>500
```




    0       True
    1       True
    2      False
    3      False
    4      False
           ...  
    772     True
    773     True
    774     True
    775     True
    776     True
    Name: Enroll, Length: 777, dtype: bool




```python
df.loc[: , "Apps" : "PhD"]
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
      <th>Apps</th>
      <th>Accept</th>
      <th>Enroll</th>
      <th>Top10perc</th>
      <th>Top25perc</th>
      <th>F.Undergrad</th>
      <th>P.Undergrad</th>
      <th>Outstate</th>
      <th>Room.Board</th>
      <th>Books</th>
      <th>Personal</th>
      <th>PhD</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1660</td>
      <td>1232</td>
      <td>721</td>
      <td>23</td>
      <td>52</td>
      <td>2885</td>
      <td>537</td>
      <td>7440</td>
      <td>3300</td>
      <td>450</td>
      <td>2200</td>
      <td>70</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2186</td>
      <td>1924</td>
      <td>512</td>
      <td>16</td>
      <td>29</td>
      <td>2683</td>
      <td>1227</td>
      <td>12280</td>
      <td>6450</td>
      <td>750</td>
      <td>1500</td>
      <td>29</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1428</td>
      <td>1097</td>
      <td>336</td>
      <td>22</td>
      <td>50</td>
      <td>1036</td>
      <td>99</td>
      <td>11250</td>
      <td>3750</td>
      <td>400</td>
      <td>1165</td>
      <td>53</td>
    </tr>
    <tr>
      <th>3</th>
      <td>417</td>
      <td>349</td>
      <td>137</td>
      <td>60</td>
      <td>89</td>
      <td>510</td>
      <td>63</td>
      <td>12960</td>
      <td>5450</td>
      <td>450</td>
      <td>875</td>
      <td>92</td>
    </tr>
    <tr>
      <th>4</th>
      <td>193</td>
      <td>146</td>
      <td>55</td>
      <td>16</td>
      <td>44</td>
      <td>249</td>
      <td>869</td>
      <td>7560</td>
      <td>4120</td>
      <td>800</td>
      <td>1500</td>
      <td>76</td>
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
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>772</th>
      <td>2197</td>
      <td>1515</td>
      <td>543</td>
      <td>4</td>
      <td>26</td>
      <td>3089</td>
      <td>2029</td>
      <td>6797</td>
      <td>3900</td>
      <td>500</td>
      <td>1200</td>
      <td>60</td>
    </tr>
    <tr>
      <th>773</th>
      <td>1959</td>
      <td>1805</td>
      <td>695</td>
      <td>24</td>
      <td>47</td>
      <td>2849</td>
      <td>1107</td>
      <td>11520</td>
      <td>4960</td>
      <td>600</td>
      <td>1250</td>
      <td>73</td>
    </tr>
    <tr>
      <th>774</th>
      <td>2097</td>
      <td>1915</td>
      <td>695</td>
      <td>34</td>
      <td>61</td>
      <td>2793</td>
      <td>166</td>
      <td>6900</td>
      <td>4200</td>
      <td>617</td>
      <td>781</td>
      <td>67</td>
    </tr>
    <tr>
      <th>775</th>
      <td>10705</td>
      <td>2453</td>
      <td>1317</td>
      <td>95</td>
      <td>99</td>
      <td>5217</td>
      <td>83</td>
      <td>19840</td>
      <td>6510</td>
      <td>630</td>
      <td>2115</td>
      <td>96</td>
    </tr>
    <tr>
      <th>776</th>
      <td>2989</td>
      <td>1855</td>
      <td>691</td>
      <td>28</td>
      <td>63</td>
      <td>2988</td>
      <td>1726</td>
      <td>4990</td>
      <td>3560</td>
      <td>500</td>
      <td>1250</td>
      <td>75</td>
    </tr>
  </tbody>
</table>
<p>777 rows × 12 columns</p>
</div>




```python
df.select_dtypes("number")*10
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
      <th>Apps</th>
      <th>Accept</th>
      <th>Enroll</th>
      <th>Top10perc</th>
      <th>Top25perc</th>
      <th>F.Undergrad</th>
      <th>P.Undergrad</th>
      <th>Outstate</th>
      <th>Room.Board</th>
      <th>Books</th>
      <th>Personal</th>
      <th>PhD</th>
      <th>Terminal</th>
      <th>S.F.Ratio</th>
      <th>perc.alumni</th>
      <th>Expend</th>
      <th>Grad.Rate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>16600</td>
      <td>12320</td>
      <td>7210</td>
      <td>230</td>
      <td>520</td>
      <td>28850</td>
      <td>5370</td>
      <td>74400</td>
      <td>33000</td>
      <td>4500</td>
      <td>22000</td>
      <td>700</td>
      <td>780</td>
      <td>181.0</td>
      <td>120</td>
      <td>70410</td>
      <td>600</td>
    </tr>
    <tr>
      <th>1</th>
      <td>21860</td>
      <td>19240</td>
      <td>5120</td>
      <td>160</td>
      <td>290</td>
      <td>26830</td>
      <td>12270</td>
      <td>122800</td>
      <td>64500</td>
      <td>7500</td>
      <td>15000</td>
      <td>290</td>
      <td>300</td>
      <td>122.0</td>
      <td>160</td>
      <td>105270</td>
      <td>560</td>
    </tr>
    <tr>
      <th>2</th>
      <td>14280</td>
      <td>10970</td>
      <td>3360</td>
      <td>220</td>
      <td>500</td>
      <td>10360</td>
      <td>990</td>
      <td>112500</td>
      <td>37500</td>
      <td>4000</td>
      <td>11650</td>
      <td>530</td>
      <td>660</td>
      <td>129.0</td>
      <td>300</td>
      <td>87350</td>
      <td>540</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4170</td>
      <td>3490</td>
      <td>1370</td>
      <td>600</td>
      <td>890</td>
      <td>5100</td>
      <td>630</td>
      <td>129600</td>
      <td>54500</td>
      <td>4500</td>
      <td>8750</td>
      <td>920</td>
      <td>970</td>
      <td>77.0</td>
      <td>370</td>
      <td>190160</td>
      <td>590</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1930</td>
      <td>1460</td>
      <td>550</td>
      <td>160</td>
      <td>440</td>
      <td>2490</td>
      <td>8690</td>
      <td>75600</td>
      <td>41200</td>
      <td>8000</td>
      <td>15000</td>
      <td>760</td>
      <td>720</td>
      <td>119.0</td>
      <td>20</td>
      <td>109220</td>
      <td>150</td>
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
      <td>...</td>
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
      <th>772</th>
      <td>21970</td>
      <td>15150</td>
      <td>5430</td>
      <td>40</td>
      <td>260</td>
      <td>30890</td>
      <td>20290</td>
      <td>67970</td>
      <td>39000</td>
      <td>5000</td>
      <td>12000</td>
      <td>600</td>
      <td>600</td>
      <td>210.0</td>
      <td>140</td>
      <td>44690</td>
      <td>400</td>
    </tr>
    <tr>
      <th>773</th>
      <td>19590</td>
      <td>18050</td>
      <td>6950</td>
      <td>240</td>
      <td>470</td>
      <td>28490</td>
      <td>11070</td>
      <td>115200</td>
      <td>49600</td>
      <td>6000</td>
      <td>12500</td>
      <td>730</td>
      <td>750</td>
      <td>133.0</td>
      <td>310</td>
      <td>91890</td>
      <td>830</td>
    </tr>
    <tr>
      <th>774</th>
      <td>20970</td>
      <td>19150</td>
      <td>6950</td>
      <td>340</td>
      <td>610</td>
      <td>27930</td>
      <td>1660</td>
      <td>69000</td>
      <td>42000</td>
      <td>6170</td>
      <td>7810</td>
      <td>670</td>
      <td>750</td>
      <td>144.0</td>
      <td>200</td>
      <td>83230</td>
      <td>490</td>
    </tr>
    <tr>
      <th>775</th>
      <td>107050</td>
      <td>24530</td>
      <td>13170</td>
      <td>950</td>
      <td>990</td>
      <td>52170</td>
      <td>830</td>
      <td>198400</td>
      <td>65100</td>
      <td>6300</td>
      <td>21150</td>
      <td>960</td>
      <td>960</td>
      <td>58.0</td>
      <td>490</td>
      <td>403860</td>
      <td>990</td>
    </tr>
    <tr>
      <th>776</th>
      <td>29890</td>
      <td>18550</td>
      <td>6910</td>
      <td>280</td>
      <td>630</td>
      <td>29880</td>
      <td>17260</td>
      <td>49900</td>
      <td>35600</td>
      <td>5000</td>
      <td>12500</td>
      <td>750</td>
      <td>750</td>
      <td>181.0</td>
      <td>280</td>
      <td>45090</td>
      <td>990</td>
    </tr>
  </tbody>
</table>
<p>777 rows × 17 columns</p>
</div>


