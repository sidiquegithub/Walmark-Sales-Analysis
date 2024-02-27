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

#### MODEL 1

Linear regression model without considering the catogorical variables

- Target Variable : Weekly_Sales
- Variables to drop completely : Store, Date, Holiday_Flag
- Minmax scalar on Temperature, Fuel_Price, CPI and Unemployment

   R² = 0.017736807411213862

   This is a very low R² value, suggesting that the model does not effectively capture the relationship between the input features and the target variable. In practical terms, it means that the linear regression 
   model is not performing well in predicting weekly sales based on the provided data.

#### MODEL 2

Comprehensive Linear Regression Analysis Incorporating All Independent Variables"


