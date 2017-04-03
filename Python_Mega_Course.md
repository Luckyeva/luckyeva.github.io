
# Python Mega Course 

Apr 2, 2017

I took this 22 hours training course on Udemy.com. The instructor Ardit Sulce is a Python and GIS expert who founded PythonHow.com. 

As I get more inolved in web development and applications of machine learning, Python quickly became a must-have skill set for me to go to the next level. So I found this course very useful because it covers web, databases, web scraping, data science, web visualizations, and image processing. I may still use R for general data mining and modeling, but Python will provide more functionalities in terms of creating applications and programs.

I will share my learning here in the following sections.

## Part I
## Getting Started with Python

One should be able to download the latest Python on python.org. There's no need to delete the old version if you've installed Python 2 before. 

The author recommend the use of Atom editor which works well for application development. He recommend Jupyter though for data analysis in particular. 

What's quite interesting is the use of a terminal IDE inside Atom - if you type 'python3' in the command line editor, you'll be able to load Python 3.6 directly in the command window. That's what works for Mac OS. For Windows, a quick trick is to change the file name of python.exe into Python36.exe and then call python36 instead of python, so as to avoid opening the old Python 2.7.x. To exit the python in the terminal, simply type 'exit()'.

If you created a '*.py' file, you can execute it using command line 'python3 *.py'. This is quite convenient to store code in a .py file and then execute it in the terminal IDE all in one place.

## Part II
## Variables, Datatypes, and Functions

I believe there are more variable types in Python than what I've learned here. But the basic variables are:

* integer, e.g. 3, 5, 200; to define an integer use 'int()'
* float, e.g. 2,0, 101.67; to define a float variable, use 'float()'
* string, e.g. "abc"; to define a string, use 'str()'

There are may Datatypes also, one may use function type() to check the datatype of any objects, so to speak. There are 

* list
* tuples
* dictionaries

NOTE here the index of items in a list or in a string variable is quite different from R. In R, we start from 1 whereas in Python, the counting starts at 0. For example


```python
a = "Super cool dude!"
a[0]
```




    'S'




```python
a[0:1]
```




    'S'




```python
a[1]
```




    'u'




```python
a[2]
```




    'p'




```python
a[-1]
```




    '!'




```python
a[0:6]
```




    'Super '




```python
a[6]
```




    'c'



Index can be tricky for a beginner like me.

The course also covered some basic math functions, mostly basic operations like the following. 


```python
100 + 20*5**2/4
```




    225




```python
50 % 7 # this is the remainder of 50/7
```




    1




```python
50/7 # in Python 2.7, this calculation returns integer while in Python 3, it gives a float variable.
```




    7



The instructor didn't go much further into math which means I'll probably hae to pick it up from other sources later.

## Part III
## Logic Expressions and Loops

This is relatively simple because  most of the functions are similar to R. The major differences is the replacement of brakets with indentation to indicate code blocks, and the additional use of ":" in Python. For example


```python
for i in range(5):
    print "t=",i
```

    t= 0
    t= 1
    t= 2
    t= 3
    t= 4



```python
a = 99

if a > 99:
    print "Number a is greater than 99"
elif a == 99:
    print 'Number a is equal to 99'
else:
    print "Number a is smaller than 99"
```

    Number a is equal to 99


## Part IV
## User Inputs and File Handling

User inputs are quite fun as it adds interactive components to the program we create. Jupyter handle some of the user inputs as the follows but it doesn't seem to work in other situations.


```python
age = input("How old are you? ")
```

    How old are you? 60



```python
age
```




    60



Reading and writing *.txt files is very cool. There are several key commands for example, to read a txt file,


```python
file = open("example.txt", 'w')

file.write("Line 1\n")
file.write("Line 2")

file.close() # the changes can only be seen after closing the file
```

## Part V
## More Functionalities

## Part VI
## Data Analysis with Pandas

Pandas is a library providing data structure and data analysis tools within Python. It allows you to load data from different sources and store them in the forms of tables, text or dataframes. To install pandas, enter 'pip3 install pandas', and it will be automatically installed to your computer. See more details about Pandas at pandas.pydata.org


```python
import pandas

df = pandas.DataFrame([[1, 5, 8], [3,6,9], [7,4,2]], columns = ["Quantity", "Price", "Cost"])
df.mean()
```




    Quantity    3.666667
    Price       5.000000
    Cost        6.333333
    dtype: float64




