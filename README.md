# Writing README.md file to /mnt/data/README.md with the project content provided earlier.
readme_content = """# FOIR-Based Customer Financial Analysis

## Project Overview
Every financial institution faces the challenge of deciding whether a customer can *safely afford* a new loan. Many borrowers already have existing EMIs or fixed obligations — which can affect their repayment capacity.

To analyze this, this project explores a real dataset containing customer income, loan details, EMI, and FOIR (Fixed Obligation to Income Ratio) data. The goal is to uncover how FOIR impacts financial stability and loan eligibility.

## What is FOIR?
**FOIR (Fixed Obligation to Income Ratio)** is a key metric in loan evaluation. It measures how much of a person’s monthly income is already committed to existing obligations.
FOIR = (Total Monthly Obligations / Gross Monthly Income) × 100

| FOIR Range | Interpretation | Risk Level |
|------------|----------------|------------|
| ≤ 40%      | Healthy financial position | Low risk |
| 40–60%     | Moderate commitment        | Medium risk |
| > 60%      | Over-leveraged             | High risk |

## Objective
To analyze customer-level FOIR data and derive insights that can help:
- Identify high-risk customers before loan approval
- Understand the relationship between FOIR, income, EMI, and loan amount
- Support data-driven lending decisions

## Dataset Details
**File Name:** `FOIR Based Customer Analysis.xlsx`  
**Main Sheet Used:** `AllSalesClosuredata`  
**Rows:** 2,448  
**Columns:** 30

**Key Fields:**
- `Salary` – Monthly income of customer  
- `emi` – Monthly EMI obligation  
- `loanAmount` – Approved loan amount  
- `foirPercentage` – Pre-calculated FOIR value  
- `Funding type` – Whether purchase was loan-based or not  
- `Project`, `Source`, `RI/NRI` – Customer and lead details

## Steps Performed

### 1. Data Cleaning
- Removed duplicates and handled missing values
- Standardized categorical columns (`Funding type`, `Source`, `RI/NRI`)
- Converted `Born Date` to datetime and created an `Age` feature
- Replaced outliers using IQR method for key financial columns

### 2. Feature Engineering
- Created `EMI_to_Salary` ratio
- Created `Loan_to_Sales` ratio
- Categorized customers into **Low FOIR (≤40%)** and **High FOIR (>40%)**

### 3. Exploratory Data Analysis (EDA)
- Analyzed salary distribution and FOIR patterns
- Visualized relationship between salary, loan amount, EMI, and FOIR
- Correlation heatmap to identify strong predictors of FOIR

### 4. (Optional) Predictive Modeling
- Built a simple logistic regression model to classify FOIR category
- Evaluated with accuracy, precision, and recall metrics

## Tech Stack
- Python (Pandas, NumPy)
- Visualization (Matplotlib, Seaborn)
- Environment: Jupyter Notebook
- File Handling: Excel, CSV

## Key Insights
- Customers with higher salaries generally maintain a lower FOIR.
- As EMI-to-Salary ratio increases, FOIR rises sharply, indicating financial stress.
- The majority of customers fall within the safe zone (≤40%), but a significant minority are high-risk.
- Correlation analysis showed moderate relationship between `loanAmount` and `foirPercentage`.

## How to Run This Project
1. Clone the repository
```bash
git clone https://github.com/yourusername/FOIR-Analysis.git
cd FOIR-Analysis
