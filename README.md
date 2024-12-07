# Medical Cost Prediction Analysis

This project aims to predict medical expenses based on various factors such as age, sex, BMI, number of children, smoking habits, and region of residence. The dataset used in this analysis is from Kaggle's Insurance dataset.

## Dataset Overview

The dataset contains 1,338 observations and 7 features:

- **age**: The age of the insured person.
- **sex**: The gender of the insured person (male, female).
- **bmi**: Body Mass Index (BMI) of the insured person.
- **children**: The number of children/dependents covered by the insurance.
- **smoker**: Whether the insured person is a smoker (yes, no).
- **region**: The region in which the insured person lives (northeast, northwest, southeast, southwest).
- **charges**: The medical expenses billed to the insured person.

## Objective

The goal is to predict the **charges** (medical expenses) based on the other features in the dataset using various machine learning models.

## Libraries Used

- **numpy**: For numerical operations.
- **pandas**: For data manipulation.
- **matplotlib**: For visualizations.
- **seaborn**: For statistical data visualizations.
- **scikit-learn**: For machine learning models and metrics.

## Data Preprocessing

1. **Data Loading**:  
   The dataset is loaded into a pandas DataFrame for exploration.
   
2. **Handling Missing Values**:  
   No missing values were found, as confirmed by the `df.info()` method.

3. **Categorical Encoding**:
   - **sex**: Encoded as `1` for male, `0` for female.
   - **smoker**: Encoded as `1` for smoker, `0` for non-smoker.
   - **region**: Encoded as `0` for northeast, `1` for northwest, `2` for southeast, and `3` for southwest.

## Exploratory Data Analysis (EDA)

- **Age Distribution**: Majority of patients are between 18 and 64 years of age.
- **Sex Distribution**: Nearly equal distribution between males and females.
- **BMI Distribution**: Most patients have a BMI between 25 and 40, which is considered overweight.
- **Children Distribution**: Most patients have zero or one child, with very few having more than three.
- **Smoking Distribution**: The majority of patients are non-smokers (around 80%).
- **Charges Distribution**: Most medical expenses are below $20,000, with a few cases exceeding $50,000.

### Key Insights:
- Smokers tend to have higher medical expenses.
- The medical expenses for patients with a BMI greater than 30 (obese) are higher than for those with a BMI less than 30 (healthy).
- Medical expenses generally increase with age.

## Correlation Analysis

- **Smoker**: Strong correlation with medical charges (`0.79`), indicating that smoking significantly affects medical expenses.
- **BMI**: Moderate correlation with charges (`0.20`), suggesting that obesity contributes to higher medical expenses.
- **Age**: Weak to moderate correlation with charges (`0.30`), which makes sense since older patients may face more medical issues.

## Model Building

### 1. **Train-Test Split**:
   - Split the data into training (80%) and testing (20%) sets.
   
### 2. **Models Used**:
   - **Decision Tree Regressor**: `R^2 = 0.71`
   - **Random Forest Regressor**: `R^2 = 0.87` (Best Model)
   - **Linear Regression**: `R^2 = 0.78`

### 3. **Model Evaluation**:
   - **Random Forest Regressor** performed the best, with the lowest RMSE value (`4563.39`), making it the chosen model for predicting medical expenses.
   - **Decision Tree Regressor** had the second-highest accuracy but suffered from overfitting.
   - **Linear Regression** showed moderate performance.

### 4. **Metrics**:
   - **Random Forest Regressor**: 
     - **MAE**: 2508.90
     - **MSE**: 20824545.51
     - **RMSE**: 4563.39
     - **R²**: 0.87
   - **Decision Tree Regressor**:
     - **MAE**: 2976.12
     - **MSE**: 44700088.50
     - **RMSE**: 6685.81
     - **R²**: 0.71
   - **Linear Regression**:
     - **MAE**: 4186.51
     - **MSE**: 33635210.43
     - **RMSE**: 5799.59
     - **R²**: 0.78

## Feature Importance

- **Random Forest Regressor** and **Decision Tree Regressor** both highlighted key features impacting the charges:
  - **Smoker** and **BMI** are the most important features.
  - **Age** also has a moderate impact, while **region** and **children** are less influential.

## Conclusion

Based on the analysis and model performance:
- **Random Forest Regressor** provides the best accuracy for predicting medical expenses.
- The key predictors of medical expenses are **smoking status**, **BMI**, and **age**.
- Smokers tend to incur higher medical costs, and patients with a BMI greater than 30 also tend to have higher medical expenses.

## Future Work

- Further exploration could involve feature engineering to improve the model’s performance.
- Additional datasets with more features, such as medical history, could refine the predictions.
- Experimenting with advanced machine learning algorithms like Gradient Boosting or XGBoost might yield better results.

