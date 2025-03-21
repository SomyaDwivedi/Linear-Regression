# Simple Linear Regression Analysis

This project demonstrates a simple linear regression analysis using Python, `matplotlib`, and `numpy`. It calculates the coefficients `w1` (slope) and `w0` (intercept) for a linear regression model and evaluates the model's performance using the R² score.

## Overview

The script performs the following tasks:

1. **Data Visualization:** Plots the given data points as a scatter plot.
2. **Linear Regression Calculation:** Computes the slope (`w1`) and intercept (`w0`) of the best-fit line using the least squares method.
3. **Prediction:** Takes a user input for a new `x` value and predicts the corresponding `y` value using the calculated regression model.
4. **Regression Line Plot:** Plots the calculated regression line along with the original data points.
5. **R² Score Calculation:** Computes the R² score to assess the model's goodness of fit.
6. **Mean Squared Error (MSE) Calculation:** Evaluates the model's average squared error.

## Files

- `main.py`: Contains the Python script for the linear regression analysis.
- `README.md`: This file, providing project documentation.

## Usage

1. **Run the script:**

    ```bash
    python main.py
    ```

2. **Input:** The script will prompt you to enter an `x` value. Enter the desired value and press Enter.

3. **Output:** The script will display the predicted `y` value and generate a plot showing the data points and the regression line. It will also print the R² score and MSE.

## Code Explanation

### Linear Regression Calculation

The slope (`w1`) and intercept (`w0`) are calculated using the following formulas:

- \( w1 = \frac{\sum (x_i - \bar{x})(y_i - \bar{y})}{\sum (x_i - \bar{x})^2} \)
- \( w0 = \bar{y} - w1 \cdot \bar{x} \)

Where:

- \( x_i \) and \( y_i \) are the individual data points.
- \( \bar{x} \) and \( \bar{y} \) are the means of the `x` and `y` values, respectively.

### R² Score Calculation

The R² score is calculated using the following formula:

- \( R^2 = 1 - \frac{SSE}{SST} \)

Where:

- \( SSE = \sum (y_i - \hat{y}_i)^2 \) (Sum of Squared Errors)
- \( SST = \sum (y_i - \bar{y})^2 \) (Total Sum of Squares)
- \( \hat{y}_i \) is the predicted value of \( y_i \).

### Mean Squared Error (MSE) Calculation

The Mean Squared Error (MSE) is calculated as:

\[
MSE = \frac{1}{n} \sum (y_i - \hat{y}_i)^2
\]

It measures the average squared difference between actual and predicted values. A lower MSE indicates better model accuracy. For this model, the MSE is **18**, meaning the predictions deviate from actual values by roughly **\( \sqrt{18} \approx 4.24 \)** units on average.

## Example

Given the data points:

```python
x = [153, 200, 140, 210, 170]
y = [900, 923, 880, 930, 910]
```

The script calculates the regression line and predicts a `y` value for a given `x` input. It also generates a plot and the R² score.

## R² Score Output Example

```
The model is 92.20% accurate.
```

## MSE Output Example

```
Mean Squared Error: 18
```

