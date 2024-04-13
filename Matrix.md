**Step 1: Base Case**
- For the base case, let's start with a function that takes a single price and a discount rate as input and returns the discounted price rounded to the nearest integer.
- We'll use basic arithmetic operations and rounding functions to implement this.

```python
def apply_discount_single(price, discount_rate):
    discounted_price = price * (1 - discount_rate)  # Apply discount
    rounded_price = round(discounted_price)  # Round to nearest integer
    return rounded_price

# Example usage:
original_price = 10
discount_rate = 0.2  # 20% discount
discounted_price = apply_discount_single(original_price, discount_rate)
print("Discounted Price (Rounded to Nearest Integer):", discounted_price)
```

Output:
```
Discounted Price (Rounded to Nearest Integer): 8
```

**Step 2: Extend to Matrix**
- Now, let's extend the function to handle matrices of prices instead of single prices.
- We'll iterate over each element of the matrix, apply the discount using scalar multiplication, and round the discounted prices to the nearest integer.

```python
import numpy as np

def apply_discount_matrix(matrix, discount_rate):
    discounted_prices = np.zeros_like(matrix)  # Initialize an empty matrix with the same shape
    rows, cols = matrix.shape
    for i in range(rows):
        for j in range(cols):
            original_price = matrix[i, j]
            discounted_price = apply_discount_single(original_price, discount_rate)
            discounted_prices[i, j] = discounted_price
    return discounted_prices

# Example usage:
prices = np.array([[10, 20, 30],
                   [15, 25, 35],
                   [12, 18, 24]])

discount_rate = 0.2  # 20% discount
discounted_prices = apply_discount_matrix(prices, discount_rate)
print("Discounted Prices (Rounded to Nearest Integer):")
print(discounted_prices)
```

Output:
```
Discounted Prices (Rounded to Nearest Integer):
[[ 8 16 24]
 [12 20 28]
 [10 14 19]]
```

**Step 3: Optimization**
- Finally, we can optimize the solution by utilizing NumPy's vectorized operations for better performance.
- This involves removing the nested loops and directly applying scalar multiplication and rounding to the entire matrix.

```python
def apply_discount_matrix_optimized(matrix, discount_rate):
    discounted_prices = matrix * (1 - discount_rate)  # Apply discount using scalar multiplication
    rounded_prices = np.round(discounted_prices).astype(int)  # Round to nearest integer
    return rounded_prices

# Example usage (same as before):
discounted_prices = apply_discount_matrix_optimized(prices, discount_rate)
print("Discounted Prices (Rounded to Nearest Integer):")
print(discounted_prices)
```

Output:
```
Discounted Prices (Rounded to Nearest Integer):
[[ 8 16 24]
 [12 20 28]
 [10 14 19]]
```

This step-by-step approach helps break down the problem into manageable parts, making it easier to understand and implement each component.