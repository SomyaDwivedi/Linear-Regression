---

# Simple Linear Regression Implementation

This project demonstrates a simple linear regression implementation in Python using. It calculates the coefficients `w1` (slope) and `w0` (intercept) for a linear regression model based on a given set of data points. The user can input a value for `x` to predict the corresponding `y` value.

---

## Files

- **`main.py`**: Contains the Python code for the linear regression calculation, prediction, and plotting.

---

## Dependencies

- `matplotlib`: For plotting the data points and the regression line.
- `numpy`: For numerical operations, specifically for creating arrays for plotting the regression line.

---


## Code Explanation

### Data

The script starts with two lists, `x` and `y`, representing the data points.

```python
x = [153, 200, 140, 210, 170]
y = [900, 923, 880, 930, 910]
```

---

### Calculating Mean

The mean of `x` (`Xmean`) and `y` (`Ymean`) are calculated.

```python
Xmean = sum(x) / len(x)
Ymean = sum(y) / len(y)
```

---

### Calculating Coefficients

The coefficients `w1` and `w0` are calculated using the following formulas:

\[
w1 = \frac{\sum{(x_i - \bar{x})(y_i - \bar{y})}}{\sum{(x_i - \bar{x})^2}}
\]

\[
w0 = \bar{y} - w1 \cdot \bar{x}
\]

```python
a = 0
b = 0
for i in range(len(x)):
    a += (x[i] - Xmean) * (y[i] - Ymean)
    b += (x[i] - Xmean) ** 2

w1 = a / b
w0 = Ymean - (w1 * Xmean)
```

---

### Prediction

The user is prompted to enter a value for `x`, and the corresponding `y` value is predicted using the calculated coefficients.

```python
x = float(input("Enter Price (X): "))
y = (w1 * x) + w0
print(y)
```

---

### Plotting

The script uses `matplotlib` to plot the original data points and the regression line.

```python
import matplotlib.pyplot as plt
import numpy as np

plt.scatter(x, y, color='blue', label='Data Points')

x_values = np.array([min(x), max(x)])
y_values = w1 * x_values + w0
plt.plot(x_values, y_values, color='red', label='Regression Line')

plt.xlabel('X')
plt.ylabel('Y')
plt.legend()
plt.show()
```

---

## Example Usage

1. Run the script.
2. When prompted, enter `180`.
3. The script will output the predicted `y` value and display the plot.

---

## Notes

- This is a basic implementation of linear regression. For more complex datasets and analyses, consider using libraries like `scikit-learn`.
- The quality of the regression depends on the linearity of the relationship between `x` and `y`.

---
