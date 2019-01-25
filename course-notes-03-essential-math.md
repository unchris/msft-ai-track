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
- chain rule: 'f(x) = g(h(x))` then `f'(x) = g'(h(x)) * h'(x)`

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

## Matrices

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

```
numpy.array([[1,2,3],
             [4,5,6]])

or the specialist subclass

```
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

```
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

```
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

## Statistics Fundamentals

### Data

### Visualizing Data

### Lab: Data and Visualization

### Measures of Central Tendency

### Measures of Variance

### Lab: Statistics Fundamentals

### Comparing Data

### Lab: Comparing Data

### Lesson Review

## Probability

## Module Assessments

Unavailable
