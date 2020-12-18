# Title: Show me your plate and I tell you who you are



[To the Data Story](https://fierceeagle.github.io/)




---

### Abstract 
The paper introduces a novel dataset of Tesco grocery stores food purchases in greater London over a whole year and uses it to explore the interrelations of nutrition and health. The dataset connects Tesco data with geographically census data down to Lower Super Output Areas. We propose to use this data together with available census data to explore connections between food habits and socio-economic factors such as *wealth, education, ethnicity* and *cultural background*. The association to the greater London area allows us to study these connections in a socio-economically diverse metropolitan area. It also offers a great opportunity for us to experiment with geodata based visualizations and to create (an) interactive map(s) of London that can then be explored by others. 

--- 
### Related Work

A few related studies have been conducted. However, these include mainly survey studies, not observational results: 

- [Socioeconomic inequalities in the healthiness of food choices: Exploring the contributions of food expenditures](https://www.sciencedirect.com/science/article/pii/S0091743516300676?via%3Dihub)
- [Social class differences in food consumption: The explanatory value of permissiveness and health and cost considerations](https://tinyurl.com/yxuof5jr)
- [Socio-economic dietary inequalities in UK adults: an updated picture of key food groups and nutrients from national surveillance data](https://tinyurl.com/y388nyyc)
- [Large-scale and high-resolution analysis of food purchases and health outcomes](https://epjdatascience.springeropen.com/articles/10.1140/epjds/s13688-019-0191-y)
---

### Research Questions

A list of research questions we would like to address during the project:

- Who is the targeted Tesco customer? Since Tesco stores are not uniformly scattered across London, can we identify what makes an area an operational target for Tesco? 
- Is there a significant difference in nutrients composition, both on an individual level and in their distribution between different socio-economic or cultural groups? 
- Can we train a predictive model that is able to predict socio-economic facts about an area based on nutrition? 
- How does purchasing behavior change over the year? Is there a change in consumption behavior observable and linkable to different strata? (*Note: Cut down due to time constraint and missing group member participitation*)

---

### Proposed dataset
- The data from the paper contains a list of food products and their corresponding food category and a table of the average food product in each area, showing its weight, energy, nutrients, categorization into product categories and additionally information from area censi like the population, population density and age distribution, to name a few. Addionally it addresses its representativness towards the population in the area by providing the ratio between inhabitants and customer base in an area. This allows to address questions of low representativness in certain aggregation granularitites, especiallly LSOA. 

- The [London Data Store](https://data.london.gov.uk/) acts as a Candy Shop, which provides a near infinite supply of possibly interesting data sets, which we could use for our analysis. Some interesting datasets for [LSOA](https://data.london.gov.uk/dataset/lsoa-atlas), [MSOA](https://data.london.gov.uk/dataset/msoa-atlas), [Wards](https://data.london.gov.uk/dataset/ward-profiles-and-atlas), and [Boroughs](https://data.london.gov.uk/dataset/london-borough-profiles) feature many important core socio-economic infromation about an area, such as *household income, income support and jobseekers allowance claimant rates, population density, household composition, religion, ethnicity, employment and economic activity, and median area incomes*. The data is clearly annotated and after a first inspection seems to be nearly complete, well organised and accessible, although in some instances rather ingranual (The ethnic grouping lets us suspect the census planners of having a long [family history](https://i.redd.it/otyd2m356wp21.jpg) of being let loose with just a ruler on maps). Some issues such as inflation might need to be addressed and some further background research needs to be done, for example how we could discretize certain data based on area population following UK standards, such as for example <i> lower/middle/upper </i> class or the more refined distingiouns made in the [Great British Class Survey](https://en.wikipedia.org/wiki/Great_British_Class_Survey). The sizes of the dataset don't exceed 6 mb each thus we can easily handle them on our personal ~~lapwarmer~~ laptop and Bob does not need to fear the bill from the EPFL Computation Cluster. We addionally will crawl further through the aisle of the data store to find additional interesting and even more specific data sets, when we might want to dive deeper into a specific sub-area. 

- To acquire geodata usable for the timeframe of data collection - census boundaries in the UK seem to follow new age trends and are in constant flow - we currently use the following [repository](https://github.com/martinjc/UK-GeoJSON). However, we are also searching for alternative, possibly more [official](https://geoportal.statistics.gov.uk/), sources. The dataset is organised based on the identifiers for the different census areas, and after filtering out all unnecessary information, we are left with around 50 mb of data, from over a Gigabyte for the full UK data set. To make later processing even easier we aim to package it both as .geojson/.json and .pkl files. Addionally, we can extract current store locations from the UK's [Foods Standards Association](https://ratings.food.gov.uk/open-data/en-GB), this however only allows for a view on current data, as historic data (from 2015) seems hard to aquiere at the current state.   

Using the former, we already tested it and indeed were able to recreate a London in its natural habitat.

Interactive Plotly Plot             |  Geopandas Plot
:-------------------------:|:-------------------------:
<img src='https://github.com/epfl-ada/ada-2020-project-milestone-p3-p3_binging_with_babbage/blob/master/Pictures/0dd39927-7cb6-4a22-8530-03d8d00d9d51.png' width = 800 height = 300>  |<img src='https://github.com/epfl-ada/ada-2020-project-milestone-p3-p3_binging_with_babbage/blob/master/Pictures/38576432-655a-4774-88a9-e03c02ff0898.jfif' width = 800 height = 300>


<p align="center">
<i> The plot allows you to appreciate the abstract beauty of Slough and the home counties as it should be, from hundreds of miles away and free from any kind of lower stimuli, such as smell or sight. </i>
</p>

---

### Methods
As the data is in a prestine state, without nearly any missing information, our main issue in regard to introductive wrangling is getting an overview what columns are provided in the dataframe and to make the naming of these more accesible to usage. Pre-processing needs to be handled on a case for case basis depending on the models we want to use. 

To start of we will use the explorative **statistical techniques** covered in the beginning of the lecture to explore and describe the acquired data. We for example would orient ourselves on **correlation analysis** and **regression** as already used in the original paper, to discover interrelationship between nutrients and products and socio-economic factors, such as education, household income, ethnicity and religion. To generate a predictive model, we would consider using models that were introduced in the lecture and that provide robustness and ease-of-use. In this regard, we consider one of the ensemble models, either **boosted trees** or **random forests**. As the data and our proposed goal touch on sensitive topics, we want to also address the issue of the black-box model that arises by using complex ensemble models and explore alternatives that present more transparent results with a more direct interpretability. As such we want to explore the results of **decision trees** and **association rule mining** and compare their interpretability and performance against the former ensemble models. 

---

### Proposed Timeline

- The Mise en place: *Setting up the environments and making sure our tools are up-to-date and ready for the tasks.*
- The Amuse-Gueule: *Preparing the Jekyll Github Page and the GeoData*
- The Bread and Butter: *Data Loading, Cleaning and Pre-Processing.*
- The Entrée: *Analysing the Data based on Correlation and Regression.*
- The Main Dish: *Training a more refined predictive model.*
- The Side Dish: *Finding an explainable model.* 
- The Dessert: *Making it a coherent data story.*
- The Cherry on Top: *Exploring more advanced visualization of the Data, to allow interactive exploration of the results.*

<p align="center">
<img src='https://github.com/epfl-ada/ada-2020-project-milestone-p3-p3_binging_with_babbage/blob/master/Pictures/On_The_First_Day_Of_Chirstmas.png'>
</p>

---

### Organization within the team
With respect to team organization, we follow a *thematically consistent* system derived from the UK parliamentary system, although from one of its previous [iterations](https://en.wikipedia.org/wiki/Personal_Rule). 

The Amuse-Gueule was pre-prepared by Sous-Chefs Luca and Michael. We set up the environments we need for processing and later visualisation, with an initial struggle seen below. Addionally we acquired datasets, in this instance geojsons that we require for the later planned visualisation. For the final report presentation we also already set up a [github.io](https://fierceeagle.github.io/) page. As a Team, we additionally conducted data loading and initial checks and conducted research into futher data sources.

As for future planning, we expect that the model training and initial analyses will be conducted by every team member individually with the common goal to compare different approaches and double check results. The side-projects, i.e GeoViz and explainable models, are conducted by Luca and Michael. For the final report we want to hold a [session](https://xkcd.com/323/) to develop a shared data story joining the individual results and achieving [peak](https://xkcd.com/1513/) [code](https://xkcd.com/1695/) [quality](https://xkcd.com/1833/).

---

### Project Contributions

Michael             |  Luca  
:-------------------------:|:--------------:
 Data Loading and Cleaning (50%) | Data Cleaning (50%) 
 Geo Data Processing (40%) | Preparing Geodata (60%)  
 Outlier Plotting and Removal | Custom Mapstyle using Mapbox
 Clustering and Labeling | Aesthetic Consistency and Colorcoding
 Tesco Location Scraping and Plotting | Plot Factory Enhancement and Consistency 
 Plot Factories (Bar, Map (75%), Multilayer Map (90%), 3D Plots (90 %), Heatmap, Feature Importance, Tree) | Donut and Sunburst (50%) 
 Donuts & Sunburst (50%) | Association Rule Mining, Filtering, Analysis 
 Website setup (30%) | Website 
 Correlation & Regression Analysis | 
 Ensemble Model Pipeline, Training and Analysis | 
 Decision Tree Pipeline, Training and Analysis | 
 Association Rule Mining Setup | 
 Data Story (Except Association Rule Analysis and Water Consumption) | 



--- 
### Questions for TAs

- Do our semi-serious or humorous texts annoy you or do they lighten up the monotony of looking at 5 times the same project? Should we continue in the more casual style or become more laconic and embrace our inner german-ness? We can stop ... Promise!

- We would like to use a little cross-pollination from the Distributed Information Systems lecture and use some of the methods introduced there, specifically associations rule mining, and would ask if this would be okay?

---

#### Warnings for weary Travelers : The *easy* GeoPandas Enviroment Setup

<p align="center">
<img src='https://imgs.xkcd.com/comics/python_environment.png'> <br>  <i> The python environmental protection agency wants to seal it in a concrete chamber, with <a href="https://en.wikipedia.org/wiki/Long-time_nuclear_waste_warning_messages"> pictorial messages to future civilisations </a> warning them about the danger of using sudo to install random Python packages. </i>
</p>

#### Rejected Working Titles: 

- <b>Between Grease and flat-nose Geezer:</b><i> A look at the effects of socio-economic realities on nutrition in Greater London. </i>
- <b>Luv a Pie, Luv ma Pub, Luv ma Tesco:</b><i> Nutrition and cultural realities in Greater London. </i>
- <b>The Pots of London:</b><i> An in-depth look beyond Cumberland Sausage and Tikka Masala. </i>
- <b>TEXIT NOW:</b><i> Why are there no Tescos in Southern London? </i>

<i> We apologize to any British person feeling personally attacked by our banter and low effort persiflage of your country, sue us in a European Court as long as you still can. - <b> Tick Tock </b> -. Tally Hoe! </i>
