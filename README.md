# Google Cloud Hackathon
## Team Super Ace
## Problem Overview
Police disproportionately kills people of color. If you are a black American, then you would be 2.6X more likely to be killed by police than white people; for Hispanic and Latino Americans, that's 1.5X.

**No matter what's the cause, the FACT that police disproportionately kills people of color itself IS THE PROBLEM.**

We want to use our analytical skills and the power of cloud computing to explore alternative solutions to this issue, as it's relative clear that educating police on shooting bias didn't solve the problem.

We want to explore alternative solutions to this problem. For example, how reducing poverty, reallocating public spendings, improving education would improve the situation.

<div class='tableauPlaceholder' id='viz1594515248672' style='position: relative'><noscript><a href='#'><img alt=' ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Po&#47;PoliceKilling&#47;Dashboard1&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='PoliceKilling&#47;Dashboard1' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Po&#47;PoliceKilling&#47;Dashboard1&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en' /><param name='filter' value='publish=yes' /></object></div>                <script type='text/javascript'>                    var divElement = document.getElementById('viz1594515248672');                    var vizElement = divElement.getElementsByTagName('object')[0];                    if ( divElement.offsetWidth > 800 ) { vizElement.style.width='1000px';vizElement.style.height='827px';} else if ( divElement.offsetWidth > 500 ) { vizElement.style.width='1000px';vizElement.style.height='827px';} else { vizElement.style.width='100%';vizElement.style.height='727px';}                     var scriptElement = document.createElement('script');                    scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                    vizElement.parentNode.insertBefore(scriptElement, vizElement);                </script>

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

