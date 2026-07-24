# Part E: Reflection

1.  **Assuming you had to do the actual implementation of this project,
    which part of your skillset do you think is the strongest and
    the weakest at this stage?**

My strongest areas are statistical and mathematical reasoning and
communicating findings clearly to a non-technical audience. I am
comfortable interpreting metrics such as R2, RMSE, and F1-score and
translating results into plain language that a policy audience like
DALRRD can act on. My weakest area is dataset evaluation: assessing
whether a dataset is truly adequate for the questions being asked.
Throughout this project I kept questioning whether I had enough
variables or was missing something important. A related weakness is
visual selection, knowing which chart type best communicates a specific
finding and when to use it.

2.  **Do you think inferential statistics are adequate to come to a
    conclusion regarding whether a data science project has been
    successful or not? **

Inferential statistics are necessary but not sufficient on their own.
Strong metrics give stakeholders the confidence to trust a model\'s
outputs, and without statistically sound results no responsible decision
should be made. However, the true measure of success for any data
science project is real-world impact. A model that performs well
statistically but is never used, misunderstood by its audience, or fails
to change anything in practice has not truly succeeded. Success means
the findings are credible enough to be acted upon and consequential
enough to shift outcomes in the real world, whether that is a policy
decision, a business change, or an improvement in people\'s lives.
Inferential statistics are the foundation of that credibility, but they
are the starting point, not the finish line.

3.  **Which successful real-world data science projects would you be
    interested in being a part of? **

I would be most interested in working at the intersection of
agricultural data science, finance, and economics in South Africa. While
data science is applied in agriculture through technology like precision
farming and smart equipment, publicly available agricultural datasets,
especially those covering the financial and economic dimensions of
farming, remain far less accessible than datasets in fields like health
or finance. This project was a direct reminder of that reality. Finding
relevant, granular agricultural data for South Africa required
significantly more effort than it would have in other domains, and
provincial-level data was not available at all. I want to use my
mathematical and statistical skills in this space precisely because the
data infrastructure is still developing, and there is meaningful work to
be done in building the kind of analytical foundation that can inform
investment decisions and contribute to rural livelihoods and policy
planning.

4.  **Do you believe good feature engineering can overcome issues of
    poor data quality? **

I do not believe so, and this project illustrated why. A key limitation
was the inability to conduct provincial-level analysis. The FAOSTAT and
World Bank datasets aggregate everything to national level, and no
amount of feature engineering could manufacture provincial granularity
that was never captured in the source data. Feature engineering can
enrich and transform existing data, but it cannot create information
that was never collected. When the core limitation is a gap at the point
of data collection, better data is the only real solution. Feature
engineering and data quality are complementary, not substitutable.

5.  **Do you believe that in the age of agentic systems and large
    language models that fundamental data science principles are still
    relevant? **

Fundamental data science principles are still relevant and arguably more
important now, because large language models can produce outputs that
look correct but are not. This project provided a direct example. When
AI tools were used to generate visualisations for Part C, the charts
produced were inconsistent with the actual project data. I identified
this only because I had a grounded understanding of the data and what
the results should look like. Without that foundation, those errors
would have gone undetected. LLMs can misrepresent relationships and
produce plausible but incorrect conclusions. A strong background in
statistics, data principles, and critical evaluation is precisely what
makes it possible to use these tools responsibly.