```python
df.max()
```




    Quantity    7
    Price       6
    Cost        9
    dtype: int64



### Reading data
In the following session, we will code to import data from various data sources.


```python
import os
os.getcwd()
```




    '/Users/lucky1eva/Python notes'




```python
os.listdir('/Users/lucky1eva/Python notes')
```




    ['.ipynb_checkpoints',
     '2017-04-02-12-04-39',
     '__pycache__',
     'app1-text-generator.py',
     'conditionals.py',
     'example.txt',
     'example2.txt',
     'example3.txt',
     'Import-data-using-Pandas.ipynb',
     'Issues_copy.txt',
     'Lecture notes (1).ipynb',
     'Lecture Notes - Python Numpy - Chapter 2 .ipynb',
     'Lecture notes.ipynb',
     'myconditionals.py',
     'myfunction.py',
     'myfunction2.py',
     'myfunction3.py',
     'myloop.py',
     'myloop2.py',
     'myloop3.py',
     'myprogram.py',
     'myprogram2.py',
     'myprogram3.py',
     'myprogram4.py',
     'name_gen.py',
     'openfiles.py',
     'Python Mega Course.ipynb',
     'R Programming Notes-Copy1.ipynb',
     'R Programming Notes.ipynb',
     'supermarkets-commas.txt',
     'supermarkets-semi-colons.txt',
     'supermarkets.csv',
     'supermarkets.json',
     'supermarkets.xlsx',
     'user_input.py']




```python
import pandas

df1=pandas.read_csv("supermarkets.csv")
df1
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Address</th>
      <th>City</th>
      <th>State</th>
      <th>Country</th>
      <th>Name</th>
      <th>Employees</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>3666 21st St</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Madeira</td>
      <td>8</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>735 Dolores St</td>
      <td>San Francisco</td>
      <td>CA 94119</td>
      <td>USA</td>
      <td>Bready Shop</td>
      <td>15</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>332 Hill St</td>
      <td>San Francisco</td>
      <td>California 94114</td>
      <td>USA</td>
      <td>Super River</td>
      <td>25</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>3995 23rd St</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Ben's Shop</td>
      <td>10</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>1056 Sanchez St</td>
      <td>San Francisco</td>
      <td>California</td>
      <td>USA</td>
      <td>Sanchez</td>
      <td>12</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>551 Alvarado St</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Richvalley</td>
      <td>20</td>
    </tr>
  </tbody>
</table>
</div>




```python
df1.set_index("ID") # this set ID as index
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Address</th>
      <th>City</th>
      <th>State</th>
      <th>Country</th>
      <th>Name</th>
      <th>Employees</th>
    </tr>
    <tr>
      <th>ID</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>3666 21st St</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Madeira</td>
      <td>8</td>
    </tr>
    <tr>
      <th>2</th>
      <td>735 Dolores St</td>
      <td>San Francisco</td>
      <td>CA 94119</td>
      <td>USA</td>
      <td>Bready Shop</td>
      <td>15</td>
    </tr>
    <tr>
      <th>3</th>
      <td>332 Hill St</td>
      <td>San Francisco</td>
      <td>California 94114</td>
      <td>USA</td>
      <td>Super River</td>
      <td>25</td>
    </tr>
    <tr>
      <th>4</th>
      <td>3995 23rd St</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Ben's Shop</td>
      <td>10</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1056 Sanchez St</td>
      <td>San Francisco</td>
      <td>California</td>
      <td>USA</td>
      <td>Sanchez</td>
      <td>12</td>
    </tr>
    <tr>
      <th>6</th>
      <td>551 Alvarado St</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Richvalley</td>
      <td>20</td>
    </tr>
  </tbody>
</table>
</div>




