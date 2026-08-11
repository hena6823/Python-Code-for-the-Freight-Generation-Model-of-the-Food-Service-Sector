Freight Generation Model for the Food Service Sector

Overview

This repository contains the Python code used to develop and evaluate the Freight Generation Models for the Food Service Sector in Addis Ababa, Ethiopia.

The analysis forms part of an MSc thesis on urban freight generation modelling. The objective is to estimate annual Freight Production (FP) and Freight Attraction (FA) using establishment-level characteristics.

The analysis applies Ordinary Least Squares (OLS) multiple regression to examine the relationship between freight generation and selected establishment characteristics.

Study Sector

The model focuses on the Food Service Sector (ISIC Code 56) in Addis Ababa.

The dataset contains 317 food service establishments. The analysis considers both outbound Freight Production and inbound Freight Attraction.

The dataset includes food service establishments with different operational characteristics, including catering and non-catering activities.

Variables

Dependent Variables

Freight Production (FP): Quantity of outbound freight in ton/year.

Freight Attraction (FA): Quantity of inbound freight in ton/year.

Explanatory Variables

The models use three establishment-level variables:

Number of Years in Operation

Number of Employees

Gross Floor Area (m²)

These variables represent important operational and physical characteristics of food and beverage establishments.

The original dataset also contained information on the number of tables and catering services. The modelling dataset excludes non-numeric categorical fields and removes the Number of Tables variable from the regression analysis.

Methodology

The Python workflow includes:

Importing and inspecting the establishment-level dataset.

Examining descriptive statistics and data structure.

Checking for missing observations.

Checking for duplicated observations.

Exploring variable distributions through graphical analysis.

Examining the correlation structure among the variables.

Separating the explanatory and dependent variables.

Dividing the data into training and hold-out test sets.

Estimating linear regression models using scikit-learn.

Estimating OLS models using statsmodels.

Calculating regression coefficients and statistical significance.

Evaluating model performance using MAE, RMSE, and R².

For both FP and FA, 80% of the observations were used for model estimation and 20% were reserved for hold-out testing.

For the Food service sector, this resulted in:

Training observations: 253

Hold-out test observations: 64

Model Specification

The general form of the regression model is:

Y = β₀ + β₁X₁ + β₂X₂ + β₃X₃ + ε

where:

Y = Freight Production or Freight Attraction

β₀ = Intercept

X₁ = Number of Years in Operation

X₂ = Number of Employees

X₃ = Gross Floor Area (m²)

ε = Error term

Freight Production Model

The estimated Food FP equation is:

FP = 94.724 + 19.701(Years) + 52.670(Employees) + 0.050(GFA)

The model results indicate that all three explanatory variables have statistically significant relationships with Freight Production at the conventional 5% significance level.

The estimated coefficients are:

Number of Years in Operation: β₁ = 19.701, p = 0.010

Number of Employees: β₂ = 52.670, p < 0.001

Gross Floor Area: β₃ = 0.050, p = 0.039

Freight Attraction Model

The estimated Food FA equation is:

FA = 91.341 + 13.174(Years) + 46.123(Employees) + 0.042(GFA)

All three explanatory variables are statistically significant at the conventional 5% significance level.

The estimated coefficients are:

Number of Years in Operation: β₁ = 13.174, p = 0.035

Number of Employees: β₂ = 46.123, p < 0.001

Gross Floor Area: β₃ = 0.042, p = 0.032

Model Performance

The Food service sector models demonstrate strong explanatory and predictive performance.

Freight Production

R²: 0.9824

MAE: 112.76 ton/year

RMSE: 134.33 ton/year

Freight Attraction

R²: 0.9876

MAE: 81.94 ton/year

RMSE: 97.07 ton/year

The results indicate that the selected establishment characteristics explain a large proportion of the observed variation in both Freight Production and Freight Attraction within the Food and Beverage sector.

The FA model shows slightly stronger predictive performance than the FP model, with a higher R² and lower MAE and RMSE.

Statistical Analysis

The statsmodels OLS implementation is used to obtain:

Regression coefficients

Standard errors

t-statistics

p-values

R² and adjusted R²

F-statistics

Confidence intervals

Full regression summaries

The analysis also evaluates the statistical significance of the individual explanatory variables.

For the Freight Production model, Number of Years in Operation, Number of Employees, and Gross Floor Area are statistically significant predictors.

The same three variables are statistically significant in the Freight Attraction model.

Number of Employees has the largest estimated coefficient in both models, indicating its strong relationship with freight generation within the Food service sector.

Python Libraries

The analysis uses Python-based statistical and data-analysis tools, including:

pandas

numpy

matplotlib

seaborn

scikit-learn

statsmodels

scipy

The principal modelling procedures used in the final analysis are LinearRegression from scikit-learn and OLS regression from statsmodels.

Reproducibility

To reproduce the analysis, open the Jupyter Notebook and run the cells sequentially.

The original analysis was developed using establishment-level Food and Beverage survey data from Addis Ababa.

The notebook performs the data preparation, exploratory analysis, correlation analysis, model estimation, statistical testing, and model evaluation.

If the underlying establishment-level dataset is not publicly available, the numerical results cannot be reproduced without access to the original data.

Data Availability

The Python code is made publicly available to support transparency and reproducibility of the research.

The availability of the underlying establishment-level dataset depends on data confidentiality and the conditions under which the survey data were collected.

Where the raw data cannot be publicly released, the code documents the modelling procedure and analytical workflow used in the study.

Research Context

This code supports research on urban freight generation modelling in Addis Ababa, Ethiopia.

The analysis contributes to the development of establishment-based freight generation models for service-sector establishments, with particular attention to the relationship between freight demand and establishment characteristics.

The Food service sector model presented here forms part of a broader multi-sector freight generation study covering selected service sectors in Addis Ababa.

The results provide sector-specific estimates of Freight Production and Freight Attraction that can support urban freight planning and demand estimation for food service establishments.

Citation

If you use or adapt this code in academic research, please cite the associated MSc thesis.

Suggested citation:

Henock. Freight Generation Modelling for Selected Service Sectors in Addis Ababa, Ethiopia. MSc Thesis.

The final bibliographic details should be updated once the thesis has been formally submitted or published.

Author

Henock

MSc Researcher

Addis Ababa, Ethiopia

Disclaimer

This repository contains research code developed for academic purposes.

The models are calibrated for the Food Service Sector in Addis Ababa and should not be assumed to be directly transferable to other cities or sectors without appropriate validation and, where necessary, recalibration.
