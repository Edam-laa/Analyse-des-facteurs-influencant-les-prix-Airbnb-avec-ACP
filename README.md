# Paris Airbnb — Multivariate Analysis & Principal Component Analysis
**Exploratory Data Analysis · PCA · Python · Statistical Interpretation**

An academic exploration of Paris Airbnb listing data using **Principal Component Analysis (PCA)** to study relationships between listing characteristics and to visualize the structure of a multidimensional dataset.

> **Project scope:** unsupervised exploratory/statistical analysis, **not a validated Airbnb price-prediction model**. PCA components do not by themselves demonstrate causal drivers of prices.

## Analysis workflow

```mermaid
flowchart LR
    A["Paris Airbnb CSV"] --> B["Data cleaning<br/>numeric variable selection"]
    B --> C["Exploratory analysis<br/>correlations"]
    C --> D["Feature scaling"]
    D --> E["PCA decomposition"]
    E --> F["Explained variance<br/>loadings & projections"]
    F --> G["Interpretation<br/>report and visualizations"]
```

This is a conceptual summary of the notebook's reported analytical method, not a separate production workflow.

## Selected visual results

### Correlations
![Correlation matrix of analyzed attributes](outputs/correlation_matrix.png)

### Listing projections
![Listings projected onto principal components](outputs/individuals_pc1_pc2_by_room_type.png)

### Component loadings
![Feature loadings on PC1 and PC2](outputs/loadings_pc1_pc2.png)

### Explained variance
![Explained variance by principal component](outputs/composantes_principales_variance_explique.png)

[View cumulative explained variance](outputs/composant_peincipale_variance_cumule.png) · [View PC1–PC3 loadings](outputs/loadings_pc1_pc3.png)

The images are **existing project artifacts**. Their values have not been independently rerun during this README update; consult the notebook and tables for definitions and interpretation. Avoid interpreting visual grouping as predictive accuracy.

## Files and evidence

| Path | Content |
| --- | --- |
| [`notebooks/airbnb_acp_analysis.ipynb`](notebooks/airbnb_acp_analysis.ipynb) | Data exploration and PCA workflow |
| [`data/paris_airbnb.csv`](data/paris_airbnb.csv) | Dataset included in the repository |
| [`outputs/`](outputs/) | Existing statistical plots |
| [`tables/loadings_table.csv`](tables/loadings_table.csv) | Exported PCA loadings |
| [`tables/loadings_pc1_pc3_table.csv`](tables/loadings_pc1_pc3_table.csv) | Loadings for selected components |
| [`tables/explained_variance_table.xlsx`](tables/explained_variance_table.xlsx) | Exported explained-variance table |
| [`report/rapport_final_acp_airbnb_paris.pdf`](report/rapport_final_acp_airbnb_paris.pdf) | Academic report (French) |

## Run the analysis

```bash
git clone https://github.com/Edam-laa/Analyse-des-facteurs-influencant-les-prix-Airbnb-avec-ACP.git
cd Analyse-des-facteurs-influencant-les-prix-Airbnb-avec-ACP
python -m venv .venv
# Activate your virtual environment, then:
python -m pip install -r requirements.txt
jupyter notebook notebooks/airbnb_acp_analysis.ipynb
```

The notebook and CSV are provided, but full execution and dependency compatibility have **not been revalidated** in this portfolio update. If notebook cells reference environment-specific paths, adjust them to the local `data/paris_airbnb.csv` location. No metrics are claimed without a documented reproduction run.

## Methodological notes

- **Standardization:** units and scales matter because PCA is variance-based.
- **Interpretation:** loadings describe contributions to component directions; sample projections show relative positions within that transformed space.
- **Explained variance:** helps assess information retained per component, but does not measure forecast accuracy.
- **Constraints:** outliers, missing values, categorical encodings, sampling bias, and variable selection can substantially change PCA interpretation.
- **No causality claim:** relationships observed in listing data do not establish the causal effect of an amenity on pricing.

## Potential improvements

Add an automated notebook execution check, explicitly document each cleaning decision, verify the original dataset license/source, and compare PCA interpretation against targeted supervised analyses if the research question shifts toward price prediction.

## Credits

Academic multivariate statistics project; detailed analysis and methodological context are available in the linked report.