```python
df2=pandas.read_json("supermarkets.json")
df2.set_index("ID")
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Address</th>
      <th>City</th>
      <th>Country</th>
      <th>Employees</th>
      <th>Name</th>
      <th>State</th>
    </tr>
    <tr>
      <th>ID</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>3666 21st St</td>
      <td>San Francisco</td>
      <td>USA</td>
      <td>8</td>
      <td>Madeira</td>
      <td>CA 94114</td>
    </tr>
    <tr>
      <th>2</th>
      <td>735 Dolores St</td>
      <td>San Francisco</td>
      <td>USA</td>
      <td>15</td>
      <td>Bready Shop</td>
      <td>CA 94119</td>
    </tr>
    <tr>
      <th>3</th>
      <td>332 Hill St</td>
      <td>San Francisco</td>
      <td>USA</td>
      <td>25</td>
      <td>Super River</td>
      <td>California 94114</td>
    </tr>
    <tr>
      <th>4</th>
      <td>3995 23rd St</td>
      <td>San Francisco</td>
      <td>USA</td>
      <td>10</td>
      <td>Ben's Shop</td>
      <td>CA 94114</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1056 Sanchez St</td>
      <td>San Francisco</td>
      <td>USA</td>
      <td>12</td>
      <td>Sanchez</td>
      <td>California</td>
    </tr>
    <tr>
      <th>6</th>
      <td>551 Alvarado St</td>
      <td>San Francisco</td>
      <td>USA</td>
      <td>20</td>
      <td>Richvalley</td>
      <td>CA 94114</td>
    </tr>
  </tbody>
</table>
</div>




```python
df3=pandas.read_excel("supermarkets.xlsx", sheetname=0)
df3
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Address</th>
      <th>City</th>
      <th>State</th>
      <th>Country</th>
      <th>Supermarket Name</th>
      <th>Number of Employees</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>3666 21st St</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Madeira</td>
      <td>8</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>735 Dolores St</td>
      <td>San Francisco</td>
      <td>CA 94119</td>
      <td>USA</td>
      <td>Bready Shop</td>
      <td>15</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>332 Hill St</td>
      <td>San Francisco</td>
      <td>California 94114</td>
      <td>USA</td>
      <td>Super River</td>
      <td>25</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>3995 23rd St</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Ben's Shop</td>
      <td>10</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>1056 Sanchez St</td>
      <td>San Francisco</td>
      <td>California</td>
      <td>USA</td>
      <td>Sanchez</td>
      <td>12</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>551 Alvarado St</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Richvalley</td>
      <td>20</td>
    </tr>
  </tbody>
</table>
</div>




```python
df5=pandas.read_csv("supermarkets-semi-colons.txt", sep=';')
df5
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Address</th>
      <th>City</th>
      <th>State</th>
      <th>Country</th>
      <th>Name</th>
      <th>Employees</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>3666 21st St</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Madeira</td>
      <td>8</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>735 Dolores St</td>
      <td>San Francisco</td>
      <td>CA 94119</td>
      <td>USA</td>
      <td>Bready Shop</td>
      <td>15</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>332 Hill St</td>
      <td>San Francisco</td>
      <td>California 94114</td>
      <td>USA</td>
      <td>Super River</td>
      <td>25</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>3995 23rd St</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Ben's Shop</td>
      <td>10</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>1056 Sanchez St</td>
      <td>San Francisco</td>
      <td>California</td>
      <td>USA</td>
      <td>Sanchez</td>
      <td>12</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>551 Alvarado St</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Richvalley</td>
      <td>20</td>
    </tr>
  </tbody>
</table>
</div>



Notice that the indexing of sheets in the excel file also starts from 0.

In the code below, we'll learn the indexing and slicing of dataframes. 

### Indexing and Slicing

We can use any column as index. For example


```python
df5.set_index("Address")
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>City</th>
      <th>State</th>
      <th>Country</th>
      <th>Name</th>
      <th>Employees</th>
    </tr>
    <tr>
      <th>Address</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3666 21st St</th>
      <td>1</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Madeira</td>
      <td>8</td>
    </tr>
    <tr>
      <th>735 Dolores St</th>
      <td>2</td>
      <td>San Francisco</td>
      <td>CA 94119</td>
      <td>USA</td>
      <td>Bready Shop</td>
      <td>15</td>
    </tr>
    <tr>
      <th>332 Hill St</th>
      <td>3</td>
      <td>San Francisco</td>
      <td>California 94114</td>
      <td>USA</td>
      <td>Super River</td>
      <td>25</td>
    </tr>
    <tr>
      <th>3995 23rd St</th>
      <td>4</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Ben's Shop</td>
      <td>10</td>
    </tr>
    <tr>
      <th>1056 Sanchez St</th>
      <td>5</td>
      <td>San Francisco</td>
      <td>California</td>
      <td>USA</td>
      <td>Sanchez</td>
      <td>12</td>
    </tr>
    <tr>
      <th>551 Alvarado St</th>
      <td>6</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Richvalley</td>
      <td>20</td>
    </tr>
  </tbody>
</table>
</div>



