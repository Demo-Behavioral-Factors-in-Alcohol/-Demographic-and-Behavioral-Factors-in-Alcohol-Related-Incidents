import pandas as pd

# Load the dataset
data = pd.read_csv('data.csv')

# Display the first few rows of the dataset
print(data.head())

# Example analysis: Count of car accidents by education level
accidents_by_education = data.groupby('Education Level')['Car Accidents'].value_counts().unstack()
print(accidents_by_education)

# Example analysis: Count of alcohol-related deaths by gender
deaths_by_gender = data.groupby('Gender')['Deaths by Alcohol'].value_counts().unstack()
print(deaths_by_gender)
