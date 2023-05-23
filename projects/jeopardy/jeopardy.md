1. A csv file containing data about the game show _Jeopardy!_ in a file named `jeopardy.csv`. 
Load the data into a DataFrame and investigate its contents. Try to print out specific columns.
Note that data hasn't been treated at all - we're giving it to you exactly how we found it. 
As a result, this data isn't as "clean" as the datasets you normally find on Codecademy. 
More specifically, there's something odd about the column names. 
After you figure out the problem with the column names, you may want to rename them to make your life easier for the rest of the project.
``` python  
import pandas as pd
pd.set_option('display.max_colwidth', None)

# Loading the data and investigating it
jeopardy_data = pd.read.csv("jeopardy.csv")
print(jeopardy_data.columns)

# Renaming misformatted columns
jeopardy_data = jeopardy_data.rename(columns = {" Air Date": "Air Date", " Round" : "Round", " Category": "Category", " Value": "Value", " Question":"Question", " Answer": "Answer"})
print(jeopardy_data.columns)
print(jeopardy_data["Question"])
```
2. Write a function that filters the dataset for questions that contains all of the words in a list of words. 
For example, when the list `["King", "England"]` was passed to our function, the function returned a DataFrame of 49 rows. 
Every row had the strings `"King"` and `"England"` somewhere in its `" Question"`.
Test your function by printing out the column containing the question of each row of the dataset.

