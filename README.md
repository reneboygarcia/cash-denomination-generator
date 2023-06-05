# Knapsack Unbounded Algorithm

This code defines a function to perform a Knapsack Unbounded Algorithm and provides a helper function to create a DataFrame. The algorithm calculates the denomination breakdowns for a given set of amounts and available denominations.

### Situation
When distributing the pay of your workers, you encountered challenges with the manual calculation of denomination breakdowns. This process was time-consuming and prone to errors, leading to delays and potential discrepancies in pay distribution. You needed a solution to streamline the process and ensure an even distribution of denominations.

### Task
The goal was to develop a code solution that could generate denomination breakdowns for the pay of your workers. This solution would enable faster and more efficient pay distribution, while ensuring an even distribution of denominations.

### Action
To accomplish this, you took the following actions:

Developed the create_denomination_breakdown function:

1. This function accepts the amounts, total_denominations, and denominations as input parameters.
Implemented the unbounded knapsack algorithm (unbounded_knapsack) within this function.

2. Utilized the algorithm to calculate the minimum number of denominations required to make up each amount, considering the available denominations and their counts.
Constructed breakdown dictionaries for each amount, representing the denomination breakdown.
Created the create_df function:

3. This function was designed to create a DataFrame (df_denom) from the denomination breakdowns, amounts, names, and denominations.
Utilized the breakdown dictionaries generated in the create_denomination_breakdown function to populate the DataFrame with relevant information, such as names, net salary amounts, denomination counts, and variances.
Utilized the code with relevant parameters:

4. Incorporated the code within the context of your pay distribution process.
Provided the amounts, names, total_denominations, and denominations specific to your workers and available denominations.
5. Executed the code to generate the denomination breakdowns and create the DataFrame.

### Result
As a result of implementing this code solution, the following outcomes were achieved:

1. Faster pay distribution: The code streamlined the process by automatically generating denomination breakdowns, eliminating the need for manual calculations. This led to significant time savings and expedited the pay distribution process.

2. Even distribution of denominations: By using the unbounded knapsack algorithm, the code ensured an even distribution of denominations across the workers' pay. This promoted fairness and eliminated potential discrepancies, resulting in a more equitable pay distribution.

### Conclusion

The code solution provided an effective way to generate denomination breakdowns for the pay of your workers. By incorporating this solution into your pay distribution process, you experienced improved efficiency, reduced errors, and enhanced fairness in the distribution of pay.




