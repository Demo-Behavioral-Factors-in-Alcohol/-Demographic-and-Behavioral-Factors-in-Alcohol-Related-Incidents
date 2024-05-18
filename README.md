# Car Accidents and Alcohol-Related Deaths Dataset

## Overview

This dataset contains information on individuals, including their age, gender, education level, involvement in car accidents, and whether their deaths were related to alcohol. It is intended to facilitate analysis of potential correlations between demographic factors and incidents related to car accidents and alcohol-related deaths.

## Dataset Structure

The dataset includes the following columns:

- **Age**: Age of the individual (in years).
- **Gender**: Gender of the individual (Male/Female).
- **Education Level**: The highest level of education attained by the individual (High School, Bachelor's, Master's, Doctorate).
- **Car Accidents**: Indicates whether the individual was involved in a car accident (Yes/No).
- **Deaths by Alcohol**: Indicates whether the individual's death was related to alcohol (Yes/No).

## Sample Data

```plaintext
| Age | Gender | Education Level | Car Accidents | Deaths by Alcohol |
|-----|--------|-----------------|---------------|-------------------|
| 25  | Male   | High School     | Yes           | No                |
| 42  | Female | Bachelor's      | No            | Yes               |
| 35  | Male   | Master's        | Yes           | Yes               |
| 50  | Male   | Doctorate       | No            | No                |
| 28  | Female | High School     | Yes           | No                |
...







import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load the dataset
data = pd.read_csv('car_accidents_alcohol_deaths.csv')

# Count of car accidents by education level
accidents_by_education = data.groupby('Education Level')['Car Accidents'].value_counts().unstack().fillna(0)
print("Count of Car Accidents by Education Level:")
print(accidents_by_education)

# Gender distribution in alcohol-related deaths
gender_alcohol_deaths = data[data['Deaths by Alcohol'] == 'Yes']['Gender'].value_counts()
print("Gender Distribution in Alcohol-Related Deaths:")
print(gender_alcohol_deaths)

# Bar plot of Car Accidents by Education Level
plt.figure(figsize=(10, 6))
sns.countplot(x='Education Level', hue='Car Accidents', data=data)
plt.title('Car Accidents by Education Level')
plt.xlabel('Education Level')
plt.ylabel('Count')
plt.legend(title='Car Accidents', loc='upper right')
plt.show()

# Pie chart of Alcohol-Related Deaths by Gender
plt.figure(figsize=(8, 8))
gender_alcohol_deaths.plot.pie(autopct='%1.1f%%', startangle=140)
plt.title('Alcohol-Related Deaths by Gender')
plt.ylabel('')
plt.show()





