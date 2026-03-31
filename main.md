### #1 EDA
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
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 11789 entries, 0 to 11788
Data columns (total 25 columns):
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
