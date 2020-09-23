```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
%matplotlib inline
```


```python
df = pd.read_csv("C:/Users/Long Nguyen/Box/My folder/Project/Soccer/Fifa20data.csv")
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
      <th>sofifa_id</th>
      <th>player_url</th>
      <th>short_name</th>
      <th>long_name</th>
      <th>age</th>
      <th>dob</th>
      <th>height_cm</th>
      <th>weight_kg</th>
      <th>nationality</th>
      <th>club</th>
      <th>...</th>
      <th>lwb</th>
      <th>ldm</th>
      <th>cdm</th>
      <th>rdm</th>
      <th>rwb</th>
      <th>lb</th>
      <th>lcb</th>
      <th>cb</th>
      <th>rcb</th>
      <th>rb</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>158023</td>
      <td>https://sofifa.com/player/158023/lionel-messi/...</td>
      <td>L. Messi</td>
      <td>Lionel Andrés Messi Cuccittini</td>
      <td>32</td>
      <td>1987-06-24</td>
      <td>170</td>
      <td>72</td>
      <td>Argentina</td>
      <td>FC Barcelona</td>
      <td>...</td>
      <td>68+2</td>
      <td>66+2</td>
      <td>66+2</td>
      <td>66+2</td>
      <td>68+2</td>
      <td>63+2</td>
      <td>52+2</td>
      <td>52+2</td>
      <td>52+2</td>
      <td>63+2</td>
    </tr>
    <tr>
      <td>1</td>
      <td>20801</td>
      <td>https://sofifa.com/player/20801/c-ronaldo-dos-...</td>
      <td>Cristiano Ronaldo</td>
      <td>Cristiano Ronaldo dos Santos Aveiro</td>
      <td>34</td>
      <td>1985-02-05</td>
      <td>187</td>
      <td>83</td>
      <td>Portugal</td>
      <td>Juventus</td>
      <td>...</td>
      <td>65+3</td>
      <td>61+3</td>
      <td>61+3</td>
      <td>61+3</td>
      <td>65+3</td>
      <td>61+3</td>
      <td>53+3</td>
      <td>53+3</td>
      <td>53+3</td>
      <td>61+3</td>
    </tr>
    <tr>
      <td>2</td>
      <td>190871</td>
      <td>https://sofifa.com/player/190871/neymar-da-sil...</td>
      <td>Neymar Jr</td>
      <td>Neymar da Silva Santos Junior</td>
      <td>27</td>
      <td>1992-02-05</td>
      <td>175</td>
      <td>68</td>
      <td>Brazil</td>
      <td>Paris Saint-Germain</td>
      <td>...</td>
      <td>66+3</td>
      <td>61+3</td>
      <td>61+3</td>
      <td>61+3</td>
      <td>66+3</td>
      <td>61+3</td>
      <td>46+3</td>
      <td>46+3</td>
      <td>46+3</td>
      <td>61+3</td>
    </tr>
    <tr>
      <td>3</td>
      <td>200389</td>
      <td>https://sofifa.com/player/200389/jan-oblak/20/...</td>
      <td>J. Oblak</td>
      <td>Jan Oblak</td>
      <td>26</td>
      <td>1993-01-07</td>
      <td>188</td>
      <td>87</td>
      <td>Slovenia</td>
      <td>Atlético Madrid</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>4</td>
      <td>183277</td>
      <td>https://sofifa.com/player/183277/eden-hazard/2...</td>
      <td>E. Hazard</td>
      <td>Eden Hazard</td>
      <td>28</td>
      <td>1991-01-07</td>
      <td>175</td>
      <td>74</td>
      <td>Belgium</td>
      <td>Real Madrid</td>
      <td>...</td>
      <td>66+3</td>
      <td>63+3</td>
      <td>63+3</td>
      <td>63+3</td>
      <td>66+3</td>
      <td>61+3</td>
      <td>49+3</td>
      <td>49+3</td>
      <td>49+3</td>
      <td>61+3</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 104 columns</p>
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
      <th>sofifa_id</th>
      <th>age</th>
      <th>height_cm</th>
      <th>weight_kg</th>
      <th>overall</th>
      <th>potential</th>
      <th>value_eur</th>
      <th>wage_eur</th>
      <th>international_reputation</th>
      <th>weak_foot</th>
      <th>...</th>
      <th>mentality_penalties</th>
      <th>mentality_composure</th>
      <th>defending_marking</th>
      <th>defending_standing_tackle</th>
      <th>defending_sliding_tackle</th>
      <th>goalkeeping_diving</th>
      <th>goalkeeping_handling</th>
      <th>goalkeeping_kicking</th>
      <th>goalkeeping_positioning</th>
      <th>goalkeeping_reflexes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>count</td>
      <td>18278.000000</td>
      <td>18278.000000</td>
      <td>18278.000000</td>
      <td>18278.000000</td>
      <td>18278.000000</td>
      <td>18278.000000</td>
      <td>1.827800e+04</td>
      <td>18278.000000</td>
      <td>18278.000000</td>
      <td>18278.000000</td>
      <td>...</td>
      <td>18278.000000</td>
      <td>18278.000000</td>
      <td>18278.000000</td>
      <td>18278.000000</td>
      <td>18278.000000</td>
      <td>18278.000000</td>
      <td>18278.000000</td>
      <td>18278.000000</td>
      <td>18278.000000</td>
      <td>18278.000000</td>
    </tr>
    <tr>
      <td>mean</td>
      <td>219738.864482</td>
      <td>25.283291</td>
      <td>181.362184</td>
      <td>75.276343</td>
      <td>66.244994</td>
      <td>71.546887</td>
      <td>2.484038e+06</td>
      <td>9456.942773</td>
      <td>1.103184</td>
      <td>2.944250</td>
      <td>...</td>
      <td>48.383357</td>
      <td>58.528778</td>
      <td>46.848889</td>
      <td>47.640333</td>
      <td>45.606631</td>
      <td>16.572765</td>
      <td>16.354853</td>
      <td>16.212934</td>
      <td>16.368038</td>
      <td>16.709924</td>
    </tr>
    <tr>
      <td>std</td>
      <td>27960.200461</td>
      <td>4.656964</td>
      <td>6.756961</td>
      <td>7.047744</td>
      <td>6.949953</td>
      <td>6.139669</td>
      <td>5.585481e+06</td>
      <td>21351.714095</td>
      <td>0.378861</td>
      <td>0.664656</td>
      <td>...</td>
      <td>15.708099</td>
      <td>11.880840</td>
      <td>20.091287</td>
      <td>21.585641</td>
      <td>21.217734</td>
      <td>17.738069</td>
      <td>16.996925</td>
      <td>16.613665</td>
      <td>17.136497</td>
      <td>18.038125</td>
    </tr>
    <tr>
      <td>min</td>
      <td>768.000000</td>
      <td>16.000000</td>
      <td>156.000000</td>
      <td>50.000000</td>
      <td>48.000000</td>
      <td>49.000000</td>
      <td>0.000000e+00</td>
      <td>0.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>...</td>
      <td>7.000000</td>
      <td>12.000000</td>
      <td>1.000000</td>
      <td>5.000000</td>
      <td>3.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <td>25%</td>
      <td>204445.500000</td>
      <td>22.000000</td>
      <td>177.000000</td>
      <td>70.000000</td>
      <td>62.000000</td>
      <td>67.000000</td>
      <td>3.250000e+05</td>
      <td>1000.000000</td>
      <td>1.000000</td>
      <td>3.000000</td>
      <td>...</td>
      <td>39.000000</td>
      <td>51.000000</td>
      <td>29.000000</td>
      <td>27.000000</td>
      <td>24.000000</td>
      <td>8.000000</td>
      <td>8.000000</td>
      <td>8.000000</td>
      <td>8.000000</td>
      <td>8.000000</td>
    </tr>
    <tr>
      <td>50%</td>
      <td>226165.000000</td>
      <td>25.000000</td>
      <td>181.000000</td>
      <td>75.000000</td>
      <td>66.000000</td>
      <td>71.000000</td>
      <td>7.000000e+05</td>
      <td>3000.000000</td>
      <td>1.000000</td>
      <td>3.000000</td>
      <td>...</td>
      <td>49.000000</td>
      <td>60.000000</td>
      <td>52.000000</td>
      <td>55.000000</td>
      <td>52.000000</td>
      <td>11.000000</td>
      <td>11.000000</td>
      <td>11.000000</td>
      <td>11.000000</td>
      <td>11.000000</td>
    </tr>
    <tr>
      <td>75%</td>
      <td>240795.750000</td>
      <td>29.000000</td>
      <td>186.000000</td>
      <td>80.000000</td>
      <td>71.000000</td>
      <td>75.000000</td>
      <td>2.100000e+06</td>
      <td>8000.000000</td>
      <td>1.000000</td>
      <td>3.000000</td>
      <td>...</td>
      <td>60.000000</td>
      <td>67.000000</td>
      <td>64.000000</td>
      <td>66.000000</td>
      <td>64.000000</td>
      <td>14.000000</td>
      <td>14.000000</td>
      <td>14.000000</td>
      <td>14.000000</td>
      <td>14.000000</td>
    </tr>
    <tr>
      <td>max</td>
      <td>252905.000000</td>
      <td>42.000000</td>
      <td>205.000000</td>
      <td>110.000000</td>
      <td>94.000000</td>
      <td>95.000000</td>
      <td>1.055000e+08</td>
      <td>565000.000000</td>
      <td>5.000000</td>
      <td>5.000000</td>
      <td>...</td>
      <td>92.000000</td>
      <td>96.000000</td>
      <td>94.000000</td>
      <td>92.000000</td>
      <td>90.000000</td>
      <td>90.000000</td>
      <td>92.000000</td>
      <td>93.000000</td>
      <td>91.000000</td>
      <td>92.000000</td>
    </tr>
  </tbody>
</table>
<p>8 rows × 61 columns</p>
</div>




```python
df.isnull().sum()
```




    sofifa_id        0
    player_url       0
    short_name       0
    long_name        0
    age              0
                  ... 
    lb            2036
    lcb           2036
    cb            2036
    rcb           2036
    rb            2036
    Length: 104, dtype: int64




```python
df = df.fillna(value=0)
```


```python
x = df.overall
plt.figure(figsize=(15,8))
plt.style.use('seaborn-paper')

