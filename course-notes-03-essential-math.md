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

## Matrices

## Module Assessments

# Statistics and Probability

## Statistics Fundamentals

## Probability

## Module Assessments
