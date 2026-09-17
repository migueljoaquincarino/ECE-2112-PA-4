# ECE-2112-PA-4
Miguel Joaquin T. Carino
# Programming Assingment 4
Before starting the Programming assingment pandas library was called as pd and later on matplotlib will be called as plt
```python
  import pandas as pd
```
```python
  import matplotlib.pyplot as plt
```
In assigning Average we assign it by calling eceboard2 data set and calling certain columns(subject) that whould be use in getting the mean average of these specified columns
```python
  eceboard2['Average'] = eceboard2[['Math', 'GEAS', 'Electronics', 'Communication']].mean(axis=1)
```
## A. Visayas Communication Dataframe
## Objective
The objective of this problem is to create a new Dataframe in which contains students whose hometown is from Visayas, and whose track is communication. While only retaining specified columns
## Discussion
The Viscomm DataFrame is filtered using two conditions which are: The student's hometown must be from Visayas, and whose track is communications.
```python
Viscomm = eceboard2.loc[(eceboard2['Hometown'] == 'Visayas')& 
                        (eceboard2['Track'] == 'Communication')]
```
The Dataframe is then returned only retaining specified columns and also displaying its number of rows.
```python
Viscomm[['Name', 'Gender', 'Math', 'Electronics', 'Average']]
```
## B. Visayas Female Dataframe
## Objective
The objective of this problem is to create a second DataFrame containing students whose hometown is from Visayas and whose gender is a Female. 
## Discussion
The Viscomm DataFrame is filtered using three conidtions which are: The student's hometown must be from visayas, gender must be a female, and their average must be atleast 60.
```python
VisFemale = eceboard2.loc[(eceboard2['Hometown'] == 'Visayas')& 
                (eceboard2['Gender'] == 'Female')&
                (eceboard2['Average']>=60)]
```
VisFemale Dataframe is returned retaining only specified columns. 
```python
VisFemale[['Name', 'Track', 'GEAS', 'Electronics', 'Average']]
```
## C. Visayas Communication Dataframe
## Objective

## Discussion
