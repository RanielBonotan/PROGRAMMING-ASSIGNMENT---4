### PROGRAMMING-ASSIGNMENT 4

#### PROBLEM 1 
We are tasked to: a. Create a dataframe containing the following items: Name, GEAS, Electronics whose grades are over 70, and has the limitation of only Instrumentation as their track and Luzon as ther Hometown and b. Create a dataframe containing the following items: Name, Track, Electronics, an Average whose grade is greater than or equal to 55, and has the limitation of only Female as their gender and Mindanao as ther Hometown

#### Problem 2 
We are tasked to create visualization charts taht will show how different attriibutes such as tracks, gender, or hometown affect their average score.

Problem 1

a.

1. I first imported pandas as pd as well as imported the .csv file to be extracted for the dataframe
```python
import pandas as pd #imports pandas to be able to use the file

boardexam = pd.read_csv("board2.csv") #imports the file
boardexam
```

2. I then renamed the previous "boardexam" to "Instru" to match the objective. Furthermore, I added the limitations of what the dataframe should include from the previous dataframe as well as listed the columns and their rows that should be displayed
```python
Instru = boardexam.loc[ (boardexam.Electronics > 70) & 
(boardexam.Hometown == "Luzon")&
(boardexam.Track == "Instrumentation"),
["Name", "GEAS", "Electronics"]
]
Instru # makes a name "Instru" where it is limited to the conditions set as well as what information it holds originating from the table
```

b.

1. I first added a new column to the previous data fram containing the average scores of each student in the grades of their subjects.
```python
boardexam["Average"] = boardexam[["Math", "Electronics", "GEAS", "Communication"]].mean(axis=1)
boardexam # Adds a column named "Average" containing the average grades between Math, Electronics, GEAS, and Communication of the students
```

2. I then renamed the previous "boardexam" to "Mindy" to match the objective. Furthermore, I added the limitations of what the dataframe should include from the previous dataframe as well as listed the columns and their rows that should be displayed
```python
Mindy = boardexam.loc[ (boardexam.Gender == "Female") &
(boardexam.Hometown == "Mindanao")&
(boardexam.Average >= 55),
["Name", "Track", "Electronics", "Average"]
]
Mindy # makes a name "Mindy" where it is limited to the conditions set, as well as what information it holds, originating from the table
```

Problem 2
1. I first imported matplotlib so I am able to vreate visual charts for the dataframe
```python
import matplotlib.pyplot as plt
```

2. I then went on to use bar as the visual charts for each comparisons
```python

plt.bar(boardexam['Track'], boardexam['Average']) #adds a bar plot of the averages of the different tracks

plt.bar(boardexam['Gender'], boardexam['Average']) #adds a bar plot of the averages of the different genders

plt.bar(boardexam['Hometown'], boardexam['Average']) #adds a bar plot of the averages of the different Hometown
```



