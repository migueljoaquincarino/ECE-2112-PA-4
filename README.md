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
The objective of this problem is to examine how the recorded Average differs across the categorical features Track, Gender, and Hometown by calculating the mean Average for each category and presenting the comparisons through bar charts.
## Discussion
The mean Average for each category of Track, Gender, and Hometown is calculated using Pandas groupby and mean. The results are stored in separate DataFrames for each categorical feature.
```python
track_avg = eceboard2.groupby('Track')['Average'].mean().reset_index()
gender_avg = eceboard2.groupby('Gender')['Average'].mean().reset_index()
hometown_avg = eceboard2.groupby('Hometown')['Average'].mean().reset_index()
```
The three summary tables are then displayed to show the calculated mean Average for every category.
```python
display(track_avg)
display(gender_avg)
display(hometown_avg)
```
```python
A figure containing three bar charts is created to compare the mean Average by Track, Gender, and Hometown. Each chart is given a title and axis labels to clearly identify the data being presented.
plt.figure(figsize=(20,10))
plt.subplot(1,3,1)
plt.bar(track_avg['Track'], track_avg['Average'])
plt.title('By Track')
plt.xlabel("Track")
plt.ylabel('Mean')

plt.subplot(1,3,2)
plt.bar(gender_avg['Gender'], gender_avg['Average'])
plt.title('By Gender')
plt.xlabel("Gender")
plt.ylabel('Mean')

plt.subplot(1,3,3)
plt.bar(hometown_avg['Hometown'], hometown_avg['Average'])
plt.title('By Hometown')
plt.xlabel("Hometown")
plt.ylabel('Mean')

plt.text(-8,-6, 'The track with the highest mean average of the three is Communication.',)
plt.text(-8,-8, 'The Gender with the highest mean average is Male.',)
plt.text(-8,-10, 'The Hometown with the highest mean average of the the three islands is Luzon.',)

plt.show()
```
## Version History
