# Walmark-Sales-Analysis


The dataset titled "Walmart Sales" was successfully downloaded from Kaggle. This dataset is accessible through the following URL: https://www.kaggle.com/datasets/mikhail1681/walmart-sales.

This dataset encompasses detailed records of sales, along with various factors influencing sales across 45 distinct Walmart stores. 

The dataset features a meticulously curated collection of variables critical for analyzing sales trends and factors influencing sales performance. The primary attributes include:

- Store       : Store number 
- Date        : Sales week start date 
- Weekly_Sales: Store week sales 
- Holiday_Flag: Mark on the presence or absence of a holidaym 
- Temperature : Air temperature in the region 
- Fuel_Price  : Fuel cost in the region 
- CPI         : Consumer price index 
- Unemployment: Unemployment rate

The dataset encompasses weekly data spanning from February 5, 2010, to October 26, 2012

##### Our objective is to thoroughly explore the dataset and employ machine learning models to analyze various variables. This approach will enable us to identify key insights and patterns that influence outcomes, supporting informed decision-making.

### Development of a Machine Learning Model for Predicting Weekly Sales

The Correlation Matrix

![download](https://github.com/sidiquegithub/Walmark-Sales-Analysis/assets/110783832/c3f6a5f0-e1d6-4abf-b454-00ec8167cf21)

## MODEL 1


Linear regression model without considering the catogorical variables

- Target Variable : Weekly_Sales
- Variables to drop completely : Store, Date, Holiday_Flag
- Minmax scalar on Temperature, Fuel_Price, CPI and Unemployment

   R² = 0.017736807411213862

   This is a very low R² value, suggesting that the model does not effectively capture the relationship between the input features and the target variable. In practical terms, it means that the linear regression 
   model is not performing well in predicting weekly sales based on the provided data.

--------------------------------------
## MODEL 2

Linear Regression Analysis Incorporating All Independent Variables

- Target Variable : Weekly_Sales
- Drop Variable   : Date
- Encode Catogorical Varaible : Store, Holiday_Flag
- Min MAx Normalisation for Features Other than Store Variable and Holiday_Flag


### Model Valuation

##### R² = 0.9208878082543459

This high R² value suggests that the model effectively captures the relationship between the independent variables and the target variable.





##### RMSE and Normalised RMSE

RMSE = 159644.460251653

Normalised RMSE = RMSE /(Range) 

                = 159644.460251653/(3818686.45-209986.25) 
                
                = 0.04423877058328453

   With an Normalised RMSE of approximately 4.42%, this result suggests that the linear regression model's predictions are, on average, within 4.42% of the actual Weekly Sales values, when considered relative to 
   the range of those sales.
         

##### Actual vs. Predicted Values 

![download](https://github.com/sidiquegithub/Walmark-Sales-Analysis/assets/110783832/9df04398-b881-4e44-899b-a4e007a5b3d9) 

##### Residuals vs. Predicted Values

![image](https://github.com/sidiquegithub/Walmark-Sales-Analysis/assets/110783832/a545f43d-9d10-448c-ba34-7bfe4fd78cd0) 

----------------------------------------
## MOEDEL 3 

ARIMA Model Analysis on Aggregate Weekly Sales Across All Stores

![download](https://github.com/sidiquegithub/Walmark-Sales-Analysis/assets/110783832/eafcf82b-90b9-415f-8a75-62d804bbd54a)

### Dickey-Fuller Test
<br> p-value = 0.000000268.
This shows the series is stationary.

### PMDARIMA
Best model:  ARIMA(2,0,0)(0,0,0)[0] intercept

![download](https://github.com/sidiquegithub/Walmark-Sales-Analysis/assets/110783832/e4275d30-d87c-4b3a-a07a-5082a80a7cc5)


### Model Valuation
- The model, being of order 2, predicts the current value of the series using the two immediate past values.
<br>Fit Statistics
- Log Likelihood: -2410.709.
- The Akaike Information Criterion(AIC): 4829.418.
- The Bayesian Information Criterion(BIC) : 4841.270.  
- The Hannan-Quinn Information Criterion(HQIC): 4834.234.
- The constant term is estimated to be 4.711e+07, with a very small p-value, indicating it is significantly different from zero.
- ar.L1: The coefficient for the first lag in the autoregressive model is 0.2953, significant at the 0.000 level, suggesting a substantial impact of the previous time step on the current value.
- ar.L2: The coefficient for the second lag is 0.1195, but with a p-value of 0.119, indicating it might not be statistically significant.

Diagnostics
- sigma2: The variance of the model's errors is 2.601e+13, indicating the scale of the residuals.
- Ljung-Box (Q): The p-value 0.94 suggests that there is little evidence to reject the null hypothesis of no autocorrelation in residuals, meaning the model residuals do not show significant autocorrelation patterns.
- Jarque-Bera (JB): With a p-value of 0.00, this test rejects the null hypothesis of normal distribution of residuals, indicating potential issues with the model's assumptions.
- Heteroskedasticity (H): The p-value 0.11 suggests that there is no strong evidence of heteroskedasticity, meaning the variance of the residuals is fairly constant.
- Skew: 2.57 indicates a significant right skew in the distribution of residuals.
- Kurtosis: 16.04 suggests a heavy-tailed or leptokurtic distribution of residuals compared to a normal distribution.

Warnings
- Covariance matrix warnings suggest potential instability in the standard errors of the coefficients, likely due to the singularity or near-singularity of the covariance matrix. This could be a sign that the model is overparameterized or that multicollinearity among predictors is present.

Analysis
While the model seems to fit the data to some extent (as indicated by the significance of the constant and the first lag), several issues are noteworthy:

- The non-significance of the second autoregressive term suggests it may not be necessary.
- The diagnostics indicate potential problems with the normality and distribution of residuals, which could affect the reliability of hypothesis tests based on the model.
- The warning about the covariance matrix suggests reviewing the model specification or data for issues that might be causing instability in the estimates.
- In conclusion, while the model captures some of the structure in the data, there may be room for improvement. Considerations could include checking for seasonality, exploring transformations of the data to address skew and kurtosis in residuals, or revisiting the model specification to ensure it appropriately captures the underlying processes.

----------------------------------
## MOEDEL 4

Decision Tree Analysis Focused on the Store Variable


