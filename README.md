# Cash Flow Optimizer: Efficient Payroll Denomination Breakdown

![Cash Flow Optimizer Banner](images\banner_2.jpg)

## Introduction

The Cash Flow Optimizer is a Python-based tool that offers a formal, algorithmic approach to a common payroll management task: distributing cash denominations for worker wages. Developed in 2023 as a response to a practical challenge, this tool provides a structured method for breaking down salary amounts into available cash denominations.

While the problem of cash distribution in payroll is not new, this tool aims to bring a more systematic approach to the process. It's important to note that while we use the term "optimizer," the tool's primary value lies in providing a consistent, reproducible method for cash breakdown, rather than claiming to revolutionize the process.

This solution is particularly useful for payroll managers or small business owners who are looking for a reliable way to plan their cash distribution, ensuring they have sufficient denominations on hand and potentially reducing the time spent on manual calculations.

## Problem Statement

When distributing wages in cash, payroll managers often face the challenge of:

1. Ensuring they have sufficient denominations to cover all payments
2. Minimizing the number of bills and coins used
3. Distributing larger denominations evenly to avoid running out

This tool addresses these challenges using advanced optimization techniques.

## Key Features

1. **Multi-Denomination Support**: Handles various bill and coin denominations simultaneously.
2. **Optimization Algorithm**: Utilizes Mixed Integer Programming to minimize the total number of bills and coins while meeting exact payment amounts.
3. **Large Denomination Distribution**: Implements a smart algorithm to distribute larger denominations more evenly across payments.
4. **Flexible Configuration**: Easily adjustable for different currency systems and available denomination quantities.
5. **Data Visualization**: Provides clear, tabular output of cash breakdowns for each payment.

## Technical Details

### Technologies Used

- **Python**: Core programming language
- **PuLP**: Linear programming library for optimization
- **pandas**: Data manipulation and analysis library

### Key Components

1. `distribute_large_denominations()`: Handles the even distribution of larger bills.
2. `optimize_breakdown()`: Uses linear programming to optimize smaller denominations.
3. `create_denomination_breakdown()`: Orchestrates the overall optimization process.
4. `create_df()`: Generates a pandas DataFrame with the final results.

## Installation

1. Ensure you have Python 3.6+ installed.
2. Install required libraries:

   ```bash
   pip install pulp pandas
   ```

## Usage

1. Prepare your payroll data in a pandas DataFrame (`df_salary`). You can use the `payroll_list_sample.csv` to get started.

2. Define your available denominations:

   ```python
   total_denominations = {
       1000: 284,
       500: 98,
       100: 130,
       50: 50,
       20: 105,
       10: 18,
       5: 50,
       1: 100,
   }
   ```

3. Run the optimization:

   ```python
   amounts = df_salary["net_salary_int"].tolist()
   names = df_salary["name"].tolist()
   denominations = sorted(total_denominations.keys(), reverse=True)

   denomination_breakdowns = create_denomination_breakdown(
       amounts, total_denominations, denominations
   )

   df_denom = create_df(denomination_breakdowns, amounts, names, denominations)
   ```

4. The resulting `df_denom` DataFrame contains the optimized breakdown for each amount.

## Example Output

| name | net_salary_int | P1000x | P500x | P100x | P50x | P20x | P10x | P5x | P1x | total_amount | variance |
|------|----------------|--------|-------|-------|------|------|------|-----|-----|--------------|----------|
| Pablo | 10058          | 10     | 0     | 0     | 1    | 0    | 0    | 1   | 8   | 10058        | 0        |
| Esteban | 5432           | 5      | 0     | 4     | 0    | 1    | 1    | 0   | 2   | 5432         | 0        |

This output shows how the amounts 10,058 and 5,432 are broken down into various denominations, ensuring exact payment with minimal bills and coins.

## Customization

- Modify the `large_denominations` list in `distribute_large_denominations()` to adjust which denominations are considered "large".
- Update the `total_denominations` dictionary to reflect your available quantities of each denomination.

## Limitations and Considerations

- The script assumes all input amounts are in the same currency.
- Ensure your total available denominations are sufficient to cover all payments.
- For very large datasets, optimization time may increase.
