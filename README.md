# causal-experiments
Causal inference and causal machine learning through experiments, implementations, and research.

Exploring causal inference and causal machine learning through experiments and implementations, with a focus on personalized decision making.

## Expriment 1:

We simulate a digital advertising scenario with 50,000 customers. Customers are randomly assigned to receive an advertisement or not, and we observe whether they make a purchase.

The experiment starts with a traditional A/B test to estimate the Average Treatment Effect (ATE), and then investigates whether the effect of the advertisement differs across customers using CATE and causal ML methods.

### Initial Findings

The A/B test showed an overall treatment effect of approximately **15.2 percentage points**.

However, the effect was not uniform across customers:

- Low-engagement customers: **18.75%** treatment effect
- High-engagement customers: **11.29%** treatment effect

We then compared S-Learner, T-Learner, and X-Learner on unseen data:

| Method | Correlation | MAE |
|---|---:|---:|
| S-Learner | **0.812** | **0.021** |
| X-Learner | 0.811 | 0.023 |
| T-Learner | 0.757 | 0.027 |

These results suggest that looking only at the overall ATE can miss useful differences between customers. A Data Scientist could use estimated treatment effects to identify customers who are more likely to benefit from an intervention rather than targeting everyone in the same way.

These are preliminary results from one synthetic setup, so the next step is to test how the methods behave with different sample sizes, treatment ratios, and levels of treatment-effect heterogeneity.
