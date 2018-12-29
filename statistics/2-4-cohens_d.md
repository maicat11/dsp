[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

`(firsts.totalwgt_lb.mean(), others.totalwgt_lb.mean()`   
First babies mean weight is ~7.201 and other babies mean weight is ~7.326.  

`firsts.totalwgt_lb.mean() - others.totalwgt_lb.mean()`   
This is a difference of ~ -0.125 less for first babies.  

    def CohenEffectSize(group1, group2):
        diff = group1.mean() - group2.mean()

        var1 = group1.var()
        var2 = group2.var()
        n1, n2 = len(group1), len(group2)

        pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
        d = diff / np.sqrt(pooled_var)
        return d
      
    CohenEffectSize(others.totalwgt_lb, firsts.totalwgt_lb)
Cohen's d (effect size) computed is ~ -0.088673.   
This represents distance between first and other babies means in standard deviations.    
It is negative because the first babies mean weight is less than the other babies mean weight.  
