# AI-Assisted Learning Exercises

## 1. Objective

This document presents five AI-assisted exercises related to the B.Tech Computer Science and Engineering (Artificial Intelligence and Data Science) curriculum.

The exercises demonstrate how AI tools can support learning, practical problem-solving, code review and technical understanding. AI-generated suggestions are treated as starting points and are checked using relevant concepts, calculations, documentation or test cases.

## 2. AI Usage Record

For each exercise, record the AI tool and model actually used, the date of the interaction, the prompt, a concise summary of the output, and the verification performed.

AI tool: ChatGPT  
Model: Record the model displayed by the tool when performing the exercise.  
Date: Record the actual date of the interaction.

## Exercise 1: Computer Programming — Python Data Validation

### Objective

Use AI to generate a Python function that checks whether a list contains valid, non-negative numeric values and identifies invalid entries.

### Prompt

"Write a simple Python function that accepts a list of values, identifies non-negative numeric values, and reports invalid entries. Explain the code and include test cases for normal input, negative numbers, strings and an empty list."

### Expected AI output

The AI should suggest a function that checks the input values, distinguishes valid values from invalid ones, and explains the handling of edge cases.

### Verification method

- Run the generated code in Python.
- Test a list containing valid non-negative numbers.
- Test negative values and strings.
- Test an empty list.
- Check whether the output matches the expected results.

### Learning outcome

The exercise demonstrates input validation, conditional logic, functions and testing.

**Execution result:** Record the actual test results after running the code.

---

## Exercise 2: Database Management Systems — SQL Aggregation

### Objective

Use AI to help write an SQL query that calculates total sales by product category.

### Prompt

"Consider an orders table containing order_id, category and sales_amount. Write an SQL query to calculate total sales for each category, sort the results from highest to lowest, and explain how GROUP BY and SUM work."

### Expected AI output

The AI should suggest a query using `GROUP BY`, `SUM()` and `ORDER BY`.

Example query:

```sql
SELECT
    category,
    SUM(sales_amount) AS total_sales
FROM orders
GROUP BY category
ORDER BY total_sales DESC;
```

### Verification method

- Create a small test table with known sales values.
- Execute the query in MySQL.
- Calculate the expected category totals manually.
- Compare the SQL output with the manual calculations.

### Learning outcome

The exercise demonstrates SQL aggregation, grouping, sorting and result verification.

**Execution result:** Record the actual query output and whether it matches the manual calculation.

---

## Exercise 3: Data Science — Data Cleaning

### Objective

Use AI to develop a basic approach for identifying missing values and duplicate records in a dataset.

### Prompt

"Explain how to inspect a CSV dataset for missing values and duplicate rows using Python and pandas. Provide code to report these issues before modifying the data. Explain why missing values should not automatically be replaced with zero."

### Expected AI output

The AI should suggest using pandas to inspect the dataset, count missing values and identify duplicates before deciding how to handle them.

Example code:

```python
import pandas as pd

df = pd.read_csv("data.csv")

print("Missing values:")
print(df.isnull().sum())

print("Duplicate rows:")
print(df.duplicated().sum())
```

### Verification method

- Create or use a small dataset with known missing values and duplicate rows.
- Run the code and compare the counts with the dataset.
- Inspect the affected rows.
- Confirm that missing-value treatment depends on the meaning of each column.

### Learning outcome

The exercise demonstrates data-quality assessment, exploratory data analysis and evidence-based cleaning decisions.

**Execution result:** Record the observed missing-value and duplicate counts from the test dataset.

---

## Exercise 4: Machine Learning — Model Evaluation

### Objective

Use AI to understand why machine-learning models should be evaluated on data that was not used for training.

### Prompt

"Explain the difference between training accuracy and test accuracy in a classification problem. Describe how overfitting can occur and give an example of how a student can evaluate a model using a train-test split. Explain why accuracy alone may be insufficient for imbalanced datasets."

### Expected AI output

The AI should explain the purpose of separating training and test data, describe overfitting, and discuss evaluation measures such as precision, recall and F1-score.

### Verification method

- Compare the explanation with the concepts covered in the Machine Learning syllabus or a trusted machine-learning reference.
- Use a small classification example.
- Check that training and test data are separated correctly.
- Calculate or inspect evaluation measures using the chosen dataset.
- Confirm that the interpretation matches the observed results.

### Learning outcome

The exercise demonstrates model validation, overfitting awareness and appropriate evaluation.

**Execution result:** Record the dataset, evaluation measures and observed results after completing the exercise.

---

## Exercise 5: Generative AI — Retrieval-Augmented Generation

### Objective

Use AI to understand how a document-question-answering application can reduce unsupported answers by grounding responses in retrieved information.

### Prompt

"Explain a simple retrieval-augmented generation (RAG) workflow for answering questions from a collection of documents. Describe document preparation, retrieval, context selection, answer generation and evaluation. Include test cases for an answerable question, a question with missing information and an unrelated question."

### Expected AI output

The AI should describe a workflow in which relevant document passages are retrieved and supplied to a language model as context. It should also explain that retrieval does not guarantee correctness and that answers must be evaluated.

### Verification method

- Create a small collection of documents containing known facts.
- Test a question whose answer is explicitly present in the documents.
- Test a question whose answer is absent.
- Test an unrelated question.
- Compare the generated answers with the source documents.
- Record unsupported statements, retrieval failures and cases where the system should acknowledge insufficient information.

### Learning outcome

The exercise demonstrates retrieval-based AI, source-grounded answers, testing and responsible evaluation of language-model outputs.

**Execution result:** Record the actual outputs and verification findings after running the tests.

---

## 3. AI Use and Human Verification

AI was used as an assistant for generating explanations, suggesting code and structuring technical exercises. The generated material should not be treated as automatically correct.

Verification involves running code where applicable, checking calculations, examining source data, comparing explanations with course concepts and testing edge cases.

The final record should identify errors or limitations found during verification and explain how they were addressed. AI-generated content must not be presented as experimentally validated unless the relevant tests were actually performed.

## 4. Conclusion

These exercises demonstrate how AI assistance can support learning across programming, databases, data science, machine learning and Generative AI.

The approach combines AI-generated suggestions with independent verification. This encourages critical thinking, reproducible work and responsible use of AI tools in academic and professional settings.
