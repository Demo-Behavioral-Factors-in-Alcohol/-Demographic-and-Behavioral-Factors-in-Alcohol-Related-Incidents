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

## Load the dataset
data = pd.read_csv('car_accidents_alcohol_deaths.csv')

