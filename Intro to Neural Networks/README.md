# ReneWind: Wind Turbine Generator Failure Prediction

## Business Context
Renewable energy sources like wind power are crucial for a sustainable future. However, wind turbines are expensive to install and maintain. Unexpected failures in components like the generator can lead to significant downtime and repair costs. Predictive maintenance, powered by machine learning, can help identify potential failures before they occur, allowing for proactive servicing and reducing operational expenses.

## Objective
The goal is to build classification models to predict the failure of wind turbine generators based on sensor data. By predicting failures accurately, we can optimize maintenance schedules and minimize the cost of energy production.

## Data Description
The dataset provided is a ciphered version of original sensor data.
- **Training Set**: 20,000 observations and 40 predictors.
- **Test Set**: 5,000 observations and 40 predictors.
- **Target Variable**: '1' indicates failure, '0' indicates no failure.

## Implementation Details

### EDA Approach
- Analyzed 20,000 training observations with 40 ciphered predictors.
- Explored data distribution and class imbalance to prepare for neural network training.

### Models Trained
Seven Neural Network architectures were evaluated:
- **Model 0**: Basic architectue with **SGD** and **ReLU**.
- **Model 1**: Enhanced with **Momentum**.
- **Model 2**: 2-layer network with **Adam** optimizer.
- **Model 3**: Adam optimizer with **Dropout Regularization**.
- **Model 4**: Integrated **BatchNormalization** and Adam.
- **Model 5**: Combined **BatchNormalization** and **Dropout**.
- **Model 6**: Used **Dropout** and **He Normalization**.

### Model Selection Criteria
- Comparison of **Accuracy**, **Recall**, **Precision**, and **F1 Score**.
- **Recall Objective**: High recall for Class 1 (failures) was prioritized to minimize expensive generator replacements (False Negatives).

### Final Model Choice
- **Selected Model**: **Model 3 (Adam & Regularization)**.
- **Reasoning**: Achieved the best balance with a high recall of **0.89** on validation and strong precision/F1-score, ensuring robust failure detection while managing inspection costs.

### Final Model Architecture
- **Hidden Layer 1**: 32 units, ReLU activation, **Dropout (0.4)**.
- **Hidden Layer 2**: 16 units, ReLU activation, **Dropout (0.2)**.
- **Output Layer**: 1 unit, Sigmoid activation.
- **Optimizer**: Adam.

### Test Performance
- **Accuracy**: 0.98
- **Recall (Class 1)**: 0.87
- **Precision (Class 1)**: 0.83
- **F1-Score (Class 1)**: 0.85

## Key Technologies Used
- Python
- TensorFlow / Keras
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn (Preprocessing and Evaluation)

## Actionable Insights and Recommendations
- **Operational Integration**: Use the model for proactive maintenance alerts to reduce replacement costs.
- **Performance Monitoring**: Regularly monitor recall on live sensor data to ensure the model adapts to changing environmental factors.
- **Optimize Inspections**: Leverage balanced F1-scores to prioritize inspections for units with high predicted risk.
