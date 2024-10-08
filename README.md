# AP Exam Score Prediction

## Project Overview
This project explores the relationship between students' PSAT scores and their AP Statistics exam scores. The primary goal is to build a linear regression model to predict AP exam scores based on PSAT results and assess the strength of this relationship.

## Files Included
- **`apdata_clean.csv`**: The cleaned dataset used for analysis.
- **`ap_exam_analysis.Rmd`**: An R Markdown file containing the code, analysis, and outputs.
- **`README.md`**: This file, explaining the project structure, workflow, and key conclusions.

## Workflow

### 1. Data Preparation
- **Handling Missing Data**: Students with missing PSAT scores were excluded.
- **Filtering Invalid Scores**: Removed students with PSAT scores below 300 as these were considered outliers.

### 2. Descriptive Statistics
- **Score Distribution**: The distribution of actual AP exam scores, which range from 0 to 5.
- **Summary Statistics**: Boxplots and summary statistics were generated to explore the spread and detect any outliers in the data.

### 3. Linear Regression Model
- **Model Creation**: A linear regression model was constructed to predict AP exam scores based on PSAT scores.
  
  ```r
  mod1 <- lm(ACTUAL ~ PSAT, data = apdata_clean)
**Model Coefficients**
- **Intercept**: `-1.76049`
- **PSAT Coefficient**: `0.00480`

### 4. Model Evaluation
- **Regression Summary**:
  - **Standard deviation of residuals (σ)**: `0.745`
  - **R-squared**: `0.492` (This means that about 49% of the variance in AP exam scores is explained by PSAT scores).

### 5. Correlation Analysis
- **Correlation Coefficient**:
  - The correlation between PSAT and AP exam scores was computed as `0.701`, indicating a strong positive correlation between the two.

### 6. Predicting AP Scores
- **Prediction**: 
  The model was used to predict the AP exam score for the first student in the dataset.
  
  ```r
  predicted_score <- predict(mod1, newdata = apdata_clean[1, ])
  
## Conclusion

The analysis conducted in this project highlights the relationship between PSAT scores and AP exam performance. The linear regression model reveals that:

- **PSAT scores** can moderately predict **AP exam scores**, indicated by a correlation coefficient of **0.701**.
- The model's **R-squared value of 0.492** suggests that approximately **49% of the variance** in AP exam scores can be explained by PSAT scores alone.

However, this also indicates that **other factors** beyond PSAT scores significantly influence student success in AP exams. To enhance the predictive power of the model, future analyses could include additional variables, such as demographic information, classroom participation, or other standardized test scores. Overall, the findings underscore the importance of PSAT scores as a useful, yet not exhaustive, predictor of AP exam outcomes.

