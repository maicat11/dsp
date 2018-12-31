[Think Stats Chapter 6 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2007.html#toc60) (household income)

**Compute the median, mean, skewness and Pearson’s skewness of the resulting sample.**

```
median = Median(sample)
mean = Mean(sample)
skewness = Skewness(sample)
pearson_skewness = PearsonMedianSkewness(sample)

print('Median: ${}'.format(round(median),2))
print('Mean: ${}'.format(round(mean,2)))
print('Skewness: {}'.format(round(skewness,5)))
print("Pearson's Skewness: {}".format(round(pearson_skewness, 5)))
```
Median: $51226.0     
Mean: $74278.71    
Skewness: 4.94992   
Pearson's Skewness: 0.73613   

**What fraction of households report a taxable income below the mean?**
```
sample_cdf = thinkstats2.Cdf(sample)
below_mean = sample_cdf.PercentileRank(mean)
print('Income reported below the mean is {}%'.format(round(below_mean,2)))
```
Income reported below the mean is 66.0%

**How do the results depend on the assumed upper bound?**   
*All results would change if the assumed upper bound were changed.  
A higher/lower upperbound would increase/decrease the mean.  
This would inturn change the skewness values since they are reliant on the mean.  
The only values unaffected is the median, which would most likely remain the same.*
