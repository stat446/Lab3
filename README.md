# Lab3


## Lab Overview
All students attending class in the group can turn in a single document with each participants name. Students not attending class will need to complete their own lab.

You have been hired to consult on a project by the Montana Department of Natural Resources. The goal is to collect data on the abundance of the Western meadowlark across a study area. Your sampling frame consists of two hundred plots of land and your budget allows sampling of twenty plots. There are four terrain types within the study area:

- desert (40 plots)
- forest (40 plots)
- wetland (20 plots)
- prairie (100 plots)

The dataset can be obtained with the following R code.

contained in the file:  `birdsurvey.csv' which can be accessed on D2L.

```
birds <- read.csv('http://math.montana.edu/ahoegh/teaching/stat446/birdsurvey.csv', header = T)
```

#### 1. 

##### a. (4 points)
Take a SRS of size 20 and create an approximate sampling distribution (by repeated samples) of the population total.

##### b. (3 points)
Plot the approximate sampling distribution and the true population total.

##### c. (3 points)
Compute the MSE of the estimator.

#### 2. 

##### a. (4 points)
Take a stratified random sample where five samples are drawn from each terrain type and create an approximate sampling distribution (by repeated samples) of the population total.
```
#Hint this will take one sample
birds %>% group_by(terrain) %>% sample_n(5) %>% ungroup() %>% select(bird.counts) %>% 
summarize(ybar = mean(bird.counts)) %>% pull()
```

##### b. (3 points)
Plot the approximate sampling distribution and the true population total.

##### c. (3 points)
Compute the MSE of the estimator.

#### 3.  (5 points)

##### a. (4 points)

 What method was most effective in terms of MSE? What shortcomings did the other methods have? 
 
##### b. (4 points)
Suppose another option was to use a stratified sample where 10 % of the sampling units in each strata are selected. Do you think this will perform better or worse than the option in part 2, why?
