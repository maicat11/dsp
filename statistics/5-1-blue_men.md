[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

```
import scipy.stats
mu = 178
sigma = 7.7
dist = scipy.stats.norm(loc=mu, scale=sigma)

# 5'10" ~ 177.8 cm and 6'1" ~ 185.42cm 
dist.cdf(185.42) - dist.cdf(177.8)
```
Roughly 0.3427 or 34.3% of the population of men would qualify for the Blue Man Group. 
