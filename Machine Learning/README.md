# Personal Loan Purchase Prediction

## Problem Statement
A bank (AllLife Bank) wants to increase its customer base of personal loan borrowers. They previously had a successful campaign to convert their liability customers to personal loan customers with a conversion rate of over 9%. The goal is to build a model that will help the marketing department identify customers who have a higher probability of purchasing a personal loan.

## Objective
To build a classification model to predict whether a customer will accept a personal loan offer based on their demographics and banking history.

## Data Dictionary
The dataset contains data on 5,000 customers.

- **ID**: Customer ID
- **Age**: Customer's age in completed years
- **Experience**: #years of professional experience
- **Income**: Annual income of the customer ($000)
- **ZIP Code**: Home Address ZIP code
- **Family**: Family size of the customer
- **CCAvg**: Avg. spending on credit cards per month ($000)
- **Education**: Education Level (1: Undergrad; 2: Graduate; 3: Advanced/Professional)
- **Mortgage**: Value of house mortgage if any ($000)
- **Personal Loan**: Did this customer accept the personal loan offered in the last campaign? (Target)
- **Securities Account**: Does the customer have a securities account with the bank?
- **CD Account**: Does the customer have a certificate of deposit (CD) account with the bank?
- **Online**: Does the customer use internet banking facilities?
- **CreditCard**: Does the customer use a credit card issued by AllLife Bank?

## Key Technologies Used
- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Logistic Regression, Decision Trees
- Scikit-learn

## Implementation Details

### Exploratory Data Analysis (EDA)
- **Customer Profiles**: The average customer age is 45 years, with wide variation (23-67).
- **Financial Context**: Average income is $73,000, but the distribution is right-skewed.
- **Outlier Analysis**: Significant outliers were identified in `CCAvg` (credit card spending) and `Mortgage` values, highlighting high-value potential customers.
- **Loan Segment**: Only 9.6% of customers in the dataset had accepted a personal loan, indicating a class imbalance.

### Data Preprocessing
- **Data Cleaning**: Dropped unique identifiers (`ID`) and corrected anomalous negative values in the `Experience` column.
- **Feature Engineering**: 
  - Mapped `Education` levels to descriptive categories (Undergraduate, Graduate, Professional).
  - Binned `ZIPCode` based on the first two digits to represent broader geographical regions.
- **Categorical Construction**: Relevant features were converted to categorical types for robust model performance.

### Model Training & Selection
- **Approach**: Several versions of **Decision Tree Classifiers** were developed.
- **Selection Criteria**: The primary goal was to maximize **Recall** for the positive class (potential loan buyers) to ensure the marketing department identifies high-probability targets.
- **Final Model**: A **Post-Pruned Decision Tree** was selected after hyperparameter tuning of the `ccp_alpha` parameter and implementing **class weighting** (e.g., higher weight to class 1) to address imbalance and favor recall.
