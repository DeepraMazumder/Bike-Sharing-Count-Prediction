# Bike-Sharing-Count-Prediction

## Project Overview

The **Bike-Sharing-Count-Prediction** project aims to predict the total number of bike rentals per hour based on various features such as weather conditions, time (hour, weekday, month), and user types (casual or registered users). The project applies both linear regression and polynomial regression techniques to build predictive models and utilizes regularization techniques such as Ridge, Lasso, and ElasticNet to improve model performance.

The dataset used for this project is the **[Bike Sharing Dataset](https://archive.ics.uci.edu/ml/datasets/Bike+Sharing+Dataset)**, which contains hourly bike rental data for two years (2011 and 2012) in the Capital Bikeshare system, Washington D.C.

## Installation

To run the project locally, follow these steps:

1. **Clone the repository**:
    ```bash
    git clone https://github.com/your-username/Bike-Sharing-Count-Prediction.git
    ```

2. **Navigate to the project directory**:
   ```bash
   cd Bike-Sharing-Count-Prediction
   ```

3. **Install the required dependencies**:
   ```bash
   pip install -- upgrade -r requirements.txt
   ```
   
## Dataset

The dataset consists of the following features:

- `season`: Season (1: Winter, 2: Spring, 3: Summer, 4: Fall)
- `yr`: Year (0: 2011, 1: 2012)
- `mnth`: Month (1 to 12)
- `hr`: Hour of the day (0 to 23)
- `weekday`: Day of the week (0: Sunday to 6: Saturday)
- `workingday`: Whether it is a working day or not (1: Yes, 0: No)
- `holiday`: Whether it is a holiday or not (1: Yes, 0: No)
- `weathersit`: Weather situation (1: Clear, 2: Mist, 3: Light snow/rain, 4: Heavy rain/snow)
- `temp`: Normalized temperature in Celsius (temperature * 41)
- `atemp`: Normalized feeling temperature in Celsius (feeling temperature * 50)
- `hum`: Normalized humidity
- `windspeed`: Normalized wind speed
- `casual`: Count of casual users (non-registered users)
- `registered`: Count of registered users
- `cnt`: Total bike rental count (target variable)

## Exploratory Data Analysis (EDA)

The project begins by analyzing the distribution of bike-sharing data through various visualizations:

- **Hourly Counts**: The count of bike rentals by the hour.
- **Distribution of Counts**: The distribution of total, casual, and registered user counts.
- **Weekday Counts**: Counts grouped by the weekday, with holiday and working day indicators.

Visualizations were created using **Seaborn** and **Matplotlib** to understand the patterns in the data.

## Feature Engineering

1. **One-Hot Encoding**: Categorical features such as `season`, `weekday`, `workingday`, etc., were encoded using `OneHotEncoder`.
2. **Scaling**: Continuous features like `temp`, `atemp`, `humidity`, and `windspeed` were scaled using `MinMaxScaler`.

The final feature set used for modeling is a combination of scaled continuous variables and one-hot-encoded categorical variables.

## Modeling

### Linear Regression

A **Linear Regression** model was implemented using the scaled and encoded feature set. The steps included:

- Splitting the dataset into training and testing sets.
- Fitting the model on the training data.
- Predicting on the test set and evaluating using Mean Squared Error (MSE) and R-squared score.

### Polynomial Regression

A **Polynomial Regression** model was implemented to capture the non-linear relationship between the features and target. Polynomial features were generated using `PolynomialFeatures` from `sklearn`.

### Regularization Techniques

Regularization techniques were applied to prevent overfitting:

- **Ridge Regression**: Adds L2 penalty to the cost function.
- **Lasso Regression**: Adds L1 penalty to the cost function.
- **ElasticNet**: A combination of L1 and L2 penalties.

Each model was evaluated based on MSE and R-squared scores.

## Results

The project evaluated several models and techniques:

- **Linear Regression**:
  - Mean Squared Error (MSE): `x.xx`
  - R-squared Score: `x.xx`
  
- **Polynomial Regression**:
  - R-squared Score on Training Data: `x.xx`
  - R-squared Score on Testing Data: `x.xx`
  
- **Ridge, Lasso, and ElasticNet Regularization**:
  - Improved generalization performance with reduced MSE.

## Contributing

Contributions are welcome! If you want to contribute to the project, please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -m 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Create a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
