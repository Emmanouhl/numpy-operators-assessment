# NumPy Operators – Hands-On Practice

A comprehensive NumPy practice project covering array creation, mathematical operations, statistical analysis, and scientific computing. This project applies NumPy to real-world scenarios in **business analytics**, **education analytics**, and **engineering & scientific computing**.

---

## Table of Contents

- Project Overview
- [Exercise 1: Sales Performance Calculator](#exercise-1-sales-performance-calculator)
- [Exercise 2: Student Performance Analysis](#exercise-2-student-performance-analysis)
- [Exercise 3: Trigonometric Series and Convergence](#exercise-3-trigonometric-series-and-convergence)
- [Bonus Challenge: Stock Market Volatility Analysis](#bonus-challenge-stock-market-volatility-analysis)
- [NumPy Concepts Covered](#numpy-concepts-covered)
- [Project Structure](#project-structure)
- [System Requirements](#system-requirements)
- [Installation & Setup](#installation--setup)
- [Author](#author)

---

## Project Overview

This project demonstrates practical applications of **NumPy** — Python's core library for numerical computing — through three hands-on exercises and one bonus challenge.

Each exercise uses NumPy arrays and operators to solve real business, educational, and scientific problems:

| Exercise | Domain | Focus |
|----------|--------|-------|
| Exercise 1 | Business Analytics | Sales performance calculation |
| Exercise 2 | Education Analytics | Student performance and deviation |
| Exercise 3 | Engineering & Science | Trigonometric series convergence |
| Bonus | Finance | Stock market volatility analysis |

**Key Goal:** Master NumPy array operations by applying them to realistic scenarios.

---

## Exercise 1: Sales Performance Calculator

### Business Analytics

**Scenario:** A retail business tracks daily sales over one week. The goal is to calculate total sales, average daily sales, and simulate a 10% sales increment.

### 1. Create Dataset

```python
import numpy as np

# Daily sales figures (in Naira) for one week
daily_sales = np.array([125000, 150000, 175000, 140000, 190000, 210000, 160000])

print(f"""
Daily Sales: {daily_sales}
Type: {daily_sales.dtype}
Shape: {daily_sales.shape}
""")
```

Output:

```
Daily Sales: [125000 150000 175000 140000 190000 210000 160000]
Type: int64
Shape: (7,)
```

2. Calculate Total Sales

```python
total_sales = np.sum(daily_sales)
print(f"Total Sales: ₦{total_sales}")
```

Output: Total Sales: ₦1150000

3. Calculate Average Daily Sales

```python
average_sales = np.mean(daily_sales)
print(f"Average Sales: ₦{(average_sales):.2f}")
```

Output: Average Sales: ₦164285.71

4. Sales Adjustment (10% Increment)

```python
# Broadcasting: multiply every element by 0.1
sales_increment = daily_sales * 0.1

# Element-wise addition
adjusted_sales = daily_sales + sales_increment

print(f"Adjusted Sales: {adjusted_sales}")
```

Output:

```
Adjusted Sales: [137500. 165000. 192500. 154000. 209000. 231000. 176000.]
```

5. Compare Original vs Adjusted Sales

```python
sales_difference = adjusted_sales - daily_sales
print(f"Difference in Sales: {sales_difference}")
```

Output:

```
Difference in Sales: [12500. 15000. 17500. 14000. 19000. 21000. 16000.]
```

6. Mathematical Functions Summary

```python
average_sales = np.mean(daily_sales)
total_sales = np.sum(daily_sales)

print(f"Average Sales: ₦{average_sales:.2f}")
print(f"Total Sales: ₦{total_sales}")
```

Interpretation:

The average daily sales of ₦164,285.71 shows the business needs to hit approximately this amount daily to reach a weekly total of ₦1,150,000. Days below this average indicate underperformance that must be offset by higher-performing days.

---

Exercise 2: Student Performance Analysis

Education Analytics

Scenario: Analyze test scores for 10 students. Calculate mean score, individual deviations, squared deviations, variance, and standard deviation.

1. Create and Inspect Data

```python
import numpy as np

scores = np.array([62, 75, 81, 69, 88, 94, 73, 85, 77, 91])

print(f"""
Scores: {scores}
Type: {scores.dtype}
Shape: {scores.shape}
""")
```

Output:

```
Scores: [62 75 81 69 88 94 73 85 77 91]
Type: int64
Shape: (10,)
```

2. Calculate Mean Score

```python
mean_score = np.mean(scores)
print(f"Mean Score: {mean_score}")
```

Output: Mean Score: 79.5

3. Calculate Each Student's Deviation

```python
deviations = scores - mean_score
print(f"Student Deviations: {deviations}")
```

Output:

```
Student Deviations: [-17.5  -4.5   1.5 -10.5   8.5  14.5  -6.5   5.5  -2.5  11.5]
```

4. Interpret Deviations

· Positive deviation → Student scored above the mean
· Negative deviation → Student scored below the mean
· Near-zero deviation → Student scored close to the mean

5. Calculate Squared Deviations

```python
squared_deviation = deviations ** 2
print(f"Squared Deviation: {squared_deviation}")
```

Output:

```
Squared Deviation: [306.25  20.25   2.25 110.25  72.25 210.25  42.25  30.25   6.25 132.25]
```

6. Sum of Squared Deviations

```python
sum_squared_deviations = np.sum(squared_deviation)
print(f"Sum of Squared Deviations: {sum_squared_deviations}")
```

Output: Sum of Squared Deviations: 932.5

7. Calculate Standard Deviation

```python
# Sample variance (Bessel's correction: n - 1)
denominator = len(scores) - 1
variance = sum_squared_deviations / denominator

# Standard deviation = square root of variance
standard_deviation = np.sqrt(variance)

print(f"""
Variance: {variance:.2f}
Standard Deviation: {standard_deviation:.2f}
""")
```

Output:

```
Variance: 103.61
Standard Deviation: 10.18
```

Interpretation:

A standard deviation of 10.18 means most student scores fall within ±10.18 points of the mean (79.5). This suggests moderate spread — the class has a mix of high performers and students needing support.

---

Exercise 3: Trigonometric Series and Convergence

Engineering & Scientific Computing

Scenario: Investigate whether the infinite series Σ sin(kθ)/k converges as the number of terms increases, using θ = 30°.

1. Define Angle

```python
import numpy as np

theta = 30
theta_radians = np.radians(theta)
print(f"Angle in Radian: {theta_radians}")
```

Output: Angle in Radian: 0.5235987755982988

2. Create Sequence of Terms

```python
k = np.arange(1, 100, 1)
print(k)
```

Output: [1 2 3 4 5 ... 99]

3. Calculate Trigonometric Component

```python
sine_function_component = np.sin(k * theta_radians)
```

4. Build Series Terms

```python
sine_component_division = np.sin(k * theta_radians) / k
```

5. Calculate Sum (99 terms)

```python
sum_sine_component = np.sum(sine_component_division)
print(sum_sine_component)
```

Output: 1.3136674864204645

6. Increase Number of Terms

```python
# 999 terms
a = np.arange(1, 1000, 1)
sum_a = np.sum(np.sin(a * theta_radians) / a)
print(sum_a)  # 1.3094937000502784

# 9999 terms
b = np.arange(1, 10000, 1)
sum_b = np.sum(np.sin(b * theta_radians) / b)
print(sum_b)  # 1.3090469066682815
```

7. Convergence Investigation

Number of Terms Series Result
99 1.3136674864204645
999 1.3094937000502784
9999 1.3090469066682815

8. Explain Convergence

Convergence is the process whereby a series of terms approaches a fixed limiting value as the number of terms increases.

Observations from this experiment:

1. With fewer terms, the sum tends to be larger
2. As the number of terms increases, the sum decreases and approaches a stable value
3. Larger term numbers produce smaller contributions (each term is divided by a larger denominator)
4. When the sum settles near a limit, the series is said to converge

Conclusion: The series Σ sin(kθ)/k converges toward approximately 1.309 as more terms are added.

---

Bonus Challenge: Stock Market Volatility Analysis

Finance

Scenario: A financial analyst analyzes daily closing prices of a fictional stock over a 7-day trading week to determine average price, total value, daily fluctuations, and volatility.

1. Create the Dataset

```python
import numpy as np

# Daily closing prices
stock_prices = np.array([150.25, 152.10, 149.50, 153.75, 155.00, 151.25, 154.50])

# Days of the week
days = np.arange(1, 8)

print(f"Stock Data: {stock_prices}")
print(f"Days: {days}")
print(f"Shape: {stock_prices.shape}")
```

Output:

```
Stock Data: [150.25 152.1  149.5  153.75 155.   151.25 154.5 ]
Days: [1 2 3 4 5 6 7]
Shape: (7,)
```

2. Perform Calculations

```python
# Total value of stock
total_value = np.sum(stock_prices)

# Average price over the week
average_price = np.mean(stock_prices)

# Daily price changes (differences between consecutive days)
daily_changes = np.subtract(stock_prices[1:], stock_prices[:-1])

# Absolute changes (magnitude of fluctuation)
absolute_changes = np.abs(daily_changes)

# Volatility (standard deviation)
deviation = np.subtract(stock_prices, average_price)
squared_dev = np.multiply(deviation, deviation)
variance = np.mean(squared_dev)
volatility = np.sqrt(variance)
```

3. Output the Results

```
Total Value of Stock: $1066.35
Average Stock Price: $152.34
Daily Price Changes: [ 1.85 -2.6   4.25  1.25 -3.75  3.25]
Volatility (Std Dev): $1.98
```

4. Interpretation

· The stock closed at an average of $152.34 over the 7 days.
· The total sum of closing prices was $1,066.35.
· The daily changes show the stock fluctuated by an average of $2.82 per day.
· A volatility (standard deviation) of $1.98** indicates **moderate risk** — the price typically stays within **$150.36 to $154.31.

---

NumPy Concepts Covered

Concept Functions / Operators Used
Array Creation np.array(), np.arange()
Array Inspection .dtype, .shape
Aggregation np.sum(), np.mean()
Arithmetic Operators +, -, *, /, **
Broadcasting Array × scalar operations
Subtraction np.subtract()
Multiplication np.multiply()
Absolute Value np.abs()
Square Root np.sqrt()
Trigonometry np.sin(), np.radians()
Slicing array[1:], array[:-1]

---

Project Structure

```
numpy-operators-assessment/
│
├── ASSESSMENT_15_NUMPY_OPERATORS.ipynb    # Jupyter Notebook
├── README.md                              # Project documentation
└── screenshots/                           # (optional) output images
```

---

System Requirements

Requirement Specification
Language Python 3.6+
Library NumPy
Environment Jupyter Notebook / JupyterLab
Platform Windows, macOS, or Linux

---

Installation & Setup

Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/numpy-operators-assessment.git
cd numpy-operators-assessment
```

Step 2: Install NumPy

```bash
pip install numpy
```

Step 3: Launch Jupyter Notebook

```bash
jupyter notebook
```

Step 4: Open and Run

Open ASSESSMENT_15_NUMPY_OPERATORS.ipynb and run all cells.

---

Key Learning Outcomes

By completing this project, you will be able to:

· Create and inspect NumPy arrays
· Apply arithmetic operations to arrays (element-wise and scalar)
· Calculate statistical metrics (sum, mean, variance, standard deviation)
· Understand array slicing and broadcasting
· Use NumPy's mathematical functions (np.sin, np.sqrt, np.abs, etc.)
· Investigate series convergence using vectorized operations
· Apply NumPy to real-world business, education, and finance scenarios

---

Author

Mustapha Emmanuel Oladeji

📧 Email: [mustaphaemmanuelola@gmail.com]
🔗 LinkedIn: [https://linkedin.com/in/mustaphaemmanouelola]
🐙 GitHub: [https://github.com/Emmanouhl]

---

Acknowledgments

This project was completed as part of the Python Study Group – Lesson 15: NumPy Operators hands-on practice.

---

License

This project is open for educational and portfolio purposes.

---

Built with NumPy – Powering numerical computing in Python.

Happy Coding!