We can also use label indexing such like


```python
df6=df5.set_index("Address")
df6.loc["332 Hill St":"551 Alvarado St", "Name"]
```




    Address
    332 Hill St         Super River
    3995 23rd St         Ben's Shop
    1056 Sanchez St         Sanchez
    551 Alvarado St      Richvalley
    Name: Name, dtype: object




```python
df6.iloc[1:4, 1:3]
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>City</th>
      <th>State</th>
    </tr>
    <tr>
      <th>Address</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>735 Dolores St</th>
      <td>San Francisco</td>
      <td>CA 94119</td>
    </tr>
    <tr>
      <th>332 Hill St</th>
      <td>San Francisco</td>
      <td>California 94114</td>
    </tr>
    <tr>
      <th>3995 23rd St</th>
      <td>San Francisco</td>
      <td>CA 94114</td>
    </tr>
  </tbody>
</table>
</div>



It seems to me that the indexing is just another way to select rows and columns. Of course there should be more efficient methods for subsetting dataframes.

### Deleting columns or rows

To delete a certain column, use df.drop() function:


```python
df6.drop("Country", 1) 
# 1 means you want to delete columns
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>City</th>
      <th>State</th>
      <th>Name</th>
      <th>Employees</th>
    </tr>
    <tr>
      <th>Address</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3666 21st St</th>
      <td>1</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>Madeira</td>
      <td>8</td>
    </tr>
    <tr>
      <th>735 Dolores St</th>
      <td>2</td>
      <td>San Francisco</td>
      <td>CA 94119</td>
      <td>Bready Shop</td>
      <td>15</td>
    </tr>
    <tr>
      <th>332 Hill St</th>
      <td>3</td>
      <td>San Francisco</td>
      <td>California 94114</td>
      <td>Super River</td>
      <td>25</td>
    </tr>
    <tr>
      <th>3995 23rd St</th>
      <td>4</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>Ben's Shop</td>
      <td>10</td>
    </tr>
    <tr>
      <th>1056 Sanchez St</th>
      <td>5</td>
      <td>San Francisco</td>
      <td>California</td>
      <td>Sanchez</td>
      <td>12</td>
    </tr>
    <tr>
      <th>551 Alvarado St</th>
      <td>6</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>Richvalley</td>
      <td>20</td>
    </tr>
  </tbody>
</table>
</div>




```python
# one can also delete columns using
df6.drop(df6.columns[1:3],1)
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Country</th>
      <th>Name</th>
      <th>Employees</th>
    </tr>
    <tr>
      <th>Address</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3666 21st St</th>
      <td>1</td>
      <td>USA</td>
      <td>Madeira</td>
      <td>8</td>
    </tr>
    <tr>
      <th>735 Dolores St</th>
      <td>2</td>
      <td>USA</td>
      <td>Bready Shop</td>
      <td>15</td>
    </tr>
    <tr>
      <th>332 Hill St</th>
      <td>3</td>
      <td>USA</td>
      <td>Super River</td>
      <td>25</td>
    </tr>
    <tr>
      <th>3995 23rd St</th>
      <td>4</td>
      <td>USA</td>
      <td>Ben's Shop</td>
      <td>10</td>
    </tr>
    <tr>
      <th>1056 Sanchez St</th>
      <td>5</td>
      <td>USA</td>
      <td>Sanchez</td>
      <td>12</td>
    </tr>
    <tr>
      <th>551 Alvarado St</th>
      <td>6</td>
      <td>USA</td>
      <td>Richvalley</td>
      <td>20</td>
    </tr>
  </tbody>
</table>
</div>



To delete rows, do this


```python
df6.drop("332 Hill St", 0) 
# 0 means you want to delete rows.
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>City</th>
      <th>State</th>
      <th>Country</th>
      <th>Name</th>
      <th>Employees</th>
    </tr>
    <tr>
      <th>Address</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3666 21st St</th>
      <td>1</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Madeira</td>
      <td>8</td>
    </tr>
    <tr>
      <th>735 Dolores St</th>
      <td>2</td>
      <td>San Francisco</td>
      <td>CA 94119</td>
      <td>USA</td>
      <td>Bready Shop</td>
      <td>15</td>
    </tr>
    <tr>
      <th>3995 23rd St</th>
      <td>4</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Ben's Shop</td>
      <td>10</td>
    </tr>
    <tr>
      <th>1056 Sanchez St</th>
      <td>5</td>
      <td>San Francisco</td>
      <td>California</td>
      <td>USA</td>
      <td>Sanchez</td>
      <td>12</td>
    </tr>
    <tr>
      <th>551 Alvarado St</th>
      <td>6</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Richvalley</td>
      <td>20</td>
    </tr>
  </tbody>
