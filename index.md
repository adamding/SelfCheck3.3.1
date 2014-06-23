---
title       : Self-Check Questions (ungraded)
subtitle    : Mean and Variance from the pdf
author      : Aidong Adam Ding
job         :  Made using Slidify in R. (Click mouse then right arrow key for next slide.)
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : solarized_dark      # 
widgets     : [mathjax, quiz, bootstrap]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides

--- &multitext

## Question 1: 
X has pdf $f(x)=x^2/338350,\quad x=1,2,...,100$.

Calculate the *mean* and *standard deviation* of X.

1. E(X)=?
2. sd(X)=?

````

*** .explanation

1) E(X)= <span class='answer'>75.3731</span>

E(X) sums x*f(x) over all cases 1,2,...,100. 

This is calculated in R with:

x<-(1:100)

fx<-x\^2/338350

EX<-sum(x*fx)

2) sd(X)= <span class='answer'>19.46</span>

Notice that the is *standard deviation*, so need to take square-root of variance. 

Using R

VarX<-sum((x-EX)\^2*fx)

sdX<-sqrt(VarX) 


*** .hint
For E(X), remember to sum x*f(x), not to sum f(x).

For sd(X), need to do Var(X): sum over (x-EX)\^2*f(x).

Remember sd(X) is the square-root of variance. 


--- &multitext

## Question 2: 
Using R, calculate the *mean* and *variance*  of the random variable X with the following pdf: $f(x) = \frac{3x^2}{2},\quad  - 1 \leqslant x \leqslant 1$. 

1. E(X)=?
2. Var(X)=?

````

*** .explanation

1) E(X)= <span class='answer'> 0 </span>

This is a continuous random variable.

E(X) integrates x*f(x) from -1 to 1. 

This is calculated in R with:

EX<-integrate(function(x) x*3*x\^2/2, lower=-1, upper=1)$value 

2) Var(X)= <span class='answer'> 0.6</span>

E(X) integrates (x-EX)\^2*f(x) from -1 to 1.

Using R

VarX<-integrate(function(x) (x-EX)\^2*3*x\^2/2, lower=-1, upper=1)$value  


*** .hint
This is a continuous random variable. So using integrations to calculate.

For E(X), the integrand is x*f(x), not f(x).

For Var(X), the integrand is (x-EX)\^2*f(x). Do not forget the square.

--- &multitext

## Question 3: 
X=3Y+2.
If E(Y)=1 and Var(Y)=4, find E(X) and Var(X).

1. E(X)=?
2. Var(X)=?

*** .explanation

1) E(X)= <span class='answer'> 5 </span>

E(X)=3(1)+2=5

2) Var(X)= <span class='answer'> 36</span>

Var(X)=9Var(Y)=36


*** .hint
Using the properties for linear combinations.

For Var(X), be careful NOT Var(aX+b)=a*Var(X)+b

--- &multitext

## Question 4: 
The random variable Y has pdf: 
$f(y) = e^{- y},\quad y > 0$.
Consider a linear transformation X=5Y-4. 

1. E(Y)=?
2. Var(Y)=?
3. E(X)=?
4. Var(X)=?

````

*** .explanation

1) E(Y)= <span class='answer'> 1 </span>

E(Y)=$\int_0^\infty y*exp(y)dy$ =1

integrate(function(x) x*exp(-x), lower=0, upper=Inf)$value 

2) Var(Y)= <span class='answer'> 1</span>

Var(Y)=$\int_0^\infty (y-1)^2*exp(y)dy$ =1

integrate(function(x) (x-1)\^2*exp(-x), lower=0, upper=Inf)$value 

3) E(X)= <span class='answer'> 1 </span>

E(X)=5*E(X)-4=5(1)-4=1

4) Var(X)= <span class='answer'> 25</span>

Var(X)=5\^2*Var(Y)

*** .hint
Using integrations to find E(Y) and Var(Y) first.

Then use the properties for linear combinations on E(X) and Var(X).

