# Part D: Ethics and Impact

1.  **Ethical Risks**

This project carries ethical responsibilities that extend beyond
standard data science practice because its findings could directly
influence public investment decisions that affect rural communities
across South Africa. This assessment identifies three specific risks
that require active mitigation. The first is policy misuse through
oversimplification. In the clustering task, cattle and chicken are
grouped together as Cluster 1 which is associated with high employment
impact while goat and sheep are grouped as Cluster 2, reflecting lower
employment impact. Should DALRRD interpret these findings without
contextual nuance, investment could be shifted away from goat and sheep
farming without realising that these commodities are the primary
livelihood for smallholder and communal farmers in some parts of South
Africa. This outcome would directly contradict the project\'s core aim
of supporting rural poverty reduction in these communities. Defunding
Cluster 2 based on national aggregate data could deepen rural poverty.

The second risk is misrepresentation of correlation as causation. The
regression model identifies associations between livestock production
growth and rural employment, not causal relationships. If findings are
communicated carelessly in policy documents or public communications,
decision-makers may treat the model's outputs as proof that increasing
production will automatically create jobs, leading to poorly designed
interventions that fail to address structural barriers such as
mechanisation and market access. The third risk is the exclusion of
smallholder farmers from the analytical frame. The data used in the
project is the national-level data that aggregates commercial and
subsistence farming together. Policy decisions informed by this model
may not serve all farmers equally. Large commercial producers whose
output tend to dominate aggregate production figures could find
themselves benefiting, while smallholder farmers who are most
economically vulnerable remain invisible in the data and underserved by
resulting policies. These risks require active mitigation through
governance structures, not passive acknowledgement.

2.  **Data Governance**

In this project data governance operates at two levels: input integrity
and output responsibility.

At the input level, all data will be downloaded directly from FAOSTAT
and World Bank Open Data with download dates and dataset versions
recorded. This ensures that any researcher can retrieve the exact
datasets used and replicate the analytical pipeline. To maintain
transparency and accountability, all missing value treatments,
interpolations, and variable exclusions will be documented in a
preprocessing log that accompanies the project. This transparency is
essential since this project's methodological choices directly affect
the validity of policy-facing findings.

At the output level, governance is the most critical commitment given
the policy stakes. Any outputs shared with DALRRD or other stakeholders
must be accompanied by a clear methodology statement, confidence
intervals, and an explicit limitations caveat. The distinction between
correlation and causation must be made visible in every output document.
To prevent confusion between original data and model-generated findings,
raw data files will be kept separate from derived analytical outputs.
Together, these input and output governance commitments directly address
the misrepresentation and policy misuse risks identified in Section 1,
ensuring that the project's findings are presented in a form that is
honest, reproducible, and resistant to misinterpretation.

3.  **Subject Matter Experts**

The datasets used in this project capture what happened numerically
between 2000 and 2023, but not why it happened, whether the patterns are
structurally stable, or how findings will be experienced by affected
communities. Expert consultation is necessary to bridge this gap. An
agricultural economist with expertise in the South African rural labour
market would validate whether the production-employment relationship is
being modelled correctly and flag structural factors the data cannot
capture, such as mechanisation trends and seasonal labour patterns that
explain why production volumes can rise while employment shares remain
flat or decline. A DALRRD policy official would provide institutional
knowledge about departmental funding cycles, political constraints, and
how analytical outputs are actually used in practice. This is essential
for ensuring the deployment recommendation is institutionally feasible
rather than theoretically sound but practically unworkable.

A statistician specialising in small-sample longitudinal analysis would
independently validate the methodological choices around five-fold
time-aware cross-validation and the 24-observation constraint, ensuring
that the modelling approach is defensible under peer scrutiny and that
confidence in the results is appropriately calibrated.

A smallholder farmer representative or rural development NGO such as
LIMA or Heifer International SA would ground the national aggregate
findings in lived experience and flag whether model outputs reflect the
realities of communities most affected by investment decisions. This
consultation directly addresses the exclusion risk identified in Section
1, creating coherence between the ethical risk assessment and the expert
engagement strategy.

4.  **Deployment Commendation**

The recommended deployment follows a three-phase process designed to
ensure credibility before reach, in recognition of the fact that a model
influencing public investment decisions must be validated and governed
before it is acted upon.

In Phase 1, the framework would be submitted for independent academic
validation by a university with an established agricultural economics
faculty, such as the University of Pretoria or Stellenbosch University.
Validation would compare the model's historical classifications against
actual recorded employment trends from Stats SA to confirm acceptable
accuracy before any engagement with DALRRD.

In Phase 2, the framework would be deployed as an annual policy briefing
document rather than a live dashboard, in recognition of DALRRD's likely
infrastructure and capacity constraints. The briefing would be timed to
inform DALRRD's Annual Performance Plan drafting cycle and framed as
contributing evidence toward the National Development Plan 2030 rural
employment targets. This format is realistic for how South African
government departments consume analytical outputs.

In Phase 3, a documented standard operating procedure would enable
DALRRD's Directorate of Agricultural Statistics to update the model
annually as new FAOSTAT and World Bank data becomes available, without
dependence on the original developer. A three-member oversight committee
comprising a senior DALRRD official, an independent statistician, and a
civil society representative would govern the model, with the
requirement that no policy decision affecting livestock investment
allocation be made solely on model outputs without committee sign-off.
This deployment plan is designed to be credible, sustainable, and
aligned with how South African government machinery actually operates.