ax = sns.distplot(x, bins = 58, kde = False, color = 'y')
ax.set_xlabel(xlabel = "Player's Overall Scores", fontsize = 16)
ax.set_ylabel(ylabel = 'Number of players', fontsize = 16)
ax.set_title(label = 'Histogram of Players\' Overall Ratings', fontsize = 20)
plt.show()
```


![png](output_6_0.png)



```python
x = df.potential
plt.figure(figsize=(15,8))
plt.style.use('seaborn-paper')

ax = sns.distplot(x, bins = 58, kde = False, color = 'y')
ax.set_xlabel(xlabel = "Player's Potential Scores", fontsize = 16)
ax.set_ylabel(ylabel = 'Number of players', fontsize = 16)
ax.set_title(label = 'Histogram of Players\' Potential Ratings', fontsize = 20)
plt.show()
```


![png](output_7_0.png)



```python
plt.rcParams['figure.figsize'] = (10, 5)
ax = sns.countplot(df['preferred_foot'], palette = 'pink')
ax.set_xlabel(xlabel = "Preferred Foot", fontsize = 16)
ax.set_ylabel(ylabel = 'Number of players', fontsize = 16)
plt.title('Distribution of Players\' Preferred Foot', fontsize = 20)
plt.show()
```


![png](output_8_0.png)



```python
labels = ['1 Star', '2 Star', '3 Star', '4 Star', '5 Star'] 
size = df['weak_foot'].value_counts()
colors = plt.cm.Wistia(np.linspace(0, 1, 5))
explode = [0, 0, 0, 0, 0.1]