</table>
</div>




```python
df6.drop(df6.index[1:3], 0) 
# you may also use the indexing to drop rows
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>City</th>
      <th>State</th>
      <th>Country</th>
      <th>Name</th>
      <th>Employees</th>
    </tr>
    <tr>
      <th>Address</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3666 21st St</th>
      <td>1</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Madeira</td>
      <td>8</td>
    </tr>
    <tr>
      <th>3995 23rd St</th>
      <td>4</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Ben's Shop</td>
      <td>10</td>
    </tr>
    <tr>
      <th>1056 Sanchez St</th>
      <td>5</td>
      <td>San Francisco</td>
      <td>California</td>
      <td>USA</td>
      <td>Sanchez</td>
      <td>12</td>
    </tr>
    <tr>
      <th>551 Alvarado St</th>
      <td>6</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Richvalley</td>
      <td>20</td>
    </tr>
  </tbody>
</table>
</div>



### Adding new columns or rows

We can add columns of the same length as the index.


```python
df6["Continent"] = df6.shape[0]*["North America"]
df6
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>City</th>
      <th>State</th>
      <th>Country</th>
      <th>Name</th>
      <th>Employees</th>
      <th>Continent</th>
    </tr>
    <tr>
      <th>Address</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3666 21st St</th>
      <td>1</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Madeira</td>
      <td>8</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>735 Dolores St</th>
      <td>2</td>
      <td>San Francisco</td>
      <td>CA 94119</td>
      <td>USA</td>
      <td>Bready Shop</td>
      <td>15</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>332 Hill St</th>
      <td>3</td>
      <td>San Francisco</td>
      <td>California 94114</td>
      <td>USA</td>
      <td>Super River</td>
      <td>25</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>3995 23rd St</th>
      <td>4</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Ben's Shop</td>
      <td>10</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>1056 Sanchez St</th>
      <td>5</td>
      <td>San Francisco</td>
      <td>California</td>
      <td>USA</td>
      <td>Sanchez</td>
      <td>12</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>551 Alvarado St</th>
      <td>6</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Richvalley</td>
      <td>20</td>
      <td>North America</td>
    </tr>
  </tbody>
</table>
</div>




