# Python and Data Analysis (PANDAS)
#### Terrado, Luke Nelson R.
#### 2ECE-A

## Description
This lesson teaches the use of Pandas in Python. Python Data Analysis is use in python to manipulate data and providing structure. This will teach on how to create two of the primary data structures, series, and data frame.

## Intended Learning Outcome
At the end of this laboratory activity, the student should be able to:
1. load a CSV dataset into a Pandas DataFrame;
2. select rows and columns using positional and label-based indexing;
3. filter records using conditions on a DataFrame column; and
4. extract a well-defined subset of data without changing the source data.

-----------------------------------------
## Download and Import
In Python, to import Pandas library, simply use ```import pandas as pd```. Using the given csv file called 'cars.csv', download the file and make sure that it is in the same location of the Jupyter notebook. To read the provided csv file, enter ```cars = pd.read_csv('cars.csv')``` inserted in a variable named 'cars'.

------------------------------------
## 1. POSITIONAL AND LABEL-BASED SLICING
After loading cars, complete the following operations.
- Display the shape and complete list of column names of cars.
- Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where
the first data row is row 1.
- From cars 6 to 10, display only the columns Model, mpg, cyl, hp, and gear, in that order.

### Code
```python
display(cars.shape) #To display the shape of cars
display(list(cars.columns)) #To display the list of columns

#Lists the cars from the row 6 to row 10
cars_6_to_10 = cars.iloc[5:10]
display(cars_6_to_10)

#Filters the list that contains row 6 to 10
filtering = cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']]
display(filtering)
```
### Explanation
The code displays the shape and the list of the columns that consists in the data frame provided. The syntax list() helps to organize the list of the name of each column. Next, the problem requires to list the cars from the row 6 to row 10, this uses the index location syntax to extract only the required rows. Finally, to choose what columns only shows in the output, call again the variable cars_6_to_10, followed by the column names that is asked in the problem.

------------------------------------
## 2. MODEL LOOKUP
Use Boolean indexing on the Model column to answer both requests.
- Display the complete row for Toyota Corolla.
- For Pontiac Firebird, display only Model, mpg, hp, and wt.
Store the two results in toyota and pontiac, respectively. Do not use a hard-coded row number to
locate either model.

### Code
```python
#Displays the complete row for Toyota Corolla
toyota = cars.loc[(cars['Model'] == 'Toyota Corolla'), :]
display(toyota)

#Displays only selected columns
pontiac = cars.loc[(cars['Model']=='Pontiac Firebird'), ['Model', 'mpg', 'hp', 'wt']]
display(pontiac)
```
### Explanation
The code displays the complete row where the Toyota Corolla is located. It will use Boolean indexing to find the model of Toyota in the column named 'Model'. To display a selected column, the code locates the model of the car "Pontiac Firebird" and define which columns to display.

--------------------------------
## 3. MULTI-MODEL SUBSETTING
Create a DataFrame named selected cars containing only the records for three models: Datsun 710,
Lotus Europa, and Ferrari Dino.
For these records, retain only Model, mpg, cyl, hp, and gear. Select the rows by their model values
rather than by row numbers. Display selected cars and its shape.

### Code
```python
#Creates a dataframe that contains selected rows and column
selected_cars = pd.DataFrame(cars.loc[[2,27,29]], columns=['Model', 'mpg', 'cyl', 'hp', 'gear'])

display(selected_cars) #Displays the dataframe that consists of selected cars
display(selected_cars.shape) #Displays the shape of the dataframe
```
### Explanation
The code creates a data frame which uses row positioning to locate the cars from the problem. The code is then gone through a filter to output the requested columns. Then it displays the variable which the data frame for the selected cars is. Finally, it displays the shape of the car, which returns (3, 5) dimension.

-------------------------------------
## Changes
1. Added detailed information about the problems and an explanation of each program (09/15/2026)
2. Uploaded the Jupyter File and the csv file that contains the cars information (09/15/2026)
