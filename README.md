# Google Cloud Hackathon
## Team Super Ace
## Problem Overview
Police disproportionately kills people of color. If you are a black American, then you would be 2.6X more likely to be killed by police than white people; for Hispanic and Latino Americans, that's 1.5X.

**No matter what's the cause, the FACT that police disproportionately kills people of color itself IS THE PROBLEM.**

We want to use our analytical skills and the power of cloud computing to explore alternative solutions to this issue, as it's relative clear that educating police on shooting bias didn't solve the problem.

We want to explore alternative solutions to this problem. For example, how reducing poverty, reallocating public spendings, improving education would improve the situation.

<iframe src="https://public.tableau.com/profile/andrew.jing7885#!/vizhome/PoliceKilling/Dashboard1?:embed=yes&:display_count=yes" width = '650' height = '450'></iframe>



Furthermore, besides black Americans, we also want to pay more attention to other non-white races such as Hispanic Americans. As we see more and more Hispanic immigrants, if the systematic police killing towards them can't be solve quickly, we would only see more and more Hispanic died.

Meanwhile, we are fully conscious of the limitations and implications in our analysis.

## Data Gathering Process and Storage Option
Source of data:
- [United States Census Bureau](https://www.census.gov/ "United States Census Bureau")
- [Mapping Police Violence](https://mappingpoliceviolence.org/ "Mapping Police Violence")

Format of source data is csv. Data are imported and stored in Google BigQuery, as data are relational and highly structural.

## GCP Solution
For this analytical project, we have needs in data storage, data cleaning, query, data visualization and exploration, computation, and presentation. Luckily, GCP and Google products provided an whole ecosystem for that.

We used GCP BigQuery for data storage, process, and query;
We used Data Studio for data visualization and exploration;
We used AutoML and Colab for model training;
We used Meet and GSuite for meeting and drafting presentation.

## Model Performance
We used Double-Lasso Regression for the analysis because it's a powerful algorithm to explore causality.

