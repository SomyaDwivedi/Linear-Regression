````markdown
# Simple Linear Regression Analysis

This project demonstrates a simple linear regression analysis using Python, `matplotlib`, and `numpy`. It calculates the coefficients `w1` (slope) and `w0` (intercept) for a linear regression model and evaluates the model's performance using the R² score.

## Overview

The script performs the following tasks:

1.  **Data Visualization:** Plots the given data points as a scatter plot.
2.  **Linear Regression Calculation:** Calculates the slope (`w1`) and intercept (`w0`) of the best-fit line using the least squares method.
3.  **Prediction:** Takes a user input for a new `x` value and predicts the corresponding `y` value using the calculated linear regression model.
4.  **Regression Line Plot:** Plots the calculated regression line along with the original data points.
5.  **R² Score Calculation:** Computes the R² score to assess the model's goodness of fit.

## Files

-   `main.py`: Contains the Python script for the linear regression analysis.
-   `README.md`: This file, providing project documentation.


## Usage

1.  **Run the script:**

    ```bash
    python main.py
    ```

2.  **Input:** The script will prompt you to enter a price (X). Enter the desired value and press Enter.

3.  **Output:** The script will display the predicted Y value and generate a plot showing the data points and the regression line. It will also print the R2 score.

## Code Explanation

### Linear Regression Calculation

The slope (`w1`) and intercept (`w0`) are calculated using the following formulas:

  - $w1 = \\frac{\\sum (x\_i - \\bar{x})(y\_i - \\bar{y})}{\\sum (x\_i - \\bar{x})^2}$
  - $w0 = \\bar{y} - w1 \\cdot \\bar{x}$

Where:

  - $x\_i$ and $y\_i$ are the individual data points.
  - $\\bar{x}$ and $\\bar{y}$ are the means of the `x` and `y` values, respectively.

### R² Score Calculation

The R² score is calculated using the following formula:

  - $R^2 = 1 - \\frac{SSE}{SST}$

Where:

  - $SSE = \\sum (y\_i - \\hat{y}\_i)^2$ (Sum of Squared Errors)
  - $SST = \\sum (y\_i - \\bar{y})^2$ (Total Sum of Squares)
  - $\\hat{y}\_i$ is the predicted value of $y\_i$.

## Example

Given the data points:

```
x = [153, 200, 140, 210, 170]
y = [900, 923, 880, 930, 910]
```

The script calculates the regression line and predicts a `y` value for a given `x` input. It also generates a plot and the R² score.

## R2 score output example

```
The model is 92.20% accurate
```
