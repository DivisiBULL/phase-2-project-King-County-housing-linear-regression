# Repo Guide

The main contents of this repo are the Jupyter Notebook under 
[student.ipynb](https://github.com/DivisiBULL/phase-2-project-King-County-housing-linear-regression/blob/main/student.ipynb)
and the project presentation under 
[Presentation King County Phase 2 Project](https://github.com/DivisiBULL/phase-2-project-King-County-housing-linear-regression/blob/main/Presentation%20King%20County%20Phase%202%20Project.pdf)

# Business Understanding

A fictional house flipping company has hired me to analyze the King County Housing Market and provide three recommendations based on the trends of the housing market. I will be providing insights on what features to look for when buying a house and the best remodeling options. This will allow the company to increase profits when it resells the house.

# Objectives

For this project, I will be using a Multivariate Linear Regression model to provide my recommendations. The model will help in understanding the relationship between our features (number of bedrooms, grade, etc.) on our dependent variable (the house price).

# Interetting the results

Since we have logged transformed our data it changes how we interpret our data

Here is a [link](https://data.library.virginia.edu/interpreting-log-transformations-in-a-linear-model/) to a more in depth explanation 

For our use case we only logged the dependent variable (price):

"Only the dependent/response variable is log-transformed. Exponentiate the coefficient, subtract one from this number, and multiply by 100. This gives the percent increase (or decrease) in the response for every one-unit increase in the independent variable. Example: the coefficient is 0.198. (exp(0.198) – 1) * 100 = 21.9. For every one-unit increase in the independent variable, our dependent variable increases by about 22%."


The coefficients:

For continuous variables you can read them as when x increases by one unit, price increase by x %

So for every additional bathroom added the price increases by 5% ((exp(0.0539) – 1) * 100 = 5.5379

For non continuous variables such as waterfront_YES we can interpret it as when there is a waterfront there is roughly a 34% increase to house price ((exp(0.0.2919) – 1) * 100 = 33.8969 compared to when the house is not on the waterfront

# Final Model

![alt text](https://github.com/DivisiBULL/phase-2-project-King-County-housing-linear-regression/blob/main/pngs/final_model_png.PNG?raw=true)

# Recommendations
Here is a quick look at my final recommendations

We can break our suggestions down to 2 main categories

Features to consider when buying:

-in_bellevue - 38% increase for being in bellevue compared to other zips
-In_seattle - 19% increase for being in Seattle compared to other zips
-waterfront - 34% increase for having a waterfront
-View - 9% increase possible (from No view to excellent view)


Features that can be remodeled:

-Condition - -48% increase from poor to excellent
-Floors - 9% increase for each floor
-Bathrooms - 5% increase for each bathroom added

# Assumptions check

![alt text](https://github.com/DivisiBULL/phase-2-project-King-County-housing-linear-regression/blob/main/pngs/final_model_qqplot.PNG?raw=true)

![alt text](https://github.com/DivisiBULL/phase-2-project-King-County-housing-linear-regression/blob/main/pngs/final_model_Homoscedasticity_check.PNG?raw=true)


Since we do not strictly pass several of our assumption checks I would not be too confident in the accuracy of the model's coefficients. 

# Conclusion

When looking to buy homes for flipping we should look for homes ideally in Bellevue on the waterfront (on Lake Sammamish, Lake Washington, Phantom Lake). We can also just consider these aspects separately as a house on the waterfront but not in Bellevue will still have an increase in price. The view is also important to the house price. 

If we can find houses in those locations in need of some repairs they will be the easiest houses to flip. When remodeling we should focus on increasing the condition of the house "Condition: How good the overall condition of the house is. Related to maintenance of house." This will be overall maintenance of the house. For adding features we can look at adding additional bathrooms and additional floors as these two also play large roles in the price of the house



The notebook will show my process and provide more in depth recommendations


# Future Projects

As a future project I would like to create an integrated system for use on house sale websites like zillow. That would automatically select houses it determines to be ideal for house flipping. It would base it’s recommendations off of our model and be able to provide an estimated price you would be able to sell for after renovations
