

```python
# hand written mean = 9.857

greg = 14
marcia = 12
peter = 11
jan = 10
bobby = 8
cindy = 6
cousin_o = 8 

mean_age = (greg + marcia + peter + jan+ bobby + cindy + cousin_o) / 7
print(mean_age)
```

    9.857142857142858
    


```python
import pandas as pd
import numpy as np

b_bunch = pd.DataFrame()

b_bunch['Kids'] = ['Greg', 'Marcia', 'Peter', ' Jan', 'Bobby', 'Cindy', 'Counsin Oliver']
b_bunch['Age'] = [14, 12, 11, 10, 8, 6, 8]

b_bunch
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
      <th>Kids</th>
      <th>Age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Greg</td>
      <td>14</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Marcia</td>
      <td>12</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Peter</td>
      <td>11</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jan</td>
      <td>10</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Bobby</td>
      <td>8</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Cindy</td>
      <td>6</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Counsin Oliver</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
b_bunch['Age'].mean()
```




    9.857142857142858




```python
# handwritten median = 10
```


```python
b_bunch['Age'].median()
```




    10.0




```python
# handwritte mode = 8
```


```python
b_bunch['Age'].mode()
```




    0    8
    dtype: int64




```python
# handwritte var approx= 12.83 with use of calculator
```


```python
b_bunch['Age'].var()
```




    7.476190476190475




```python
# my math was incorrect in the sum of squared error. 
# When I do it with a bias I get 6.41 but I do not understand why it is biased considering
# what I drew from was the entire population of starring children cast members. I assumed
# using n-1 was only when we drew a sample.

```


```python
# handwritten std = 2.7
```


```python
b_var = b_bunch['Age'].var()

b_var ** .5
```




    2.734262327610589




```python
b_bunch['Age'].std()
```




    2.734262327610589




```python
# approximate se = 1.023
```


```python
(b_var ** .5) / (len(b_bunch['Age']) ** .5)
```




    1.0334540197243192




```python
b_bunch['Age'].std() / (len(b_bunch['Age']) ** .5)
```




    1.0334540197243192




```python
b_bunch.describe(include='all')
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
      <th>Kids</th>
      <th>Age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>7</td>
      <td>7.000000</td>
    </tr>
    <tr>
      <th>unique</th>
      <td>7</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>top</th>
      <td>Peter</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>freq</th>
      <td>1</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>NaN</td>
      <td>9.857143</td>
    </tr>
    <tr>
      <th>std</th>
      <td>NaN</td>
      <td>2.734262</td>
    </tr>
    <tr>
      <th>min</th>
      <td>NaN</td>
      <td>6.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>NaN</td>
      <td>8.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>NaN</td>
      <td>10.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>NaN</td>
      <td>11.500000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>NaN</td>
      <td>14.000000</td>
    </tr>
  </tbody>
</table>
</div>



Initially I would have chosen the mean, however, upon further inspection, I found that the median value extended by four values equally, while the mean was a little under.

my first assumption for the birthday of Cindy is that the mean will increase and the median and mode will stay the same. I also think the std will decrease. 


```python
import pandas as pd
import numpy as np

b_bunch = pd.DataFrame()

b_bunch['Kids'] = ['Greg', 'Marcia', 'Peter', ' Jan', 'Bobby', 'Cindy', 'Counsin Oliver']
b_bunch['Age'] = [14, 12, 11, 10, 8, 7, 8]

b_bunch
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
      <th>Kids</th>
      <th>Age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Greg</td>
      <td>14</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Marcia</td>
      <td>12</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Peter</td>
      <td>11</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jan</td>
      <td>10</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Bobby</td>
      <td>8</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Cindy</td>
      <td>7</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Counsin Oliver</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
def test_stats(x, s):    
    print('mean: ', x[s].mean())
    print('median: ', x[s].median())
    print('mode: ', x[s].mode())
    print('var: ', x[s].var())
    print('std: ', x[s].std())
    print('se:', x[s].std() / (len(x[s]) ** .5))

    print('\n', b_bunch.describe())
    
test_stats(b_bunch, 'Age')
```

    mean:  9.0
    median:  10.0
    mode:  0     1
    1     7
    2     8
    3    10
    4    11
    5    12
    6    14
    dtype: int64
    var:  18.0
    std:  4.242640687119285
    se: 1.6035674514745462
    
                  Age
    count   7.000000
    mean    9.000000
    std     4.242641
    min     1.000000
    25%     7.500000
    50%    10.000000
    75%    11.500000
    max    14.000000
    

For the next question, having Cousin Oliver change to 1 year old jessica would greatly decrease the mean. median and mode will stay the same. I'm going to keep Cindy at 7.


```python
b_bunch = pd.DataFrame()

b_bunch['Kids'] = ['Greg', 'Marcia', 'Peter', ' Jan', 'Bobby', 'Cindy', 'Jessica']
b_bunch['Age'] = [14, 12, 11, 10, 8, 7, 1]

b_bunch
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
      <th>Kids</th>
      <th>Age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Greg</td>
      <td>14</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Marcia</td>
      <td>12</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Peter</td>
      <td>11</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jan</td>
      <td>10</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Bobby</td>
      <td>8</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Cindy</td>
      <td>7</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Jessica</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
   
test_stats(b_bunch, 'Age')
```

    mean:  9.0
    median:  10.0
    mode:  0     1
    1     7
    2     8
    3    10
    4    11
    5    12
    6    14
    dtype: int64
    var:  18.0
    std:  4.242640687119285
    se: 1.6035674514745462
    
                  Age
    count   7.000000
    mean    9.000000
    std     4.242641
    min     1.000000
    25%     7.500000
    50%    10.000000
    75%    11.500000
    max    14.000000
    

I didn't realize that the second 8 would leave and thus return no mode. The mean didn't decrease by as dramatic an amount as I would have first thought. This leads me to believe I should have initially gone with the mean as my central tendency because it can change with the dataset. 


```python
fans = pd.DataFrame()
fans['Magazine'] = ['Tv Guide', 'Entertainment Weekly', 'Pop Culture', 'SciPhi Phanatic']
fans['Fan poll'] = [20, 23, 17, 5]

fans
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
      <th>Magazine</th>
      <th>Fan poll</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Tv Guide</td>
      <td>20</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Entertainment Weekly</td>
      <td>23</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Pop Culture</td>
      <td>17</td>
    </tr>
    <tr>
      <th>3</th>
      <td>SciPhi Phanatic</td>
      <td>5</td>
    </tr>
  </tbody>
</table>
</div>




```python
test_stats(fans, 'Fan poll')
```

    mean:  16.25
    median:  18.5
    mode:  0     5
    1    17
    2    20
    3    23
    dtype: int64
    var:  62.25
    std:  7.88986691902975
    se: 3.944933459514875
    
                  Age
    count   7.000000
    mean    9.000000
    std     4.242641
    min     1.000000
    25%     7.500000
    50%    10.000000
    75%    11.500000
    max    14.000000
    

I would say that around 16% of people like The Brady Bunch
