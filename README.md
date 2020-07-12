# Google Cloud Hackathon
## Team Super Ace

[Andrew Jing](https://github.com/andrewjing404)

[Breno Albuquerque](https://www.linkedin.com/in/brenoea/)

[Jacqueline Huang](https://github.com/JacquelineHSH)

[Maxine Li](https://github.com/Mengsha-Li)



## Problem Overview
Police disproportionately kills people of color. Comparing to white people, Hispanics are 1.3x more likely to be killed, native American 1.5x, black people is 2.6x, and Pacific Islanders are 3.7x.

**THE FACT ITSELF IS THE PROBLEM, no matter what's the cause.**

We want to use our analytical skills and explore how solving some of the social injustice might contribute to the resolution of police killing. 

We want to explore how poverty, education, and employment affect police killing. 

Meanwhile, we are fully conscious of the assumptions in the analysis and limitations in the data.

## Data Gathering Process and Storage Option
Source of data:
- [United States Census Bureau](https://www.census.gov/ "United States Census Bureau")
- [Mapping Police Violence](https://mappingpoliceviolence.org/ "Mapping Police Violence")
- [Lincoln Institue of Land Policy](https://www.lincolninst.edu/)

Format of source data is csv. Data are imported and stored in Google BigQuery, as data are relational and highly structural.

We cleaned and integrated 5 years (2013-2018) of census data on poverty rate by race and county, data on police killing cases, as well as city budgets, and we joined all three datasets carefully by county. 


## GCP Solution
For this analytical project, we have needs in data storage, data cleaning, query, data visualization and exploration, computation, and presentation. Luckily, GCP and Google products provided an whole ecosystem for that.

We used : 
### GCP BigQuery
**For Data storage, process, and querying**

As a team, the project let us always sync with the latest datasets. Even though the datasets are huge, BigQuery takes little time to process each query, leaving us more time to do the analysis. User friendly, BigQuery has many features that save data wranglers' time and efforts, including auto correlation and click to select. Meanwhile, it can be connected to almost all the GCP product seamlessly, such as google colabratory. 


![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/BigQuery.png?raw=true)

### Data Studio 
**For data visualization and exploration**

  Since all our data is stored in Big Query, it is very convenient for us to do EDA (Exploratory analysis) on Data studio as it can extract directly from BigQuery and put charts from multiple sources on the same report. 
 
![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/Data%20Studio.png?raw=true)


### GCP AutoML API,  Colaboratory and Notebooks API  
**For modeling collaboration**

First, we used AutoML to generate a benchmark of modeling in a fast and efficient manner. 
Then, we built the prorotype of our own customized model using Colab, which supports multiple coding language. Comparing with the result from AutoML as a reference, we can be more confident about our own model.

At last, while iterating the model, Notebooks API gives the best experience as we can use it to directly commits to Github and share among team members.

*[GCP AutoML API]* Evaluating a model
![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/AutoML%20test.png?raw=true)

*[GCP Notebook API]* Creating a new instance
![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/AI%20Platform%20-%20Notebook%20Instance.png?raw=true)

*[GCP Notebook API]* Running a model
![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/AI%20Platform%20-%20Notebook.png?raw=true)

*[GCP Notebook API]* Pushing a commit
![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/AI%20Platform%20-%20Git%20Push.png?raw=true)


### Google Meet and GSuite
**For communication and story telling**

With only 24 hours in our hand to finish the hackathon, our team needs to stay online communicating with each other most of the time. Google Meet as a free tool provides unlimited time length and great video quality for screen sharing. 
Google slide and Google Drive are also great collaboration tool to share updates in real time manner. 
![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/Google%20Slide.png?raw=true)



## Model Performance

### AutoML API 
![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/AutoML%20test.png?raw=true)
The R square of this AutoML model is up to 90%. The top 3 important features are population of black people in the county, number of unemployment, population of people not graduated from high school, which could mean that the black community size, unemployment and education are three aspects influencing the police killing. 


### Treatment Effects Lasso: Double-Lasso Regression


Our team used Double-Lasso Regression for the analysis because it's a powerful algorithm to explore causality in the presence of a high number of controls (http://economics.mit.edu/files/7610). From 1st stage of lasso regression, poverty of each race, such as black and hispanic, can be strongly explained by variables like education, gender ratio and employment rate. From 2nd stage of lasso regression, we keep 79 variables and have a strong R-square value of 0.9999. The bootstrap methods shows there is significant effect from the poverty rate on number of killings for each race, but the effect is very close to zero
