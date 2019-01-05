[Think Stats Chapter 9 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2010.html#toc90) (resampling)

**Write a class named DiffMeansResample that inherits from DiffMeansPermute and overrides RunModel to implement resampling, rather than permutation.**
```
class DiffMeansResample(DiffMeansPermute):
    
    def RunModel(self):
        
        group1 = np.random.choice(self.pool, self.n, replace=True)
        group2 = np.random.choice(self.pool, self.m, replace=True)
        return group1, group2
```

**Use this model to test the differences in pregnancy length and birth weight.** 
```
import first
live, firsts, others = first.MakeFrames()

def RunResampleTest(firsts, others, column):

    if column == 'preglength':
        data = firsts.prglngth.values, others.prglngth.values
    elif column == 'totalwgt_lb':
        data = (firsts.totalwgt_lb.dropna().values, others.totalwgt_lb.dropna().values)

    ht = DiffMeansPermute(data)
    p_value = ht.PValue(iters=10000)
    print(f'\ndifference means resample {column}')
    print('p-value =', p_value)
    print('actual =', ht.actual)
    print('test stat max =', ht.MaxTestStat())

RunResampleTest(firsts, others, 'preglength')
RunResampleTest(firsts, others, 'totalwgt_lb')
```
difference means resample preglength    
p-value = 0.1662    
actual = 0.07803726677754952    
test stat max = 0.2459321133130956    

difference means resample totalwgt_lb    
p-value = 0.0    
actual = 0.12476118453549034    
test stat max = 0.11445949838272984     


**How much does the model affect the results?**    
*Using resampling instead of permutation has very little effect on the results.  There is no evidence to sway a choice  of resampling over permutation.*

