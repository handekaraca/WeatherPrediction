**Project Description: Weather Condition Prediction using PySpark in Google Colab**

**Overview:**
This project aims to develop a machine learning model to predict weather conditions using historical weather data. The dataset used in this project consists of various meteorological features, including precipitation, minimum and maximum temperatures, wind speed, and the corresponding weather conditions. By leveraging PySpark's powerful data processing capabilities, we build and evaluate a classification model to predict categorical weather conditions. This project is implemented in Google Colab, utilizing the distributed processing features of PySpark.

**Objectives:**
The primary objective of this project is to predict the type of weather condition (e.g., clear, cloudy, rainy) based on features such as precipitation, wind speed, temperature, etc. Our goal is to understand the relationships between these features and to evaluate the model's ability to make accurate predictions.

**Dataset:**
The dataset used is publicly available on Kaggle and includes the following columns:
- **Date**: The date of the recorded weather data.
- **Precipitation**: The amount of precipitation in millimeters.
- **Temp Max**: Maximum temperature recorded on a given day.
- **Temp Min**: Minimum temperature recorded on a given day.
- **Wind**: Wind speed recorded in km/h.
- **Weather**: Descriptive weather condition (e.g., clear, cloudy, rainy).

**Methodology:**
1. **Data Loading and Preprocessing**: The dataset is loaded from Kaggle into Google Colab using KaggleHub, and then cleaned to remove any missing values. String indexing is used to convert the categorical weather column into numerical labels for classification.
2. **Feature Engineering**: Key meteorological variables are selected as features to create the `features` vector, which is used as input for the model.
3. **Model Building**: A **Classification Model** is developed using logistic regression to predict the categorical weather condition (`weather`).
4. **Manual Testing**: The model is also tested manually by providing user-defined input values to see how well the model can generalize to new, unseen data.
5. **Evaluation and Visualization**: Predictions are evaluated using metrics such as accuracy, precision, recall, and F1-score. A confusion matrix is generated to visualize the model's performance.

**Results:**
- **Classification Model**: The logistic regression model achieved an accuracy of 83% in predicting the weather condition. The detailed classification report is as follows:
  
  - **Class 0.0 (Clear)**: Precision = 0.97, Recall = 0.89, F1-score = 0.93, Support = 179
  - **Class 1.0 (Cloudy)**: Precision = 0.73, Recall = 0.98, F1-score = 0.84, Support = 164
  - **Class 2.0 (Rainy)**: Precision = 0.00, Recall = 0.00, F1-score = 0.00, Support = 24
  - **Class 3.0 (Foggy)**: Precision = 0.00, Recall = 0.00, F1-score = 0.00, Support = 16
  - **Class 4.0 (Snowy)**: Precision = 0.50, Recall = 0.38, F1-score = 0.43, Support = 8
  
  - **Overall Accuracy**: 83%
  - **Macro Average**: Precision = 0.44, Recall = 0.45, F1-score = 0.44
  - **Weighted Average**: Precision = 0.76, Recall = 0.83, F1-score = 0.78
  
  Some classes, such as "clear" and "cloudy", showed higher prediction performance, while other minor classes performed poorly due to limited representation in the dataset. The confusion matrix provided insights into which classes the model was able to predict correctly and where it faced challenges. For example, the classification report showed high precision for certain classes, while others, like rare weather conditions, had low recall and F1-scores.
- **Manual Testing**: A manual test was performed with a sample data point (`precipitation` = 1.2, `temp_max` = 18.0, `temp_min` = 10.0, `wind` = 7.0). The model predicted the weather class as `0.0`, which corresponded to a specific weather type. The model's confidence was high, as indicated by the probability scores.

**Conclusion:**
This project showcases the potential of PySpark in building scalable machine learning models for weather prediction. The classification model demonstrated varying performance depending on the balance and distribution of weather classes. There is room for improvement by balancing classes, using additional features, and exploring more complex algorithms like Random Forests or Gradient Boosting. This project also emphasizes the importance of proper feature engineering and data balancing for improving model accuracy.

**Technologies Used:**
- **PySpark** for distributed data processing and model training.
- **Google Colab** as the development environment.
- **Matplotlib** and **Seaborn** for data visualization.
- **KaggleHub** for easy dataset integration from Kaggle.

