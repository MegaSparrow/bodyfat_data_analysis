# Body Fat Analysis
This project aims to predict body fat percentage using easily accessible body measurements such as weight, height, and circumference of different body parts. 

Body fat percentage can be estimated using the Siri's equation below; however this would require body density measurements which are not easily accessible.
    
    body fat percentage = (495/Density) - 450

The aim of this project is to predict body fat percentages using machine learning algorthims without the use of body density values.


## Dataset
The dataset was dowloaded from [kaggle.com](https://www.kaggle.com/datasets/fedesoriano/body-fat-prediction-dataset) and contains the following variables:

- Density determined from underwater weighing - Excluded as it is not easily accessible
- Percent body fat from Siri's (1956) equation - To be predicted (target)
- Age (years)
- Weight (lbs) 
- Height (inches) 
- Neck circumference (cm)
- Chest circumference (cm)
- Abdomen 2 circumference (cm)
- Hip circumference (cm)
- Thigh circumference (cm)
- Knee circumference (cm)
- Ankle circumference (cm)
- Biceps (extended) circumference (cm)
- Forearm circumference (cm)
- Wrist circumference (cm)


## Preprocessing
Preprocessing involved removing outliers, filling in any missing data with mean values, scaling the data, and feature engineering using a custom transformer.

<img width="295" alt="image" src="https://user-images.githubusercontent.com/77254817/233465650-23a692e2-de59-4f32-afd7-836a409c5d4b.png">

To reduce colinearity, the following new features were calculated and used in place of the original data (i.e. weight, height, and measurements of abdoment, chest, hip and thighs were removed):

- BMI: clculated based on weight and height
- Ratio of Abdomen to Chest Measurements
- Ratio of Abdomen to Hip Measurements
- Ratio of Hip to Thigh Measurements

## Models
Multiple regression models were trained using cross-validation and evaluated using RMSE and R2 score. The following models were tested:

- Linear Regression
- Ridge Regression
- Lasso Regression
- Decision Tree
- Random Forest Regressor

The Ridge and Linear models performed the best, and the Ridge model was chosen as the final model.
<img width="272" alt="image" src="https://user-images.githubusercontent.com/77254817/233466461-700f00ca-f2af-4264-a85c-68802adb7e6c.png">

The top five contributing features were identified as:
1. BMI
2. Ratio of Abdomen to Hip Measurement
3. Ratio of Abdomen to Chest Measurement
4. Wrist Measurement
5. Neck Measurement

## Libraries
This project was implemented using the following libraries:

- Pandas
- Numpy
- Matplotlib
- Scikit-learn
- seaborn
- scipy

## Usage
To run the project, clone the repository and run the code using Google Colab, Jupyter notebook or Python IDE. Note, the project was produced on Google Colab and the input data is read from Google drive. The input data should be in CSV format with the above-mentioned variables. The code will preprocess the data, train the models, and output the final prediction for body fat percentage.
