### Phase 1: EDA
Importing required libraries for EDA
```py
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
```
Pulling dataset using pandas
```py
df = pd.read_csv(r'')
```
```py
df.info()

 #   Column                       Non-Null Count  Dtype  
---  ------                       --------------  -----  
 0   age                          11789 non-null  int64  
 1   monthly_income               11789 non-null  int64  
 2   daily_internet_hours         11789 non-null  float64
 3   smartphone_usage_years       11789 non-null  int64  
 4   social_media_hours           11789 non-null  float64
 5   online_payment_trust_score   11789 non-null  int64  
 6   tech_savvy_score             11789 non-null  int64  
 7   monthly_online_orders        11789 non-null  int64  
 8   monthly_store_visits         11789 non-null  int64  
 9   avg_online_spend             11789 non-null  int64  
 10  avg_store_spend              11789 non-null  int64  
 11  discount_sensitivity         11789 non-null  int64  
 12  return_frequency             11789 non-null  int64  
 13  avg_delivery_days            11789 non-null  int64  
 14  delivery_fee_sensitivity     11789 non-null  int64  
 15  free_return_importance       11789 non-null  int64  
 16  product_availability_online  11789 non-null  int64  
 17  impulse_buying_score         11789 non-null  int64  
 18  need_touch_feel_score        11789 non-null  int64  
 19  brand_loyalty_score          11789 non-null  int64  
 20  environmental_awareness      11789 non-null  int64  
 21  time_pressure_level          11789 non-null  int64  
 22  gender                       11789 non-null  object 
 23  city_tier                    11789 non-null  object 
 24  shopping_preference          11789 non-null  object 
dtypes: float64(2), int64(20), object(3)
memory usage: 2.2+ MB
```
```py
df.isna().sum().sort_values(ascending=True)
age                            0
monthly_income                 0
daily_internet_hours           0
smartphone_usage_years         0
social_media_hours             0
online_payment_trust_score     0
tech_savvy_score               0
monthly_online_orders          0
monthly_store_visits           0
avg_online_spend               0
avg_store_spend                0
discount_sensitivity           0
return_frequency               0
avg_delivery_days              0
delivery_fee_sensitivity       0
free_return_importance         0
product_availability_online    0
impulse_buying_score           0
need_touch_feel_score          0
brand_loyalty_score            0
environmental_awareness        0
time_pressure_level            0
gender                         0
city_tier                      0
shopping_preference            0
dtype: int64
```
```py
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
      <th>age</th>
      <th>monthly_income</th>
      <th>daily_internet_hours</th>
      <th>smartphone_usage_years</th>
      <th>social_media_hours</th>
      <th>online_payment_trust_score</th>
      <th>tech_savvy_score</th>
      <th>monthly_online_orders</th>
      <th>monthly_store_visits</th>
      <th>avg_online_spend</th>
      <th>...</th>
      <th>free_return_importance</th>
      <th>product_availability_online</th>
      <th>impulse_buying_score</th>
      <th>need_touch_feel_score</th>
      <th>brand_loyalty_score</th>
      <th>environmental_awareness</th>
      <th>time_pressure_level</th>
      <th>gender</th>
      <th>city_tier</th>
      <th>shopping_preference</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>11789.000000</td>
      <td>11789.000000</td>
      <td>11789.000000</td>
      <td>11789.000000</td>
      <td>11789.000000</td>
      <td>11789.000000</td>
      <td>11789.000000</td>
      <td>11789.000000</td>
      <td>11789.000000</td>
      <td>11789.000000</td>
      <td>...</td>
      <td>11789.000000</td>
      <td>11789.000000</td>
      <td>11789.000000</td>
      <td>11789.000000</td>
      <td>11789.000000</td>
      <td>11789.000000</td>
      <td>11789.000000</td>
      <td>11789</td>
      <td>11789</td>
      <td>11789</td>
    </tr>
    <tr>
      <th>unique</th>
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
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3</td>
      <td>3</td>
      <td>3</td>
    </tr>
    <tr>
      <th>top</th>
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
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Male</td>
      <td>Tier 1</td>
      <td>Store</td>
    </tr>
    <tr>
      <th>freq</th>
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
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3966</td>
      <td>3982</td>
      <td>10244</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>48.729409</td>
      <td>131704.282382</td>
      <td>6.011367</td>
      <td>7.597930</td>
      <td>2.514471</td>
      <td>5.498770</td>
      <td>5.534312</td>
      <td>24.677581</td>
      <td>9.482144</td>
      <td>74554.929341</td>
      <td>...</td>
      <td>5.462041</td>
      <td>5.518704</td>
      <td>5.486386</td>
      <td>5.485368</td>
      <td>5.532021</td>
      <td>5.448554</td>
      <td>5.504114</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>std</th>
      <td>17.899445</td>
      <td>68120.726684</td>
      <td>1.976811</td>
      <td>4.011628</td>
      <td>1.263047</td>
      <td>2.880366</td>
      <td>2.887251</td>
      <td>14.431277</td>
      <td>5.728825</td>
      <td>43167.126595</td>
      <td>...</td>
      <td>2.882177</td>
      <td>2.867613</td>
      <td>2.877918</td>
      <td>2.877264</td>
      <td>2.848796</td>
      <td>2.872740</td>
      <td>2.876561</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>min</th>
      <td>18.000000</td>
      <td>15005.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>523.000000</td>
      <td>...</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>33.000000</td>
      <td>72450.000000</td>
      <td>4.600000</td>
      <td>4.000000</td>
      <td>1.600000</td>
      <td>3.000000</td>
      <td>3.000000</td>
      <td>12.000000</td>
      <td>5.000000</td>
      <td>36797.000000</td>
      <td>...</td>
      <td>3.000000</td>
      <td>3.000000</td>
      <td>3.000000</td>
      <td>3.000000</td>
      <td>3.000000</td>
      <td>3.000000</td>
      <td>3.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>49.000000</td>
      <td>131916.000000</td>
      <td>6.000000</td>
      <td>8.000000</td>
      <td>2.500000</td>
      <td>5.000000</td>
      <td>6.000000</td>
      <td>25.000000</td>
      <td>9.000000</td>
      <td>74859.000000</td>
      <td>...</td>
      <td>5.000000</td>
      <td>6.000000</td>
      <td>5.000000</td>
      <td>5.000000</td>
      <td>6.000000</td>
      <td>5.000000</td>
      <td>6.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>64.000000</td>
      <td>190505.000000</td>
      <td>7.400000</td>
      <td>11.000000</td>
      <td>3.400000</td>
      <td>8.000000</td>
      <td>8.000000</td>
      <td>37.000000</td>
      <td>14.000000</td>
      <td>112134.000000</td>
      <td>...</td>
      <td>8.000000</td>
      <td>8.000000</td>
      <td>8.000000</td>
      <td>8.000000</td>
      <td>8.000000</td>
      <td>8.000000</td>
      <td>8.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>max</th>
      <td>79.000000</td>
      <td>249989.000000</td>
      <td>12.000000</td>
      <td>14.000000</td>
      <td>6.000000</td>
      <td>10.000000</td>
      <td>10.000000</td>
      <td>49.000000</td>
      <td>19.000000</td>
      <td>149996.000000</td>
      <td>...</td>
      <td>10.000000</td>
      <td>10.000000</td>
      <td>10.000000</td>
      <td>10.000000</td>
      <td>10.000000</td>
      <td>10.000000</td>
      <td>10.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>11 rows × 25 columns</p>
</div>

```py
df.shape
(11789, 25)
```
```py
fig, axes = plt.subplots(figsize=(15, 15))

df.hist(ax=axes) 
plt.show()
```
<Figure size 1500x1500 with 25 Axes><img width="1245" height="1221" alt="image" src="https://github.com/user-attachments/assets/5292b2ec-7d2c-48a3-a702-5360a86bb4e9" />
