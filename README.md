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

Format of source data is csv. 

We cleaned and integrated 5 years (2013-2018) of census data on poverty rate by race and county, data on police killing cases, as well as city budgets, and we joined all three datasets carefully by county. 


## GCP Solution
For this analytical project, we have needs in data storage, data cleaning, query, data visualization and exploration, computation, and presentation. Luckily, GCP and Google products provided a whole ecosystem for that.

The best part of using Google products all the way is, **collaboration**. No matter at which stage of the analysis we are, we can easily sync with our own team members. 

And that is extremely important for a **virtual** hackathon like ours. 


We used the following products: 

### GCP BigQuery
**For Data storage, process, and querying**

Data are imported, stored and transfomred in Google BigQuery, as the data is relational and highly structural.

As a team, the project let us always sync with the latest datasets. 

Even though the datasets are huge, BigQuery takes little time to process each query, leaving us more time to do the analysis. 

User friendly, BigQuery has many features that save data wranglers' time and efforts, including auto correlation and click to select. Meanwhile, it can be connected to almost all the GCP product seamlessly, such as google colabratory. 

![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/BigQuery.png?raw=true)

### Data Studio 
**For data visualization and exploration**

Since all our data is stored in Big Query, it is very convenient for us to do EDA (Exploratory analysis) on Data studio as it can extract directly from BigQuery and put charts from multiple sources on the same report.

We used plots to examine the data distribution, and mark variables with obvious patterns.  
 
![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/Data%20Studio.png?raw=true)


### GCP AutoML API,  Colaboratory and Notebooks API  
**For modeling collaboration**

#### AutoML API
First, we used **AutoML API** to generate a **benchmark** of modeling in a fast and efficient manner. It is very easy to use -  just import from Big query, select target column and let GCP works its magic. 

[Evaluating a model]
![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/AutoML%20test.png?raw=true)

#### Colaboratory
Then, we built the prorotype of our own customized model using **Colaboratory**, which gives more flexibility to transform data such as log or data split. Comparing with the result from **AutoML API** as a reference, we can be more confident and critizing about our own model.

[Evaluating a model]
![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/Colab.png?raw=true)

#### Notebooks API
At last, while iterating the model, **Notebooks API** gives the best experience as it uses Jupyter format and can directly commits to Github. And on top of that we can configurate the computing power based on our needs. 


*Creating a new instance*
![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/AI%20Platform%20-%20Notebook%20Instance.png?raw=true)

*Running a model*
![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/AI%20Platform%20-%20Notebook.png?raw=true)

*Pushing a commit*
![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/AI%20Platform%20-%20Git%20Push.png?raw=true)


### Google Meet and GSuite
**For communication and story telling**

With only 24 hours in our hand to finish the hackathon, our team needs to stay online communicating with each other most of the time. Google Meet as a free tool provides unlimited time length and great video quality for screen sharing. 
Google slide and Google Drive are also great collaboration tool to share updates in real time manner. 
![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/Google%20Slide.png?raw=true)


## Model Performance

### AutoML API 
The R square of this AutoML model is up to **0.06**. The top 3 important features are percentage of black people population in the county,  percentage of white people population in the county,poverty rate of pacific people.
![alt text](https://github.com/Mengsha-Li/gcphackathorn_superace/blob/master/GCP%20Screenshots/AutoML%20percent%20result.png?raw=true)


### Treatment Effects Lasso: Double-Lasso Regression

Our team used Double-Lasso Regression for the analysis because it's a powerful algorithm to explore **causality** in the presence of a high number of controls (http://economics.mit.edu/files/7610). 

One thing we did that is very important here is we controled how we transform the data. For example, we put a log on the population number when regressing against black killing rate. The other thing is that we used **bootstrap** method to produce a 95% **confidence interval**

From 1st stage of lasso regression, poverty of each race, such as black and hispanic, can be strongly explained by variables like education, gender ratio and employment rate. From 2nd stage of lasso regression, we keep 79 variables and have a strong R-square value of 0.18 (the average of multiple models). The bootstrap methods shows there is significant effect from the education, unemployment on number of killings for each race.
