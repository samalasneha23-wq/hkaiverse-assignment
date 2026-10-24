# AI Use and Verification Log

## 1. Purpose

This log records how AI assistance was used to prepare five practical exercises for the curriculum audit. Each entry describes the prompt, the type of output produced, and how the result should be verified.

AI-generated content was treated as a starting point. Expected results and verification methods are documented separately from actual execution results.

## 2. AI Tool Information

| Field | Details |
|---|---|
| AI tool | ChatGPT |
| Model | GPT-6 |
| Date of preparation | 24 October 2026 |
| Purpose | Generate example code, SQL queries, explanations and test cases for educational exercises |
| Verification approach | Code inspection, manual calculation, expected-output comparison and execution checks where applicable |

## 3. Exercise Records

### Exercise 1: Computer Programming — Python Data Validation

**Prompt used:**

"Write a simple Python function that accepts a list of values, separates non-negative numeric values from invalid entries, and tests normal input, negative numbers, strings and an empty list. Explain the code."

**AI-assisted output:**

A Python function using a loop, conditional statements and type checking to separate valid non-negative numbers from invalid entries.

**Expected result:**

- Normal input `[10, 0, 4.5, 7]` should return all four values as valid.
- Input `[5, -3, "hello", 2]` should identify `-3` and `"hello"` as invalid.
- An empty list should return empty valid and invalid lists.

**Verification method:** Check the function's conditions and compare its output with the expected results for all three test cases.

**Verification status:** Expected behaviour documented; execution result to be confirmed by running the code.

### Exercise 2: Database Management Systems — SQL Aggregation

**Prompt used:**

"Create a small SQL example with a Customers table and an Orders table. Write a query to calculate the total order amount for each customer using a JOIN, GROUP BY and SUM."

**AI-assisted output:**

An SQL query joining customer and order records and grouping orders by customer to calculate total spending.

**Expected result:**

- Asha: 800
- Ravi: 700
- Meena: 200

**Verification method:** Calculate each customer's total manually and compare it with the SQL query results. Check that the join uses `customer_id` and that the grouping includes the customer identifier and name.

**Verification status:** Expected totals manually calculated; execution in a database environment to be confirmed.

### Exercise 3: Data Analytics — Missing-Value Analysis

**Prompt used:**

"Write a Python example using pandas to identify missing values in a small dataset and calculate the average of a numeric column while ignoring missing values. Explain the result."

**AI-assisted output:**

A pandas example using `isnull().sum()` to count missing entries and `mean()` to calculate the average of available marks.

**Expected result:**

- The `marks` column contains one missing value.
- The average of 80, 90 and 70 is 80.
- The missing value is excluded from the average calculation.

**Verification method:** Count the missing entries and manually calculate `(80 + 90 + 70) / 3`. Compare the result with the pandas output.

**Verification status:** Expected result manually calculated; execution result to be confirmed by running the code.

### Exercise 4: Machine Learning — Regression and Evaluation

**Prompt used:**

"Provide a simple Python example using scikit-learn to split a small numerical dataset into training and testing sets, fit a linear regression model, make predictions, and calculate mean absolute error."

**AI-assisted output:**

A linear regression example using `train_test_split`, `LinearRegression` and `mean_absolute_error`.

**Expected result:**

The sample data follows the relationship \(y = 2x\). The model should learn a relationship close to this pattern and produce predictions close to the actual test values.

**Verification method:** Check that the model is fitted on the training data, predictions are made on the test data, and mean absolute error is calculated from the actual and predicted values.

**Verification status:** Expected behaviour documented; the actual predictions and error value must be confirmed by running the code.

### Exercise 5: Artificial Intelligence — Rule-Based Classification

**Prompt used:**

"Write a beginner-friendly Python program that classifies a sentence as positive, negative or neutral using lists of positive and negative words. Include example sentences and explain the limitations."

**AI-assisted output:**

A rule-based classifier that counts matching positive and negative words and assigns a category based on the comparison.

**Expected result:**

- "The service was excellent" → Positive
- "The experience was bad" → Negative
- "The class starts today" → Neutral

**Verification method:** Compare each sentence with the word lists and confirm that the classification follows the stated rules.

**Verification status:** Expected classifications checked against the program's rules; execution result to be confirmed by running the code.

## 4. Overall Verification Summary

| Exercise | Verification performed in preparation | Remaining check |
|---|---|---|
| Python data validation | Expected cases and conditions reviewed | Run code and confirm output |
| SQL aggregation | Totals calculated manually | Execute query in a database |
| Missing-value analysis | Missing-value count and mean calculated manually | Run code and confirm output |
| Regression | Model workflow and evaluation method reviewed | Run code and record predictions and error |
| Rule-based classification | Example sentences checked against word lists | Run code and confirm output |

## 5. Limitations and Responsible Use

1. AI-generated code may contain errors and must be checked before use.
2. Expected output is not the same as an observed execution result.
3. The examples use small synthetic datasets and demonstrate basic concepts rather than production performance.
4. SQL results depend on the tables and records available in the database.
5. The rule-based classifier cannot reliably understand context, sarcasm or negation.
6. Actual execution results should be recorded only after the relevant code or query has been run and checked.

## 6. Conclusion

AI assistance helped prepare practical examples across programming, database management, data analytics, machine learning and artificial intelligence. The exercises connect theoretical concepts with small, testable examples. Recording expected behaviour and verification methods makes the use of AI more transparent and encourages independent checking rather than relying on generated answers without review.
