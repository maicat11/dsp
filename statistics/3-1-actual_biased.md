[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

  `resp = nsfg.ReadFemResp()`    
  `actual_child = thinkstats2.Pmf(resp.numkdhh, label='actual')`   

```
def BiasPmf(pmf, label):   
    new_pmf = pmf.Copy(label=label) 
    for x, p in pmf.Items():   
        new_pmf.Mult(x, x)   
    new_pmf.Normalize()   
    return new_pmf  
```  
  
  `biased_child = BiasPmf(actual_child, label='observed')`   
  
  `# create graph`   
  `thinkplot.PrePlot(2)`  
  `thinkplot.Pmfs([actual_child, biased_child])`   
  `thinkplot.Config(xlabel='Num of children', ylabel='PMF')`   

<img width="402" alt="exercise_3-1_graph" src="https://user-images.githubusercontent.com/20651507/50542156-15ffc280-0b6b-11e9-83cc-23f022137033.png">

`print('Actual mean: {}'.format(actual_child.Mean()))`   
 `print('Biased mean: {}'.format(biased_child.Mean()))`    
 
Actual mean: 1.024205155043831   
Biased mean: 2.403679100664282
