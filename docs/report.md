# DATA606 - Capstone Report

## Title and Author
- **Title** : Prediction of CO2 Emission from Vehicles
- **Author** : Gurram Ranadeep Reddy
- Fall 2023
- [GitHub]( https://github.com/Ranadeepgurram/UMBC-DATA606-FALL203-TUESDAY)
- [LinkedIn]([linkedin.com/in/alekhyanarala](https://www.linkedin.com/feed/?trk=guest_homepage-basic_google-one-tap-submit))
- [presentation](https://docs.google.com/presentation/d/1ikZ7zktLEsU8QH-QFqqUMJ72cBo-se_x/edit?usp=drive_link&ouid=104919725301177379198&rtpof=true&sd=true)
- [YouTube video](https://youtu.be/LDS2K5xrWrs)

    
## Background
Vehicle emissions of carbon dioxide (CO2) are a significant factor in climate change.Governments and organizations from all over the world are supporting the adoption of cleaner automobiles in an effort to cut emissions. Giving consumers information on how their car choices will affect the environment is one strategy to promote the use of cleaner automobiles. The goal of this project is to create a machine learning-based system that can forecast a vehicles CO2 emissions based on its attributes. A dataset of vehicle characteristics, including cylinder count, transmission type, fuel type, and fuel consumption in city, highway, and combination situations, will be used to train the system. The projects objective is to create a system that can precisely forecast CO2 emissions for new cars, assisting consumers.


**Research Questions**
 - Determine or put to the test how various factors affect CO2 emission?
 - What are the most influencing features that affect the CO2 emission the most?
 - When considering the fuel consumption for city and highway separately as well as the weighted variable interaction 
   between the two,    will the CO2 emissions differ in any way?



## Data 

**Describe the datasets you are using to answer your research questions.**

- Data size: 90 kB
- Data shape: # Number of rows - 6282 and # Number of  columns - 12

**What features are important, what column means what**
- 1.Make: Company of the vehicle.
- 2.Model: Car model.
- 3.Vehicle Class: A classification of vehicles based on their weight, utility, and capacity.
- 4.Engine Size: Engine Size (in Litres).
- 5.Cylinders: Number of cylinders.
- 6.Transmission: Transmission type with number of gears.
- 7.Fuel Type: Type of Fuel used.
- 8.Fuel Consumption City: Fuel used on city roads per 100 km.
- 9.Fuel Consumption Hwy: Fuel consumption in Hwy roads (L/100 km).
- 10.Fuel Consumption Comb: The combined fuel consumption (45% on the highway and 55% in the cities) is displayed in L/100 
  km.
- 11.Fuel Consumption Comb mpg: The combined fuel consumption in both city and highway is shown in mile per gallon(mpg)

# 4. Exploratory Data Analysis(EDA)

## 4.1 Data Cleaning.

### 4.1.1 Checking and removing Duplicates from the Data Set.
* Checking the duplicates from in the data set and we can see that there are no duplicates present in the data. So the data is free from duplicates.

## 4.2 Analysing the data and Visualizations.
* In this step we checked the columns in the data frame and derived some insights to modify the data.
* First, we will see the what are the types present in the Column.
* This column contains the  unique values such as fuel type, emission, transmission.
* The below is the distribution of these types throughout the data set.
   <img width="1000" alt="image" src="https://github.com/DATA-606-2023-FALL-TUESDAY/Gurram_Ranadeep/blob/main/data/pics/image_1.png">
* From the graph, it can be seen that there we plotted graph between the  'Engine Size(L)' and 'CO2 Emissions(g/km)' which is a scatter plot.

  
    <img width="1000" alt="image" src="https://github.com/DATA-606-2023-FALL-TUESDAY/Gurram_Ranadeep/blob/main/data/pics/image_2.png">
* The graph shows a pair plot using seaborn for a subset of numerical variables ('Engine Size(L)', 'Cylinders', 'Fuel Consumption Comb (mpg)', 'CO2 Emissions(g/km)'), visualizing pairwise relationships and histograms 
  for each variable. The title is set at the top with a slight vertical offset.
     <img width="1000" alt="image" src="https://github.com/DATA-606-2023-FALL-TUESDAY/Gurram_Ranadeep/blob/main/data/pics/image_3.png">
* The pair plot visualizes the relationships and distributions of selected numerical variables ('Engine Size(L)', 'Cylinders', 'Fuel Consumption Comb (mpg)', 'CO2 Emissions(g/km)') from the dataset, with histograms on 
  the diagonal, and points colored by the categorical variable 'Vehicle Class'.
     <img width="1000" alt="image" src="https://github.com/DATA-606-2023-FALL-TUESDAY/Gurram_Ranadeep/blob/main/data/pics/image_4.png">
* The heatmap illustrates the pairwise correlation coefficients between numerical variables in the DataFrame, using a color scale (red for positive, blue for negative correlations), with annotated correlation values. 
  Stronger correlations tend to be closer to -1 or 1, while weaker correlations are closer to 0.

## 4.3 Data Preprocessing

* Before diving into model training, it's essential to preprocess the data to ensure it's in the right format for our machine learning algorithms.

  ### In this Section
* We drop the unused columns.
* Further divide the data into training and testing sets. 


  #### Data Preprocessing:

 * Data Cleaning: Handling missing values, outliers, and other inconsistencies in the data.
 * Feature Scaling: Standardizing or normalizing features to bring them to a similar scale.
 * Feature Engineering: Creating new features from existing ones or transforming features to improve model performance.

   #### Model Training:

 * Model Selection: Picking a suitable machine learning algorithm depending on the problem type (classification, regression, etc.) and data characteristics.

 * Model Training: Utilizing training data to educate the model on discerning patterns within the dataset.

 #### Model Evaluation:

 * Testing and Validation: Evaluating how well the model performs on new, unseen data to ensure its generalizability and effectiveness.
 ### Linear Regression Model Evaluation:
 #### Mean Squared Error (MSE) and R-squared (R2):
 * Training Mean Squared Error: The average squared difference between the actual and predicted CO2 emissions for the training data is calculated. Lower values indicate better model fit.

 * Testing Mean Squared Error: Similar to the training MSE, this measures the average squared difference for the testing data. It helps assess how well the model generalizes to new, unseen data.

 * Training R-squared: This metric quantifies the proportion of variance in the training data explained by the model. A value closer to 1 indicates a better fit.

 * Testing R-squared: Similar to training R2, this measures the proportion of variance explained by the model on the testing data. A high R2 suggests good predictive performance.
 * Training Mean Squared Error: 403.6908678399931
 * Testing Mean Squared Error: 404.1233302241802
 *  Training R-squared: 0.8819117031025883
 *  Testing R-squared: 0.8825095623681144
   <img width="1000" alt="image" src="https://github.com/DATA-606-2023-FALL-TUESDAY/Gurram_Ranadeep/blob/main/data/pics/image_5.png">
 * Scatter Plot of Actual vs. Predicted CO2 Emissions: Visual representation of how well the model predictions align with actual values. Each point represents an observation, and a tighter alignment indicates better 
   prediction accuracy.
 * The regression model demonstrates strong performance with low Mean Squared Error (MSE) values (403.69 for training, 404.12 for testing) and high R-squared (R2) values (0.88 for both training and testing), indicating 
   accurate predictions and a good fit to the data.

 ### Random Forest Regression Model Evaluation:
 * Model Training:
 * Training Accuracy (R-squared): 99.55%

 * The model explains approximately 99.55% of the variance in the training data, indicating an excellent fit.
 * Training Root Mean Squared Error (RMSE): 3.90

 * The average magnitude of the residuals in the training data is relatively low, with an RMSE of 3.90.
 * Model Testing:
 * Testing Accuracy (R-squared): 98.02%

 * The model demonstrates strong predictive performance on new, unseen data, explaining approximately 98.02% of the variance.
 * Testing Root Mean Squared Error (RMSE): 8.26

 * The average magnitude of the residuals in the testing data is reasonable, with an RMSE of 8.26.
 * The Random Forest Regression model demonstrates outstanding performance, achieving high training accuracy (R-squared: 99.55%), strong testing accuracy (R-squared: 98.02%), and accurate predictions with low root mean 
   squared errors, indicating excellent fit and generalization.

 ### XGBoost Regression Model Evaluation:
 #### Model Training:
 * Training Accuracy (R-squared): 99.47%

 * The XGBoost model explains approximately 99.47% of the variance in the training data, indicating an excellent fit.
 * Training Root Mean Squared Error (RMSE): 3.90

 * The average magnitude of the residuals in the training data is relatively low, with an RMSE of 3.90 (previously calculated).
 * Model Testing:
 * Testing Accuracy (R-squared): 98.23%

 * The model demonstrates strong predictive performance on new, unseen data, explaining approximately 98.23% of the variance.
 * Testing Root Mean Squared Error (RMSE): 8.26

 * The average magnitude of the residuals in the testing data is reasonable, with an RMSE of 8.26 (previously calculated).
    <img width="1000" alt="image" src="https://github.com/DATA-606-2023-FALL-TUESDAY/Gurram_Ranadeep/blob/main/data/pics/image_6.png">
 * Scatter Plots:
 * Training Data Scatter Plot:
 * The scatter plot illustrates a strong alignment between actual and predicted CO2 emissions in the training data, suggesting accurate predictions.
 * Testing Data Scatter Plot:
 * The scatter plot for testing data also shows a good alignment, indicating the model's ability to generalize well to new observations.
 * The XGBoost Regression model demonstrates outstanding performance, achieving high training accuracy (R-squared: 99.47%) and strong testing accuracy (R-squared: 98.23%). The RMSE values indicate accurate predictions 
   with low average residuals. The scatter plots confirm the model's accuracy in predicting CO2 emissions for both seen and unseen data. Overall, the XGBoost model is effective in capturing the underlying patterns in 
   the data, making it a robust choice for regression tasks.

 ### Support Vector Regression (SVR) Model Evaluation:

1. **Dataset Preparation:**
   - The dataset is loaded, and features (X) such as 'Engine Size(L)', 'Cylinders', and 'Fuel Consumption Hwy (L/100 km)' are selected. The target variable (y) is set as 'CO2 Emissions(g/km)'.

2. **Data Splitting:**
   - The dataset is split into training and testing sets using an 80-20 split ratio.

3. **SVR Model Creation and Training:**
   - An SVR model with a linear kernel is created.
   - The model is trained on the training data.

4. **Prediction and Evaluation:**
   - Predictions are made on the testing data.
   - Mean Squared Error (MSE) is calculated, measuring the average squared difference between actual and predicted values.
   - R-squared (accuracy) is calculated, representing the proportion of variance explained by the model.

5. **Results Display:**
   - **Mean Squared Error (MSE):** 578.46
     - The MSE indicates the average squared difference between actual and predicted CO2 emissions, with lower values indicating better accuracy.

   - **R-squared (Accuracy):** 0.83
     - The R-squared value of 0.83 suggests that the SVR model explains approximately 83.18% of the variance in CO2 emissions, indicating a good fit.
     <img width="1000" alt="image" src="https://github.com/DATA-606-2023-FALL-TUESDAY/Gurram_Ranadeep/blob/main/data/pics/image_7.png">

6. **Scatter Plot Visualization:**
   - A scatter plot visualizes the actual vs. predicted values on the testing data, providing a visual assessment of how well the model's predictions align with the actual values.

   * The SVR model, trained with a linear kernel, demonstrates good performance with a relatively low Mean Squared Error (578.46) and a high R-squared value (0.83). The scatter plot visually confirms the alignment of 
     predicted and actual values, indicating the model's effectiveness in predicting CO2 emissions based on the selected features.


  # Results and Comparision
  ### Prediction Using SVR Model:

 **New Feature Values:**
   - New feature values are provided for prediction, including 'Engine Size(L)': 2.0, 'Cylinders': 4, and 'Fuel Consumption Hwy (L/100 km)': 7.0.

 **Prediction with SVR Model:**
   - The Support Vector Regression (SVR) model previously trained is utilized to predict CO2 Emissions for the new data.

 **Predicted CO2 Emissions:**
   - The model predicts that the CO2 Emissions for the given set of feature values will be approximately 196.38 grams per kilometer.

* The SVR model, trained on the dataset, is applied to predict CO2 Emissions for new feature values. The predicted value of 196.38 grams per kilometer provides an estimate of the expected CO2 Emissions based on the 
  specified engine size, number of cylinders, and fuel consumption on the highway.

  ### Overall Conclusion on Regression Models:

 1. **Linear Regression:**
   - Linear Regression achieved good accuracy with an R-squared value of 88.15%. The scatter plot visually confirmed the model's ability to predict CO2 emissions accurately.

 2. **Random Forest Regression:**
   - The Random Forest Regression model demonstrated outstanding performance with high accuracy (R-squared: 99.02% for testing) and low root mean squared errors. Scatter plots illustrated accurate predictions for both training and testing data.

 3. **XGBoost Regression:**
   - XGBoost Regression showcased exceptional accuracy with high R-squared values (99.47% for training, 98.23% for testing). The model exhibited accurate predictions, as seen in scatter plots for both training and testing datasets.

 4. **Support Vector Regression (SVR):**
   - SVR with a linear kernel performed well, explaining approximately 83.18% of the variance in CO2 emissions. The model demonstrated accurate predictions, as evident in the scatter plot.

# Conclusion

* The regression models, including Random Forest and XGBoost, exhibited high accuracy in predicting CO2 emissions. Model selection should be tailored to application needs, with considerations for interpretability and computational efficiency.





