# Assignment 04 Interpretation Memo

**Student Name:** [Ashley Seale]
**Date:** [2/13/2026]
**Assignment:** REIT Annual Returns and Predictors (Simple Linear Regression)

---

## 1. Regression Overview

You estimated **three** simple OLS regressions of REIT *annual* returns on different predictors:

| Model | Y Variable | X Variable | Interpretation Focus |
|-------|------------|------------|----------------------|
| 1 | ret (annual) | div12m_me | Dividend yield |
| 2 | ret (annual) | prime_rate | Interest rate sensitivity |
| 3 | ret (annual) | ffo_at_reit | FFO to assets (fundamental performance) |

For each model, summarize the key results in the sections below.

---

## 2. Coefficient Comparison (All Three Regressions)

**Model 1: ret ~ div12m_me**
- Intercept (β₀): 0.1082 (SE: 0.006, p-value: 0.000)
- Slope (β₁): -0.0687 (SE: 0.032, p-value: 0.035)
- R²: 0.002 | N: 2527

**Model 2: ret ~ prime_rate**
- Intercept (β₀): 0.1998 (SE: 0.016, p-value: 0.000)
- Slope (β₁): -0.0194 (SE: 0.003, p-value: 0.000)
- R²: 0.016 | N: 2527

**Model 3: ret ~ ffo_at_reit**
- Intercept (β₀): 0.0973 (SE: 0.009, p-value: 0.000)
- Slope (β₁): 0.5770 (SE: 0.567, p-value: 0.309)
- R²: 0.000 | N: 2518

*Note: Model 3 may have fewer observations if ffo_at_reit has missing values; statsmodels drops those rows.*

---

## 3. Slope Interpretation (Economic Units)

**Dividend Yield (div12m_me):**
- A 1 percentage point increase in dividend yield (12-month dividends / market equity) is associated with a -0.0687 change in annual return.
- Higher dividend yield is associated with lower returns, which may suggest that higher yields are a signal of risk or distress.

**Prime Loan Rate (prime_rate):**
- A 1 percentage point increase in the year-end prime rate is associated with a -0.0194 change in annual return.
- The evidence suggests REIT returns are negatively sensitive to interest rates, as higher rates increase borrowing costs.

**FFO to Assets (ffo_at_reit):**
- A 1 unit increase in FFO/Assets (fundamental performance) is associated with a 0.5770 change in annual return.
- The relationship is not statistically significant, so we cannot conclude that more profitable REITs earn higher returns.

---

## 4. Statistical Significance

For each slope, at the 5% significance level:
- **div12m_me:** Significant — Dividend yield has a statistically significant negative relationship with returns.
- **prime_rate:** Significant — Prime rate has a statistically significant negative relationship with returns.
- **ffo_at_reit:** Not significant — The relationship between FFO/Assets and returns is not statistically significant.

**Which predictor has the strongest statistical evidence of a relationship with annual returns?** Prime rate shows the strongest statistical evidence of a relationship with annual returns.

---

## 5. Model Fit (R-squared)

Compare R² across the three models:
- Prime rate explains the most variation in annual returns (R² = 0.016), though the value is still very low. This suggests that other factors beyond these predictors drive REIT returns.

---

## 6. Omitted Variables

By using only one predictor at a time, we might be omitting:
- **Market conditions:** Broader economic factors like GDP growth or inflation may influence returns.
- **Sector-specific factors:** Characteristics unique to REIT sectors (e.g., retail vs. industrial).
- **Leverage:** Debt levels may interact with interest rates to affect returns.

**Potential bias:** If omitted variables are correlated with both the X variable and ret, our slope estimates may be biased. For example, if leverage is correlated with both prime_rate and returns, the estimated effect of prime_rate may be overstated.

---

## 7. Summary and Next Steps

**Key Takeaway:**
Prime rate shows the strongest relationship with REIT annual returns, consistent with the idea that higher borrowing costs reduce profitability. Dividend yield also has a significant negative relationship, while FFO/Assets does not show a statistically significant effect.

**What we would do next:**
- Extend to multiple regression (include two or more predictors)
- Test for heteroskedasticity and other OLS assumption violations
- Examine whether relationships vary by time period or REIT sector

---

## Reproducibility Checklist
- [ ] Script runs end-to-end without errors
- [ ] Regression output saved to `Results/regression_div12m_me.txt`, `regression_prime_rate.txt`, `regression_ffo_at_reit.txt`
- [ ] Scatter plots saved to `Results/scatter_div12m_me.png`, `scatter_prime_rate.png`, `scatter_ffo_at_reit.png`
- [ ] Report accurately reflects regression results
- [ ] All interpretations are in economic units (not just statistical jargon)