```python
df6_t = df6.T  # this is the transposed dataframe 
df6_t
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>Address</th>
      <th>3666 21st St</th>
      <th>735 Dolores St</th>
      <th>332 Hill St</th>
      <th>3995 23rd St</th>
      <th>1056 Sanchez St</th>
      <th>551 Alvarado St</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>ID</th>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>4</td>
      <td>5</td>
      <td>6</td>
    </tr>
    <tr>
      <th>City</th>
      <td>San Francisco</td>
      <td>San Francisco</td>
      <td>San Francisco</td>
      <td>San Francisco</td>
      <td>San Francisco</td>
      <td>San Francisco</td>
    </tr>
    <tr>
      <th>State</th>
      <td>CA 94114</td>
      <td>CA 94119</td>
      <td>California 94114</td>
      <td>CA 94114</td>
      <td>California</td>
      <td>CA 94114</td>
    </tr>
    <tr>
      <th>Country</th>
      <td>USA</td>
      <td>USA</td>
      <td>USA</td>
      <td>USA</td>
      <td>USA</td>
      <td>USA</td>
    </tr>
    <tr>
      <th>Name</th>
      <td>Madeira</td>
      <td>Bready Shop</td>
      <td>Super River</td>
      <td>Ben's Shop</td>
      <td>Sanchez</td>
      <td>Richvalley</td>
    </tr>
    <tr>
      <th>Employees</th>
      <td>8</td>
      <td>15</td>
      <td>25</td>
      <td>10</td>
      <td>12</td>
      <td>20</td>
    </tr>
    <tr>
      <th>Continent</th>
      <td>North America</td>
      <td>North America</td>
      <td>North America</td>
      <td>North America</td>
      <td>North America</td>
      <td>North America</td>
    </tr>
  </tbody>
</table>
</div>



Now let's look at a real world example of geocoding addresses using pandas. For this exercise we need to install 'geopy' to Python. 

This will help us get the corresponding altitudes and latitutes of any location.



```python
import geopy
from geopy.geocoders import Nominatim
```


```python
nom=Nominatim()
```


```python
n=nom.geocode("7373 Valley View Lane, Dallas, TX 75240")
```


```python
n
```




    Location((32.926108, -96.778965, 0.0))




```python
dir(n)
```




    ['__class__',
     '__delattr__',
     '__doc__',
     '__eq__',
     '__format__',
     '__getattribute__',
     '__getitem__',
     '__hash__',
     '__init__',
     '__iter__',
     '__len__',
     '__module__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__setattr__',
     '__sizeof__',
     '__slots__',
     '__str__',
     '__subclasshook__',
     '__unicode__',
     '_address',
     '_point',
     '_raw',
     '_tuple',
     'address',
     'altitude',
     'latitude',
     'longitude',
     'point',
     'raw']




```python
n.longitude
```




    -96.778965




```python
n.altitude
```




    0.0




```python
n.latitude
```




    32.926108



So we will now use the geocode methods to our dataframe df1. We will construct a column using the geocodes.


```python
df=pandas.read_csv("supermarkets-semi-colons.txt", sep=';')
df
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Address</th>
      <th>City</th>
      <th>State</th>
      <th>Country</th>
      <th>Name</th>
      <th>Employees</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>3666 21st St</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Madeira</td>
      <td>8</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>735 Dolores St</td>
      <td>San Francisco</td>
      <td>CA 94119</td>
      <td>USA</td>
      <td>Bready Shop</td>
      <td>15</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>332 Hill St</td>
      <td>San Francisco</td>
      <td>California 94114</td>
      <td>USA</td>
      <td>Super River</td>
      <td>25</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>3995 23rd St</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Ben's Shop</td>
      <td>10</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>1056 Sanchez St</td>
      <td>San Francisco</td>
      <td>California</td>
      <td>USA</td>
      <td>Sanchez</td>
      <td>12</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>551 Alvarado St</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Richvalley</td>
      <td>20</td>
    </tr>
  </tbody>
</table>
</div>




```python
df["Address"]=df['Address']+","+df["City"]+","+df["State"]
df
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Address</th>
      <th>City</th>
      <th>State</th>
      <th>Country</th>
      <th>Name</th>
      <th>Employees</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>3666 21st St,San Francisco,CA 94114</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Madeira</td>
      <td>8</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>735 Dolores St,San Francisco,CA 94119</td>
      <td>San Francisco</td>
      <td>CA 94119</td>
      <td>USA</td>
      <td>Bready Shop</td>
      <td>15</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>332 Hill St,San Francisco,California 94114</td>
      <td>San Francisco</td>
      <td>California 94114</td>
      <td>USA</td>
      <td>Super River</td>
      <td>25</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>3995 23rd St,San Francisco,CA 94114</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Ben's Shop</td>
      <td>10</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>1056 Sanchez St,San Francisco,California</td>
      <td>San Francisco</td>
      <td>California</td>
      <td>USA</td>
      <td>Sanchez</td>
      <td>12</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>551 Alvarado St,San Francisco,CA 94114</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Richvalley</td>
      <td>20</td>
    </tr>
  </tbody>
</table>
</div>




```python
n=nom.geocode(df1["Address"][0])
n
```




    Location((37.7564888776, -122.429343347, 0.0))




```python
df["Address"]
```




    0           3666 21st St,San Francisco,CA 94114
    1         735 Dolores St,San Francisco,CA 94119
    2    332 Hill St,San Francisco,California 94114
    3           3995 23rd St,San Francisco,CA 94114
    4      1056 Sanchez St,San Francisco,California
    5        551 Alvarado St,San Francisco,CA 94114
    Name: Address, dtype: object




```python
# We create a 'Coordinates' column using apply()

