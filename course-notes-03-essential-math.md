Essential Mathematics for Machine Learning: Python Edition - Course Notes
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

I may have lost some notes here or it's also possible that the sections were too simple to make notes worth it.

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

easy, they didn't get into any advanced topic at all

## Differentiation and Derivatives

### Introduction to Differentiation

their basic explanation is that if `y = f(x)` then `m = f'(x)` where `m` is the slope and `f'(x)` is the derivative. i guess that's a pretty brief introduction

### Differentiability

Knowing whether a function can have a derivative at every point on the function's line. It has to be continuous and the tangent can't be vertical, and it has to be "smooth" at that point.

this was stupid brief

### Derivative Rules and Operations

ahh good ol' calculus identities

- if `f(x) = c` then `f'(x) = 0` (makes sense because if y is a constant it's a horizontal line meaning slope is 0)
- power rule: `f(x) = x^n` then `f'(x) = nx^(n-1)`
- `f(x) = g(x) + h(x)` then `f'(x) = g'(x) + h'(x)`
- product rule: `f(x) = g(x) * h(x)` then `f'(x) = (g'(x) * h(x)) + (g(x) * h'(x))`
- quotient rule: `f(x) = g(x)/h(x)` then `f'(x) = (g'(x) * h(x) - g(x) * h'(x))/[h(x)]^2`
- chain rule: `f(x) = g(h(x))` then `f'(x) = g'(h(x)) * h'(x)`

### Lab: Differentiation and Derivatives

reminder that slope is calculated as delta(y)/delta(x) meaning `m=(f(x+h) - f(x))/((x+h)-x)` which is how we get to derivatives where you're trying to find a value of h so small but not quite 0 so that you can effectively calculate the slope at a point on a curve. so you get `lim(h->0)(m)` using the definition of `m` just laid out.

they also bring up notations like Lagrange

```
 \begin{equation}f'(x) = \lim_{h \to 0} \frac{f(x + h) - f(x)}{h} \end{equation}
```

and Leibniz

```
\begin{equation}\frac{d}{dx}f(x) = \lim_{h \to 0} \frac{f(x + h) - f(x)}{h} \end{equation}
```

and generalized for a specific point `a`

```
\begin{equation}f'(a) = \lim_{h \to 0} \frac{f(a + h) - f(a)}{h} \end{equation}
```

This lab also makes a better example of what it means that a derivative can only be calculated when the curve is "smooth" at that point, showing a very sharp turn in direction, while the video showed a point that did not look sharp at all.

Finally a justification for Leibniz notation being that it makes sense when you're doing derivatives of equations instead of functions. (though they've put no effort into explaining the difference between an equation and a function, probably because it's practically irrelevant in data science programming? The best they offer later is "functions are just equations encapsulated as a named entity that return a value" which is, I guess a distinction but it's hardly what `function` means in mathematics

The lab demonstrates some of the rules like sub, power, product etc. It just seems so fast compared to taking a week or two to demonstrate these same things in high school and university.

### Using Derivatives to Analyze Functions

- finding a relationship between function and its derivative
- derivative positive: rising / negative: falling / 0: neither

finally use the word "inflection point" - they should have had a unit on curves and their terms

- whenever the value of the derivative is zero, it's a "critical point"
  - derivative always 0 -> function is a constant C with 0 slope
  - derivative positive to negative -> function is changing direction from upward to downward indicating a local maximum
  - derivative negative to positive -> function is changing direction from downward to upward indicating a local minimum
  - derivative pos to pos or neg to neg but touches 0 briefly -> inflection point where the function flattens out then resumes changing in the same direction (imagine a wavy slide in a park where it's occasionally flat)

### Second Order Derivatives

- `f''(x)` is negative when `f'(x)` is 0 means local maximum because it's decreasing at that point, so `f(x)` is the value of the maximum at that point
- `f''(x)` is positive when `f'(x)` is 0 means local minimum because it's increasing at that point,
so `f(x)` is the value of the minimum at that point

### Optimizing Functions

they just kind of restate what you're taught in Second Order Derivatives

### Lab: Critical Points and Optimization

The only decent part of this is they give practical examples of functions like growth of flowers when applying fertilizer, or maximizing potential revenue given a function modelling it against subscriber count

### Multivariate Differentiation

f(x,y) = x^2 + y^2

partial derivatives is about solving for each independently (i.e., for x and y separately)

e.g,

```
d(x,y)/dx = d(x^2 + y^2)/dx

then d(x^2)/dx = 2x and d(y^2)/dx = 0

then d(x,y)/dx = 2x

similarly,

d(x,y)/dy = d(x^2 + y^2)/dy

then d(x^2)/dy = 0 and d(y^2)/dy = 2y

then d(x,y) = 2y
```

### Lab: Multivariate Differentiation

Of course they leave it to the lab to explain what the point of partial derivatives is. This course should just be a short text book and review questions, what is the point of narrating graphs?

GRADIENTS! I miss math class so much.

On the other hand I don't have the patience to type out a gradient formula in vim. Suddenly Jupyter notebooks look really interesting...

Why are they using Python lists when they taught the value of `np.array` in the Python course? All these unnecessary list appends and comprehensions...

`numpy.meshgrid` is cool. `matplotlib.pyplot.quiver` and `matplotlib.pyplot.contour` too.

Here are some verbatim notes from the lab I will copy now in case they become relevant later as this section of my calculus is a bit rusty:

> Notice the following properties of this plot.
> - The arrows in the plot point in the direction of the gradient.
> - The width of the arrows is proportional to the value of the gradient. The width of the arrows and the **gradient decreases as function gets closer to the minimum**. If this is the case everywhere, you can say that a function is **convex**. It is always much easier to find minimum of convex functions.
> - The **direction of the gradient is always perpendicular to the contours**. This is an important property of multivariate functions.

They then briefly bring up Gradient Descent which means we are finally getting into the relevant maths!

### Introduction to Integration

Integral = AUC. Integral = Anti-derivative, so we need a function whose derivative is f(x). he uses the power rule in reverse, tada.

### Lab: Integration

Integrals are the inverse of derivatives.

Need to `conda install scipy` now so we can make use of `scipy.integrate.quad`.

It's kind of a shame that they only really show calculating anti-derivatives for easy cases like the power rule and then skip right to AUC calculations for contrived easy examples. This stuff gets harder. Though I guess they're basically just prepping you for using numerical approximation methods to calculate it for you later.

### Lesson Review

These were decent questions but do not fully cover the work. My guess is the Module Assessments must be much more thorough. Hopefully so since they're gated behind $99 :)

## Module Assessments

Couldn't take them due to auditing.






# Vectors and Matrices

## Vectors

### Introduction to Vectors

Explains that it's a set of co-ordinates of magnitude encoding a direction and that it's standard to come from the origin but not necessary.

He also brings up polar co-ordinates, and how you can get a magnitude+bearing as the hypotenuse of the triangle formed by the first two co-ordinates. Brings up the sort(sum of squares) approach to getting the hypotenuse magnitude then later brings up finding the angle via inverse tangent, but hand-waves about more difficult problems and points towards more of the same "just use your tools to calculate it".

### Vector Addition

Add the individual components, mentions it's like "adding another leg to the journey" by putting the tail of the second vector at the head of the first. That was brief!

### Lab: Vectors

They make good use of `matplotlib.pyplot.quiver()` to display vectors on a `grid()`.

They are demonstrating the sum of squares method for finding the magnitude of the vector but I wish they would bring up that leaving it in squared form is commonly better for calculations purposes. I wonder if maybe common wisdom has changed on that topic?

Useful for finding vector magnitude, using `numpy.linalg.norm(v)` .

Bring up inverse tangent and "opposite over adjacent" but no general intro to SOHCAHTOA which is a shame.

`math.atan()` and `math.degrees()` (EWWWW use radians!)

A reminder that:

- if x is negative, add 180deg to result of `atan()` and
- if x is positive and y is negative, add 360deg to result of `atan()`

Then, just after explaining the rules, they go on to say that `numpy.arctan2()` will do the correction for you.

### Vector Multiplication

- scalar multiplication: vector * scalar => new vector
- dot product: vector . vector => scalar
- cross product: vector x vector => scalar

his explanation of cross product has NO theory at all, he just says "oh you do this and this and this" and now you have a vector... I guess this will be another place where the math is just done by `numpy` so they don't want to talk about it?

### Lab: Vector Multiplication

You can do scalar multiplication just by multiplying the numpy vector by a scalar e.g., `2 * np.array([2, 1])` or `np.array([2,1]) / 2`

Dot product is done via `numpy.dot(v1, v2)` but you can also use the `@` operator as in `v1 @ v2`

I forgot to mention they briefly introduced the symbol for magnitude as the double bar brackets i.e., `||e||` (can't do an arrow in ascii but you get what I mean. `mag(e)` takes me one more char so I may just use that.

cosine rule comes in suddenly to teach how to get the angle between two vectors. Here it is in Python

```python
vMag = numpy.linalg.norm(v)
sMag = numpy.linalg.norm(s)
cosTheta = (v @ s)/(vMag * sMag)
theta = math.degrees(math.acos(cosTheta))
```

They bring up that vector multiplication (cross product) results in a vector that is at right angles to both of the multiplied vectors and so the cross product only really makes sense with 3D vectors.

In Python:

```python
r = numpy.cross(p,q)
```

In math:

```
r1 = p2q3 - p3q2
r2 = p3q1 - p1q3
r3 = p1q2 - p2q1
```

### Lesson Review

Covers a simple addition, scalar multiplication, dot product, and cross product.

### Introduction to Matrices

Matrices usually named with capital letter.

You can add or subtract matrices of the same size by adding up the corresponding components in each.

The negative of a matrix is just the same matrix with reversed signs. (They've kind of given away scalar multiplication here without showing it)

The transpose is superscripted T.

Refresher:

```
|3 5 1| transposed |3 1|
|1 4 3| becomes:   |5 4|
                   |1 3|
```

### Lab: Matrices

```python
numpy.array([[1,2,3],
             [4,5,6]])
```

or the specialist subclass

```python
numpy.matrix([[1,2,3],
              [4,5,6]])
```

You can add and subtract them with `+` and `-` but only work if the matrices have the same shape.

Numpy arrays have a `.T` attribute that returns the transpose (they call it a function but it's not).

### Matrix Multiplication

Scalar and dot product.

Dot product requires the matrices to have the transposed shape of each other (e.g., 2,3 row,col multiplying a 3,2) which includes the special case when they both rows=cols.

### Identity Matrices

The equivalent of the number 1 in matrix terms. It's a zero matrix with 1 in all of the elements where i=j (i.e., diagonal top left to bottom right). When you dot product an Identity matrix with another, it is like multiplying the other matrix by 1.

### Matrix "Division"

Multiplying by the reciprocal.

Divide matrix A by matrix B means you want to multiply A by the inverse of B.

Find the inverse of a matrix: specific formula that I wish they would explain.

Determinant of a matrix is briefly brought up as subtracting the diagonal elements from each other. Ughhhhh explain thisss!

"However in reality you'll likely use tools or scripting languages to do the heavy lifting for you" --> yup, why am I yelling?

### Solving Systems of Equations with Matrices

"One of the cool things about matrices" haha ok I'll accept it.

easier to just show his example:

```
2x + 4y = 10
3x + 3y = 12

in matrix form:

|2 4| . |x| = |10|
|3 3|   |y|   |12|

inverse multiplication:

    -1
|2 4| . |10| = |x|
|3 3|   |12|   |y|

which is roughly

|-0.5 0.67| . |10| = |x|
|0.5  0.33|   |12| = |y|

calc the dot product, giving you x and y

|3| = |x|
|1| = |y|
```

### Lab: More Matrices

`A @ B` works for numpy.array() matrices for dot product. But with numpy.matrix() you can use `A * B`

Matrix dot product is not commutative, i.e., A.B==B.A DOES NOT HOLD as a rule, though it is possible.

They don't bring it up but `np.identity(n)` will give you an nxn identity matrix.

They give the formula for calculating the inverse of a 2x2 matrix

```
    -1
|a b|  =___1___ .  | d -b|
|c d|   ad - bc    |-c  a|
```

The determinant of the matrix (above) is the `ad - bc` part.

Naturally, you can use `invB = numpy.linalg.inv(B)` to calculate the inverse, and if you had already been using `numpy.matrix()` then it's available also as `B.I` (this probably has some fail cases for when an inverse is unavailable)

They show the formula for doing this for a 3x3 matrix but even I don't feel like writing it out now. It's available online in any math tutorial anyway. Suffice it to say you can still use `numpy.linalg.inv(B)` on a 3x3 so woot woot.

Then the capstone which is the systems of equations part where you've transformed your Ax + By = C and Dx + Ey = F into matrix form:

```
|A B| . |x| = |C|
|D E|   |y|   |F|
```

you can then solve this by storing them as matrices (respectively, X, Y, and Z for the above)

```python
Y = numpy.linalg.inv(X) @ Z
```

### Matrix Transformations

Functions that operate on vectors are called transformations.

If your transformation is a matrix, you perform the dot product to appyly the transform.

### Eigenvalues and Eigenvectors

Matrix dot Vector = Vector.

This explanation of eigenvectors was terrible. One of the most fundamentally important concepts in matrix mathematics. I hope the lab has better intro for people.

Eigenvectors of a matrix can be stored in a matrix and its eigenvalues can be stored in a diagonal matrix. Usually the Eigenvalue matrix is represented with the symbol Lambda.

### Lab: Transformations, Eigenvalues, and Eigenvectors

Ah here at least they explain that transformations can map from 2D to 2D space or 2D to 3D space.

When a matrix transforms a vector it can change it in at least one of two ways:

- Changing the length (magnitude)
- Changing the direction (amplitude)

An Affine Transformation is one which multiplies a vector by a Matrix and then adds an offset vector (sometimes called _bias_), e.g., `T(v) = Av + b` (v and b are vectors)

This is "the basis of linear regression, a core foundation for machine learning". `A` defines the _features_, `v` is the _coefficients_ and `b` is the _intercept_.

When a matrix transform is the equivalent of a scalar-vector multiplication, then the scalar-vector pairs that correspond to the matrix are known respectively as eigenvalues and eigenvectors. We generally indicate eigenvalues using Lambda, and the formula `T(v) = Av` can be restated `T(v) = Lambda.v`.

This means Lambda is the eigenvalue and `v` is the eigenvector for `A`.

Matrices can have multiple eigenvector-eigenvalue pairs and they can be calculated manually but you can use `eVals, eVecs = numpy.linalg.eig(A)` instead.

(The columns of the Eigenvector matrix result are the eigenvectors

Oh my god they're just going to bring up Eigendecomposition off-hand in the lab. Alright.

We can decompose a matrix `A = Q L Qinv` where Q is the matrix of eigenvectors, L is a matrix with the eigenvalues along the diagonal, and Qinv is the inverse of Q.

You can get Q, L and Qinv like so:

```py
l, Q = numpy.linalg.eig(A)
L = numpy.diag(l)
Qinv = numpy.linalg.inv(Q)
```

So the original transform `A.v` can be represented as `Q.L.Qinv.v` Since `A` decomposes into `Q.L.Qinv`

Rank of a square matrix is the number of non-zero eigenvalues of the matrix. (number of non-zero diagonal elements in L). A full rank matrix has the same number of non-zero eigenvalues as the dimension of the matrix. Rank deficient when it's fewer than dimensions. A rank deficient matrix does not have an inverse, as a result.

One easy way to spot a rank-deficient matrix is if some rows are scalar multiples of another row.

You can calculate the inverse of a full rank square matrix using `Ainv = Q.Linv.Qinv`

### Lesson Review

Covers matrix addition, transpose, dot product, and inverse.

## Module Assessments

Unavailable







# Statistics and Probability

Notes prior to the following section were lost in a vim crash.

### Lab: Statistics Fundamentals

Pandas data frames have `mean()`, `median()`, and `mode()` functions. And `min()` and `max()`

It also looks like you can do plots directly from the data frame, e.g., `df.plot.hist()` for a histogram. You still need to do `matplotlib.pyplot.show()` later

`scipy.stats.gaussian_kde(x_values)` will give you a density function so you can generate a curve (y values) for `x_values` input. Helps you interpret your histograms of data giving a sense of skewness. If the tail is to the right, it's right-skewed, and vice-versa.

If no skew, it's a normal/gaussian curve.

`df[column].skew()` will give positive for right skew, negative for left skew, roughly 0 for no skew
`df[column].kurt()` will give measure of "kurtosis" or "sharpness" of the curvature. Higher numbers for more kurtosis. They don't explain the term very well.

Had to install `statsmodels` (`conda install statsmodels`)

`scipy.stats.percentileofscore(df[column], score, type)` will calculate the percentile for a particular data point's "score" (value). `type` indicates either `weak` or `strict` which will either include or not include the particular score when calculating. `type=rank` will calculate grouped percentiles (useful when some data points have the same score).

`df[column].quantile([0.25, 0.5, 0.75])` will print quantiles (you can pick values to get percentiles, quartiles, etc)

When you plot a box chart the outliers will appear as open circles outside of the box-and-whiskers.

`df[column].var()` for variance

`df[column].std()` for standard deviation

Reminder that in a normal distribution

- 68.26% of values within 1 stddev
- 95.45% of values within 2 stddev
- 99.73% of values within 3 stddev

To calculate z-score you do `Z = (x-xbar)/s)` where `x` is a particular score, `xbar` is the mean score, and `s` is the standard deviation. This formula's terms are for the "sample" variant. For the full population `xbar` would be `mu` and `s` would be lower case `sigma`

Then, they show right at the end you can just write `df.describe()` To get `count`, `mean`, `stddev`, `min`, `25%`, `50%`, `75%`, `max` for each of the columns in your `df`. `median` is not included so you still need to run that (I wonder if you could overload `describe()` to provide more data?)

### Comparing Data

Calculate a statistic `correlation` to determine  relationship between two variables. correlation is mapped from -1 to 1. Positive values mean a positive correlation, negative mean negative correlation.

Draw a line of best fit using least squares regression. Can be used to predict one variable given another if it fits well.

### Lab: Comparing Data

Comparing Multivariate data and making sure the values are normalized so you can actually compare them. You can run a min-max scaling to get values proportional to the originals but between 0 and 1.

```py
from sklearn.preprocessing import MinMaxScaler
scaler = MinMaxScaler()
df['col1','col2','col3'] = scaler.fit_transform(df['col1','col2','col3'])
```

(need to `conda install scikit-learn` to use `sklearn`)

You can also compare bivariate data with a scatterplot to see if there is any apparent relationship.

`df.plot(kind='scatter', ...)`

Here's an example of how they plot a line of best fit using the usual suspects:

```py
# Add a line of best fit
plt.plot(np.unique(df['Grade']), np.poly1d(np.polyfit(df['Grade'], df['Salary'], 1))(np.unique(df['Grade'])))
```

This is for a data frame where Grade and Salary were not normalized so it should be applicable. This line of best fit can show if there's some _colinearity_

To calculate the correlation statistic, you can use `df['col'].corr(df['col2]')` which will give you either positive negative or near 0 in range -1...+1

Least Squares Regression is about calculating a line of best fit for a set of points. You already have x and y (they are the two variables you're comparing) in the `y = mx + b` equation, so need a y-intercept and slope that creates a line that best fits the points.

We're looking for a linear function `f(x)` which takes the x-values and produces NEW y values which are close to the original y values. The error is measured as the distance between y-f(x) and to get the overall error, you square each error and add them all up. Thus the best line has the LEAST squared error which is why this is called Least Squares Regression.

They list the formula for calculating `m` and then subsequently `b` in the `y=mx+b` equation. The error values are often called `residuals` when comparing estimated values from `f(x)` with known values `y` (this was brought up in the first course!)

You can use `scipy.stats.linregress()` function to do most of the work for you.

```py
m, b, r, p, se = stats.linregress(df['col1'], df['col2'])

df['fx'] = (m*df['col1']) + b
df['error']  = df['fx'] - df['col2']
```

When you have a good-fitting line, you can use it to predict values for any given x value.

### Lesson Review

This covered mean, median, stddev, and skewness. Not particularly good review.

## Probability

### Probability Basics

Based on experiments or trials with an uncertain outcome. Gives a dice roll as example.

Sample Space: all the possible outcomes of the experiment
Event: something which produces a specific outcome

P to denote probability. Usually an uppercase letter for specific event.

`P(A) = (number of sample points that result in the event) / (number of sample points in the sample space)`

So for a die roll it's `P(A) = 1/6` for example.

The probability of it not to occur is P(A') which is the compliment. So in the die roll, 5/6. `P(A) + P(A') = 0` always adds up

### Conditional Probability and Dependence

Rolling a die once doesn't affect subsequent roles. So the events are independent.

Other events are dependent. E.g., taking a card from a deck leaves fewer of that kind of card in the deck, so affects probability of subsequent events.

For independent events A, B, C, what's the probability of all three occurring?

`P(A int B int C) = P(A) * P(B) * P(C)` (int = intersection)

Consider another two events A and B. And you want to know the probability of A OR B occurring. What if parts of event A intersect with event A? (A = roll an odd number, B = roll a number divisible by 3, note that `3` is in both events outcomes)

`P(A U B)`=`P(A) + P(B)` gives you the probability of all the events occurring in A and B, but we want to subtract the events that occur in both so they aren't double-counted, so we need to subtract `P(A int B)`, so ultimately `P(A U B)` == `P(A) + P(B) - P(A int B)` == `P(A) + P(B) - (P(A)*P(B))`

For dependent events it's different. Take lottery drawing, and your numbers are 2,5,4. Once you pick 2 (event A) then the probability of that was P(A), but the probability of the next one has changed because fewer balls are in the bowl. The next ball is now `P(B|A)` (probability of B given A)

`P(B|A) = P(A int B) / P(A)`

now we can even re-arrange it to get: `P(A int B) = P(A) * P(B|A)`

Now you can extend this to calculate `P(C)` (when you chose ball 4)

P(A int B int C) = P(A) * P(B|A) * P(C|A int B)`

### Binomial Variables and Distributions

Apply probability to statistics.

binomial variable: number of successful outcomes of a non-dependent experiment with two possible outcomes; success or failure. For example, you pick three people from a class and want to know the probability that 2/3 of them have green eyes. `X` is the binomial variable, and you want to calculate the probability of a given value of `x` (lowercase).

so, `P(x=2) = p^2((1-p)^1)`, where `p` is the probability of green eyes and `(1-p)` is the probability of other eye colours.

k successes out of n trials. We want 2 successes out of 3 trials.

`P(x=2)= p^k((1-p)^(n-k))` is the general form.

`nCk` or `n choose k` is calculated `n! / (k!(n-k)!`

but this isn't the whole formula yet, because this hasn't yet accounted for the fact that there are multiple possible cases where two of the students have green eyes. If you work it out it says there are 3 combinations (which is true).

So this gives you the probability mass function or PMF which is

`P(x=k) = (n choose k) * p^k((1-p)^(n-k))` (you're basically multiplying nCk by the formula just developed.

A result of the Central Limit Theorem causes the distribution of the PMF values to resemble a normal distribution with the mean referred to as the "expected value for the variable" or `E(x) = mu`

Wow he really breezed through this stuff. This needs more time spent on it, even if I've already seen it before, it was too brief a refresher even.

### Lab: Probability

Bias makes one outcome more likely than another. E.g., an experiment on what the weather might be like in the summer, there's a bias toward sunny days as opposed to rainy or even snowy days.

Probability trees come up out of nowhere drawn in ascii no less. nice.

Mutually exclusive events. Example: what's the probability that a single coin flip can result in heads *and* tails? For mutually exclusive events, `P(A int B) = 0` and so `P(A U B) = P(A) + P(B)` (since the intersection is 0, you don't need to subtract it)

Another example is, what's the chance of rolling a 6 and an odd number in the same dice roll? `P(A U B)=0` again.

`scipy.special.comb` can be used to calculate `n choose k`.

OK so here they explain the two different formulas for `P(x=k)` much better.

For the binomial variables/distributions you can use the form `P(x=k) = (n choose k)` but when there is _bias_ in the results (i.e., the probability of event being tested for failure and success is not equal) then you have to account for the bias.

In this case, it's not as simple as saying n possibilities, choose k of them. In this case you have to calculate the probability across your experiment of the k successes and the n-k failures, and then multiply it by `(n choose k)` which is to say, multiply it by the number of ways k successes and n-k failures can occur.

So first, the probability of k successes and n-k failures is `p^k * ((1 - p)^(n-k))` where `p` is the probability of success. So, e.g., in this case let's say the probability of success is 0.25, and you want to know the chance of 3 successes out of 5 events, you would calculate (0.25^3) * (0.75^2), or about 0.088.

Second, you multiply that by all the possible ways you can get 3 successes and 2 failures, which is (n choose k) or (5 choose 3) or 5.  so the total probability `P(x=k) = 5 * 0.088 = 0.01375`

This full formula is called the General Binomial Probability Formula, and it is used to calculate the probability Mass Function (PMF). We can use `scipy.stats.binom.pmf`

The `scipy.stats.binom.pmf` function encapsulates the general binomial probability formula, and you can use it to calculate the probability of a random variable having a specific value `k` (not same as `k` above!) for a given number of experiments `n` where the event being tested has a given probability `p`. They give some example code that I copied here:

```python
from scipy.stats import binom
from matplotlib import pyplot as plt
import numpy as np

n = 5
p = 0.25
x = np.array(range(0, n+1))

prob = np.array([binom.pmf(k, n, p) for k in x])

# Set up the graph
plt.xlabel('x')
plt.ylabel('Probability')
plt.bar(x, prob)
plt.show()
```

They note that if you increase `n` it will start to look more and more like a normal distribution (try `n=50`). I also tested changing `p` to `0.5` which causes the distribution to be centred wherethe median value of `x` is. When `p=0.25` it is pushed left and when `p=0.75`, it's pushed right.

Note: Normal Distribution applies to continuous variables, while the Binomial Distribution applies to discrete variables. However because of the Central Limit Theorum, the number of observations being large enough can make the distribution of binomial variables behave like a normal distribution.

You can calculate the mean of a binomial distribution `mu=n*p`

You can calculate variance with `sigma^2 = np(1-p)`

You can calculate stddev with the usual square root `sigma = sqrt(np(1-p))`

These can be accomplished with `scipy.stats.binom.mean(n,p)`, `scipy.stats.binom.var(n,p)`, and `scipy.stats.binom.std(n,p)`

### Sample and Sampling Distributions

When you don't actually know the probability of certain events happening, you can sample a population and find out a proportion `phat` which are one way, and `1-phat` which are the other way. (e.g, phat might be the number of people with red hair / n to get proportion like 0.33 if it's 33/100). the mean of this sample is `u=phat` which isn't very fair, so you have to collect more samples, to see a Sample Distribution. In this case you're plotting the means (`mu`, i.e., `phat`) for each sample).

With enough samples, the central limit theorem "ensures" you get a normal distribution of means. Then the mean of this distribution will be the mean of the sample means and assumed to be the population mean (so we use mu and capital letters) or `mu_p=sum(x-1 to N)phat_i / N`

The standard deviation is called the standard error when dealing with probability distributions and is calculated as `sigma_p = sqrt(p(1-p)/n)`

### Confidence Intervals

A confidence interval is a range of values around a sample statistic within which we're confident that the true parameter lies.

How do we define, e.g., 95% confidence interval? Since the data is showing a normal distribution, we can look up a table of z-scores to find out what our margin of error is, to give a confidence interval for our mean. e.g, if the mean is 0.33, you look up z-score and multiply it by the standard deviation (standard error) that we got. the z-score for 95% confidence interval is 1.96 and let's say the standard error is 0.0466, then your confidence interval is `0.33 +/- (1.96*0.466)` or `0.33 +/- 0.091`, so `mu +/- (Zscore * stderror)`

### Lab: Sampling Distributions

Right at the top of the lab:

> Most statistical analysis involves working with distributions - usually of sample data.

When talking about probability the mean is also known as the _expected value_.

The central limit theorem applies to any distribution of sample data if the size of the sample is large enough. The effect of the central limit theorem is that as you increase the number of and/or size of samples, the mean remains constant but the amount of variance around it is reduced.

In a confidence interval, the value of the +/- is called the _margin of error_.

What about when the data is continuous instead of discrete? Up until now we've been treating discrete values as continuous and creating sampling distributions of _proportions_, i.e., `phat` ("P hat"). Formulae are different when the data is continuous.

In this case, the means of each sample are called `xbar` ("X Bar") and  the sampling distribution of those means will be called `Xbar` (capital X).

If a variable X can be assumed to be random variable representing every possible outcome then its mean (`mu_x`) is the population mean (`mu`). The mean of the `Xbar` sampling distribution (which is indicated as `mu_xbar`) is considered to have the same value. Or, `mu_x = mu_xbar`.

The standard deviation of the sample mean, which is technically the standard error, is `sigma_xbar = sigma/sqrt(n)` where `sigma` is the population stddev and `n` is the size of each sample. Since our population stddev (`sigma`) is unknown, we can use the full sample standard deviation `s` instead: `SE_xbar ~= s/sqrt(n)`

`scipy.stats.norm.interval` can be used to calculate a confidence interval for a normal distribution,e.g., `scipy.stats.norm.interval(0.95, m, sd)` where `m` is mean-of-means (mean of distribution) and `sd` is standard error (std dev of means)

They have a nice full example at the end of this lab if you need to refer back.

### Hypothesis Testing

Define two mutually exclusive hypotheses `H_0` (the null hypothesis we wish to disprove) and `H_1` (the alternative hypothesis, the belief we want to find evidence to support).

The terms come in fast and furious here so I'll just make the rest of the notes from the lab.

### Lab: Hypothesis Testing

**SINGLE TAILED**

Say you're trying to prove something, like the population mean (`mu`) is > 0. You can't do this from a single sample, but you start with a sample with mean `xbar`, which is greater than 0.

Start with the null hypothesis `H_0 : mu <= 0` and the alternative hypothesis `H_1: mu > 0`

To prove that `H_0` is probably false (you can't state with certainty, just probably), you attempt to prove that it's true first. In this case it would mean that the sampling distribution for the values would be a normal distribution with a mean of `0` (or less I guess). So from that normal distribution, how probable is it to get a sample with a high mean above 0? How improbable would it need to be for us to conclude that `H_0` is probably false?

How many stddev's above the `H_0` mean of `0` is our sample mean `xbar`? Once we know that, we measure the AUC between that point onward to the right, which will give us the probability of observing a mean that is at least as high as our sample mean. This number of stddevs above is called our test statistic (`t-statistic`) and the AUC there the `p-value`.

We then set a threshold `alpha` under which we consider we consider it too improbable under random chance alone that our sample mean was in this area. Most commonly it's set to 0.05 (5%).

When the stddev of the pop is known, we call it a `z-test` because normal distribution often called a z-distribution and because of `z-zcores`. When the stddev of the pop is not known, it's referred to as a t-test and based on an adjusted version of a normal distribution called a Student's t distribution (where the distribution is flattened to allow for more sample variation depending on the sample size).

TIL:

> Generally, with a sample size of 30 or more, a t-test is approximately equivalent to a t-test

We've been talking about a Single Sample test (because we're comparing the mean of a single sample to the hypothesized pop mean) and it's one-tailed (because we want to know if it's on the right tail of the distribution).

The formula for a one-tailed, single-sample t-test is `t=(xbar - mu) / (s / sqrt(n))` where `xbar` is the sample mean, `mu` is the pop mean, `s` is the stddev, and `n` is the sample size. The numerator is thought of as the _signal_ and the denominator as the _noise_. The t-statistic is essentially the ratio of signal-to-noise, and measures the number of standard errors between the `H_0` value and the observed sample mean. A large value tells you that your result/signal was much larger than you would typically expect by chance.

`t, p = scipy.stats.ttest_1samp(sample, 0)` is a two-tailed test, so make sure you cut `p` in half if you're doing a one-tailed test.

If `t * pop.std()` is greater than the right-sided confidence interval for a 90% confidence interval (90% because that leaves 10% or 0.1, and we're doing right-tailed, so 0.05 or 5%), then it's unlikely under random chance that our sample mean is greater than the `H_0` mean so we can safely reject he null hypothesis. You can alternately state that if after calculating `t, p` from `ttest_1samp()` as above (and cutting `p` in half) that `p < 0.05` then we can say the same thing (since the p value is the AUC past the t*pop.std() line and 0.05 is the AUC for critical value)

**TWO TAILED**

`H_0: mu = 0` and `H_1: mu != 0`

When running `t,p=stats.ttest_1samp(sample,0)` this time you don't need to cut `p` in half because it's already been doubled for us in the function for a two-tailed test.

This time they do a 95% confidence interval leaving 2.5% for each tail. We're still testing whether `p < 0.05` later, it's just that half of it is in one tail and half of its AUC is under the other.

> You may note that doubling the p-value in a two-tailed test makes it harder to reject the null. This is true; we require more evidence because we are asking a more complicated question.

**TWO SAMPLE**

Let's say you want to compare two samples against each other, e.g., two samples of students, one sample had prior math study, other sample did not. You hypothesize that the grades will be higher for the students who had previously studied math.

`H_0: mu_1 <= mu_2` and `H_1: mu_1 > mu_2`

Apparently the formula for the t-statistic is a bit different but they don't elaborate.

`t, p = stats.ttest_ind(sample1, sample2)`

It's an "independent samples" t-test function. It's also assumed two-tailed so we use 90% confidence interval for our one-tailed hypothesis above, and we make sure to cut `p` in half too. If `p<alpha` (alpha=0.05, the critical value) then reject `H_0` and the kids with prior math probably have better scores

I re-ran it with the standard deviation sent to `np.random.normal()` at 2.0 and the test failed. So he did pick specific data to support the test succeeding here. And I've showed that by increasing the stddev it was more likely that the higher average for math people was just due to random chance which makes intuitive sense. Cool.

**PAIRED TESTS**

In the previous two-sample test, the samples were independent, i.e., no relationship between the observations in the first sample and the observations in the second sample. Consider two samples where the first is grades of students who took a mid-term and the second is the same students but graded on their final exam. In this case it's more appropriate to compare the two test scores for each individual student than to compare average grade improvement.

This is known as a paired-samples t-test or a dependent-samples t-test. It tests whether the changes tend to be in the positive or negative direction.

`t, p = stats.ttest_rel(examSample, midtermSample)` is still-two-tailed, make sure to halve `p` and use 90% confidence interval later.

This was one of the better labs in the course.

### Lesson Review

Passed lesson review by looking up the binomial distribution PMF section and multiplying 5 choose 3 by (p^k)*((1-p)^(n-k)).

## Module Assessments

Unavailable
