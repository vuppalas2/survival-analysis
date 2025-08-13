# Survival Analysis of Lung Cancer Patients in Bombay Using Cox Proportional Hazards Model

## Project Overview
This project investigates survival outcomes among lung cancer patients from the Bombay Lung Cancer Registry using **advanced survival analysis methods**. The dataset contains 682 patients registered between January 1, 1989, and December 31, 1991. Survival times are measured from diagnosis to death or censoring.  

The primary objective is to explore factors affecting patient survival, including demographic, socio-economic, and clinical characteristics. Key goals include:  
- Summarizing patient characteristics using descriptive statistics.  
- Evaluating the impact of sex, age, education, religion, marital status, and tumor type on survival.  
- Fitting **Cox proportional hazards models** to estimate hazard ratios.  
- Checking **proportional hazards (PH) assumptions**, including time-dependent covariates.  
- Visualizing survival patterns with **Kaplan-Meier curves** and hazard ratios with **forest plots**.  
- Developing nested Cox models to identify the most parsimonious predictive model.  

## Statistical Methods
This analysis uses the following **statistical methods**:  
1. **Descriptive Statistics**: Median, IQR, minimum, maximum for continuous variables; counts and proportions for categorical variables.  
2. **Survival Analysis**:  
   - **Kaplan-Meier curves** with log-rank tests to compare survival distributions across groups.  
   - **Cox proportional hazards (PH) models**:  
     - Univariate models for each predictor.  
     - Multivariable models for adjusted hazard ratios.  
     - Nested models to identify significant predictors and the most parsimonious model.  
     - **Time-dependent covariates** to assess PH assumption violations.  
3. **PH Assumption Checks**: Schoenfeld residuals (`cox.zph`) and graphical inspection.  
4. **Visualization**: Kaplan-Meier survival curves, Schoenfeld residual plots, and forest plots for hazard ratios with 95% confidence intervals.  

## Dataset
The dataset used in this project is `bombay_lung_cancer.csv`, which contains the following variables:

| Variable | Description | Values/Definition |
|----------|-------------|-----------------|
| `surv_time` | Survival time in days | Min = 1, Max = 852 |
| `censored` | Censoring indicator | 0 = Death, 1 = Censored |
| `sex` | Patient sex | 1 = Male, 2 = Female |
| `age` | Age at diagnosis | Years, Min = 11, Max = 99 |
| `education` | Educational level | 1 = Literate, 2 = Illiterate |
| `religion` | Religion | 1 = Hindu, 2 = Christian, 3 = Muslim |
| `marital_status` | Marital status | 1 = Single, 2 = Separated/Divorced, 3 = Married |
| `tum0r_type` | Tumor type | 1 = Local, 2 = Regional, 3 = Advanced |

## Project Structure
```
│
├─ data/
│ └─ bombay_lung_cancer.csv
│
├─ output/
│ ├─ tables/
│ │ ├─ summary/   # Cox model summaries
│ │ ├─ anova/     # ANOVA results for each model
│ │ └─ PH_tests/  # Proportional hazards assumption tests
│ │
│ └─ plots/
│ ├─ KM/          # Kaplan-Meier survival curves
│ ├─ PH/          # Schoenfeld residual plots
│ └─ Forest/      # Forest plots for hazard ratios
│
├─ scripts/
│ └─ survival_analysis.R # Full analysis script
│
└─ README.md
```


## Analysis Overview
1. **Data Preparation**: Load libraries, convert categorical variables to factors, create event indicator.  
2. **Descriptive Statistics**: Summarize continuous and categorical variables; perform group-wise summaries.  
3. **Cox Models**: Fit univariate, multivariable, and nested Cox PH models; include time-dependent covariates to test PH assumptions.  
4. **PH Assumption Checks**: Use Schoenfeld residuals for each model and generate diagnostic plots.  
5. **Visualization**: Generate Kaplan-Meier survival curves and forest plots for all models.

## Running the Analysis
1. Clone the repository.  
2. Place `bombay_lung_cancer.csv` in the `data/` directory.  
3. Open `survival_analysis.R` in RStudio or another R environment.  
4. Run the script to generate:  
   - Summary tables (`output/tables/summary/`)  
   - ANOVA results (`output/tables/anova/`)  
   - PH test outputs (`output/tables/PH_tests/`)  
   - Kaplan-Meier plots (`output/plots/KM/`)  
   - Forest plots (`output/plots/Forest/`)  
   - PH residual plots (`output/plots/PH/`)  

## Key Outputs
- Descriptive statistics for continuous and categorical variables.  
- Univariate and multivariable Cox model results with hazard ratios.  
- Time-dependent Cox models for PH assumption checks.  
- Parsimonious nested models highlighting key predictors.  
- All plots and tables organized in structured directories.  

## References
- Therneau, T. M. (2022). *A Package for Survival Analysis in R*. R package version 3.5-2.  
- Kassambara, A., & Kosinski, M. (2021). *survminer: Drawing Survival Curves using ‘ggplot2’*. R package version 0.4.9.  
- Bombay Lung Cancer Registry, Mumbai Municipal Corporation (1989–1991).


