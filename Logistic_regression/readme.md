Dr. Aydede
ECONOMETRICS
ECON 4403 - Winter 2019
Assignment 4
It’s due on Sunday, by midnight April 7th (only by email). You can submit it individually
or as a team (maximum 3 members).
• You can only use R and/or Stata
• What you submit must be your own work.
• I need ONLY your rmd (R) and/or smcl (Stata) files nothing else. You can use
Stata in one section and R in another section. If you do so, please submit both
smcl and rdm files. Make sure that you don’t print matrix and vector outputs.
• The solutions will be provided later only for R and Stata.
This assignment has 3 parts:
A. House Prices: Dummy-variable models.
B. MC Simulations for biased estimations with model misspecification and measurement errors.
C. Probability models with “utown” data.
Sources: Your ECON 3303 notes and the relevant sections in the textbook. The data,
“utown.dta” for part A and C is on Brightspace.
A. Housing Market estimations
You can use model.matrix() for R or factor operators in Stata (look at your handouts
and the example we had in the class). In this example, we are going to analyze the real
estate market in University Town (UT) and Golden Oak (GO).
1. What’s the average price difference between houses with and without a pool? Is it
significant?
2. Is there any significant difference in the effect of age on house prices between
a. GO and UT,
b. With pool and without pool,
c. With pool and in UT and with pool and in GO
d. Without pool in UT and with pool in GO
3. Are the large houses mostly in UT? Is the size of the house related to the existence a pool?
4. What are the most important factors in house pricing in the market?Dr. Aydede
5. Find the difference in per square foot price between UT and GO. Would that difference be different with and without fireplace and age?
6. Create two binary variables, “old house” and “big house” from “age” and “sqft”
given in the data. Use the mean values of the these variables as thresholds.
What’s the average price difference “new - big” house and “new – small” house?
Do the same comparison between “old-big” house and “new-small” house.
B. MC Simulations for misspecification and measurement errors
Our DGM is defined below. In this assignment we have fixed (non-stochastic) x’s.
Therefore, we will create x’s out of the loop to fix their values for repeated samples
and then we use DGM to create y’s within a loop for each sample. (You have done
many simulations before. Or look at the solutions for nay assignment in Brightspace).
DGM
1. x1 is 1, as usual.
2. x2 contains random integers between 0 and 100.
3. x3 has random numbers drawn from a uniform distribution with min=1,
max=50.
4. x4 is a vector with random numbers drawn from a normal distribution (mean
= 5.2, sd = 1.25).
5. Create a coefficient vector with your choice of values. For example, beta =
(12, -0.7, 34, -0.17).
6. DGM is
�푡 = �1 + �2�2푖 + �3�3푖 + �4�4푖 + �푖
and � ~ �(0,1).
MC Simulation. (you can use lm() if you prefer)
1. Create 2000 samples (with 300 observations) with your DGM and make sure that
your x’s are identical in each of 2000 samples. You will have five sampling distributions each of which is for one estimator in beta_hat. Calculate the mean of
each of these sampling distributions. Compare them with the population parameters. Are they similar as we expect? That is if �(�)̂ = �?
2. Now we will create 2000 samples (with 300 observations) by the DGM but we will
have a misspecified model that underfits the true model in estimations. To do
that we will drop X4 from the estimations. In order to do that you have to haveDr. Aydede
another X matrix that doesn’t contain X4. That’s all. Make sure that your x’s
are identical in each of 2000 samples. You will now have three sampling distributions each of which is for one estimator in beta_hat2. Calculate the mean of each
of these sampling distributions. Compare them with the population parameters
(x1, x2, and x3). Are they similar? That is if �(�)̂ = �?
3. Now we will introduce a measurement error to one of the variables in DGM when
we estimate the model. Create x4_me = x4 + e, where e is �(0,1). Estimations in the MC simulation should contain x4_me, instead of x4. You will now
have four sampling distributions each of which is for one estimator in beta_hat3.
Calculate the mean of each of these sampling distributions. Compare them with
the population parameters (x1, x2, x3, and x4). Are they similar? That is if
�(�)̂ = �?
4. Repeat the same example in 3 but introduce a measurement error to y, instead of
X4. Is �(�)̂ = �?
5. BONUS: if you have time, you can check if the bias in (3) confirms the function
we covered in the class.
C. Probability models
Use “utown” data and create an indicator variable from “price” that reveals if the
house in the top 25 percentile. Call it “high”, which will be 1 if the house price
higher than (and equal to) the threshold, 0 otherwise. Here is the model that we
want to estimate:
ℎ��ℎ푡 = �1 + �2���2푖 + �3����3푖 + �4����4푖 + �5������5푖 + �6�����6푖 + �푡
1. Estimate linear probability model (LPM) and interpret the results.
2. Estimate logistic regression
a. Interpret the coefficients.
b. Calculate and interpret odd ratios (OR).
c. Calculate the marginal effects at means. Are they different than the
ones given by LPM?
d. Predict the probabilities.
e. Based on predications, identify the models success. What’s the “false
positive” rateDr. Aydede
5. Find the difference in per square foot price between UT and GO. Would that difference be different with and without fireplace and age?
6. Create two binary variables, “old house” and “big house” from “age” and “sqft”
given in the data. Use the mean values of the these variables as thresholds.
What’s the average price difference “new - big” house and “new – small” house?
Do the same comparison between “old-big” house and “new-small” house.
B. MC Simulations for misspecification and measurement errors
Our DGM is defined below. In this assignment we have fixed (non-stochastic) x’s.
Therefore, we will create x’s out of the loop to fix their values for repeated samples
and then we use DGM to create y’s within a loop for each sample. (You have done
many simulations before. Or look at the solutions for nay assignment in Brightspace).
DGM
1. x1 is 1, as usual.
2. x2 contains random integers between 0 and 100.
3. x3 has random numbers drawn from a uniform distribution with min=1,
max=50.
4. x4 is a vector with random numbers drawn from a normal distribution (mean
= 5.2, sd = 1.25).
5. Create a coefficient vector with your choice of values. For example, beta =
(12, -0.7, 34, -0.17).
6. DGM is
�푡 = �1 + �2�2푖 + �3�3푖 + �4�4푖 + �푖
and � ~ �(0,1).
MC Simulation. (you can use lm() if you prefer)
1. Create 2000 samples (with 300 observations) with your DGM and make sure that
your x’s are identical in each of 2000 samples. You will have five sampling distributions each of which is for one estimator in beta_hat. Calculate the mean of
each of these sampling distributions. Compare them with the population parameters. Are they similar as we expect? That is if �(�)̂ = �?
2. Now we will create 2000 samples (with 300 observations) by the DGM but we will
have a misspecified model that underfits the true model in estimations. To do
that we will drop X4 from the estimations. In order to do that you have to haveDr. Aydede
another X matrix that doesn’t contain X4. That’s all. Make sure that your x’s
are identical in each of 2000 samples. You will now have three sampling distributions each of which is for one estimator in beta_hat2. Calculate the mean of each
of these sampling distributions. Compare them with the population parameters
(x1, x2, and x3). Are they similar? That is if �(�)̂ = �?
3. Now we will introduce a measurement error to one of the variables in DGM when
we estimate the model. Create x4_me = x4 + e, where e is �(0,1). Estimations in the MC simulation should contain x4_me, instead of x4. You will now
have four sampling distributions each of which is for one estimator in beta_hat3.
Calculate the mean of each of these sampling distributions. Compare them with
the population parameters (x1, x2, x3, and x4). Are they similar? That is if
�(�)̂ = �?
4. Repeat the same example in 3 but introduce a measurement error to y, instead of
X4. Is �(�)̂ = �?
5. BONUS: if you have time, you can check if the bias in (3) confirms the function
we covered in the class.
C. Probability models
Use “utown” data and create an indicator variable from “price” that reveals if the
house in the top 25 percentile. Call it “high”, which will be 1 if the house price
higher than (and equal to) the threshold, 0 otherwise. Here is the model that we
want to estimate:
ℎ��ℎ푡 = �1 + �2���2푖 + �3����3푖 + �4����4푖 + �5������5푖 + �6�����6푖 + �푡
1. Estimate linear probability model (LPM) and interpret the results.
2. Estimate logistic regression
a. Interpret the coefficients.
b. Calculate and interpret odd ratios (OR).
c. Calculate the marginal effects at means. Are they different than the
ones given by LPM?
d. Predict the probabilities.
e. Based on predications, identify the models success. What’s the “false
positive” rate
