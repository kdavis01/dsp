# Statistics

# Table of Contents

[1. Introduction](#section-a)  
[2. Why We Are Using Think Stats](#section-b)  
[3. Instructions for Cloning the Repo](#section-c)  
[4. Required Exercises](#section-d)  
[5. Optional Exercises](#section-e)  
[6. Recommended Reading](#section-f)  
[7. Resources](#section-g)

## <a name="section-a"></a>1.  Introduction

[<img src="img/think_stats.jpg" title="Think Stats"/>](http://greenteapress.com/thinkstats2/)

Use Allen Downey's [Think Stats (second edition)](http://greenteapress.com/thinkstats2/) book for getting up to speed with core ideas in statistics and how to approach them programmatically. This book is available online, or you can buy a paper copy if you would like.

Use this book as a reference when answering the 6 required statistics questions below.  The Think Stats book is approximately 200 pages in length.  **It is recommended that you read the entire book, particularly if you are less familiar with introductory statistical concepts.**

Complete the following exercises along with the questions in this file. Some can be solved using code provided with the book. The preface of Think Stats [explains](http://greenteapress.com/thinkstats2/html/thinkstats2001.html#toc2) how to use the code.  

Communicate the problem, how you solved it, and the solution, within each of the following [markdown](https://guides.github.com/features/mastering-markdown/) files. (You can include code blocks and images within markdown.)

## <a name="section-b"></a>2.  Why We Are Using Think Stats 

The stats exercises have been chosen to introduce/solidify some relevant statistical concepts related to data science.  The solutions for these exercises are available in the [ThinkStats repository on GitHub](https://github.com/AllenDowney/ThinkStats2).  You should focus on understanding the statistical concepts, python programming and interpreting the results.  If you are stuck, review the solutions and recode the python in a way that is more understandable to you. 

For example, in the first exercise, the author has already written a function to compute Cohen's D.  **You could import it, or you could write your own code to practice python and develop a deeper understanding of the concept.** 

Think Stats uses a higher degree of python complexity from the python tutorials and introductions to python concepts, and that is intentional to prepare you for the bootcamp.  

**One of the skills to learn here is to understand other people’s code.  And this author is quite experienced, so it’s good to learn how functions and imports work.**

---

## <a name="section-c"></a>3.  Instructions for Cloning the Repo 
Using the [code referenced in the book](https://github.com/AllenDowney/ThinkStats2), follow the step-by-step instructions below.  

**Step 1. Create a directory on your computer where you will do the prework.  Below is an example:**

```
(Mac):      /Users/yourname/ds/metis/metisgh/prework  
(Windows):  C:/ds/metis/metisgh/prework
```

**Step 2. cd into the prework directory.  Use GitHub to pull this repo to your computer.**

```
$ git clone https://github.com/AllenDowney/ThinkStats2.git
```

**Step 3.  Put your ipython notebook or python code files in this directory (that way, it can pull the needed dependencies):**

```
(Mac):     /Users/yourname/ds/metis/metisgh/prework/ThinkStats2/code  
(Windows):  C:/ds/metis/metisgh/prework/ThinkStats2/code
```

---


## <a name="section-d"></a>4.  Required Exercises

*Include your Python code, results and explanation (where applicable).*

### Q1. [Think Stats Chapter 2 Exercise 4](statistics/2-4-cohens_d.md) (effect size of Cohen's d)  
Cohen's D is an example of effect size.  Other examples of effect size are:  correlation between two variables, mean difference, regression coefficients and standardized test statistics such as: t, Z, F, etc. In this example, you will compute Cohen's D to quantify (or measure) the difference between two groups of data.   

You will see effect size again and again in results of algorithms that are run in data science.  For instance, in the bootcamp, when you run a regression analysis, you will recognize the t-statistic as an example of effect size.

>> I used the following code to investigate if first born babies are lighter or heavier than all other babies:

>> <img src="img/cohensd.png">

>> After splitting up the babies into 2 groups (first borns and others), I calculated the mean weight for each group and found that first born babies have a slightly lower mean weight at 7.2011 pounds compared to the mean weight of 7.3259 pounds for other babies. In calculating the Cohen's D Effect of the 2 groups, I got a -0.0887 effect from first babies to others. This means that the difference in weight between first babies and others is about 3 times as large as the difference in pregnancy lengths between first babies and others which has a Cohen's D Effect of about 0.0289.

### Q2. [Think Stats Chapter 3 Exercise 1](statistics/3-1-actual_biased.md) (actual vs. biased)
This problem presents a robust example of actual vs biased data.  As a data scientist, it will be important to examine not only the data that is available, but also the data that may be missing but highly relevant.  You will see how the absence of this relevant data will bias a dataset, its distribution, and ultimately, its statistical interpretation.

>> I first made a dictionary of the counts of the number of kids in each household taken from the nsfg respondents numkdhh column. From this dictionary, I made a pmf of this actual data and plotted it. The code and plot are as follows:

>> <img src="img/pmf.png">

>> Then I used a function that creates biased data from the actual data and plotted the biased data as follows:

>> <img src="img/biased.png">

>> Finally, I combined both the actual and biased data into one plot for comparison and calculated the means of both the actual and biased data. As suspected, the biased data has a much larger mean than the actual data.

>> <img src="img/plotboth.png">

### Q3. [Think Stats Chapter 4 Exercise 2](statistics/4-2-random_dist.md) (random distribution)  
This question asks you to examine the function that produces random numbers.  Is it really random?  A good way to test that is to examine the pmf and cdf of the list of random numbers and visualize the distribution.  If you're not sure what pmf is, read more about it in Chapter 3.

>> For this question I generated 1000 random numbers between 0 and 1 and plotted both the PMF and CDF of these random numbers. While the PMF was messy and unreadable on a graph, the CDF closely resembled a straight line, which shows that the distribution of these random numbers is approximaely uniform. The code I used for this question is as follows:

>> <img src="img/randomcdf.png">

### Q4. [Think Stats Chapter 5 Exercise 1](statistics/5-1-blue_men.md) (normal distribution of blue men)
This is a classic example of hypothesis testing using the normal distribution.  The effect size used here is the Z-statistic. 

>> For this question, I created a normal distribution using scipy.stats with a specified mu of 178 inches and sigma of 7.7 to mirror the BRFSS data. Using this distribution, I calculated the CDF of a height of 6'1" and subtracted that by the CDF of a height of 5'11" to get the percentage of people between these 2 heights who would qualify for the height requirement for the Blue Men Group. The answer was 34.27% of men. The code I used for this question is as follows:

>> <img src="img/blueman.png">

### Q5. Bayesian (Elvis Presley twin) 

Bayes' Theorem is an important tool in understanding what we really know, given evidence of other information we have, in a quantitative way.  It helps incorporate conditional probabilities into our conclusions.

Elvis Presley had a twin brother who died at birth.  What is the probability that Elvis was an identical twin? Assume we observe the following probabilities in the population: fraternal twin is 1/125 and identical twin is 1/300.  

>> The conditional probability that Elvis Presley was an indentical twin is 5/11. To calculate this, I first found the probabilities of having 2 identical boy twins (1/600) and having 2 fraternal boy twins (1/500). Then using those, I calculated the conditional probability that Elvis Presley was an identical twin given that his twin was a boy. (1/600) / ((1/600) + (1/500)) = 5/11 = 0.454545

---

### Q6. Bayesian &amp; Frequentist Comparison  
How do frequentist and Bayesian statistics compare?

>> Frequentist and Bayesian statistics both consider models to determine the probability of an event happening. However, in Frequentist Statistics, only repeatable random events can have probabilities, which are equal to their long term frequency of occurrence. The Frequentist will make an inference based purely on the likelihood of the data. In Bayesian statistics, probabilities are used for both data and hypotheses. The Baysian will make an inference based on the likelihood of the data as well as the observations of prior data. Bayesian statistics takes in the information around the event and updates the probabilities as more observations occur.

---

## <a name="section-e"></a>5.  Optional Exercises

The following exercises are optional, but we highly encourage you to complete them if you have the time.

### Q7. [Think Stats Chapter 7 Exercise 1](statistics/7-1-weight_vs_age.md) (correlation of weight vs. age)
In this exercise, you will compute the effect size of correlation.  Correlation measures the relationship of two variables, and data science is about exploring relationships in data.

>> For this question, I looked at the Mother's Age vs. the Child's Birth Weight and plotted 3 Birth Weight Percentiles from the 25th to the 75th. The plot and the code used are as follows:

>> <img src="img/weightpercentilevsage.png">

>> Next, I did a scatter plot of the Mother's Age and Child's Birth Weight to look at the correlation between the two variables. I calculated the Pearson's Correlation to be about 0.07 and the Spearman Rank Correlation to be about 0.09. Both the correlation factor calculations and the scatter plot show a weak relationship between these 2 variables. The code I used for the correlation factor calculations and the scatter plot are as follows:

>> <img src="img/weightagescatter.png">

### Q8. [Think Stats Chapter 8 Exercise 2](statistics/8-2-sampling_dist.md) (sampling distribution)
In the theoretical world, all data related to an experiment or a scientific problem would be available.  In the real world, some subset of that data is available.  This exercise asks you to take samples from an exponential distribution and examine how the standard error and confidence intervals vary with the sample size.

>> For this question, I used a function that took in different sample sizes (n) and calculated the standard error of the lambda estimates and the confidence interval. It then created a plot of the estimates and CDF. The code for this function is as follows:

>> <img src="img/sampleexponential.png">

>> I then created a dictionary in which to append all of the standard errors with their associated sample sizes and ran the function with a few different sample sizes to determine the associated standard errors.

>> <img src="img/testn1.png">
>> <img src="img/testn2.png">

>> Finally, I plotted the key/value pairs of the dictionary and it shows that as the sample size n gets larger, the standard error gets closer to 0.

>> <img src="img/plotnerrors.png">

### Q9. [Think Stats Chapter 6 Exercise 1](statistics/6-1-household_income.md) (skewness of household income)

>> For this question, I used the household income data and a graph of the CDF with an upper bound of $1,000,000. I calculated the Mean, Median, Skewness, and Pearson Median Skewness with the following code:

>> <img src="img/1milbound.png">

>> Using those statistics, it looks like about 2/3 or 66% of the population has a household income below the mean. However, an upper bound of $1,000,000 is not very reasonable. By increasing the upper bound to $10,000,000, I found that the skewness factor significantly increases with it. 

>> <img src="img/10milbound.png">

### Q10. [Think Stats Chapter 8 Exercise 3](statistics/8-3-scoring.md) (scoring)

>> For this question, I used a function called Simulate Game which takes in a scoring rate and returns the number of goals scored in a game. Another function, MultGameSimulator was then used to simulate several games and store the lambda estimates from each game in a list. The function then computes the RMSE and Mean Error of the estimates. The code for the functions is as follows:

>> <img src="img/gamesimulation.png">

>> I ran the MultGameSimulator function a few times using an increasing number of games as input to compare their Mean Errors and found that as the amount of simulated games increases, the Mean Error decreases and comes very close to 0. This leads me to assume that this estimator is unbiased. 

>> <img src="img/rungamesimulation.png">

### Q11. [Think Stats Chapter 9 Exercise 2](statistics/9-2-resampling.md) (resampling)

---

## <a name="section-f"></a>6.  Recommended Reading

Read Allen Downey's [Think Bayes](http://greenteapress.com/thinkbayes/) book.  It is available online for free, or you can buy a paper copy if you would like.

[<img src="img/think_bayes.png" title="Think Bayes"/>](http://greenteapress.com/thinkbayes/) 

---

## <a name="section-g"></a>7.  More Resources

Some people enjoy video content such as Khan Academy's [Probability and Statistics](https://www.khanacademy.org/math/probability) or the much longer and more in-depth Harvard [Statistics 110](https://www.youtube.com/playlist?list=PL2SOU6wwxB0uwwH80KTQ6ht66KWxbzTIo). You might also be interested in the book [Statistics Done Wrong](http://www.statisticsdonewrong.com/) or a very short [overview](http://schoolofdata.org/handbook/courses/the-math-you-need-to-start/) from School of Data.
