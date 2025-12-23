# Qube Research & Technologies Data Challenge 2025

**Ranked 14th out of 634 participants**

## 📄 Challenge Description

This project was carried out as part of the **Qube Research & Technologies Data Challenge 2025**, a data science competition organized on the Challenge Data platform by ENS Paris, Collège de France, and Institut Louis Bachelier, in partnership with **Institut Gustave Roussy**, Europe's leading cancer center.

The objective was to develop predictive models for **Overall Survival** in patients diagnosed with myeloid leukemia, using structured clinical and molecular data from real patients.

### 🏆 Results
*   **Ranking**: 14th out of 634 participants.
*   **Performance**: Strong predictive capability demonstrated in a highly competitive environment.

## 🛠️ Methodology

Our approach relies on a rigorous combination of domain-specific feature engineering and ensemble techniques for survival analysis.

### 1. Advanced Feature Engineering
The most critical step was transforming raw data into relevant prognostic indicators, based on medical literature in hematology.

*   **Clinical Data**:
    *   **Risk Scores**: Creation of composite scores for hematological risk and organ dysfunction.
    *   **Ratios & Interactions**: Calculation of key biological ratios (e.g., Blasts/Leukocytes) and non-linear interactions.
    *   **Cytogenetics**: Complex parsing of cytogenetic strings to identify specific chromosomal abnormalities (del(5q), monosomy 7, complex karyotype) and classify patients according to risk standards (Favorable, Intermediate, Adverse).

*   **Molecular Data**:
    *   **Mutation Analysis**: Aggregation of mutations by gene and impact type (frameshift, stop gained, etc.).
    *   **Driver Genes**: Targeted identification of mutations in known driver genes (TET2, DNMT3A, TP53, FLT3, etc.).
    *   **Clonality**: Estimation of clonal structure (clonal vs subclonal mutations) via Variant Allele Frequency (VAF) analysis.
    *   **Signatures**: Detection of specific co-occurrences (e.g., FLT3-NPM1 signature).

### 2. Modeling Strategy
A multi-model approach was adopted to capture both linear and non-linear relationships.

*   **Models Used**:
    *   **Cox Proportional Hazards (Regularized)**: Use of ElasticNet regularization (L1/L2) for variable selection and collinearity management.
    *   **Random Survival Forests (RSF)**: To capture complex interactions and non-linearities without strong parametric assumptions.
    *   **Gradient Boosting Survival Analysis**: To optimize performance on the residuals of other models.

### 3. Validation and Robustness
To avoid overfitting and ensure model generalization:

*   **Stability Selection**: Use of resampling techniques to identify the most robust variables and eliminate noise.
*   **Stratified Cross-Validation**: Rigorous validation strategy respecting the distribution of events (deaths/censored).
*   **Ensemble Stacking**: Combination of predictions from different models (Cox, RSF, Gradient Boosting) via optimized weighting on Out-Of-Fold (OOF) predictions.

## 💻 Technologies
*   **Language**: Python
*   **Main Libraries**: `scikit-survival`, `lifelines`, `scikit-learn`, `pandas`, `numpy`.

## 🎓 Skills Applied
*   Python Programming
*   Machine Learning & Survival Analysis
*   Feature Engineering on Biomedical Data
*   Data Science & Visualization
*   Data Science Project Management
