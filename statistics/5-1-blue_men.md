[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

```
import scipy.stats
mu = 178
sigma = 7.7
dist = scipy.stats.norm(loc=mu, scale=sigma)

# convert heights into cm
height_5_10 = 177.8
height_6_1 = 185.4
dist.cdf(height_6_1) - dist.cdf(height_5_10)
```
Roughly 0.3421 or 34.2% of the population of men would qualify for the Blue Man Group. 
