# The Weather Dataset
### Big Data Analysis with Python
<p> 
The Weather Dataset is a time-series dataset with per-hour information about the conditions at a particular location.
<p>

### Importing Pandas Library

import pandas as pd 

### Importing data from csv file

data = pd.read_csv(r"F:\anaconda\Weather with Pandas\Weather.csv")

data

## Exploring the Dataset 

### .head()

data.head(5)

### .shape

data.shape

### .index

data.index

### .columns

data.columns

### .dtypes

data.dtypes

### .unique

data['Weather'].unique()

### .nunique()

data['Weather'].nunique()

### .count() 

data.count()

### .value_counts()

data['Weather'].value_counts()

### .info()

data.info()

### Q-1 Find all the unique "Wind Speed" values in the data.

data.head(2)

data.nunique()

data['Wind Speed_km/h'].nunique()

data['Wind Speed_km/h'].unique()

### Q-2 Find the number of times when the "Weathe is exactly Clear"

data.head(2)

data.Weather.value_counts()

data[data.Weather == 'Clear']

data.groupby('Weather').get_group('Clear')

## Q-3 Find the number of times when the "Wind Speed is exactly 4km/h" 

data.head(2)

data[data['Wind Speed_km/h'] == 4]

data[data['Wind Speed_km/h'] == 4]

## Q-4 Find out all the null vlaues in the data

data.isnull().sum()

data.notnull().sum()

## Q-5 Rename the column name "Weather" of the Dataframe to "Weather Condition"

data.rename(columns = {'Weather' : 'Weather Condition'})

## Q-6 What is the mean "Visibility"

data.Visibility_km.mean()

## Q-7 What is the standard deviation of "Pressure" in this data

data.Press_kPa.std()

## Q-8 What is the variance of "Relative Humidity" is this data

data['Rel Hum_%'].var()

## Q-9 Find all instances when "Snow" was recorded

data['Weather'].value_counts()

data[data['Weather'] == 'Snow']

data.groupby('Weather').get_group('Snow')

data[data['Weather'].str.contains('Snow')]

## Q-10 Find all instances when "Wind Speed is above 24" and "Visibilty is 25"

data.tail(30)

data[(data['Wind Speed_km/h'] > 24) & (data['Visibility_km']  == 25)]

## Q-11 What is the mean value of each column against each "Weather"?

data.groupby('Weather').mean()

## Q-12 What is the minimum and maximum value of each column against each "Weather"?

data['Weather'].value_counts().min()

data['Weather'].value_counts().max()

## Q-13 Show all the records where "Weather" is Fog

data[data['Weather'] == 'Fog']

## Q-14 Find all instances when "Weather is Clear" and "Visibilty is above 40"

data[(data['Weather'] == 'Clear') & (data['Visibility_km'] > 40)]

## Q-15 Find the all instances when:

#### A. 'Weather is Clear' and 'Relative humidity is greater than 50'
#### or
#### B. 'Visibility is above 40'

data.head(2)

data[(data['Weather'] == 'Clear') & (data['Rel Hum_%'] > 50) | (data['Visibility_km'] > 40)]

