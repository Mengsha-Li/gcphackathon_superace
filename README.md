# Google Cloud Hackathon
## Team Super Ace
## Problem Overview
Police disproportionately kills people of color. If you are a black American, then you would be 2.6X more likely to be killed by police than white people; for Hispanic and Latino Americans, that's 1.5X.

**No matter what's the cause, the FACT that police disproportionately kills people of color itself IS THE PROBLEM.**

We want to use our analytical skills and the power of cloud computing to explore alternative solutions to this issue, as it's relative clear that educating police on shooting bias didn't solve the problem.

We want to explore alternative solutions to this problem. For example, how reducing poverty, reallocating public spendings, improving education would improve the situation.

Furthermore, besides black Americans, we also want to pay more attention to other non-white races such as Hispanic Americans. As we see more and more Hispanic immigrants, if the systematic police killing towards them can't be solve quickly, we would only see more and more Hispanic died.

Meanwhile, we are fully conscious of the limitations and implications in our analysis.

## Data Gathering Process and Storage Option
Source of data:
- [United States Census Bureau](https://www.census.gov/ "United States Census Bureau")
- [Mapping Police Violence](https://mappingpoliceviolence.org/ "Mapping Police Violence")

Format of source data is csv. Data are imported and stored in Google BigQuery, as data are relational and highly structural.

## GCP Solution
For this analytical project, we have needs in data storage, data cleaning, query, data visualization and exploration, computation, and presentation. Luckily, GCP and Google products provided an whole ecosystem for that.

We used : 
### GCP BigQuery for data storage, process, and query
As a team, the project let us always sync with the latest datasets. Even though the datasets are huge, BigQuery takes little time to process each query, leaving us more time to do the analysis.

### Data Studio for data visualization and exploration
  Since all our data is stored in Big Query, it is very convenient for us to do EDA (Exploratory analysis) on Data studio as it can extract directly from BigQuery and put charts from multiple sources on the same report. 
  
### AutoML and Colab for model training
We use AutoML to generate a benchmark of modeling in a fast and efficient manner. Then, we built our own customized model using Colab, which supports multiple coding language. 
Comparing with the result from AutoML, we are very confident about our own model.

### Google Meet and GSuite for meeting and drafting presentation
With only 24 hours in our hand to finish the hackathon, our team needs to stay online communicating with each other most of the time. Google Meet as a free tool provides unlimited time length and great video quality for screen sharing. 
Google slide and Google Drive are also great collaboration tool to share updates in real time manner. 


## Model Performance
We used Double-Lasso Regression for the analysis because it's a powerful algorithm to explore causality.

