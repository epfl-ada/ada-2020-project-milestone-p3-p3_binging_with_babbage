# Title: Show me your plate and I tell you who you are

---

### Abstract 

The Paper introduces a novel dataset and with it explores the interrelations of nutrion and health. This utilizes the easy association between the Tesco data and aviable census data, which we want to extend on to explore to see if food is a dividing factor or a great unifier in a society.
We propose to combine the data set with aviable census data to explore relationships between socie-economic factors - such as wealth, education, ethnicity and cultural background -, and nutrion.
The association to the Greater London area allows us to explore the inter-relation between nutrion and other census data in a socie-economically diverse metropolitian area.  
This association also allows us to explore geodata based visaulization and to make a possibly interactive Map/s of London, that can be explored. 

While the paper explores the general Twitter graph properties, we propose to study if we can detect political division in the graph.
To do so, we propose to build an additional dataset with US politicians' Twitter handles and political alignments, and assign their corresponding nodes in the Twitter graph an appropriate label (e.g. "democrat" or "republican").
We will then run a community detection algorithm on the Twitter graph of followers, and see whether we can detect political clusters and their shapes, and to what extent they may be connected.
Since visualizing the full graph may be challenging due to its size, we may have to find alternative methods to study the result.
This would allow us to understand a small part of the political landscape, and reflect on how it reflects or affects the real landscape, and how that can be improved (for example, by encouraging more cross-party communication).

--- 

### Research Questions

A list of research questions you would like to address during the project.

- Who is a Tesco customer, can we find difference in areas were Tesco operates dominantly? 
- Is there a significant difference in nutrients, both individual and in their distribition between different cultural groups? 
- What impact do different socie-economic circumstances have on calories, nutrients and nutrient diversity? 
- Can we train a predictive model that is able to predict socio-economic facts about an area based on nutrion? 
- How does purchase behavior change over the year, is there a change in consumption behavior observable and linkable to different strata 
---

### Proposed dataset

List the dataset(s) you want to use, and some ideas on how you expect to get, manage, process, and enrich it/them. Show us that you've read the docs and some examples, and that you have a clear idea on what to expect. Discuss data size and format if relevant. It is your responsibility to check that what you propose is feasible given the datasets at hand.

- The [London Data Store](https://data.london.gov.uk/) acts as a Candy Shop, which provides a near infinite supply of possibly interesting data sets, which we could use for our analysis. Some interesting datasets for [LSOA](https://data.london.gov.uk/dataset/lsoa-atlas), [MSOA](https://data.london.gov.uk/dataset/msoa-atlas), [Wards](https://data.london.gov.uk/dataset/ward-profiles-and-atlas), and [Boroughs](https://data.london.gov.uk/dataset/london-borough-profiles) feature many important core socio-economic informations about an area, such as Household income, Income Support and JobSeekers Allowance claimant rates, population density, household composition, religion, ethnicity, employment and economic activity, and median area incomes. The data is cleary annotated and after a first inspection seems to be nearly complete, well organised and accessible. The sizes of the dataset don't exceed 6 mb each thus we can easily handle them on our personal ~~lapwarmer~~ laptop. (Bob does not need to fear the bill from the EPFL Computation Cluster). 

- To acquiere geodata useable for the timeframe of data collection - census boundries in the UK seem to follow new age trends and are in constant flow - we currently use following [repository](https://github.com/martinjc/UK-GeoJSON), however we are also searching alternative, possibly more [offical](https://geoportal.statistics.gov.uk/), sources. The Data set is organised based on the Identifiers for the different Census areas, and after filtering out all unnecessary information we are left with around 50 mb of data, from over a Gigabyte for the full UK data set. To make later processing even easier we aim to package it both as .geojson/.json and .pkl files.

Using the former, we already tested it and indeed were able to recreate a London in its natural habitat.

Interactive Plotly Plot             |  Geopandas Plot
:-------------------------:|:-------------------------:
<img src='https://github.com/epfl-ada/ada-2020-project-milestone-p3-p3_binging_with_babbage/blob/master/Pictures/0dd39927-7cb6-4a22-8530-03d8d00d9d51.png' width = 800 height = 400>  |<img src='https://github.com/epfl-ada/ada-2020-project-milestone-p3-p3_binging_with_babbage/blob/master/Pictures/38576432-655a-4774-88a9-e03c02ff0898.jfif' width = 800 height = 400>

---


### Methods

The 

---

### Proposed Timeline

- The amuse-gueule (Setting up the Enviroments and making sure our tools are up-to-date and ready for the tasks)
- The bread and butter (Data Loading, Cleaning and Pre-Processing)
- The entrée ()
- The main dish ()
- The side dish ()
- The dessert (Making it a coherent data story)
- The cherry on top (Exploring more advanced visualization of the Data, to allow interactive exploration of the results)

---

### Organization within the team

The amuse-geule was pre-prepared by Sous-Chef Luca and Michael. We setup the enviroments we need for processing and later visualization, with an initial struggle. Addionally we acquiered data sets, in this instance GeoJson that we requiere for the later planned visualization. 




The easy GeoPandas Enviroment Setup: 

<p align="center">
<img src='https://imgs.xkcd.com/comics/python_environment.png'> <br>  <i> The Python environmental protection agency wants to seal it in a cement chamber, with pictorial messages to future civilizations warning them about the danger of using sudo to install random Python packages. </i>
</p>





---


### Questions for TAs

Do our semi-serious or humorous texts annoy you or do they lighten up the monotony of looking at 5 times the same project? Should we continue in the more casual style or become more laconic and embrass our inner german-ness? We can stop ... Promise!

---

#### Rejected Working Titles: 

- <b>Between Grease and flat-nose Geezer:</b><i> A look at the effect of socie-economic realities on nutrion in Greater London  </i>
- <b>Luv a Pie, Luv ma Pub, Luv ma Tesco:</b><i> Nutrion and cultural realities in Greater London  </i>
- <b>The Pots of London:</b><i> A in-depth look beyond Cumberland Sausage and Tikka Marsalla  </i>
- <b>TEXIT NOW:</b><i> Why are there no Tescos in Southern London?[$^1$]</i>
- Jazzing it up in London <i>with Prof. Bob</i> 
