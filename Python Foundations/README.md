# FoodHub: Data Analysis for Food Delivery Service

## Business Context
FoodHub is an online food delivery service that connects customers with a variety of restaurants in New York City. Understanding customer preferences, restaurant performance, and delivery logistics is crucial for optimizing the platform and improving the overall user experience.

## Objective
The objective is to analyze the FoodHub order data to gain insights into restaurant demand, customer behavior, and delivery efficiency. This analysis will help FoodHub identify popular cuisines, peak order times, and areas for improvement in their service.

## Data Dictionary
The dataset contains information on orders placed through the FoodHub platform.

- **order_id**: Unique ID of the order
- **customer_id**: ID of the customer who ordered the food
- **restaurant_name**: Name of the restaurant
- **cuisine_type**: Cuisine ordered by the customer
- **cost_of_the_order**: Cost of the order
- **day_of_the_week**: Indicates whether the order is placed on a weekday or weekend
- **rating**: Rating given by the customer out of 5
- **food_preparation_time**: Time (in minutes) taken by the restaurant to prepare the food
- **delivery_time**: Time (in minutes) taken to deliver the food

## Key Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn

## Implementation Details

### Exploratory Data Analysis (EDA)
- **Cuisine Demand**: Identified **American**, **Japanese**, and **Italian** as the top 3 most popular cuisines in New York City.
- **Revenue Patterns**: Analyzed order counts and revenue, highlighting a significant surge in weekend orders compared to weekdays.
- **Customer Loyalty**: Evaluated the frequency of orders per customer, identifying key segments for targeted marketing.

### Operational Efficiency Analysis
- **Preparation Trends**: Analyzed `food_preparation_time` across restaurant types to identify those with the highest speed-to-delivery ratios.
- **Logistics Bottlenecks**: Evaluated `delivery_time` distributions to pinpoint regions or times requiring delivery network optimization.
- **Total Duration**: Calculated total time (prep + delivery) to establish benchmarks for customer experience excellence.

### Business Recommendations
- Optimized restaurant partnerships by identifying those with high ratings but lower transaction volume.
- Suggested promotional strategies for low-order cuisines during off-peak weekday hours.
