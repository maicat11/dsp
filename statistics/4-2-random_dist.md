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
thinkplot.Pmf(rand_pmf, linewidth=0.1) 
thinkplot.Config(xlabel='Random Values', ylabel='PMF')
```

<img width="432" alt="exercise_4-2_pmf" src="https://user-images.githubusercontent.com/20651507/50542582-fb7f1680-0b75-11e9-9caa-7d90e6c957a0.png">

There are too many different individual values (1000), their frequencies are low and not visible on the graph

```
rand_cdf = thinkstats2.Cdf(rand_vals, label='rand vals')
thinkplot.Cdf(rand_cdf)
thinkplot.Config(xlabel='Random Values', ylabel='CDF', loc='upper left')
```

<img width="410" alt="exercise_4-2_cdf" src="https://user-images.githubusercontent.com/20651507/50542591-27020100-0b76-11e9-9d3c-809a30f6414e.png">

The mostly straight line is an indication that the distribution is uniform, a mostly one-to-one relationship of percentle rank and its distribution.