plt.pie(size, labels = labels, colors = colors, explode = explode, shadow = True, startangle = 90, radius = 1)
plt.title('Distribution of Players\' Week Foot', fontsize = 15)
plt.legend()
plt.show()
```


![png](output_9_0.png)



```python
plt.figure(figsize = (10, 8))
ax = sns.countplot(x = 'skill_moves', data = df, palette = 'pastel')
ax.set_title(label = 'Distribution of Players based on their skill moves', fontsize = 20)
ax.set_xlabel(xlabel = 'Number of Skill Moves', fontsize = 16)
ax.set_ylabel(ylabel = 'Number of players', fontsize = 16)
plt.show()
```


![png](output_10_0.png)



```python
plt.figure(figsize = (15, 8))
ax = sns.countplot(x = 'height_cm', data = df, palette = 'dark')
ax.set_title(label = 'Histogram of Players\' Height', fontsize = 20)
ax.set_xlabel(xlabel = 'Height in cm', fontsize = 16)
ax.set_ylabel(ylabel = 'Number of players', fontsize = 16)
plt.show()
```


![png](output_11_0.png)



```python
plt.figure(figsize = (15, 8))
ax = sns.countplot(x = 'weight_kg', data = df, palette = 'dark')
ax.set_title(label = 'Histogram of Players\' Weight', fontsize = 20)
ax.set_xlabel(xlabel = 'Weight in kg', fontsize = 16)
ax.set_ylabel(ylabel = 'Number of players', fontsize = 16)
plt.show()
```


![png](output_12_0.png)



```python
plt.figure(figsize = (15, 8))
plt.style.use('_classic_test')

