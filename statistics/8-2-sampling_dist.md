[Think Stats Chapter 8 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77) (scoring)

**Suppose you draw a sample with size n=10 from an exponential distribution with λ=2. Simulate this experiment 1000 times and plot the sampling distribution of the estimate L. Compute the standard error of the estimate and the 90% confidence interval.**

```
def Exercise_8_2_part_a(n=10, iters=1000):
    lam = 2

    estimates = [] 
    for _ in range(iters):
        xs = np.random.exponential(1.0/lam, n)
        L = 1 / np.mean(xs)
        Lm = np.log(2) / thinkstats2.Median(xs)
        estimates.append(L)

    print('Standard Error:', round(RMSE(estimates, lam),5))
    
    cdf = thinkstats2.Cdf(estimates)
    ci_lower, ci_upper = cdf.Percentile(5), cdf.Percentile(95)
    print('Confidence Interval: ({}, {})'.format(round(ci_lower,5), round(ci_upper,5)))
    
    thinkplot.Plot([ci_lower, ci_lower], [0, 1], color='0.8', linewidth=3)
    thinkplot.Plot([ci_upper, ci_upper], [0, 1], color='0.8', linewidth=3)
    thinkplot.Cdf(cdf)
    thinkplot.Config(title = 'Sampling Distribution',
                     xlabel='Estimates',
                     ylabel='CDF',
                     legend=False)
    
Exercise_8_2_part_a()
```
Standard Error: 0.86221   
Confidence Interval: (1.2833, 3.81024)    
*(Answer varies based on samples)*

<img width="398" alt="screen shot 2018-12-31 at 10 47 01 am" src="https://user-images.githubusercontent.com/20651507/50566004-91877e00-0ce9-11e9-9514-1e83b1a31e46.png">

**Repeat the experiment with a few different values of n and make a plot of standard error versus n.**
```
def Exercise_8_2_part_b(n, iters=1000):
    lam = 2

    estimates = [] 
    for _ in range(iters):
        xs = np.random.exponential(1.0/lam, n)
        L = 1 / np.mean(xs)
        Lm = np.log(2) / thinkstats2.Median(xs)
        estimates.append(L)
        
    cdf = thinkstats2.Cdf(estimates)
    ci_lower, ci_upper = cdf.Percentile(5), cdf.Percentile(95)
    print('Confidence Interval for n={}: ({}, {})'.format(n, round(ci_lower,3), round(ci_upper,3)))
    
    return RMSE(estimates, lam)

all_rmse = []
sample_sizes = [10,20,50,100,500,1000,5000,10000]

for size in sample_sizes:
    all_rmse.append(Exercise_8_2_part_b(n=size))
    
thinkplot.Plot(sample_sizes, all_rmse, color='red')
thinkplot.Config(title = 'Error Reduction',
                 xlabel='n sizes',
                 ylabel='Standard Error',
                 legend=False)
```
Confidence Interval for n=10: (1.276, 3.747)    
Confidence Interval for n=20: (1.41, 3.006)    
Confidence Interval for n=50: (1.588, 2.581)    
Confidence Interval for n=100: (1.704, 2.367)    
Confidence Interval for n=500: (1.853, 2.15)    
Confidence Interval for n=1000: (1.899, 2.106)    
Confidence Interval for n=5000: (1.955, 2.047)    
Confidence Interval for n=10000: (1.966, 2.032)  
*The actual lambda value of 2 falls in every confidence interval instance of n.*

<img width="410" alt="screen shot 2018-12-31 at 10 47 15 am" src="https://user-images.githubusercontent.com/20651507/50566018-b7148780-0ce9-11e9-9bb5-e1144dedbc44.png">
