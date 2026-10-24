# AI-Assisted Practical Exercises Across Five Subjects

## 1. Introduction

This document presents five small AI-assisted practical exercises across different subjects in the B.Tech Artificial Intelligence and Data Science curriculum. Each exercise connects a subject concept with a practical application.

The exercises use AI assistance to generate or explain an initial solution. The suggested outputs and verification checks are included so that the results can be checked against expected behaviour. An expected result is not treated as a personally observed result unless it has actually been tested.

## Exercise 1: Computer Programming — Python Data Validation

### Objective

To develop a Python function that separates valid non-negative numeric values from invalid entries.

### Prompt Used

"Write a simple Python function that accepts a list of values, separates non-negative numeric values from invalid entries, and tests normal input, negative numbers, strings and an empty list. Explain the code."

### Python Code

```python
def validate_values(values):
    valid_values = []
    invalid_entries = []

    for value in values:
        if (isinstance(value, (int, float))
                and not isinstance(value, bool)
                and value >= 0):
            valid_values.append(value)
        else:
            invalid_entries.append(value)

    return valid_values, invalid_entries


test_cases = [
    [10, 0, 4.5, 7],
    [5, -3, "hello", 2],
    []
]

for test in test_cases:
    valid, invalid = validate_values(test)
    print("Input:", test)
    print("Valid values:", valid)
    print("Invalid entries:", invalid)
    print()
```

### Expected Output

```text
Input: [10, 0, 4.5, 7]
Valid values: [10, 0, 4.5, 7]
Invalid entries: []

Input: [5, -3, 'hello', 2]
Valid values: [5, 2]
Invalid entries: [-3, 'hello']

Input: []
Valid values: []
Invalid entries: []
```

### Verification

Check that zero and positive numbers are accepted, negative numbers and strings are rejected, and an empty list returns two empty lists. The output should match the expected results above.

### Learning Outcome

This exercise demonstrates functions, lists, loops, conditional statements, data-type checking and basic testing.

---

## Exercise 2: Database Management Systems — SQL Aggregation

### Objective

To calculate the total amount spent by each customer using SQL aggregation.

### Prompt Used

"Create a small SQL example with a Customers table and an Orders table. Write a query to calculate the total order amount for each customer using a JOIN, GROUP BY and SUM."

### Example Tables

**Customers**

| customer_id | customer_name |
|---:|---|
| 1 | Asha |
| 2 | Ravi |
| 3 | Meena |

**Orders**

| order_id | customer_id | amount |
|---:|---:|---:|
| 101 | 1 | 500 |
| 102 | 1 | 300 |
| 103 | 2 | 700 |
| 104 | 3 | 200 |

### SQL Query

```sql
SELECT
    c.customer_id,
    c.customer_name,
    SUM(o.amount) AS total_amount
FROM Customers c
JOIN Orders o
    ON c.customer_id = o.customer_id
GROUP BY c.customer_id, c.customer_name
ORDER BY c.customer_id;
```

### Expected Output

| customer_id | customer_name | total_amount |
|---:|---|---:|
| 1 | Asha | 800 |
| 2 | Ravi | 700 |
| 3 | Meena | 200 |

### Verification

Add the order amounts manually for each customer and compare them with the query results. Asha's total should be 500 + 300 = 800. Ravi's total should be 700, and Meena's total should be 200.

### Learning Outcome

This exercise demonstrates relational joins, aggregate functions, grouping and sorting. It also shows how SQL can summarise transaction data.

---

## Exercise 3: Data Analytics — Missing-Value Analysis Using Python

### Objective

To identify missing values in a dataset and calculate the average of the available numeric values.

### Prompt Used

"Write a Python example using pandas to identify missing values in a small dataset and calculate the average of a numeric column while ignoring missing values. Explain the result."

### Python Code

```python
import pandas as pd

data = {
    "student": ["Asha", "Ravi", "Meena", "Arun"],
    "marks": [80, 90, None, 70]
}

df = pd.DataFrame(data)

print("Original dataset:")
print(df)

print("\nMissing values:")
print(df.isnull().sum())

average_marks = df["marks"].mean()
print("\nAverage marks:", average_marks)
```

### Expected Output

```text
Original dataset:
  student  marks
0    Asha   80.0
1    Ravi   90.0
2   Meena    NaN
3    Arun   70.0

Missing values:
student    0
marks      1
dtype: int64

Average marks: 80.0
```

### Verification