sns.countplot(x = 'work_rate', data = df, palette = 'hls')
plt.title('Distribution of Players based on their work rate', fontsize = 20)
plt.xlabel('Work rate', fontsize = 16)
plt.ylabel('Number of Players', fontsize = 16)
plt.show()
```


![png](output_13_0.png)



```python
plt.style.use('ggplot')
df['nationality'].value_counts().head(80).plot.bar(color = 'orange', figsize = (20, 7))
plt.title('Histogram of Players\' Nationality', fontsize = 30, fontweight = 20)
plt.xlabel('Name of The Country')
plt.ylabel('Number of Players')
plt.show()
```


![png](output_14_0.png)



```python
sns.set(style = "dark", palette = "colorblind", color_codes = True)
x = df.age
plt.figure(figsize = (15,8))
ax = sns.distplot(x, bins = 58, kde = False, color = 'g')
ax.set_xlabel(xlabel = "Player\'s age", fontsize = 16)
ax.set_ylabel(ylabel = 'Number of players', fontsize = 16)
ax.set_title(label = 'Histogram of Players\' Age', fontsize = 20)
plt.show()
```


![png](output_15_0.png)



```python
#Top 15 youngest players

df.sort_values('age', ascending = True)[['short_name', 'age', 'club', 'nationality']].head(15)
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
      <th>short_name</th>
      <th>age</th>
      <th>club</th>
      <th>nationality</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>18171</td>
      <td>J. Starbuck</td>
      <td>16</td>
      <td>Grimsby Town</td>
      <td>England</td>
    </tr>
    <tr>
      <td>4764</td>
      <td>A. Hložek</td>
      <td>16</td>
      <td>Sparta Praha</td>
      <td>Czech Republic</td>
    </tr>
    <tr>
      <td>18243</td>
      <td>E. Sartorius</td>
      <td>16</td>
      <td>Lincoln City</td>
      <td>England</td>
    </tr>
    <tr>
      <td>17827</td>
      <td>D. Burns</td>
      <td>16</td>
      <td>St. Patrick's Athletic</td>
      <td>Northern Ireland</td>
    </tr>
    <tr>
      <td>17614</td>
      <td>D. Obbekjær</td>
      <td>16</td>
      <td>Odense Boldklub</td>
      <td>Denmark</td>
    </tr>
    <tr>
      <td>17782</td>
      <td>S. Anderson</td>
      <td>16</td>
      <td>Colorado Rapids</td>
      <td>United States</td>
    </tr>
    <tr>
      <td>18242</td>
      <td>R. Wikberg</td>
      <td>16</td>
      <td>Östersunds FK</td>
      <td>Sweden</td>
    </tr>
    <tr>
      <td>18031</td>
      <td>O. Stefánsson</td>
      <td>16</td>
      <td>IFK Norrköping</td>
      <td>Iceland</td>
    </tr>
    <tr>
      <td>14626</td>
      <td>A. Velasco</td>
      <td>16</td>
      <td>Independiente</td>
      <td>Argentina</td>
    </tr>
    <tr>
      <td>12160</td>
      <td>S. Esposito</td>
      <td>16</td>
      <td>Inter</td>
      <td>Italy</td>
    </tr>
    <tr>
      <td>12158</td>
      <td>E. Millot</td>
      <td>16</td>
      <td>AS Monaco</td>
      <td>France</td>
    </tr>
    <tr>
      <td>6630</td>
      <td>Fábio Silva</td>
      <td>16</td>
      <td>FC Porto</td>
      <td>Portugal</td>
    </tr>
    <tr>
      <td>13979</td>
      <td>N. Wood</td>
      <td>17</td>
      <td>Middlesbrough</td>
      <td>England</td>
    </tr>
    <tr>
      <td>13981</td>
      <td>M. Olise</td>
      <td>17</td>
      <td>Reading</td>
      <td>France</td>
    </tr>
    <tr>
      <td>13987</td>
      <td>F. Tolomello</td>
      <td>17</td>
      <td>Trapani</td>
      <td>Italy</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Top 15 oldest players

