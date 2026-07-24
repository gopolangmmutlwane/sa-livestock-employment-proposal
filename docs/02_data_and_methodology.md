# Part B: Data and Methodology

1.  **Data Sources**

Two publicly available and internationally validated databases provide
data for this project.

The first is FAOSTAT (fao.org/faostat), the statistical database of the
United Nations Food and Agriculture Organisation. FAOSTAT will provide
livestock stock numbers, production volumes, and producer prices for
cattle, goat, sheep, and chicken; government expenditure on agriculture,
agricultural land use, and employment indicators. FAOSTAT was selected
because it aligns with the SDG monitoring framework, which strengthens
credibility and ensures findings related to this project's SDG remain
reproducible.

The second is World Bank Open Data (data.worldbank.org), which
contributes three indicators: employment in agriculture as a percentage
of total employment, agriculture value-added as a percentage of GDP, and
GDP in current USD. World Bank Open Data contains reliable, annually
updated macroeconomic indicators which align with the project's SDG 8
and 1 objectives.

All variables are continuous, ratio-scale, and longitudinal, recorded
annually at national level for South Africa. The risk of systematic
error is limited since both sources adhere to international quality
standards. However, isolated missing values may exist across the
2000--2023 period and will be addressed through linear interpolation.
Variables with more than 20% missing values will be marked for potential
exclusion. The two datasets will be merged on a common annual year index
to build one analytical dataset covering 24 annual observations at
national level for South Africa.

2.  **Feature Engineering**

Features are organised into two categories: raw variables which are
extracted directly from datasets and derived categories engineered to
capture dimensions not included in the raw data. Raw variables include
livestock stock numbers, production volumes, producer prices, government
agricultural expenditure, land use, and GDP. These variables represent
the project\'s core production, economic, and policy dimensions. To
capture dimensions not included in the raw data, two derived features
will be constructed: a production efficiency index (production volume
divided by stock numbers per commodity) and a rolling five-year price
volatility index (standard deviation of producer prices over a rolling
five-year window) that feeds directly into the clustering task.

Agriculture value-added as a percentage of GDP serves two roles, as the
regression target variable and as a predictive feature in the
classification task. Data leakage controls will be applied explicitly to
prevent information from the target variable contaminating the
classification training process. Pearson correlation analysis will be
conducted prior to model training to identify relationships between
features and target variables, while Random Forest importance scores
will be extracted post-training to confirm and rank feature
contributions. Features that rank consistently low across both methods
will be considered for removal, with a threshold of below 5% relative
importance applied as the criterion for exclusion from the final feature
set.

3.  **Modelling**

The sequential analytical design of this project is operationalised by
five models across three tasks.

Task 1: Supervised learning (Regression)

Random Forest Regressor is our primary model because it has the ability
to model non-linear relationships between production and macroeconomic
input features and continuous target variables, which include rural
employment in agriculture (% of total employment) and agriculture value
added (% of GDP). Random Forest does not assume a linear relationship
between inputs and outputs, making it better suited to the complexity of
longitudinal economic data compared to linear regression. To determine
whether the added complexity of Random Forest produces a meaningful
improvement in predictive accuracy, we will retain linear regression as
a baseline model.

Because the dataset contains only 24 annual observations, a standard
80/20 train-test split would produce fewer than five testing
observations, which is insufficient for reliable model evaluation. This
constraint will therefore be addressed by five-fold cross-validation,
maximising the utility of the limited data by rotating training and
testing data across five folds. Time-aware cross-validation ensures that
models are always trained on earlier observations and tested on later
ones, preserving the temporal integrity of the longitudinal data.

Task 2: Supervised Learning (Classification)

The classification task translates findings from Task 1 into actionable
binary categories for DALRRD and rural development policymakers. For
this task, Random Forest Classifier will serve as the primary model.
This task requires the model to assign each year a binary employment
label (employment growth or employment decline) using livestock
production variables as predictors. Its ability to handle potential
class imbalance and capture feature interactions that cannot be detected
by linear models makes it particularly well-suited for this task.
Logistic Regression provides both interpretability and a meaningful
performance benchmark for comparison, therefore it will be included as
the baseline. Five-fold time-aware cross-validation is applied
consistently across both models.

Task 3: Unsupervised Learning (Clustering)

We need to cluster four livestock types by the economic and employment
characteristics that define each commodity (production growth, price
stability, trade value, and employment contribution). K-Means Clustering
is the most appropriate model to perform this, given its suitability for
grouping a small number of commodities across multiple dimensions
simultaneously. Rather than clustering annual observations, the
algorithm treats each livestock type as a single point summarising its
profile across the full study period. Hierarchical Clustering serves as
a comparison method, producing a dendrogram to verify whether the
K-Means groupings are internally consistent and interpretable as
meaningful commodity clusters.

Collectively, these three tasks form a sequential pipeline in which
regression establishes the relationship, classification makes it
actionable, and clustering directs policymakers where to intervene.

4.  **Descriptive and Inferential Statistical Methods**

This section covers two distinct analytical stages: describing and
understanding the dataset prior to modelling and evaluating and
comparing model performance after modelling.

Stage 1: Descriptive Statistics for Dataset Analysis

Descriptive statistics will characterise each variable prior to
modelling. Measures of central tendency (mean and median) summarise
typical values for production volumes, employment rates, and price
levels. Measures of dispersion, which include range, standard deviation
and coefficient of variation, reveal the degree of variability over
time, which is the essential step for identifying which livestock
commodities are most prone to production volatility and price
instability.

Pearson correlation is used prior to modelling to assess linear
relationships between independent and target variables; this provides an
initial indication of which features are likely most predictive and
identifies multicollinearity between features that may require attention
before model training. Spearman rank correlation will be applied as a
non-parametric alternative when variables are not normally distributed.

Stage 2: Inferential and Model Evaluation Statistics

Regression model performance will be measured using three metrics.
R-squared indicates the proportion of variance in the target variable
explained by the model, providing an overall measure of fit. Root Mean
Square Error (RMSE) penalises large prediction errors more heavily,
making it useful for identifying models that produce occasional
significant mispredictions. Mean Absolute Error (MAE) expresses
prediction error in the same units as the target variable, making it the
most interpretable metric for a policy audience such as DALRRD, who may
not be statistically trained. Random Forest Regressor and Linear
Regression will be compared directly on all three metrics to determine
whether model complexity is justified.

Classification Model Evaluation

F1-score is the primary evaluation metric for the classification task.
Since growth and decline years may not be evenly distributed across the
2000--2023 period, accuracy alone would be a misleading measure of
performance on an imbalanced dataset. F1-score balances precision and
recall, providing a more reliable assessment of how well the model
identifies both classes. Accuracy, precision, and recall will be
reported alongside F1-score for completeness.

Clustering Evaluation

The Silhouette Score will measure how well each commodity fits within
its assigned cluster relative to other clusters, with scores closer to
one indicating well-defined groupings. The Elbow Method, applied to
inertia values across different values of k, will determine the optimal
number of clusters and validate the K-Means configuration.
