# AI Audit Appendix (Assignment 04)

## Tool(s) Used
- GitHub Copilot
- 

## Task(s) Where AI Was Used
- Helped me complete to-do's and answer this.

## Prompt(s)

1. **Prompt:** "fix error notifications"
   - **Answer:** No errors were found in the file `assignment04_regression.py`.

2. **Prompt:** "was all of this done? 1. Read the CSV file. 2. If 'year' is missing but 'date' exists, extract year from date. 3. Rename ret12 to ret (annual return = 12-month cumulative return). 4. Merge year-end interest rates using _merge_annual_interest_rates. 5. Drop rows with missing ret, div12m_me, or prime_rate."
   - **Answer:** Yes, all the steps mentioned in the list have been implemented in the `load_reit_annual_data` function.

3. **Prompt:** "TODO: Drop rows with missing values in ret, div12m_me, prime_rate"
   - **Answer:** The TODO mentioned in the code has already been implemented with the line: `df = df.dropna(subset=["ret", "div12m_me", "prime_rate"])`.

4. **Prompt:** "TODO: Use statsmodels.formula.api.ols to estimate ret ~ x_var"
   - **Answer:** Implemented the regression estimation using statsmodels' `ols` function to fit the model and return it.

5. **Prompt:** "TODO: Write str(model.summary()) to the output file"
   - **Answer:** Implemented the functionality to write the regression model summary to the specified output file.

6. **Prompt:** "# TODO: Create fig, ax with plt.subplots(figsize=(10, 6)) # TODO: Filter to rows with valid x_var and ret # TODO: Scatter plot # TODO: Overlay regression line (use model.params['Intercept'] and model.params[x_var]) # TODO: Set axis limits to zoom on central data (e.g., percentiles 2–98) # TODO: Add title (include R²), xlabel, ylabel=\"Annual Return\", legend # TODO: Save with plt.savefig(output_path, dpi=300, bbox_inches='tight')"
   - **Answer:** Implemented the scatter plot with regression line, axis limits, title, labels, and saving functionality as described in the TODO.

7. **Prompt:** "Print intercept (β₀), slope (β₁), standard errors, t-stats, p-values # TODO: Print R², Adj R², N # TODO: Print whether slope is positive/negative and significant at 5%"
   - **Answer:** Added code to print regression coefficients, standard errors, t-stats, p-values, R², adjusted R², and the number of observations. Also included a check for slope significance at the 5% level.

## Output Summary
- Put above in a question answer format. 

## Verification & Modifications (Disclose • Verify • Critique)
- **Verify:** Ran script and checked over it.
- **Critique:** Little things but overall not much.
- **Modify:** Not many things this time.
## If No AI Tools Used
Write: "No AI tools were used for this assignment."
