# Non-Retail Probability of Default (PD) Model

**Author**: Hamed Vosgha

## Project Overview

This project develops a Probability of Default (PD) model to predict the likelihood of default for non-retail credit portfolios, focusing on corporate entities. The model utilizes financial indicators and macroeconomic factors to assess credit risk and forecast bankruptcy.

## Dataset

- **Source**: [American Bankruptcy Dataset](https://github.com/sowide/bankruptcy_dataset)
- **Time Period**: 1999–2018
- **Details**:
  - Accounting data for 8,262 companies.
  - 78,682 firm-year observations labeled as:
    - `1`: Bankruptcy (failed companies)
    - `0`: Alive (non-failed companies)
  - Data Splits:
    - **Training**: 1999–2011
    - **Validation**: 2012–2014
    - **Testing**: 2015–2018
  - No missing or synthetic values.

## Methodology

### 1. Data Preprocessing

- **Handling Imbalance**:
  - Applied Synthetic Minority Oversampling Technique (SMOTE) to balance the dataset.
- **Feature Engineering**:
  - Standardized financial ratios and incorporated macroeconomic variables.
- **Data Splitting**:
  - Divided data into training, validation, and testing sets.

### 2. Modeling

- **Algorithm**: Logistic Regression
- **Features**:
  - Financial ratios (e.g., Debt/Equity, Liquidity).
  - Macroeconomic variables (e.g., GDP growth).
- **Model Equation**:

  \[
  \text{Logit}(PD) = \beta_0 + \beta_1 \cdot X_1 + \beta_2 \cdot X_2 + \dots + \beta_n \cdot X_n
  \]

### 3. Threshold Optimization

- Adjusted the decision threshold to enhance recall for default cases.
- **Optimal Threshold**: 0.92

## Results

### Performance Metrics

| Dataset      | Accuracy | ROC AUC | Precision (1) | Recall (1) | F1 Score (1) |
|--------------|----------|---------|---------------|------------|--------------|
| **Validation** | 90%      | 0.711   | 16%           | 33%        | 21%          |
| **Testing**    | 89%      | 0.742   | 18%           | 35%        | 24%          |

## Visualizations

- **Data Insights**:
  - Distribution of defaults (bar chart/pie chart).
  - Key financial ratios (histograms).
- **Model Performance**:
  - ROC Curve.
  - Precision-Recall Curve.
- **Risk Segmentation**:
  - Stacked bar chart for default probabilities.

## How to Run

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
