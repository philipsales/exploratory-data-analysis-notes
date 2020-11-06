---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Regression Exploratory Data Analysis
  language: python
  name: python3
---

# Exploratory Data Analysis - Regression Modelling #
Reference: [Comprehensive data exploration with Python](https://www.kaggle.com/pmarcelino/comprehensive-data-exploration-with-python#)

## Summary of Steps ##
1. Import dataset
1. Understand the problem
    1. Explore data columns
        - create spreadsheet analysis and prepare a column for each below.
        | new columns  | description | 
        | ---          | ---         |
        | variable     | variable name or column names          |
        | type         | identify categorical vs numerical      |
        | segment      | identify grouping or variable segments |
        | expectation  | tag the influence level to independent variable (i.e. High, Medium, Low) |
        | conclusion   | tag the importance level to independent variable (i.e. High, Medium, Low) |
        | comments     | general comments | 
    2. Feature Selection (`subjective approach`)
        1. filter the **high expectation** variables only
        1. scatter plot the variables to the independent variable to fill the `conclusion column` - which is the correction of the expectation
        1. analyse the **Independent** variable first
        1. analyse the filtered **Dependent** variables
            1. plot relationship for numerical values
            1. plot relationship for categorical values
    3. Feature Selection (`objective approach`)
        1. create correlation matrix
        1. plot highest correlation
        1. filter only the variables with no collinearity
    4. Handle Missing Data
        1. Assess missing data
            1. Drop missing data
        1. Assess for outliers - Univariate
            1. Standard Scalar
        1. Assess for outliers - Multivariate
            1. Delete outlier
    5. Assess Regression Assumptions
        1. Test for Normality
            1. Visualize/Detect
                1. plot histogram
                1. plot normal probability plot (Q-Q plot)
            1. Remedy
                1. log transformation
        1. Test for Homoscedasticity
            1. Visualize/Detect
                1. plot scatterplot
    
## Regression Assumptions ##

### 1. Normality / Normality of Errors
  - Gaussian distribution
  - detection
    1. Histogram 
      - Kurtosis and Skewness
    1. Normal probability plot **(Q-Q plot)**
      - data distribution
    1. Shapiro-Wilk test
    1. Komolgorov-Smirnov test
    1. Anderson-Darling test
  - remedy
    1. log transformation
    
### 2. Homoscedasticity 
  - `constant error variance`
  - assumption that dependent variable(s) exhibit equal levels of variance across the range of predictor/independent variables
  - having even spread of error terms
  - detection
    1. Residual plot
    1. Goldfeldt-Quandt test
    1. Breusch-Pagant test
  - remedy
    1. log transformation
    
### 3. Linearity 
  - `correct functional form`
    - either linear, quadratic, complex
  - assesssed thru scatterplot
  - additive
  - detection
    1. Residual Plots
    1. Likelihood Ratio (LR) test
  - remedy
    1. get the specification correct

### 4. Absence of correlated errors
  - often occurs in time series
  - happen when one error is correlated to another
  
### 5. Exogeneity
  - `no omitted variable bias`
  - detection
    1. intuition/subjective
    1. checking correlations/correlation matrix
  - remedy
    1. instrumental variables
    
### 6. Independent Error Terms
  - `no autocorrelation`
    - can only occur in time series data
  - each residual is affected by the residual before it
  - `snake-like` pattern plot in residual plot
  - detection
    1. Durbin-Watson test
    1. Breusch-Godfrey test
  - remedy
    1. investigate omitted variables
    1. Generalised difference equation
      1. Cochrane-Orchut
      1. AR(1) method
      
### 7. No multi-collinearity


