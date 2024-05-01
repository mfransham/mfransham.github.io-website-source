---
title: Modelling rates with Poisson regression
author: Mark Fransham
date: '2024-04-30'
slug: poisson-model-rates
categories: []
tags:
subtitle: ''
summary: 'Modelling rates with Poisson regression'
---

**Modelling rates with Poisson regression** 

A simple Poisson regression model is given by 

$$
log[E(Y|X=x)] \equiv log[E(Y|x)] = \alpha + \beta x
$$

where $Y$ is a random variable that follows a Poisson distribution with mean E(Y|X). 

The Poisson distribution is a common probability distribution, an alternative to the normal distribution which you may be more familiar with. With the Poisson distribution, the outcomes can only be integers (i.e. 0, 1, 2, ...) and can only be non-negative. Consequently the Poisson distribution is useful for modelling counts of events e.g. number of people diagnosed with a particular condition, deaths, traffic accidents etc.

By contrast, a linear regression model assumes a conditional normal distribution with possible values ranging continuously from $-\infty$ to $+\infty$ - so using this for non-negative discrete counts may produce misleading results. This is especially the case where the number of events is small as the distribution is likely to be asymmetric as it is constrained (by zero) at the lower tail. 

So modelling our count variable with a conditional Poisson distribution is often appropriate. However the number of events typically depends upon the size of the population at risk of experiencing that event. For example, we would expect more diagnoses in a place with 10,000 residents compared to a place with 100 residents. To account for the different size of populations at risk, rather than modelling the count $Y$ we might want to model the rate $Y/N$ where $N$ is the total population at risk. For example, if 10 people experienced an event in a place with 500 residents, the rate would be $10/500 = 0.02$ 

Starting with the rate as the dependent variable and then rearranging the equation (using the [rules of logarithms](https://www.bbc.co.uk/bitesize/guides/zn3ty9q/revision/2)) so that we still have a count as our dependent variable, we arrive at the following:

$$
log[E(\frac{Y}{N}|x)] = log[\frac{E(Y|x)}{N}] = log[E(Y|x)] - log N = \alpha + \beta x
$$

and 

$$
log[E(Y|x)] = \alpha + \beta x + log N
$$

This $log N$ term on the RHS is the natural logarithm of the population. When modelling counts in which the population at risk varies, we would include the log population in our Poisson regression model as an *offset* term, which is a term in the model where the regression coefficient is fixed at 1. This is because, in the above equation, there is no regression coefficient to estimate for $log N$. In R, this is specified in the `glm()` function using the `offset` argument. 

**Interpreting Poisson regression coefficients as risk ratios**

Poisson regression coefficients are often interpreted as risk ratios - let's explain how.

From the equation above, we have

$$
log[E(Y|x)] = \alpha + \beta x + log N_x
$$

If we define the conditional rate as $R_x = E[{Y|x}]/{N_x}$ then we can rearrange this as

$$
log(R_x) = \alpha + \beta x
$$

and for a one unit increment in the explanatory variable $x$

$$
log(R_{x+1}) = \alpha + \beta (x + 1) = \alpha + \beta x + \beta 
$$

Subtracting these two and rearranging gives us

$$
log(R_{x+1}) - log(R_x) = \beta
$$

$$
log(\frac{R_{x+1}}{R_x}) = \beta
$$

$$
\frac{R_{x+1}}{R_x} = e ^ \beta
$$

So the exponentiating the regression coefficient $e ^ \beta$ gives us the ratio of two rates - the ratio of the rate for $x+1$ divided by the rate for $x$. Another way of writing this is that 

$$
R_{x+1} =  R_x \times e ^ \beta
$$

So if we compare two units of observation with explanatory variables that are different by one unit, our Poisson regression model tell us that the expected rate is multiplied by $e ^ \beta$. 
