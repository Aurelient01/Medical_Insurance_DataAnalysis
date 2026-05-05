In this Medical Insurance Data Analysis, we used a kaggle dummy medical insurance data set to show exploratory data analysis,
Risk Score Correlation Matrix, gap analysis, PCA and Linear/RandomForest Regressions.

Medical Insurance Cost Dataset Kaggle 
https://www.kaggle.com/datasets/mohankrishnathalla/medical-insurance-cost-prediction

Exploratory Data Analysis
- Aggregated data to get sum and mean for key features, grouped by plan and network tier
- Created additional calculations to find Loss Ratio, total member paid, Charges vs claim paid Diff, Dollar loss per member
- Analysis of Total Claims by paid bucket with Bar chart
- Rename Null values to unknown for smokers and alcohol freq
- Created 4 subplots to AVG claims paid by Region, Sex, Smoker, Alochol freq
- Did a Gender Agg for Counts, total claims paid by gender + bar graph
- AVG paid claims per person

Correlation Matrix
- Ran a risk correlation for Risk score, pulled the top 10 features correlated to Risk Scores
- Correlation Heat map

Gap Analysis
- Checked AVG Risk Score against the top 3 features (not including Age)
- Found Data opportunities, members with high risk scores (higher than average) with 0 as Is_high_risk
- Most of the opportunites are members with chronic counts and lower than average Risk Scores, same with systolic count used 130 as a threshold benchmark

Principal Component Analysis (PCA)
- Ran a PCA for ['is_high_risk', 'age','chronic_count', 'systolic_bp'] and got a total variance of 80.7% which tells us these 4 features drove the risk scores
- Ran another PCA using all features except for monthly premium
- PCA scatter - color map shows from green to red risk score, found this graph interesting, due to the categorical nature of is_high_risk
  and chronic being binary 1/0, the data spread has gaps between them. As the patients move to the right they have greater propencity to have age,
  chronic count, high risk and high blood pressure

Linear Regression 
- Linear Regression model that uses the same 4 inputs as PCA, the linear regression is predicting the risk scores using those 4 inputs.
- Model had an R2 score of .89, this tells us the model can fairly predict risk scores with those 4 inputs

RandomForest Regression
- RandomForest Regression model that uses the same 4 inputs as PCA, the RandomForest regression is predicting the risk scores using those 4 inputs.
- Model had an R2 score of .91, this tells us the model can fairly predict risk scores with those 4 inputs
