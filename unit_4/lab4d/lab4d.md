Interpreting correlations
===
transition: none
css: ../../IDSLabCSS.css

Lab 4D

Directions: Follow along with the slides and answer the questions in **red** font in your journal.




Some background...
===
- So far, we’ve learned about measuring the success of a model based on how close it’s predictions come to the actual observations. 
- The _correlation coefficient_ is a tool that gives us a fairly good idea of how these predictions will turn out without having to make predictions on future observations.
- For this lab, we will be using the `movie` data set to investigate the following questions:

_Which variables are better predictors of a movie's `audience_rating` when the predictions are made using a line of best fit?_


Correlation coefficients
===
- The _correlation coefficient_ describes the _strength_ and _direction_ of the linear trend.
- It's only useful when the trend is linear and both variables are numeric.
<img src="lab4d-figure/unnamed-chunk-2-1.png" title="plot of chunk unnamed-chunk-2" alt="plot of chunk unnamed-chunk-2" style="display: block; margin: auto;" />

- **Are these variables linearly related? Why or why not?**


Correlation review I
===

<img src="lab4d-figure/unnamed-chunk-3-1.png" title="plot of chunk unnamed-chunk-3" alt="plot of chunk unnamed-chunk-3" style="display: block; margin: auto;" />

- Correlation coefficients with values close to 1 are very strong with a positive slope. Values close to -1 means the correlation is very strong with a negative slope. 
    - **Does this plot have a positive or negative correlation?**

Correlation review II
===

<img src="lab4d-figure/unnamed-chunk-4-1.png" title="plot of chunk unnamed-chunk-4" alt="plot of chunk unnamed-chunk-4" style="display: block; margin: auto;" />

- **Recall that if there is no linear relation between two numerical variables, the correlation coefficient is close to 0. What do you guess the correlation coefficient will be for these two variables?**


The movie data
=== 

- Load the `movie` data using the `data` command.
- The data comes from a movie rating website called _Rotten Tomatoes_. 
    - The `critics_rating` and `audience_rating` are values that range between 0 and 100, 100 being the best.
    - The `critics_score` and `audience_score` are summaries of which films _Rotten Tomatoes_ feels are worth, or not worth, watching.
    - `domest_gross` descibes the domestic gross income of a film, i.e. the amount of money it made in the U.S.


Calculating Correlation Coefficients!
===

- We can use the `cor()` function to find the particular correlation coefficient of the variables from the previous plot, which happen to be `audience_rating` and `critics_rating`.
    - **Calculate the correlation coefficient for these variables using the `cor` function. The inputs to the functions work just like the inputs of the `xyplot` function.**


Now answer the following.
===

- **What was the value of the correlation coefficient you calculated?**
- **How does this actual value compare with the one you estimated previously?**
- **Does this indicate a strong, weak, or moderate association? Why?**
- **How would the scatter plot need to change in order for the correlation to be stronger?**
- **How would it need to change in order for the correlation to be weaker?**


<!-- What if we changed the data? -->
<!-- === -->
<!-- - **Would the correlation coefficient change if we took all of our values and subtracted 50 from all of the `critics_score`? Why do you think this is?** -->
<!-- - Test your answer by running the following code: -->
<!-- ```{r, eval=FALSE} -->
<!-- cor(audience_rating~(critics_rating-50),  -->
<!--      data = movie) -->
<!-- ``` -->
<!-- - **What value was returned for the correlation coefficient?** -->
<!-- - **How does this actual value compare with the one you estimated previously?** -->

<!-- What if we changed the data, again? -->
<!-- === -->

<!-- - **What happens to the correlation coefficient if we multiplied all of the `critics_rating` values by 50?  How do you explain this?** -->
<!-- - Test your answer by running the following code: -->
<!-- ```{r, eval=FALSE} -->
<!-- cor(audience_rating~(critics_rating*50), data = movie) -->
<!-- ``` -->
<!-- - **What value was returned for the correlation coefficient?** -->
<!-- - **How does this actual value compare with the one you estimated previously?** -->


Correlation and Predictions
===

- Find the two variables that look to have the strongest correlation with `critics_rating`.
    - Compute the correlation coefficients for `critics_rating` and each of the two variables.
    - **Use the correlation coefficient to determine which variable has a stronger linear relationship with `critics_rating`.**
- Fit two `lm` models to predict `critics_rating` with each variable and compute the MSE for each. 
    - **Use the MSE to determine which variable is a better predictor of `critics_rating`.**
- **How are the correlation coefficient and the MSE related?**


On your own
===
- Select two different numerical variables from the `movie` data.
- Plot the variables using the `xyplot()` function.
    - **Would calculating a correlation coefficient for the two variables be appropriate. Justify your answer.**
    - **Predict what value you think the correlation coefficient will be. Compare this value to the actual value. Finally, interpret what the actual correlation coefficient means.**
- Work with your classmates to determine which two variables have the strongest correlation coefficient.
  - **Why do you think these variables are so strongly related? Is using the correlation coefficient to describe the relationship appropriate and why/why not?**
