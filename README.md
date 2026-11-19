# OilyGiant — Oil Well Profitability & Risk Analysis

### Machine Learning | Business Analytics | Investment Risk Assessment

**Author:** Ana Paula Takezawa        
**Education:** MBA in Data Science & Artificial Intelligence — TripleTen Brasil  
**Field:** Data Science | Predictive Modeling | Business Analytics  
**Technologies:** Python | Pandas | NumPy | Scikit-learn | Matplotlib | Seaborn  
**Project Type:** Linear Regression | Profitability Analysis | Bootstrapping | Risk Assessment

---

## Project Overview

This project evaluates three potential regions for new oil well development for OilyGiant, an oil extraction company.

The objective is to identify the region offering the highest expected profitability while maintaining an estimated probability of financial loss below 2.5%.

Linear Regression models are used to predict oil reserves, and Bootstrapping is applied to estimate potential profits and investment risks.

## Business Problem

OilyGiant plans to invest $100 million in the development of 200 new oil wells.

The business challenge is to select the most promising region based on geological data and predictive modeling, considering both expected financial returns and the risk of loss.

The analysis evaluates three regions and supports the investment decision through a data-driven approach.

## Dataset

The project uses three geological exploration datasets:

- `geo_data_0.csv`
- `geo_data_1.csv`
- `geo_data_2.csv`

Each dataset contains 100,000 records and five columns.

| Feature | Description |
|---|---|
| `id` | Unique oil well identifier |
| `f0` | Geological feature |
| `f1` | Geological feature |
| `f2` | Geological feature |
| `product` | Oil reserves in thousands of barrels |

The three geological features are used as model predictors, while `product` is the target variable.

## Methodology

The project follows a structured machine learning and financial evaluation workflow.

### 1. Data Preparation

- Loaded and inspected the three regional datasets.
- Checked data types, missing values, duplicate records, and descriptive statistics.
- Selected geological features for predictive modeling.

### 2. Predictive Modeling

- Trained a separate Linear Regression model for each region.
- Split the data into training and validation sets using a 75:25 ratio.
- Generated reserve predictions for each validation set.
- Evaluated model performance using Root Mean Squared Error (RMSE).

### 3. Financial Assumptions

The investment analysis follows the business constraints:

| Parameter | Value |
|---|---:|
| Total investment budget | $100,000,000 |
| Number of wells to develop | 200 |
| Revenue per unit of product | $4,500 |
| Candidate locations sampled | 500 |
| Wells selected per sample | 200 |
| Maximum acceptable loss risk | 2.5% |

The estimated break-even reserve volume is approximately 111.11 thousand barrels per well.

### 4. Profitability Analysis

- Ranked wells according to predicted oil reserves.
- Selected the 200 wells with the highest predicted values in each region.
- Calculated revenue using actual reserve volumes.
- Subtracted the development budget to estimate potential profit.

### 5. Risk Assessment with Bootstrapping

- Performed 1,000 Bootstrap iterations for each region.
- Randomly sampled 500 candidate wells with replacement.
- Selected the 200 wells with the highest predicted reserves in each sample.
- Calculated simulated profit distributions.
- Estimated mean profit, 95% confidence intervals, and probability of financial loss.

## Model Performance

The Linear Regression models achieved the following validation results:

| Region | Mean Predicted Reserves (thousand barrels) | RMSE |
|---|---:|---:|
| Region 0 | 92.59 | 37.58 |
| Region 1 | 68.73 | 0.89 |
| Region 2 | 94.97 | 40.03 |

Region 1 achieved substantially lower prediction error, indicating greater predictive accuracy within the evaluated dataset.

## Profitability Results

The initial profitability assessment selected the 200 wells with the highest predicted reserves in each region.

| Region | Estimated Profit |
|---|---:|
| Region 0 | $33.21 million |
| Region 1 | $24.15 million |
| Region 2 | $27.10 million |

These are point estimates based on the selected validation wells. The final investment recommendation also considers uncertainty and the probability of loss.

## Bootstrapping Results

The Bootstrap analysis produced the following results:

| Metric | Region 0 | Region 1 | Region 2 |
|---|---:|---:|---:|
| Mean Profit | $3.69M | **$4.55M** | $3.93M |
| 95% CI — Lower | -$1.77M | $0.61M | -$1.39M |
| 95% CI — Upper | $8.87M | $8.64M | $9.28M |
| Loss Risk | 8.5% | **1.0%** | 7.4% |
| Meets Risk Criterion | No | **Yes** | No |

## Investment Recommendation

**Region 1 is the recommended region for investment.**

It is the only region that satisfies the business requirement of maintaining an estimated probability of loss below 2.5%.

Additionally, Region 1 achieved the highest mean simulated profit, approximately $4.55 million, with an estimated loss risk of just 1.0%.

Although Regions 0 and 2 showed higher point-estimate profits in the initial selection, their Bootstrap loss probabilities exceeded the acceptable threshold.

Therefore, Region 1 offers the strongest combination of expected profitability and risk control under the assumptions of this analysis.

## Key Findings

- Linear Regression successfully estimated oil reserves across the three regions.
- Region 1 achieved the lowest RMSE among the evaluated models.
- Average reserve volumes across all regions were below the estimated break-even level, reinforcing the importance of predictive well selection.
- Bootstrap simulation revealed meaningful differences in investment risk.
- Region 1 was the only eligible region under the maximum 2.5% loss-risk criterion.

## Repository Structure

```text
oilygiant-profitability-analysis/
├── data/
│  
