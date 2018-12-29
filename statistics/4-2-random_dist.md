[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)


```
# Generate 1000 numbers from numpy.random.random.
# verify a sample of the list
rand_vals = np.random.random(size=1000)
rand_vals[:5]
```
Output: array([0.70951536, 0.36790217, 0.46374716, 0.04632809, 0.56911358])

```
# Plot the PMF of the list above
rand_pmf = thinkstats2.Pmf(rand_vals, label='random vals')
thinkplot.Hist(rand_pmf) 
thinkplot.Config(xlabel='Random Values', ylabel='PMF')
```

Graph1 here

There are too many different individual values (1000), their frequencies are low and not visible on the graph

```
rand_cdf = thinkstats2.Cdf(rand_vals, label='rand vals')
thinkplot.Cdf(rand_cdf)
thinkplot.Config(xlabel='Random Values', ylabel='CDF', loc='upper left')
```

Graph2 here

The mostly straight line is an indication that the distribution is uniform, a mostly one-to-one relationship of percentle rank and its distribution.
