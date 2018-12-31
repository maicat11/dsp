[Think Stats Chapter 7 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2008.html#toc70) (weight vs. age)

**Using data from the NSFG, make a scatter plot of birth weight versus mother’s age**   

```
import first
live, firsts, others = first.MakeFrames()
live = live.dropna(subset=['agepreg', 'totalwgt_lb'])

ages, weights = live['agepreg'], live['totalwgt_lb']
ages = Jitter(ages, 0.5)

thinkplot.Scatter(ages, weights, alpha=0.1, s=10)
thinkplot.Config(xlabel='Age of Mother (years)',
                 ylabel='Weight of baby (lbs)',
                 axis=[10, 45, 0, 15],
                 legend=False)
```
<img width="410" alt="screen shot 2018-12-31 at 7 54 04 am" src="https://user-images.githubusercontent.com/20651507/50563517-5af23900-0cd2-11e9-8c0c-d79a079bdb51.png">

*This appears to be a weak relationship between mother's age and baby weight.*   

**Plot percentiles of birth weight versus mother’s age.**

```
bins = np.arange(10, 46, 3)
indices = np.digitize(live['agepreg'], bins)
groups = live.groupby(indices)

ages = [group.agepreg.mean() for i, group in groups][1:-1]
cdfs = [thinkstats2.Cdf(group.totalwgt_lb) for i, group in groups][1:-1]

for percent in [75, 50, 25]:
    weight_percentiles = [cdf.Percentile(percent) for cdf in cdfs]
    label = '%dth' % percent
    thinkplot.Plot(ages, weight_percentiles, label=label)
    
thinkplot.Config(xlabel='Mother\'s Age (years)',
                 ylabel='Baby Weight (lbs)',
                 xlim=[10, 45],
                 legend=True)
```
graph2 here

*This plot suggests there is a non-linear relationship between mother's age and babies weight.    
There is a noticible weight increase from years 15-25, but after that the relationship appears to level off.*

**Compute Pearson’s and Spearman’s correlations.** 
```
ages, weights = live['agepreg'], live['totalwgt_lb']

pearson_corr = Corr(ages, weights)
spearman_corr = SpearmanCorr(ages, weights)

print('Pearson\'s Correlation: {}'.format(round(pearson_corr,5)))
print('Spearman\'s Correlation: {}'.format(round(spearman_corr,5)))
```
Pearson's Correlation: 0.06883
Spearman's Correlation: 0.09461

*The low correlation values supports the scatter plot that there is a weak linear relationship.*   

**How would you characterize the relationship between these variables?**   
*There is a difference in the variables most likely due to outliers that the Pearson coefficient 
is more sensitive to outliers or there could possibly a non-linear relationship.*