There should be one missing value in the `marks` column. The average should be calculated from 80, 90 and 70:

Average = (80 + 90 + 70) / 3 = 80.

The missing value is excluded from the mean calculation; it is not replaced with zero.

### Learning Outcome

This exercise demonstrates data-frame creation, missing-value detection, basic data cleaning and descriptive statistics. It highlights why missing values must be handled carefully before analysis.

---

## Exercise 4: Machine Learning — Train-Test Split and Model Evaluation

### Objective

To understand how a dataset is divided into training and testing sets and how a simple regression model is evaluated.

### Prompt Used

"Provide a simple Python example using scikit-learn to split a small numerical dataset into training and testing sets, fit a linear regression model, make predictions, and calculate mean absolute error."

### Python Code

```python
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_absolute_error

X = [[1], [2], [3], [4], [5], [6]]
y = [2, 4, 6, 8, 10, 12]

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.33, random_state=42
)

model = LinearRegression()
model.fit(X_train, y_train)

predictions = model.predict(X_test)
mae = mean_absolute_error(y_test, predictions)

print("Actual values:", y_test)
print("Predicted values:", predictions)
print("Mean Absolute Error:", mae)
```

### Expected Result

The dataset follows the relationship \(y = 2x\). A linear regression model should learn a slope close to 2 and make predictions close to the actual test values. The mean absolute error should be close to zero for this dataset.

The exact printed values depend on the selected training and testing rows and the model's fitted parameters. The code should be run to record the actual output.

### Verification

Check that the training and testing sets are separate, the model is fitted only on the training set, and predictions are evaluated against the test labels. Confirm that the mean absolute error is calculated from the differences between actual and predicted values.

### Learning Outcome

This exercise demonstrates supervised learning, regression, data splitting, prediction and model evaluation. It also reinforces the importance of evaluating a model on data not used to fit it.

---

## Exercise 5: Artificial Intelligence — Rule-Based Classification

### Objective

To create a basic rule-based classifier that categorises a text message as positive, negative or neutral using simple word matching.

### Prompt Used

"Write a beginner-friendly Python program that classifies a sentence as positive, negative or neutral using lists of positive and negative words. Include example sentences and explain the limitations."

### Python Code

```python
positive_words = ["good", "great", "excellent", "happy"]
negative_words = ["bad", "poor", "terrible", "sad"]


def classify_sentiment(sentence):
    words = sentence.lower().split()

    positive_count = sum(
        1 for word in words if word.strip(".,!?") in positive_words
    )
    negative_count = sum(
        1 for word in words if word.strip(".,!?") in negative_words
    )

    if positive_count > negative_count:
        return "Positive"
    elif negative_count > positive_count:
        return "Negative"
    else:
        return "Neutral"


examples = [
    "The service was excellent",
    "The experience was bad",
    "The class starts today"
]

for sentence in examples:
    print(sentence, "->", classify_sentiment(sentence))
```

### Expected Output

```text
The service was excellent -> Positive
The experience was bad -> Negative
The class starts today -> Neutral
```

### Verification

Check that a sentence containing a positive word is classified as positive, a sentence containing a negative word is classified as negative, and a sentence containing neither is classified as neutral.

### Limitations

This is a simple rule-based demonstration, not a trained machine-learning model. It may fail to understand negation, sarcasm, context, spelling variations and words that have different meanings in different situations.

### Learning Outcome

This exercise demonstrates text preprocessing, simple classification rules, conditional logic and the limitations of basic AI systems.

---

## 2. Overall Findings

The five exercises demonstrate how AI assistance can support learning across programming, databases, data analytics, machine learning and artificial intelligence.

| Subject | Main concept | Verification approach |
|---|---|---|
| Computer Programming | Python data validation | Check valid and invalid lists |
| Database Management Systems | JOIN and aggregation | Manually verify totals |
| Data Analytics | Missing values and mean | Count missing entries and calculate the average |
| Machine Learning | Regression and evaluation | Inspect predictions and mean absolute error |
| Artificial Intelligence | Rule-based text classification | Compare classifications with the rules |

## 3. Responsible Use of AI

AI-generated code and explanations should be treated as starting points, not automatically correct answers. Each exercise should be checked against its stated objective and expected behaviour. Actual execution results, tool details and verification outcomes should be recorded separately in `ai_use_log.md` after completing the relevant checks.

These examples are educational demonstrations using small synthetic datasets. They are not evidence of production-system performance or of improvements to the university's actual processes.
