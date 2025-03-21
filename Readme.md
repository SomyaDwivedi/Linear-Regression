
# Linear Regression Model - Explanation of Formulas and Functions

This Python script demonstrates a linear regression model to predict values based on a given dataset.

## Imports

```python
import matplotlib.pyplot as plt
import numpy as np
import math
```

- **matplotlib.pyplot** is used for plotting the data points and the regression line.
- **numpy** is used for numerical operations such as creating arrays.
- **math** is used to compute the square root of the Mean Squared Error (MSE).

## Data

```python
x = [140, 153, 170, 200, 210, 180, 160, 220, 230, 250, 240, 160, 180, 200, 190, 205, 215, 225, 235, 245]
y = [880, 900, 910, 923, 930, 915, 905, 935, 940, 950, 945, 910, 920, 925, 915, 930, 935, 940, 950, 960]
```

Here, `x` represents the prices, and `y` represents the corresponding sales.

## Calculating the Means

```python
Xmean = sum(x) / len(x)
Ymean = sum(y) / len(y)
```

- **Xmean**: The mean of `x` values.
- **Ymean**: The mean of `y` values.

## Calculating the Regression Coefficients (`w1` and `w0`)

```python
a = 0
b = 0
for i in range(len(x)):
    a += (x[i] - Xmean) * (y[i] - Ymean)
    b += (x[i] - Xmean) ** 2

w1 = a / b
w0 = Ymean - (w1 * Xmean)
```

- **w1**: The slope of the regression line, calculated using the formula:  
  
   $$w1 = \frac{\sum{(x_i - Xmean)(y_i - Ymean)}}{\sum{(x_i - Xmean)^2}}$$
  
  
- **w0**: The intercept of the regression line, calculated as:  

   $$w0 = Ymean - (w1 \times Xmean)$$


These values represent the linear relationship between `x` and `y`.

## Predicting `y` for a Given `x` Value

```python
X_input = int(input("Enter Price (X): "))
Y_pred = (w1 * X_input) + w0
```

- This predicts the corresponding `y` (sales) for a given `x` (price) using the equation:  
 
   $$Y_{pred} = w1 \times X_{input} + w0$$
 

## Plotting the Data and Regression Line

```python
plt.scatter(x, y, color='blue', label='Data Points')
x_values = np.array([min(x), max(x)])
y_values = w1 * x_values + w0
plt.plot(x_values, y_values, color='red', label='Regression Line')
plt.xlabel('X')
plt.ylabel('Y')
plt.legend()
plt.show()
```

- This plots the data points and the regression line using **matplotlib**.

## R² Score Calculation

```python
sse = 0.0
sst = 0.0

for i in range(len(x)):
    y_pred = (w1 * x[i]) + w0
    sse += (y[i] - y_pred)**2
    sst += (y[i] - Ymean)**2

r2_score = 1 - (sse / sst)
```

- **SSE (Sum of Squared Errors)**: Measures the difference between the actual `y` values and the predicted `y` values.
- **SST (Total Sum of Squares)**: Measures the difference between the actual `y` values and the mean of `y`.
- **R² Score**: Represents the proportion of the variance in `y` explained by the model, calculated as:  
  
   $$R^2 = 1 - \frac{SSE}{SST}

  The higher the R², the better the model fits the data.

## Mean Squared Error (MSE)

```python
mse = sse / len(x)
```

- **MSE** is calculated as the average of the squared errors. It indicates how far off the predictions might be on average.

## Conclusion

The script takes a price (`x`) as input, predicts the corresponding sales (`y`) using the linear regression model, and outputs the **R² score** and **MSE** to evaluate the model’s accuracy.