df["Coordinates"]=df["Address"].apply(nom.geocode)
df
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Address</th>
      <th>City</th>
      <th>State</th>
      <th>Country</th>
      <th>Name</th>
      <th>Employees</th>
      <th>Coordinates</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>3666 21st St,San Francisco,CA 94114</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Madeira</td>
      <td>8</td>
      <td>(3666, 21st Street, Noe Valley, SF, California...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>735 Dolores St,San Francisco,CA 94119</td>
      <td>San Francisco</td>
      <td>CA 94119</td>
      <td>USA</td>
      <td>Bready Shop</td>
      <td>15</td>
      <td>None</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>332 Hill St,San Francisco,California 94114</td>
      <td>San Francisco</td>
      <td>California 94114</td>
      <td>USA</td>
      <td>Super River</td>
      <td>25</td>
      <td>(332, Hill Street, Liberty Street Historic Dis...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>3995 23rd St,San Francisco,CA 94114</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Ben's Shop</td>
      <td>10</td>
      <td>(3995, 23rd Street, Noe Valley, SF, California...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>1056 Sanchez St,San Francisco,California</td>
      <td>San Francisco</td>
      <td>California</td>
      <td>USA</td>
      <td>Sanchez</td>
      <td>12</td>
      <td>(1056, Sanchez Street, Noe Valley, SF, Califor...</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>551 Alvarado St,San Francisco,CA 94114</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Richvalley</td>
      <td>20</td>
      <td>(551, Alvarado Street, Noe Valley, SF, Califor...</td>
    </tr>
  </tbody>
</table>
</div>



We want to create two columns to show the Latitude and Longitude. 


```python
df["Latitude"]=df["Coordinates"].apply(lambda x: x.latitude if x != None else None)
df
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Address</th>
      <th>City</th>
      <th>State</th>
      <th>Country</th>
      <th>Name</th>
      <th>Employees</th>
      <th>Coordinates</th>
      <th>Latitude</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>3666 21st St,San Francisco,CA 94114</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Madeira</td>
      <td>8</td>
      <td>(3666, 21st Street, Noe Valley, SF, California...</td>
      <td>37.756489</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>735 Dolores St,San Francisco,CA 94119</td>
      <td>San Francisco</td>
      <td>CA 94119</td>
      <td>USA</td>
      <td>Bready Shop</td>
      <td>15</td>
      <td>None</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>332 Hill St,San Francisco,California 94114</td>
      <td>San Francisco</td>
      <td>California 94114</td>
      <td>USA</td>
      <td>Super River</td>
      <td>25</td>
      <td>(332, Hill Street, Liberty Street Historic Dis...</td>
      <td>37.755725</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>3995 23rd St,San Francisco,CA 94114</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Ben's Shop</td>
      <td>10</td>
      <td>(3995, 23rd Street, Noe Valley, SF, California...</td>
      <td>37.752965</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>1056 Sanchez St,San Francisco,California</td>
      <td>San Francisco</td>
      <td>California</td>
      <td>USA</td>
      <td>Sanchez</td>
      <td>12</td>
      <td>(1056, Sanchez Street, Noe Valley, SF, Califor...</td>
      <td>37.752146</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>551 Alvarado St,San Francisco,CA 94114</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Richvalley</td>
      <td>20</td>
      <td>(551, Alvarado Street, Noe Valley, SF, Califor...</td>
      <td>37.753673</td>
    </tr>
  </tbody>
</table>
</div>




```python
df["Longitude"]=df["Coordinates"].apply(lambda x: x.longitude if x != None else None)
df
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Address</th>
      <th>City</th>
      <th>State</th>
      <th>Country</th>
      <th>Name</th>
      <th>Employees</th>
      <th>Coordinates</th>
      <th>Latitude</th>
      <th>Longitude</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>3666 21st St,San Francisco,CA 94114</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Madeira</td>
      <td>8</td>
      <td>(3666, 21st Street, Noe Valley, SF, California...</td>
      <td>37.756489</td>
      <td>-122.429343</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>735 Dolores St,San Francisco,CA 94119</td>
      <td>San Francisco</td>
      <td>CA 94119</td>
      <td>USA</td>
      <td>Bready Shop</td>
      <td>15</td>
      <td>None</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>332 Hill St,San Francisco,California 94114</td>
      <td>San Francisco</td>
      <td>California 94114</td>
      <td>USA</td>
      <td>Super River</td>
      <td>25</td>
      <td>(332, Hill Street, Liberty Street Historic Dis...</td>
      <td>37.755725</td>
      <td>-122.428601</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>3995 23rd St,San Francisco,CA 94114</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Ben's Shop</td>
      <td>10</td>
      <td>(3995, 23rd Street, Noe Valley, SF, California...</td>
      <td>37.752965</td>
      <td>-122.431714</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>1056 Sanchez St,San Francisco,California</td>
      <td>San Francisco</td>
      <td>California</td>
      <td>USA</td>
      <td>Sanchez</td>
      <td>12</td>
      <td>(1056, Sanchez Street, Noe Valley, SF, Califor...</td>
      <td>37.752146</td>
      <td>-122.429815</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>551 Alvarado St,San Francisco,CA 94114</td>
      <td>San Francisco</td>
      <td>CA 94114</td>
      <td>USA</td>
      <td>Richvalley</td>
      <td>20</td>
      <td>(551, Alvarado Street, Noe Valley, SF, Califor...</td>
      <td>37.753673</td>
      <td>-122.433220</td>
    </tr>
  </tbody>
</table>
</div>



So we have both columns created as shown in the table above. The issue with NaN value in the Coordinates column is handled by the 'if-else' conditionals. This example reminded me of the apply() function in R. However, I have never used a if-else inside of this function before. So that's cool.

## Part VII
## Numpy



## Application 1. 
## Building a Text Generator Application

We first build a generator() function to randomly generate a three-letter string


```python
import random, string

def generator():
    letter1=random.choice(string.ascii_lowercase)
    letter2=random.choice(string.ascii_lowercase)
    letter3=random.choice(string.ascii_lowercase)
    name=letter1+letter2+letter3

    return(name)

print(generator())
```

    jqo


We then add User input to customize the names generated using vowels, consonants, or random letters.


```python
import random, string

vowels = "aeiouy"
consonants = "bcdfghjklmnpyrstvwxz"
letters = string.ascii_lowercase

letter_input_1=input("What letter do you want? Enter 'v' for vowels, 'c' for consonants, 'l' for any letter: ")
letter_input_2=input("What letter do you want? Enter 'v' for vowels, 'c' for consonants, 'l' for any letter: ")
letter_input_3=input("What letter do you want? Enter 'v' for vowels, 'c' for consonants, 'l' for any letter: ")

def generator():
    if letter_input_1 == 'v':
        letter1 = random.choice(vowels)
    elif letter_input_1 == 'c':
        letter1 = random.choice(consonants)
    elif letter_input_1 == 'l':
        letter1 = random.choice(letters)
    if letter_input_2 == 'v':
        letter2 = random.choice(vowels)
    elif letter_input_2 == 'c':
        letter2 = random.choice(consonants)
    elif letter_input_2 == 'l':
        letter2 = random.choice(letters)
    if letter_input_3 == 'v':
        letter3 = random.choice(vowels)
    elif letter_input_3 == 'c':
        letter3 = random.choice(consonants)
    elif letter_input_3 == 'l':
        letter3 = random.choice(letters)

    name=letter1+letter2+letter3

    return(name)

print(generator())
```


    ---------------------------------------------------------------------------

    KeyboardInterrupt                         Traceback (most recent call last)

    <ipython-input-5-3b4aa1821965> in <module>()
          5 letters = string.ascii_lowercase
          6 
    ----> 7 letter_input_1=input("What letter do you want? Enter 'v' for vowels, 'c' for consonants, 'l' for any letter: ")
          8 letter_input_2=input("What letter do you want? Enter 'v' for vowels, 'c' for consonants, 'l' for any letter: ")
          9 letter_input_3=input("What letter do you want? Enter 'v' for vowels, 'c' for consonants, 'l' for any letter: ")


    /Users/lucky1eva/anaconda/lib/python2.7/site-packages/ipykernel/ipkernel.pyc in <lambda>(prompt)
        162             self._sys_eval_input = builtin_mod.input
        163             builtin_mod.raw_input = self.raw_input
    --> 164             builtin_mod.input = lambda prompt='': eval(self.raw_input(prompt))
        165         self._save_getpass = getpass.getpass
        166         getpass.getpass = self.getpass


    /Users/lucky1eva/anaconda/lib/python2.7/site-packages/ipykernel/kernelbase.pyc in raw_input(self, prompt)
        692             self._parent_ident,
        693             self._parent_header,
    --> 694             password=False,
        695         )
        696 


    /Users/lucky1eva/anaconda/lib/python2.7/site-packages/ipykernel/kernelbase.pyc in _input_request(self, prompt, ident, parent, password)
        722             except KeyboardInterrupt:
        723                 # re-raise KeyboardInterrupt, to truncate traceback
    --> 724                 raise KeyboardInterrupt
        725             else:
        726                 break


    KeyboardInterrupt: 


The user input can't be processed here interactively but you get the idea. Try it out on a terminal using command line in Python. You'll get a three-letter name based on your inputs. 
