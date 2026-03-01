# HelmNet: Safety Helmet Detection

## Business Context
Ensuring workplace safety is a critical priority for industries like construction, manufacturing, and mining. Safety helmets are essential personal protective equipment (PPE) that can prevent serious head injuries. Manual monitoring of helmet usage is often impractical in large-scale operations. An automated system that can detect whether workers are wearing helmets in real-time can significantly enhance safety compliance.

## Objective
The objective of this project is to develop an image classification model to detect whether a person in a workspace is wearing a safety helmet or not. This system can be integrated with surveillance cameras to provide real-time alerts for safety violations.

## Data Description
The dataset provided contains images of workers in various environments, categorized into two classes:
- **With Helmet**: Images of workers wearing safety helmets.
- **Without Helmet**: Images of workers not wearing safety helmets.

The images vary in lighting conditions, backgrounds, and camera angles to ensure the model's robustness.

## Key Technologies Used
- Python
- TensorFlow / Keras
- OpenCV
- Pandas, NumPy
- Matplotlib

## Implementation Details

### Image Preprocessing
- **Resizing**: All images were standardized to a resolution of **200x200** pixels to ensure consistent input for the neural network.
- **Data Augmentation**: Implemented techniques such as **rotation**, **width/height shifting**, **shear**, **zoom**, and **horizontal flipping** to improve model generalization and prevent overfitting.
- **Normalization**: Pixel values were scaled to the [0, 1] range to facilitate faster convergence during training.

### Model Architecture
- **Approach**: Built a **Convolutional Neural Network (CNN)** for binary classification.
- **Architecture**: Leveraged a deep network structure (custom or based on **VGG16**) with multiple convolutional and pooling layers for feature extraction, followed by dense layers for classification.
- **Activation Functions**: Utilized **ReLU** for hidden layers and **Sigmoid** for the output layer to predict the probability of helmet usage.

### Model Evaluation
- **Metrics**: Performance was evaluated using **Accuracy**, **Precision**, **Recall**, and **F1-score**.
- **Analysis**: Employed a **Confusion Matrix** to visualize the model's ability to distinguish between the 'With Helmet' and 'Without Helmet' classes, ensuring high reliability for workplace safety.
