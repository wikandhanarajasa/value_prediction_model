# Car Value Prediction Model

## Introduction

This project is developed for Rusty Bargain, a fictitious used car trading company, aiming to build an application that helps users quickly determine the market value of their cars. The application will utilize historical data, technical specifications, and vehicle prices to provide accurate car value predictions.

## Goals

The primary objectives of this project are:
- **Prediction Quality**: Achieve high accuracy in car value predictions.
- **Prediction Speed**: Ensure the model provides fast predictions.
- **Training Time**: Optimize the time required to train the model.

## Project Steps

1. **Data Observation and Storage**:
   - Save and observe the provided dataset.
   
2. **Model Training**:
   - Train multiple models with different hyperparameters.
   - Evaluate at least two distinct models, including but not limited to Random Forest, Decision Tree, and Linear Regression.
   - Note: Different gradient boosting implementations do not count as separate models.
   
3. **Model Analysis**:
   - Analyze the speed and quality of each trained model.

## Data Description

The dataset contains 27,077 rows and 16 columns with the following features:

- **DateCrawled**: Date when the profile was downloaded.
- **VehicleType**: Body type of the vehicle.
- **RegistrationYear**: Year of vehicle registration.
- **Gearbox**: Type of transmission.
- **Power**: Power in horsepower (hp).
- **Model**: Vehicle model.
- **Mileage**: Distance traveled in km.
- **RegistrationMonth**: Month of vehicle registration.
- **FuelType**: Type of fuel used.
- **Brand**: Vehicle brand.
- **NotRepaired**: Indicates if the vehicle has been repaired.
- **DateCreated**: Date when the profile was created.
- **NumberOfPictures**: Number of vehicle pictures.
- **PostalCode**: Postal code of the profile owner.
- **LastSeen**: Date of the user's last activity.

### Target

- **Price**: Market value of the vehicle (in Euros).

## Data Cleaning

The following columns had missing values which were handled:
- **VehicleType**: 2,933 rows
- **Gearbox**: 1,505 rows
- **Model**: 1,474 rows
- **FuelType**: 2,570 rows
- **NotRepaired**: 5,453 rows

One duplicate row was removed.

## Insights

- Top three vehicle types: Sedan, Small, Wagon.
- Top three fuel types: Petrol, Gasoline, LPG.
- Top three models: Golf, Other, 3er.

## Model Training and Analysis

Five models were trained and evaluated based on prediction quality, speed, and training time:

| Model                | RMSE (Train) | RMSE (Test) | RMSE (Validation) | Wall Time (sec) |
|----------------------|--------------|-------------|-------------------|-----------------|
| Logistic Regression  | 5843.437     | 5979.321    | 5746.115          | 201.0           |
| Random Forest        | 655.695      | 2608.961    | 2657.262          | 28.0            |
| Light GBM            | 2046.961     | 2240.519    | 2181.612          | 1.1             |
| CatBoost Regressor   | 2099.117     | 2286.783    | 2170.087          | 1.5             |
| XGBoost Regressor    | 1716.396     | 2066.720    | 1981.200          | 5.6             |

## Conclusion

Based on the evaluation metrics, the **XGBoost Regressor** emerged as the best model:

- **Highest Prediction Quality**: Lowest RMSE on test (2066.720) and validation (1981.200) sets.
- **Reasonable Prediction Speed**: Took 5.6 seconds for wall time.
- **Balanced Training Time**: Efficient training time relative to prediction quality.

## Recommendations

- **Implementation**: Use the XGBoost Regressor for the application due to its superior accuracy and performance.
- **Future Improvements**: Consider further hyperparameter tuning and additional data preprocessing to enhance model performance.
- **User Experience**: Ensure the application utilizes the model effectively to provide quick and accurate car value predictions to attract and retain users.
