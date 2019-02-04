Data Science Research Methods: Python Edition - Course Notes
============
February 2019
Chris Cameron

I am auditing [Microsoft Professional Program for Artificial Intelligence track](https://academy.microsoft.com/en-us/tracks/artificial-intelligence/).

The fitth of 10 courses is [Data Science Research Methods: Python Edition](https://courses.edx.org/courses/course-v1:Microsoft+DAT273x+1T2019/courseware/9a27d5b6-48c4-1194-3afa-cf0232935159/8f6609c4-212c-a8bf-7283-d22e85998cc9/).

# Introduction

The Jupyter Notebooks for the labs are [here](https://github.com/MicrosoftLearning/Research-Methods-for-Data-Science-with-Python)

# The Research Process

## The Research Process

### Goals of Research

1. Question Development, with Analytics in mind
2. Collecting data for the question you want to answer
  - straight analytics you already have the data sources, but you might not like the variables
  - in research, you get to find the data you need to answer your question
3. Dynamic, iterative problem-solving process

Process
- frame the question
- form a theory
- form a hypothesis
- design an experiment / study and test
- draw conclusions; repeat as necessary
- final conclusion

Goals for you (me) in the course
- when given _data out of context_, you can be more effective
- _prevent data misuse_; not all data are created equal
- know _when to recommend_ data collection
_ can design your own research

### Goals of Research Part 2

**Basic Reasearch**

- describe / explain / predict / control (these are the subtypes)
- goal: understand X
  - how does x work
  - why do customers do x
- advantage: planning next moves
- about understanding your topic
- doesn't allow us to "make new moves"

**Applied Research**

- evaluation of practice, product, idea, assumption
- choices often made based on _assumptions_ or _intuition_
- be right. stand on firm ground!
- a way to test assumptions
- could be smaller scale tests, shorter, tests

### The Circle of Science

1. Theory: detailed explanation of how something works
2. Hypothesis: what i should expect to see if theory is true
3. Data Collection: use appropriate research methods
4. Descriptive Statistics: is my hypothesis suported _in my sample_?
5. Inferential Statistics: If so, can I reject 'chance' as an explanation and generalize to the population?
6. Draw Conclusions: implications for Theory and Methods
7. back to 1!

### Clarifying the Questions

Common Problem: overstuff a survey
- we want to know everything

Problem: depth(quality) vs breadth

Clarifying Interview
- uncover the 'question behind the question'
- re-imagining the project around that

goal
- 1-2 learning objectives
- several lines of attack for those objectives
- tight focus on key objectives

Research Foxtrot
1. Look at proposed design. Step back. What are underlying assumptions and questions?
2. Formalize that (theory)
3. Identify focused several lines of attack (hypotheses) ways of testing that theory
4. Develop study / survey around those

## The Psychology of Providing Data

### The Psychology of Providing Data - Part 1

Participants are people.
- not robots giving info
- biased!
- influenced by design decisions

People want to manage their impressions of you and themselves

Rule 1: Be NEUTRAL. If you say "how often do you recycle?" they'll say "ALL THE TIME!" because they want to feel good

Rule 2: Sound Objective, because people are really good at knowing what answer you're looking for. Some want to sabotage you, others want to co-operate.

### The Psychology of Providing Data - Part 2

People do not know _why_ they do things and will _make up_ answers when asked.

People are biased by the order of things.

Especially with "why?" questions, people make things up.

more generally: avoid more complex questions.

goal for survey questions: you want Simple and Knowable questions. If people can't "gut" know the answer to it, don't ask them.

### The Psychology of Providing Data - Part 3

Placebo Effects

- Beliefs matter. e.g., products are _more effective_ when people think they are.
- manage expectations. if something is more expensive, they assume it's better

Observer bias: see what you want to see
Observer effect: act differently when observed

Solution: Blinding

neither participants, _nor people collecting the data_, should know what to expect.

if you expose people to words about the elderly, people appeared to walk away slowly. so then they didn't tell the observers what the study was about and the difference went away.

double-blind is best

## Knowledge Check

### Knowledge Check

not available

# Planning for Analysis

## Planning for Analysis

### Samples vs Populations

samples are error-prone guesses. we almost never have population data in data science

problem is Sampling Error.
- sample may not be representative.
- the large the sample, the more trustworthy it is

Standard Error lets you know how trustworthy your sample is

### Null Hypothesis

A lot of this is repeating stuff from the Essential Math course. I'll only take notes that add to what is already learned.

### Discrediting the Null Hypothesis - P Values

large p value - result easily produced by random chance
small p value - not easily produced by random chance

"significant", but chance has not been disproved!

### Discrediting the Null Hypothesis - Confidence Intervals

Confidence interval can also tell you a range for where the true value is. larger sample sizes will give you a better interval too

## Power for Sample Size Planning

### Power Part 1

How do you know you have a big enough sample?

Power/Statistical Power: % of the time an effect will be detected

Power depends on
  - effect size (bigger effect is easier to detect)
  - sample size (bigger sample has more power)

### Power Part 2

Effect Size

Cohen's d (difference)

Numbers here in standard deviations. Jay Cohen (statistician) came up with these ranges:

* 0-0.2 = trivial
* 0.2 - 0.5 = small
* 0.5 - 0.8 = medium
* > 0.8 = large

r-value (correlation coefficient) is another way to measure.

you can convert between `r` and `d`

```python
r = d/sqrt(d**2 + 4)

d = (2*r)/sqrt(1 - r**2)
```

Basically this video is about making sure you have a large enough sample based on your effect size.

### Sample Size Planning

effect size to sample size is not a linear relationship

he shows a power chart which shows you several curves showing you x axis sample size and y axis power. each curve represents different Cohen's d-values.

Need samples > 400-500 for smaller effects

When comparing groups, size is per group

Better to just use the power calculation tools available in statistical packages.

## Research Practices

### False Positives - False Negatives

What happens when you have weak Power?

False Positive is a Type 1 Error
- Find effect when absent.
- 5% of the time with 95% power

False Negative is a Type 2 Error
- Find no effect/relationship when actually present
- 20% of time when actually present with 80% power

***Note: This video reminds me of the Replicability crisis in several fields right now.***

### Questionable Research Practices (QRPs)

Filtering for Significance
- what: selecting only `p < 0.05` results to share
- why it's bad: context of all results makes false positives clear

P-hacking
- what: trying many analyses, data subsets, etc to get `p < 0.5`
- why it's bad: guaranteed to find false positives
- really common when someone is motivated to find a significant result

HARKing
- what: hypothesizing after results are known
- why it's bad: overfitting. sample results are estimates only

Optional Stopping
- what: stopping your test during data collection when `p < 0.5`
- why it's bad: false positives guaranteed
- HUGE no-no. some people keep checking the data at every point coming in hoping for p<0.5.  BAD

## Knowledge Check

### Knowledge Check

Unavailable

## Lab

### Module 2 Lab

Five labs for module 2

- Sampling
- P Values
- CIs
- Power (part 1)
- Power (part 2)

I copied this verbatim from the P Values lab because even the guy's slides went against some of this advice

> There is a lot of confusion about *p*-values, so let's review:

> -   *p*-values represent how often you could get a result as big as you did *if the null were true*
> -   *p*-values therefore represent how easy/hard it would be to get a result by chance
> -   *p*-values do **not** tell you the probability that the result is due to chance; only the probability of seeing *your result* if the null were true
> -   If the *p*-value for a result is small, it would be rare to get that result by chance (i.e., if the null were true)
> -   If the *p*-value for a result is large, it would be common to get that result by chance (i.e., if the null were true)
> -   Conclusion: the *p*-value is a measure of "incompatibility" between your result and the null. If the *p*-value is small, one of the two (the data, or the null) is likely wrong. We opt to trust our data and reject the null.

> To be clear: the *p*-value is a backwards way of testing the null hypothesis. We would love to know the *probability* that the null hypothesis is true--the probability that the results *are* due to chance--but we cannot know that. You will often hear the *p*-value described this way, but that is **very wrong**.

> So, to repeat, the *p-value states the probability of getting **your result** if the null is true*. It is essentially a statement of incompatibility between your data and the null. A small *p*-value (typically, less than 5% or "&lt; . 05") tells you that the data and null are highly incompatible. Since you did in fact observe the data, you conclude the null hypothesis is false. This is the only use for the *p*-value.

In the lab about Confidence Intervals it needs access to a file I cloned outside of the docker container.

### Lab Check

# Research Claims

# Measurement

# Correlation and Experimental Designs
