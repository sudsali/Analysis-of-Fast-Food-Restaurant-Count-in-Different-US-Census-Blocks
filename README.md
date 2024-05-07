# 6053 Final Project

## Summary

### The estimand to be tested:
As median income (I) increases in Metropolitan Counties, there is an increase in the fast-food restaurant count (F). Conversely, when the median income (I) increases in Micropolitan Counties, there is a decrease in the fast-food restaurant count (F).

### Statistical Model:
We have tested 3 different models based on our assumptions on fast food locations per area:

- **LogNormal**
- **Poisson**
- **NegativeBinomial**

- The LogNormal Model proved superior, demonstrating the best balance of complexity and predictive accuracy, making it ideal for our analysis. It effectively captured the variance and skewness in restaurant counts, using median income and area type as predictors.
- The Poisson and Negative Binomial Models were considered but showed less optimal performance. The Poisson model particularly suffered from significant overfitting as indicated by its high predictive information criteria scores and low effective model weight in cross-validation comparison.
- Model Comparison using LOO-CV (Leave-One-Out Cross-Validation) reinforced the LogNormal model's superiority, with it showing the highest log predictive density, indicating it is the most suitable for predicting new data without overfitting.

### Posterior Predictive Analysis:
1. **Micropolitan Areas**
   - **Observation**: The graph shows a slight decrease in the predicted count of fast food restaurants as median income increases. The red line, representing the posterior mean, trends downward slightly amidst a wide confidence interval shaded in pink.
   - **Interpretation**: This indicates that in micropolitan areas, higher median incomes might be associated with a decrease in the number of fast-food restaurants, although the data points (blue dots) display considerable variability around the prediction.

2. **Metropolitan Areas**
   - **Observation**: There is a clear upward trend in the predicted number of fast food restaurants as median income increases, illustrated by the green line. The confidence interval, shaded in green, widens at higher income levels, suggesting increased uncertainty in the predictions as income rises.
   - **Interpretation**: This suggests that in metropolitan areas, higher median incomes are strongly associated with increases in the number of fast-food restaurants. The observed data points (blue dots) mostly cluster around the lower income levels but support the upward trend.
3. **Insights**:
- The contrasting trends between micropolitan and metropolitan areas align with the estimand, affirming that area type significantly modifies the impact of median income on fast food restaurant prevalence.
- The variability in both graphs, especially in the metropolitan data, underscores the influence of other unmodeled factors or inherent data variability that might affect restaurant counts.

### Conclusion:
The estimand can be observed by the posterior predictive simulation plots, especially the ones done using the LogNormal Model. The model effectively reflects the estimand positive relationship in metropolitan areas and a negative or neutral trend in micropolitan areas

## Generating a PDF

```sh
jupyter nbconvert --to html --allow-chromium-download project.ipynb && mv project.html ./output/project.html
```
