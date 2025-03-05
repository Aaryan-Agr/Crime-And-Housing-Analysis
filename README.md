# Crime and Housing Price Index (HPI) Analysis

## Overview

This project involves analyzing crime data from various cities and states in the United States, with a focus on understanding the relationship between socio-economic factors (such as population size, crime rates, and housing prices) over multiple years. The main objective is to identify significant predictors of crime and understand how they influence the Housing Price Index (HPI) through regression models.

## Dataset

The dataset used in this project contains information about various crimes (e.g., robberies, assaults, homicides, rapes), population size, and the Housing Price Index (HPI) for multiple cities across the United States. The data is structured with the following columns:

- `Year`: The year of the data entry.
- `City`: The city name.
- `State`: The state where the city is located.
- `HPI`: Housing Price Index, a measure of housing price trends.
- `Population`: The population size of the city.
- `TotalCrime`: The total number of crimes (sum of various crime types).
- Individual columns for different crime types: `Robberies`, `Assaults`, `Homicides`, `Rapes`.

## Libraries Used

The following R libraries were used in this project:

- `dplyr`: For data manipulation.
- `tidyr`: For data tidying.
- `psych`: For statistical methods.
- `car`: For variance inflation factor (VIF) testing and regression diagnostics.
- `corrgram`: For correlation visualization.
- `ggplot2`: For data visualization.
- `MASS`: For model selection and AIC-based analysis.

## Key Steps in the Analysis

1. **Data Preprocessing**: 
    - Loading the crime dataset.
    - Removing missing values.
    - Splitting the `City..State` column into two separate columns: `City` and `State`.
    - Renaming columns for clarity and consistency.

2. **Exploratory Data Analysis (EDA)**:
    - Calculating and visualizing correlations between variables (e.g., HPI, population, crime rates).
    - Creating interaction plots to investigate the relationships between continuous and categorical variables (e.g., Year vs HPI by City and State).

3. **Regression Modeling**:
    - Fitting multiple regression models by hand, evaluating their goodness-of-fit using R-squared values.
    - Using dummy variables for categorical predictors (City and State).
    - Performing an Elasticity Score Sum (ESS) test to evaluate model fit.
    - Investigating multicollinearity using Variance Inflation Factor (VIF) tests.

4. **Model Refinement**:
    - Testing different transformations on the predictors and response variable (e.g., log, square root, polynomial).
    - Using AIC-based stepwise selection to refine the best model.
    - Comparing multiple models based on their adjusted R-squared and AIC.

5. **Final Model Selection**:
    - After testing different transformations and variables, the best model was identified, achieving an adjusted R-squared of 0.9167.

## Key Findings

- The `Year` variable was found to have a significant impact on the Housing Price Index (HPI), and it was crucial to include it in the model.
- The `City` variable was more important than `State` for modeling purposes, providing better results.
- `Population` was observed to have a significant correlation with both crime rates and HPI, but its effect varied depending on the city and state.
- The total number of crimes (`TotalCrime`) was a better predictor for HPI than individual crime types (e.g., robbery, assault).

## Conclusion

The analysis demonstrated that socio-economic factors such as population size, total crime rates, and year-over-year changes in crime and HPI are significant predictors of the Housing Price Index. The refined model, which included year, city, and total crime, yielded the best results with an adjusted R-squared value of 0.9167.

## Future Work

- Investigate additional external factors (e.g., unemployment rate, income level) that could influence crime and housing prices.
- Perform more advanced model selection techniques (e.g., cross-validation) to further refine the model.

## Files

- `crime.csv`: The raw crime data used in this analysis.
- `analysis.R`: The R script containing the data preprocessing, exploratory data analysis, and regression modeling.
- `README.md`: This file, providing an overview of the project.

