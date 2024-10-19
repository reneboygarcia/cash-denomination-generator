# Mixed Integer Programming for Payroll Breakdown
This project aims to optimize the distribution of payroll amounts among different denominations of bills and coins. It utilizes mixed integer programming to find the most efficient way to break down a given amount into the available denominations, minimizing the number of bills and coins used.

## Key Features

* Supports various denominations of bills and coins
* Optimizes the distribution to minimize the number of bills and coins used
* Handles large and small denomination distributions separately for more efficient breakdowns
* Provides a detailed breakdown of the distribution for each amount

## Technical Details

* Utilizes the PuLP library for linear programming
* Implements a mixed integer programming approach to solve the optimization problem
* Supports dynamic addition or removal of denominations as needed
* Includes data visualization for easy analysis of the breakdowns

## Usage

1. Install the required libraries, including PuLP and pandas.
2. Load the payroll data into a pandas DataFrame.
3. Call the `create_denomination_breakdown` function with the payroll amounts, available denominations, and the list of denominations.
4. Analyze the resulting breakdowns for each amount.

## Example Output

The output includes a detailed breakdown of the distribution for each amount, including the number of each denomination used. For example:

| Amount | Denomination | Count |
| ------ | ------------ | ----- |
| 10058  | 1000         | 10    |
| 10058  | 500          | 2     |
| 10058  | 50           | 1     |
| 10058  | 8            | 1     |

This breakdown indicates that for an amount of 10058, the optimal distribution is 10 bills of 1000, 2 bills of 500, 1 bill of 50, and 1 coin of 8.

