# SuperKart: Sales Forecasting and Model Deployment

## Business Context
SuperKart is a large retail chain with multiple stores across the country. Accurate sales forecasting is essential for efficient inventory management, staff scheduling, and strategic planning. By predicting future sales, SuperKart can ensure that the right products are in stock at the right time, minimizing waste and maximizing customer satisfaction.

## Objective
The goal of this project is to develop a sales forecasting model for SuperKart and deploy it as a web application. This allows store managers and executives to easily access forecasts and make data-driven decisions.

## Data Description
The dataset includes historical sales data for various products (items) at different SuperKart stores.

- **Item_Identifier**: Unique product ID
- **Item_Weight**: Weight of product
- **Item_Fat_Content**: Whether the product is low fat or not
- **Item_Visibility**: The percentage of total display area of all products in a store allocated to the particular product
- **Item_Type**: The category to which the product belongs
- **Item_MRP**: Maximum Retail Price (list price) of the product
- **Outlet_Identifier**: Unique store ID
- **Outlet_Establishment_Year**: The year in which store was established
- **Outlet_Size**: The size of the store in terms of ground area covered
- **Outlet_Location_Type**: The type of city in which the store is located
- **Outlet_Type**: Whether the outlet is just a grocery store or some sort of supermarket
- **Item_Outlet_Sales**: Sales of the product in the particular store (Target)

## Key Technologies Used
- Python
- Pandas, NumPy
- Scikit-learn
- Flask (for deployment)
- Heroku / AWS (mentioned for deployment)
- Matplotlib, Seaborn

## Implementation Details

### Exploratory Data Analysis (EDA)
- **Data Insights**: Evaluated product attributes across various store types (Food Mart, Departmental Store, Supermarkets).
- **Correlation**: Identified strong correlations between `Product_MRP` and sales totals, influencing feature selection.

### Data Preprocessing
- **Missing Value Imputation**: Handled missing weights and store sizes using median and mode imputation strategies.
- **Feature Engineering**: Created new features like `Store_Age` and simplified categorical variables (e.g., binning product types).
- **Categorical Encoding**: Utilized Label Encoding and One-Hot Encoding to prepare data for model training.

### Model Training & Selection
- **Approach**: Built a regression pipeline involving various algorithms (Linear Regression, Random Forest, XGBoost).
- **Final Model**: A tuned **XGBoost Regressor** was selected for its superior performance in minimizing forecasting error.

### Model Deployment
- **Framework**: Developed a web API using the **Flask** micro-framework.
- **Functionality**: Local endpoint accepts product and store attributes to return real-time sales revenue forecasts.
- **Persistence**: Used **joblib** for efficient model serialization and retrieval during production inference.