df.sort_values('age', ascending = False)[['short_name', 'age', 'club', 'nationality']].head(15)
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
      <th>short_name</th>
      <th>age</th>
      <th>club</th>
      <th>nationality</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>13003</td>
      <td>H. Sulaimani</td>
      <td>42</td>
      <td>Al Ahli</td>
      <td>Saudi Arabia</td>
    </tr>
    <tr>
      <td>11832</td>
      <td>C. Muñoz</td>
      <td>42</td>
      <td>CD Universidad de Concepción</td>
      <td>Argentina</td>
    </tr>
    <tr>
      <td>200</td>
      <td>G. Buffon</td>
      <td>41</td>
      <td>Juventus</td>
      <td>Italy</td>
    </tr>
    <tr>
      <td>3706</td>
      <td>C. Lucchetti</td>
      <td>41</td>
      <td>Atlético Tucumán</td>
      <td>Argentina</td>
    </tr>
    <tr>
      <td>10665</td>
      <td>F. Kippe</td>
      <td>41</td>
      <td>Lillestrøm SK</td>
      <td>Norway</td>
    </tr>
    <tr>
      <td>868</td>
      <td>Hilton</td>
      <td>41</td>
      <td>Montpellier HSC</td>
      <td>Brazil</td>
    </tr>
    <tr>
      <td>2965</td>
      <td>Cifuentes</td>
      <td>40</td>
      <td>Cádiz CF</td>
      <td>Spain</td>
    </tr>
    <tr>
      <td>15812</td>
      <td>M. Gurski</td>
      <td>40</td>
      <td>SpVgg Unterhaching</td>
      <td>Germany</td>
    </tr>
    <tr>
      <td>8359</td>
      <td>F. Cubero</td>
      <td>40</td>
      <td>Vélez Sarsfield</td>
      <td>Argentina</td>
    </tr>
    <tr>
      <td>2963</td>
      <td>D. Dainelli</td>
      <td>40</td>
      <td>Livorno</td>
      <td>Italy</td>
    </tr>
    <tr>
      <td>14527</td>
      <td>D. Bulman</td>
      <td>40</td>
      <td>Crawley Town</td>
      <td>England</td>
    </tr>
    <tr>
      <td>6235</td>
      <td>J. Gillet</td>
      <td>40</td>
      <td>Standard de Liège</td>
      <td>Belgium</td>
    </tr>
    <tr>
      <td>10702</td>
      <td>M. Caranta</td>
      <td>40</td>
      <td>Club Atlético Talleres</td>
      <td>Argentina</td>
    </tr>
    <tr>
      <td>7230</td>
      <td>Lee Dong Gook</td>
      <td>40</td>
      <td>Jeonbuk Hyundai Motors</td>
      <td>Korea Republic</td>
    </tr>
    <tr>
      <td>1880</td>
      <td>C. Pizarro</td>
      <td>40</td>
      <td>SV Werder Bremen</td>
      <td>Peru</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Top 10 left footed footballers

