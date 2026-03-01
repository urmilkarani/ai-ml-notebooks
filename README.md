# EasyVisa: Visa Approval Prediction

## Business Context
The process of visa portal is a complex and time-consuming process for both the applicants and the government. Applicants have to go through many rounds of interviews and submit many documents. The government has to go through many applications and verify each one of them. In order to expedite this process, many companies use machine learning to shortlist the candidates who have a higher chance of visa approval.

## Objective
The goal is to build a machine learning model to help shortlist candidates with a higher chance of visa approval. This will help the company to save time and resources by focusing on the candidates who are more likely to get their visa approved.

## Data Description
The dataset contains information about various attributes of employees and employers.

- **case_id**: ID of each visa application
- **continent**: Information of continent the employee's company is located in
- **education_of_employee**: Information of education of the employee
- **has_job_experience**: Does the employee has any job experience? [Y/N]
- **requires_job_training**: Does the employee requires any job training? [Y/N]
- **no_of_employees**: Number of employees in the company of the employee
- **yr_of_establish**: Year in which the company was established
- **region_of_employment**: Information of foreign worker's intended region of employment in US
- **prevailing_wage**: Average wage paid to similarly employed workers in a specific occupation in the area of intended employment.
- **unit_of_wage**: Unit of prevailing wage [Hourly, Weekly, Bi-Weekly, Monthly, Yearly]
- **full_time_position**: Is the position of full-time? [Y/N]
- **case_status**: Flag if visa was certified or denied [Certified/Denied]

## Key Technologies Used
- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn

## Implementation Details

### Exploratory Data Analysis (EDA)
- **Feature Analysis**: Identified key drivers such as `education_of_employee`, `has_job_experience`, and `prevailing_wage` that significantly influence visa certification.
- **Data Distribution**: Analyzed the distribution of applications across different continents and employment regions.

### Data Preprocessing
- **Data Cleaning**: Dropped unique identifiers (`case_id`) and ensured data types were appropriate for modeling.
- **Handling Imbalance**: Evaluated the class distribution of `case_status` to determine the need for sampling techniques.
- **Categorical Transformation**: Conducted One-Hot Encoding for categorical variables and standardized numerical features for optimal model performance.

### Model Training & Selection
- **Approach**: Multi-model training approach including **Logistic Regression**, **Decision Trees**, **Random Forest**, and **XGBoost**.
- **Selection Criteria**: The primary optimization metric was **Recall** for the 'Denied' class to minimize the risk of incorrectly shortlisting unsuitable candidates.
- **Final Model**: A hyperparameter-tuned **Random Forest** or **XGBoost** model was selected for providing the best balance between precision and recall.
