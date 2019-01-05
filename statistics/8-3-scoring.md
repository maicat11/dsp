[Think Stats Chapter 8 Exercise 3](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77)

---

**Write a function that takes a goal-scoring rate, lam, in goals per game, and simulates a game by generating the time between goals until the total time exceeds 1 game, then returns the number of goals scored.**
```
def SimulateGame(lam):
    """Simulates a game and returns the estimated goal-scoring rate.

    lam: actual goal scoring rate in goals per game
    """
    goals = 0
    t = 0
    while True:
        time_between_goals = random.expovariate(lam)
        t += time_between_goals
        if t > 1:
            break
        goals += 1

    # estimated goal-scoring rate is the actual number of goals scored
    L = goals
    return L
```

**Write another function that simulates many games, stores the estimates of lam, then computes their mean error and RMSE.**
```
# Solution goes here
def MultipleGames(games, lam):
    all_lam = []
    
    for n in range(games):
        all_lam.append(SimulateGame(lam))
    
    return MeanError(all_lam, lam), RMSE(all_lam, lam)

mean_error, rmse = MultipleGames(1000000, 3)
print('RMSE (L): {}'.format(rmse))
print('Mean Error (L): {}'.format(mean_error))
```
RMSE (L): 1.7323980489483357    
Mean Error (L): 0.003859


**Is this way of making an estimate biased?**    
As the number of game simulation increase, then the mean-error drecreases and gets closer to zero.  An indication that this simulation is unbiased. 

---