df[df['preferred_foot'] == 'Left'][['short_name', 'age','overall' ,'club', 'nationality']].head(10)
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
      <th>short_name</th>
      <th>age</th>
      <th>overall</th>
      <th>club</th>
      <th>nationality</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>L. Messi</td>
      <td>32</td>
      <td>94</td>
      <td>FC Barcelona</td>
      <td>Argentina</td>
    </tr>
    <tr>
      <td>9</td>
      <td>M. Salah</td>
      <td>27</td>
      <td>90</td>
      <td>Liverpool</td>
      <td>Egypt</td>
    </tr>
    <tr>
      <td>16</td>
      <td>G. Chiellini</td>
      <td>34</td>
      <td>89</td>
      <td>Juventus</td>
      <td>Italy</td>
    </tr>
    <tr>
      <td>22</td>
      <td>A. Griezmann</td>
      <td>28</td>
      <td>89</td>
      <td>FC Barcelona</td>
      <td>France</td>
    </tr>
    <tr>
      <td>23</td>
      <td>P. Dybala</td>
      <td>25</td>
      <td>88</td>
      <td>Juventus</td>
      <td>Argentina</td>
    </tr>
    <tr>
      <td>25</td>
      <td>Ederson</td>
      <td>25</td>
      <td>88</td>
      <td>Manchester City</td>
      <td>Brazil</td>
    </tr>
    <tr>
      <td>28</td>
      <td>T. Courtois</td>
      <td>27</td>
      <td>88</td>
      <td>Real Madrid</td>
      <td>Belgium</td>
    </tr>
    <tr>
      <td>32</td>
      <td>H. Lloris</td>
      <td>32</td>
      <td>88</td>
      <td>Tottenham Hotspur</td>
      <td>France</td>
    </tr>
    <tr>
      <td>33</td>
      <td>David Silva</td>
      <td>33</td>
      <td>88</td>
      <td>Manchester City</td>
      <td>Spain</td>
    </tr>
    <tr>
      <td>40</td>
      <td>A. Laporte</td>
      <td>25</td>
      <td>87</td>
      <td>Manchester City</td>
      <td>France</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Top 10 Right footed footballers

df[df['preferred_foot'] == 'Right'][['short_name', 'age','overall' ,'club', 'nationality']].head(10)
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
      <th>short_name</th>
      <th>age</th>
      <th>overall</th>
      <th>club</th>
      <th>nationality</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>Cristiano Ronaldo</td>
      <td>34</td>
      <td>93</td>
      <td>Juventus</td>
      <td>Portugal</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Neymar Jr</td>
      <td>27</td>
      <td>92</td>
      <td>Paris Saint-Germain</td>
      <td>Brazil</td>
    </tr>
    <tr>
      <td>3</td>
      <td>J. Oblak</td>
      <td>26</td>
      <td>91</td>
      <td>Atlético Madrid</td>
      <td>Slovenia</td>
    </tr>
    <tr>
      <td>4</td>
      <td>E. Hazard</td>
      <td>28</td>
      <td>91</td>
      <td>Real Madrid</td>
      <td>Belgium</td>
    </tr>
    <tr>
      <td>5</td>
      <td>K. De Bruyne</td>
      <td>28</td>
      <td>91</td>
      <td>Manchester City</td>
      <td>Belgium</td>
    </tr>
    <tr>
      <td>6</td>
      <td>M. ter Stegen</td>
      <td>27</td>
      <td>90</td>
      <td>FC Barcelona</td>
      <td>Germany</td>
    </tr>
    <tr>
      <td>7</td>
      <td>V. van Dijk</td>
      <td>27</td>
      <td>90</td>
      <td>Liverpool</td>
      <td>Netherlands</td>
    </tr>
    <tr>
      <td>8</td>
      <td>L. Modrić</td>
      <td>33</td>
      <td>90</td>
      <td>Real Madrid</td>
      <td>Croatia</td>
    </tr>
    <tr>
      <td>10</td>
      <td>K. Mbappé</td>
      <td>20</td>
      <td>89</td>
      <td>Paris Saint-Germain</td>
      <td>France</td>
    </tr>
    <tr>
      <td>11</td>
      <td>K. Koulibaly</td>
      <td>28</td>
      <td>89</td>
      <td>Napoli</td>
      <td>Senegal</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Top 10 players with highest earnings

