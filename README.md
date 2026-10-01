# numpy-operators-assessment
Hands-on NumPy practice covering array creation, mathematical operators, statistical analysis, trigonometric series, and stock volatility analysis.
# NumPy Operators – Hands-On Practice

A comprehensive NumPy practice project covering array creation, mathematical operations, statistical analysis, and scientific computing. This project applies NumPy to real-world scenarios in **business analytics**, **education analytics**, and **engineering & scientific computing**.

---

## Table of Contents

- [Project Overview](#project-overview)
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
