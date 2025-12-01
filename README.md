---
title: 'Assignment 6 Part 2: Multivariable Linear Regression'
author: 'Mr. Berg, Lane Tech College Prep'
geometry: margin=1in
---

# Setup Instructions - IMPORTANT!

**Remember:** Open VS Code through Anaconda Navigator!

1. **Open Anaconda Navigator** on your computer
2. **Wait for it to fully load**
3. **Click on VS Code** from within Anaconda Navigator
4. **Open this assignment folder** in VS Code

---

# Assignment Overview

In Part 1, you learned linear regression with **one feature** (one X variable predicting Y).

In Part 2, you'll learn **multivariable linear regression** - using **multiple features** to make better predictions!

## Real-World Example

**Part 1:** Predict test score from hours studied
**Part 2:** Predict test score from hours studied, hours slept, AND practice tests taken

More features = potentially better predictions!

---

# Part 1: Unplugged Activity - "Build Your Own Equation"

Before we code, we'll manually explore multivariable regression using paper and pencils!

## The Dataset: Used Car Prices

You and your partner will work with data about used cars:
- **Price** (what we're predicting - the target)
- **Mileage** (miles driven)
- **Age** (years old)
- **Brand** (encoded as 0=Toyota, 1=Honda, 2=Ford)

## Your Tasks (in groups of 2-4):

### Step 1: Explore Individual Features (15 minutes)
Mr. Berg will give you printed datasets. For each feature:
1. Create a scatter plot (by hand!) of that feature vs Price
2. Describe the relationship: positive? negative? strong? weak?
3. Rank the features from "most important" to "least important"

### Step 2: Estimate Coefficients (15 minutes)
Try to create your own equation:
```
Price = (??? × Mileage) + (??? × Age) + (??? × Brand) + ???
```

Work with your group to:
1. Estimate reasonable numbers for each coefficient
2. Explain your reasoning (why did you choose those numbers?)
3. Test your equation on 2-3 cars from the "holdout set"

### Step 3: Compare Results (10 minutes)
- Each group shares their equation
- We calculate error for each group's predictions
- Discuss: Why are some equations better than others?

## Key Questions We'll Explore:

1. **Which features matter most?**
2. **Can you predict accurately with just pen and paper?**
3. **How do negative coefficients work?** (older cars = lower price)
4. **What makes a "good" coefficient?**

---

# Part 2: Coding Multivariable Regression

After the unplugged activity, you'll see how Python does this automatically!

## In-Class Example: Car Prices (Revisited)

We'll use `car_price_example.py` to:
- Load the same car data from the unplugged activity
- Visualize multiple features
- Train a multivariable linear regression model
- Compare it to your manual equation!
- Understand feature importance

---

# Part 3: Your Assignment - House Prices

You'll predict house prices using **multiple features**:
- Square footage
- Number of bedrooms
- Number of bathrooms
- Age of house

## Your Tasks

Complete the following in `a6_part2.py`:

1. **`load_and_explore_data(filename)`**
   - Load the housing dataset
   - Print summary statistics for ALL features
   - Return the dataframe

2. **`visualize_features(data)`**
   - Create 4 scatter plots (one for each feature vs Price)
   - Save as a single figure with subplots
   - Identify which features seem most important

3. **`prepare_features(data)`**
   - Separate features (X) from target (y)
   - Handle multiple columns properly
   - Return X and y

4. **`split_data(X, y)`**
   - Split into training (80%) and testing (20%) sets
   - Return X_train, X_test, y_train, y_test

5. **`train_model(X_train, y_train, feature_names)`**
   - Train a LinearRegression model with multiple features
   - Print coefficients for EACH feature
   - Return the trained model

6. **`evaluate_model(model, X_test, y_test, feature_names)`**
   - Make predictions
   - Calculate R² and RMSE
   - Print feature importance (which features matter most?)
   - Return predictions

7. **`compare_predictions(y_test, predictions, num_examples=5)`**
   - Show side-by-side comparison of actual vs predicted
   - Print the first 5 test examples
   - Calculate percentage error for each

8. **`make_prediction(model, sqft, bedrooms, bathrooms, age)`**
   - Make a prediction for a new house
   - Print the specs and predicted price

---

# Understanding Multiple Coefficients

**Single variable equation:**
```
Price = 7.2 × Hours + (-255)
```

**Multiple variable equation:**
```
Price = 50 × SquareFeet + 10000 × Bedrooms + 8000 × Bathrooms + (-500) × Age + 20000
```

**Interpreting coefficients:**
- **50:** Each additional square foot adds $50 to price
- **10000:** Each additional bedroom adds $10,000 to price
- **-500:** Each year older reduces price by $500
- **20000:** Base price (intercept)

---

# Grading

See `a6_part2_rubric.md` for detailed grading criteria.

**Total: 10 points**
- Code Functionality: 5 points
- Visualizations: 2 points  
- Writeup: 3 points

**Note:** The unplugged activity will be graded separately.

---

# Key Differences from Part 1

| Part 1 | Part 2 |
|--------|--------|
| One feature (X) | Multiple features (X₁, X₂, X₃...) |
| Simple visualization | Multiple scatter plots |
| One coefficient | Multiple coefficients |
| Direct interpretation | Compare feature importance |

---

# Helpful Resources

- [Multiple Linear Regression](https://scikit-learn.org/stable/modules/linear_model.html#ordinary-least-squares)
- [StandardScaler Documentation](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html)
- [A Practical Guide to Linear Regression](https://towardsdatascience.com/a-practical-guide-to-linear-regression-3b1cb9e501a6/)