df.sort_values('wage_eur', ascending = False)[['short_name','wage_eur', 'age', 'club', 'nationality']].head(15)
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
      <th>short_name</th>
      <th>wage_eur</th>
      <th>age</th>
      <th>club</th>
      <th>nationality</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>L. Messi</td>
      <td>565000</td>
      <td>32</td>
      <td>FC Barcelona</td>
      <td>Argentina</td>
    </tr>
    <tr>
      <td>4</td>
      <td>E. Hazard</td>
      <td>470000</td>
      <td>28</td>
      <td>Real Madrid</td>
      <td>Belgium</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Cristiano Ronaldo</td>
      <td>405000</td>
      <td>34</td>
      <td>Juventus</td>
      <td>Portugal</td>
    </tr>
    <tr>
      <td>5</td>
      <td>K. De Bruyne</td>
      <td>370000</td>
      <td>28</td>
      <td>Manchester City</td>
      <td>Belgium</td>
    </tr>
    <tr>
      <td>22</td>
      <td>A. Griezmann</td>
      <td>370000</td>
      <td>28</td>
      <td>FC Barcelona</td>
      <td>France</td>
    </tr>
    <tr>
      <td>19</td>
      <td>L. Suárez</td>
      <td>355000</td>
      <td>32</td>
      <td>FC Barcelona</td>
      <td>Uruguay</td>
    </tr>
    <tr>
      <td>8</td>
      <td>L. Modrić</td>
      <td>340000</td>
      <td>33</td>
      <td>Real Madrid</td>
      <td>Croatia</td>
    </tr>
    <tr>
      <td>36</td>
      <td>T. Kroos</td>
      <td>330000</td>
      <td>29</td>
      <td>Real Madrid</td>
      <td>Germany</td>
    </tr>
    <tr>
      <td>17</td>
      <td>S. Agüero</td>
      <td>300000</td>
      <td>31</td>
      <td>Manchester City</td>
      <td>Argentina</td>
    </tr>
    <tr>
      <td>21</td>
      <td>Sergio Busquets</td>
      <td>300000</td>
      <td>30</td>
      <td>FC Barcelona</td>
      <td>Spain</td>
    </tr>
    <tr>
      <td>18</td>
      <td>Sergio Ramos</td>
      <td>300000</td>
      <td>33</td>
      <td>Real Madrid</td>
      <td>Spain</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Neymar Jr</td>
      <td>290000</td>
      <td>27</td>
      <td>Paris Saint-Germain</td>
      <td>Brazil</td>
    </tr>
    <tr>
      <td>46</td>
      <td>K. Benzema</td>
      <td>285000</td>
      <td>31</td>
      <td>Real Madrid</td>
      <td>France</td>
    </tr>
    <tr>
      <td>29</td>
      <td>Piqué</td>
      <td>285000</td>
      <td>32</td>
      <td>FC Barcelona</td>
      <td>Spain</td>
    </tr>
    <tr>
      <td>33</td>
      <td>David Silva</td>
      <td>265000</td>
      <td>33</td>
      <td>Manchester City</td>
      <td>Spain</td>
    </tr>
  </tbody>
</table>
</div>


