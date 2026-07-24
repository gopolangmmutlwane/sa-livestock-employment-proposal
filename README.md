# Livestock Production, Rural Employment & Economic Output in South Africa

**A data science research proposal.** This is a project *design* — a fully worked-out plan
for a regression → classification → clustering pipeline investigating whether national-level
livestock production growth relates to rural employment and agricultural GDP contribution in
South Africa (2000-2023). It has not yet been executed against real data.

Built by **Gopolang Mmutlwane**.

> **A note on the presentation deck:** `presentation/concept_presentation.pptx` demonstrates
> the intended reporting format for DALRRD (South Africa's Department of Agriculture, Land
> Reform and Rural Development) — what the findings slides, model comparison, and policy
> recommendations would look like once the pipeline is actually run. Every results-bearing
> slide is explicitly labelled **(Simulated)**, and the figures shown (R² = 0.74, F1 = 0.68,
> etc.) are illustrative placeholders, not real findings from a trained model. Real FAOSTAT
> and World Bank data has not yet been acquired and no model in this pipeline has been trained.

## The research question

Does national-level livestock production growth (cattle, goat, sheep, chicken) contribute to
rural employment gains and increased agricultural GDP contribution in South Africa between
2000 and 2023? The project maps to three UN SDGs: SDG 8 (decent work), SDG 1 (poverty
reduction), and SDG 2 (food security) as a secondary lens.

## What's inside

| File | What it covers |
|---|---|
| [`docs/01_problem_definition.md`](docs/01_problem_definition.md) | Problem statement, stakeholder analysis (rural farmers, DALRRD, NGOs, Stats SA, industry bodies), and the three-task formulation (regression, classification, clustering). |
| [`docs/02_data_and_methodology.md`](docs/02_data_and_methodology.md) | Data sources (FAOSTAT, World Bank Open Data), feature engineering plan, model selection and justification for all five models across the three tasks, and the statistical evaluation plan. |
| [`docs/03_ethics_and_impact.md`](docs/03_ethics_and_impact.md) | Three specific, named ethical risks (policy misuse from oversimplified clustering, correlation-as-causation misreading, smallholder-farmer exclusion from national-aggregate data), a two-level data governance plan, required subject-matter expert consultations, and a three-phase deployment plan. |
| [`docs/04_reflection.md`](docs/04_reflection.md) | Honest reflection on skill gaps, what "success" means for a data science project beyond statistical metrics, and — notably — catching that AI-generated visualisations didn't match the (placeholder) project data, and why that catch depended on having a grounded statistical foundation. |
| [`presentation/concept_presentation.pptx`](presentation/concept_presentation.pptx) | The intended stakeholder-facing report format — see the disclaimer above. |

## Why this is worth including as-is

The honest framing here is deliberate. Part of what this proposal demonstrates is *design*
skill — the ability to scope a data science project properly before writing a line of
modelling code: picking defensible data sources, justifying model choice against a real
sample-size constraint (24 annual observations, which rules out a standard train/test split
and requires time-aware cross-validation instead), and — probably the strongest part of the
whole proposal — naming specific policy-misuse risks *before* they happen rather than
generically gesturing at "responsible AI." The reflection also documents a real instance of
catching an AI-generated artefact that didn't match the underlying (placeholder) data, which
is itself a data-literacy skill worth showing.

## Data sources (for future execution)

- **FAOSTAT** (fao.org/faostat) — livestock stock numbers, production volumes, producer
  prices for cattle, goat, sheep, chicken; agricultural expenditure, land use, employment
- **World Bank Open Data** (data.worldbank.org) — employment in agriculture (% of total),
  agriculture value-added (% of GDP), GDP (current USD)

## Planned modelling approach

| Task | Primary model | Baseline | Evaluation |
|---|---|---|---|
| Regression | Random Forest Regressor | Linear Regression | R², RMSE, MAE |
| Classification | Random Forest Classifier | Logistic Regression | F1-score (primary), accuracy, precision, recall |
| Clustering | K-Means | Hierarchical Clustering (validation) | Silhouette Score, Elbow Method |

All three tasks use five-fold **time-aware** cross-validation — chosen specifically because a
standard 80/20 split on 24 annual observations would leave fewer than 5 test points, too few
for reliable evaluation.
