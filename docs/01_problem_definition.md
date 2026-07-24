# Part A: Problem Definition

1.  **Problem Statement**

Unemployment in South African rural areas remains critically high, with
livestock farming being integral to the livelihoods of rural
communities. The livestock industry, which includes goats, cattle, sheep
and poultry farming, offers an opportunity for large-scale labor
absorption and may make a vital contribution to rural employment growth.
This project examines whether national-level growth in livestock
production contributes to rural employment gains and an increased
agricultural contribution to GDP over the 2000-2023 period. Livestock
production growth serves as the independent variable, while rural
employment levels and agricultural GDP contribution (%) are the primary
dependent variables. This project addresses SDG 8 by evaluating how
significant livestock production growth is associated with rural job
creation across rural areas. It speaks to SDG 1 by exploring the
correlation between increased production output and economic conditions
for rural farming households. SDG 2 serves as a secondary lens, as
sustained national-level livestock production may support broader food
availability and agricultural sustainability. Dealing with multiple
longitudinal datasets covering production, pricing, trade, land use,
employment, and macroeconomic indicators, will introduce noise and
complex patterns which traditional statistical tools cannot handle hence
data science approach is essential.

2.  **Stakeholder Identification**

The following table identifies key stakeholders and their interest in
the project's methodological, ethical, and practical success:

  ---------------------------------------------------------------------------
  Stakeholder            Type            Interest in the project
  ---------------------- --------------- ------------------------------------
  Rural Livestock        Primary         They are directly affected by
  Farmers                Beneficiaries   findings from the project. Findings
                                         must accurately reflect the economic
                                         value and the employment potential
                                         of their hardwork.

  Department of          Government      Findings will assist to prioritise
  Agriculture, Land                      livestock commodities for
  Reform and Rural                       investment, extension services, and
  Development (DALRRD)                   rural development funding.

  NGOs: Heifer           Civil Society   NGOs work directly with stallholder
  International SA and                   and communal famers, they provide
  LIMA Rural Development                 the field-level context necessary to
                                         validate national-level data.
                                         Findings could influence how donor
                                         funding and development programmes
                                         are directed toward rural livestock
                                         communities.

  Statistics South       Data Provider   Has an institutional interest in
  Africa (Stats SA)                      ensuring its employment and
                                         agricultural data is accurately
                                         interpreted in quantitative
                                         research.

  Red Meat Producers     Industry Body   Ensures findings on production
  Organisation (RMPO)                    efficiency, pricing trends, and
  and Poultry                            employment contribution are
  Association of South                   methodologically sound and not
  Africa (PASA)                          misrepresented in policy
                                         discussions.
  ---------------------------------------------------------------------------

3.  **Task Formulation**

This project will be operationalized on the following structured machine
learning tasks:

Task 1 will apply supervised regression to quantify how livestock stock
numbers, production volumes, and producer prices for cattle, goat,
sheep, and chicken predict rural agricultural employment and
agricultural GDP share both continuous target variables suited to
regression analysis.

Task 2 applies supervised classification to translate those continuous
findings into discrete, policy-actionable categories: each year from
2000 to 2023 is labelled an employment growth or decline period,
providing DALRRD with a forward-looking diagnostic tool.

Task 3 applies unsupervised clustering to group the four livestock
commodities by their combined profiles of production growth, price
stability, trade value, and employment contribution. This reveals
natural data groupings that enable DALRRD to design differentiated
interventions per commodity cluster rather than applying a uniform
livestock support policy.
