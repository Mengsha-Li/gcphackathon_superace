# Google Cloud Hackathon
## Team Super Ace
## Problem Overview
Police disproportionately kills people of color. If you are a black American, then you would be 2.6X more likely to be killed by police than white people; for Hispanic and Latino Americans, that's 1.5X.

**No matter what's the cause, the FACT that police disproportionately kills people of color itself IS THE PROBLEM.**

We want to use our analytical skills and the power of cloud computing to explore alternative solutions to this issue, as it's relative clear that educating police on shooting bias didn't solve the problem, and is also hard to quantify the action.

We want to explore alternative solutions to this problem.
Here we mainly focus on several aspects, for example, how poverty, public spendings, education have impacted police killing. If the data confirms our assumption, then there can be actionable suggestions, such as reallocating public spending to improve the situation.

Furthermore, besides black Americans, we also want to pay more attention to other non-white races such as Hispanic Americans. As we see more and more Hispanic immigrants, if the systematic police killing towards them can't be solve quickly, we would only see more and more Hispanic suffer from the same situation black people are facing.

Meanwhile, we are fully conscious of the limitations and implications in our analysis.

## Data Gathering Process and Storage Option
Source of data:
- [United States Census Bureau](https://www.census.gov/ "United States Census Bureau")
- [Mapping Police Violence](https://mappingpoliceviolence.org/ "Mapping Police Violence")
- [Lincoln Institue of Land Policy](https://www.lincolninst.edu/ "Lincoln Institue of Land Policy")
Format of source data is csv. Data are imported and stored in Google BigQuery, as data are relational and highly structural.

We cleaned and integrated 5 years (2013-2018) of census data on poverty rate by race and county, data on police killing cases, as well as city budgets, and we joined all three datasets carefully by county. 


## GCP Solution
For this analytical project, we have various needs in data storage, data cleaning, query, data visualization and exploration, computation, and presentation. Luckily, GCP and Google products provided an whole ecosystemm, end-to-end, for us.

We used : 
### GCP BigQuery
**For Data storage, process, and querying**

Sharing the same project, all our team members can stay updated to the latest data without worrying about syncing. 
Our datasets are huge. However, Bigery takes little time to process each query, leaving us more time to do the analysis.
Most importantly, it can be connected to almost all the GCP product seamlessly, making it very easy to use multiple tools.

![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/BigQuery.png?raw=true)

### Data Studio 
**For data visualization and exploration**

Directly extracting data from BigQuery, it is very convenient for us to do EDA (Exploratory analysis) on one report file with data from multiple sources. It is very efficient and also provides a complete overview. 
 
![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/Data%20Studio.png?raw=true)


### GCP AutoML API and Colaboratory 
**For modeling**
AutoML is extremely intuitive to use and reliable, so it is a perfect tool for us to generate a model benchmark with AutoML in a fast and efficient manner. 
Then, we built our own customized model using Colab, which supports multiple coding language. 
Comparing with the result from AutoML, we are very confident about our own model.
![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/AutoML%20test.png?raw=true)


### Google Meet and GSuite
**For communication and story telling**

With only 24 hours in our hand to finish the hackathon, our team needs to stay online communicating with each other most of the time. Google Meet as a free tool provides unlimited time length and great video quality for screen sharing. 
Google slide and Google Drive are also great collaboration tool to share updates in real time manner. 
![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/Google%20Slide.png?raw=true)



## Model Performance
We used Double-Lasso Regression for the analysis because it's a powerful algorithm to explore causality.

