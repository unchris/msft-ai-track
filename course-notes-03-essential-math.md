Introduction to Artificial Intelligence (AI) - Course Notes
============
January 2019
Chris Cameron

I am auditing [Microsoft Professional Program for Artificial Intelligence track](https://academy.microsoft.com/en-us/tracks/artificial-intelligence/).

The third of 10 courses is [Essential Math for Machine Learning: Python Edition](https://courses.edx.org/courses/course-v1:Microsoft+DAT208x+1T2019/course/).

# Before You Start

## Course Introduction

### Welcome

### Preparing for the Labs

It's done with Jupyter Notebooks (woo!)

I downloaded the notebooks into the course folder.

### Pre-Course Survey

meh

# Equations, Graphs, and Functions


### Lab: Linear Equations

meh

### Systems of Equations

meh

### Lab: Systems of Equations

meh

### Lesson Review

Got everything right.

## Quadratic Equations and Functions

### Exponentials, Radicals, and Logarithms

refresher: `4^x = 16` means `x = log4(16)`

### Lab: Exponentials

refresher:
- common logarithm is log base 10 typically expressed log() or log10()
- natural logarithm is log base e typically expressed ln()
  - note: python's `math` package has natural logarithm `log()`

they call `y = 3(x^3)` an exponential equation but it's not - it's a quadratic/monomial equation

### Polynomials

meh

### Polynomial Operations

ooh polynomial long-division

### Lab: Polynomials

refresher: polynomials can only have non-negative integer exponents

https://en.wikipedia.org/wiki/Polynomial_long_division

### Factorization

refresher: greatest common factor (gcf)

### Factoring Squares

refresher for factorization:
- difference of squares: `x^2 + 4 = x^2 + 2^2 = (x+2)(x-2)`
- perfect squares: `x^2 + 6x + 9 = (x+3)(x+3) = (x+3)^2`
- multiplying perfect squares: `(a + b)^2 = a^2 + b^2 + 2ab`

### Lab: Factorization

meh. these labs are too simple.

### Introduction to Quadratic Equations

this was the briefest "introduction" to quadratic equations I've ever seen. this course is very clearly a refresher course for people who already know this stuff. he didn't even mention that it's quadratic because there's at least one `x^2` term, or bring up the standard form `ax^2 + bx + c = 0`

### Lab: Quadratic Equations

The notebook just would not seem to finish booting a container on Azure so I ran the calcs locally for the examples that mattered.

Basically the lab boils down to teaching the basic ways to solve quadratic equations

- factoring
- calculating square root
- completing the square
- using the vertex form of the equation `y = a(x - h)^2 + k)`
- figuring out h and k when your equation is in standard form
  - `h = (-b/2a)`
  - `k = ah^2 + bh + c`
- the quadratic formula to calculate values of x when y=0
  - x = (-b +or- sqrt(b^2 - 4ac))/2a
  - if y never touches 0 you will get non-real roots IIRC, but they don't mention this

### Functions

- he brings up when functions can be undefined for particular values
- the set of numbers for which a function is defined is called its domain
- the set of possible outputs for a function is called its range

### Lab: Functions

meh

### Lesson Review

passed

## Module Assessments

no access while auditing

# Derivatives and Optimization

## Differential Calculus Foundations

### Rates of Change

- slope of a line
- slope of a secant line

### Lab: Rates of Change

meh

### Introduction to Limits

I think this was the worst possible introduction to limits they could have given

### Continuity

ugh

### Finding Limits

through looking at graphs and interpolation. talks about approaching from negative, positive sides, sometimes two-sided limits don't exist. useful info but this is so brief

### Lab: Limits

I've switched now to running Jupyter locally because Azure Notebooks is a shitshow (at least in the free tier anyway)

I ran the command from `course-notes-01` that begins `docker run` but instead of the whole thing I just bashed in and ran the commands in the `-c` argument manually.

Later I had to exec into the running container to do `conda3 install matplotlib` so that the inline magic call would work `%matplotlib inline`

I can see why people tend to run `anaconda3` instead of `miniconda3` - this way they don't have to install all of this on their own. still I like that this takes up way less space on my machine and I should eventually make Dockerfile that wraps this.

This Lab has a much better explanation of limits and continuity than the video, but still lacking.

They even bring up asymptotes and infinity in the lab which wasn't in the video lectures.

Had to install pandas `conda install pandas` for some more inline magic.

They bring up _rationalization_ in this part of the lab which was a critical miss in the videos. 

And finally they're just going to drop some common limit addition, subtraction, multiplication, division and exponentiation with no theoretical backing whatsoever. 

### Lesson Review

## Differentiation and Derivatives

## Module Assessments

# Vectors and Matrices

## Vectors

## Matrices

## Module Assessments

# Statistics and Probability

## Statistics Fundamentals

## Probability

## Module Assessments
