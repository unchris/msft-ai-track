Introduction to Python for Data Science - Course Notes
============
January 2019
Chris Cameron

I am auditing [Microsoft Professional Program for Artificial Intelligence track](https://academy.microsoft.com/en-us/tracks/artificial-intelligence/).

The second of 10 courses is [Introduction to Python for Data Science](https://courses.edx.org/courses/course-v1:Microsoft+DAT208x+1T2019/course/).

Since I know a lot of Python already I will probably skim the first 3-4 chapters and focus on Matplotlib and Control Flow/Pandas since I haven't used matplotlib in years and I've never used Pandas.

# Start Here

nothing noteworthy

# Python Basics

nothing noteworthy

# Python Lists

nothing noteworthy

# Functions and Packages

nothing noteworthy

# Numpy

## Numpy Arrays

the justification for using numpy is being able to type `(arr1 / arr2**2)` where `arr1` and `arr2` are numpy arrays. You could do this with lists too if you wanted to but I understand that the performance and statistical usage of numpy arrays is important.

he does `arr1 > 23` to get an array of booleans

then he does `arr1[arr1 > 23]` to get the specific values that were greater than 23.

neat

## 2D Numpy Arrays

*side note: it's pretty obvious (and a bit hilarious) these transcriptions were done by AI.*

you can retrieve elements `arr2d[n][m]` or `arr2d[n,m]`. Works with slices too like `arr2d[:,1:3]`

## Numpy Basic Statistics

- `numpy.mean`,
- `numpy.median`
- `numpy.corrcoef` (correlation coefficient, I believe)
- `numpy.std` standard deviation
- `numpy.sum`
- `numpy.sort`
- `numpy.round`
- `numpy.random.normal` random number
- `numpy.column_stack` (creates a columnar 2d numpy array)

# Matplotlib

## Basic Plots with Matplotlib

- Shows Hans Rosling's GDP vs Life Expectancy bubble chart.
- `matplotlib.pyplot as plt` subpackage
- `plt.plot(...)`
- `plt.show()` to display it
- `plt.scatter(...)`

## Histograms

- `plt.hist()`

## Customization

- label your axes `plt.xlabel('Year')`, `plt.ylabel('Population')`
- `plt.title("blah")`
- `plt.yticks()`
- `plt.fill_between()`

## Further Readings

They bring up `ggplot` as an alternative plotting library.

They mention a [gallery](http://matplotlib.org/1.5.1/gallery.html) of nice plots that matplotlib supports

# Control flow and Pandas

## Boolean Logic and Control Flow

introduces `or` `and` `if` `else` `elif`

## Pandas

store data in a `DataFrame`

typically you import your DataFrame as opposed to declaring it manually (I wonder if this is true generally - this course has been pretty basic)

- `import pandas as pd`
- `pd.read_csv()`
- `pd.read_csv('filepath', index_col=0)` (this makes sure you don't use an index column as a data column by accident)
- `df['column_header']` works with data frames
- `df['column_header'] = [some list]`
- it's based on numpy so you can do like `df['density'] = df['population'] / df['area'] * 1000000` to create new columns
- to access rows you have to use `df.loc['rowname']` to find that row
- you can combine it either way like `df.loc['row']['col']` or `df['col'].loc('row')`

## Further Reading

http://pandas.pydata.org/

# Final Lab

Unfortunately all labs and exercises in this course were locked by the fee. Fortunately this course is so basic it's not worth the cost to unlock this stuff.


