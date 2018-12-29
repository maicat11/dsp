[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)


  `actual_child = thinkstats2.Pmf(resp.numkdhh, label='actual')`   
  `biased_child = BiasPmf(actual_child, label='observed')`   
  `# create the graph`
  `thinkplot.PrePlot(2)`  
  `thinkplot.Pmfs([actual_child, biased_child])`   
  `thinkplot.Config(xlabel='Num of children', ylabel='PMF')`   

image goes here

`print('Actual mean: {}'.format(actual_child.Mean()))`   
 `print('Biased mean: {}'.format(biased_child.Mean()))`    
 
Actual mean: 1.024205155043831   
Biased mean: 2.403679100664282
