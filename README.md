# Coursera_Capstone
![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/image1.png)
*Prepared by M. Boufous*
## The Battle of Neighborhoods - Paris


In this project we will be looking for **Suitable Locations in Paris for Business Activities**

This presentation document contains multiple parts :

- A description of the problem and a discussion of the background - Week 1

- A description of the data and how it will be used to solve the problem - Week 1

- Methodology and Exploratory Data Analysis - Week 2

- Inferences and Discussion - Week 2


## 1. Introduction : Discussion - Objective


**Locations for High Traffic and Best Suitable Areas in Paris France.**


**The Task in Hand :**

We will make data-driven decisions on Paris neighborhoods, locations that are **most suitable for certain specified activities** - we will specify our prefences later the way we are curious. This will be a major part of our decision-making process, the other being on the ground qualitative analysis of districts once this data and report are reviewed and studied.

Giving our project a clear **objective**, we will be looking for **high traffic areas** and **hot spots** where most people go for shopping, restaurants and entertainment. Moreover, we will seek for areas where **Tourists** spend most time in order to narrow our perimeter of **research for higher level of density**. **Foursquare data** will be very helpful in making data-driven decisions about where located the best of those areas.


**Criteria :**

Looking for the best locations for **high traffic**, can be similar to looking for areas where people usully got out to, or frequently use. Thus we can suggest to look for such locations in order to seek high traffic for a specified activity, Clothing Stores as an example, or any other activity.

Our data will strongly suggest that the best places are in fact areas that are near **French Restaurants, Coffee shops and Wine Bars**. Parisians are very social people that frequent these place often, so seeking high traffic in these locations is  something to consider and expect.

One can also think to target location know for **Artistic Activities** of which Paris is of high repution, these location can also be where most **Tourists** spend their time as they are the best to see and frequent. This can help us getting even **higher levels of traffic** for certain activities. This process can get us curious to check **the density of trending areas** within each neighborhood of Paris city, which can lead will me to try explore trending spots using the **Foursquare API**, if possible or other data in order to get insights about density of Neighborhoods of our research.

**The analysis** and **recommendations** for best suitable location for **hot spots** where to seek certain activities of our choice will focus on general districts with these establishments, not on specific addresses. Narrowing down the best district options derived from analysis allows for either further research to be conducted as well as advising who is concerned with the business of the chosen district.


**Why Data ?**

Without leveraging data to make decisions about where to seek high traffic areas locations,  one could spend countless hours walking around districts, consulting many tourist guides, real estate agents with their own district biases, and end up in yet another location that is not ideal.

Data will provide better answers and better solutions to this task.


**Outcomes :**

The goal is to identify **the best districts - Arrondissements -** to seek or choose for certain activities. The results will be translated in a simple form that will convey the data-driven analysis for the best locations for specified activities.

![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/image3.png)

## 2 . The Data Science Workflow : 


**Data Requirements :**

The main districts in Paris are divided into **20 Arrondissements Municipaux** (administrative districts), shortened to arrondissements.

The data regarding the districts in Paris needs to be researched and a suitable useable source identified. If it is found but is **not in a useable form, data wrangling and cleaning will have to be performed.**

**The cleaned data** will then be used alongside **Foursquare data**, which is readily available. Foursquare location data will be **leveraged to explore or compare districts** around Paris, **identifying the high traffic areas** where most people
go for shopping, dining and entertainment.

**The Data Science Workflow for Part 1 includes the following :**

- Outline the initial data that is required : District data for Paris including names, location data if available, and any other details required.

- Obtain the Data :
    - **Research** and find suitable sources for the district data for Paris.
    - **Access and explore** the data to determine if it can be manipulated for our purposes.

- Initial **Data Wrangling** and **Cleaning** : Clean the data and convert to a useable form as a dataframe.



**The Data Science Workflow for Part 2 includes the following :**

- Data Analysis and Location Data :
    - **Foursquare** location data will be leveraged to explore or compare districts around Paris.
    - **Data manipulation and analysis** to derive subsets of the initial data.
    - Identifying **the high traffic areas**, trending venues and the more suitable locations for certaine activities using **data visualisation** and **statistical analysis**.

- Visualization :
    - Analysis and plotting visualizations.
    - Data visualization using various mapping libraries.


- Discussion and Conclusions :
    - **Recomendations** and results based on the **data analysis**.
    - Discussion of any **limitations** and how the results can be used, and any **conclusions** that can be drawn.


## 2.1. Data Research - Preparation :

##### Arrondissements Municipaux for Paris CSV (administrative districts) file.

Paris is divided into **20 Arrondissements Municipaux** (or administrative districts), shortened to just arrondissements. They and normally referenced by the arrondissement number rather than a name.

Data for the arrondissements is necessary to select the most suitable of these areas.

Initially looking to get this data by **scraping** the relevent Wikipedia page (https://en.wikipedia.org/wiki/Arrondissements_of_Paris), fortunately, after much research, *this data is available on the web and can be manipulated and cleansed to provide a meaningful dataset to use.

Data from Open|DATA France: https://opendata.paris.fr/explore/dataset/arrondissements/table/?dataChart

Also available from Opendatasoft: https://data.opendatasoft.com/explore/dataset/arrondissements%40parisdata/export/

The Arrondissements dataset was downloaded from Paris|DATA France, then placed on the GitHub repository for the project : https://raw.githubusercontent.com/Bufucci/Coursera_Capstone/master/Arrondissements_Paris_data.csv

##### Importing Paris District Data :

![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/image2.png)

We now have located and imported the relevant data for the districts of Paris, and have constructed a dataframe.

Our business objective, strategy and methods to achieve our goal have been laid out, and a data workflow established.

Next up, we will **leverage Foursquare location data** to obtain data on **high traffic areas** and the more suitable location for a certain business activity - where most people go for shopping, restaurants and entertainment, as well as other activities and their corresponding trending spots - in all of the 20 districts.

The Battle of Neighborhoods continues in the next section.


## 2.2. Exploring Paris and Clustering Neighborhoods :

For this task i used the **geopy library** to get the latitude and longitude values of Paris in order to create, visualize, check a map of Paris and its principal neighborhoods.

The geographical coordinates of Paris France are 48.8566969, 2.3514616.

**Mapping Paris city** neighborhoods would look like follow :

![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/image4.png)

At this level, one can define his or her **Foursquare Credentials and Version** and start utilizing the **Foursquare API** to explore the neighborhoods and segment them into clusters based on their category or their venues corresponding more frequent categories.

After words, we can be more precise by selecting the most suitable neighborhoods for a certain activity or activities and find out the density of trending spots in each of them with respect to the concerned activities.


### Explore Paris Neighborhoods :

We create a function to repeat the same process to all the neighborhoods in order to **scrap the near-by venues from the centre of each neighborhood via the Foursquare API.** 

In this context, we will use the **Foursquare API** to explore neighborhoods in Paris city, after that i used explore function to get the *most common venue categories* in each neighborhood that i will use as a feature to group the neighborhoods into clusters. **K-means clustering algorithm** will be use to complete this task and the **Folium library** to visualize the neighborhoods **clusters** in Paris and the **matplotlib library** to visualize **violin plots** for venues categories **frequencies** which if of central interest in this project.

At this point, the database for paris venues result from the *Foursquare API Explore command*, with some **data structuring and wrangling**, is as following :


![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/image6.png)


As a first step exploring of Paris neighborhoods we get that there are **197 unique categories** are curated from all the returned venues. 

Also, **the number of venues** within each neighborhoods are reprensented in the following **Bar-Chart** :


![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/image5.png)


It can be useful to visualize Paris venues **categories Word-Cloud**. 
This will give us insight about categories returned by the **Foursquare API**.


![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/wc1.png)


We can see that some categories such **French Restaurants** and other categories, are **very frequent** within Paris venues categories.
We now have an idea about which categories to let-down looking for better representation as well as for better significance and maybe later for **hidden categories**. 

After some categories **wrangling** for hidden categories and for a better visualisation we can have a satisfying **Paris Word-Cloud** looking for more insights:

![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/wc2.png)


### Analysing Paris Neighborhoods :

Now that we have a **clean form of the foursquare data** of Paris venues and their categories we can try putting the neiborhoods on the scope and **explore the most frequent activity categories these neighborhoods provide**.

Afterwords we will be trying to **Cluster** our neighborhoods based on these **categories** in order to locate the best neighborhoods for each business activitie and **locate high traffic areas or more adequate locations** for certain groups of preferences or activity categories.

Taking **the mean of the frequency of occurrence** of each **category** within our **one-hot-encoding** dataframe, we can check for **the top N° most  frequent** categories for each Paris Neighbhood.

In this context, i created the new dataframe and **display the top 20 venues categories** for each Paris neighborhood, which i will use later to check clusters as well as the corresponding geographical caracteristics of Paris neighborhoods.

A dataframe for the top 20 venues categories :
![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/image8.png)

### Clustering Paris Neighborhoods :

In this section we will be clustering Paris neighborhoods. For this task we decide to run **k-means algorithm** to cluster the neighborhood into 5 clusters based on their **top 20 venues categories**.

We choose to cluster Paris city Neighborhoods to **5 clusters** out of 20 neighborhood which can be plausible or significant.

One can choose the most adequate number of clusters based on observations, or the number of neighborhood types on which we want to distribute/Cluster Paris Neighborhoods based on their most frequent corresponding activities.

To solve the ambiguity of which K to use for **K-Means Clustering** one can also proceed using **Dicision Trees** and dendrogram for better choice of number of clusters to use, or can base the choice on other methods such the **Elbow method**.

Lets examine our result neighborhood **clusters** in Paris City :

![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/image9.png)

#### Cluster 1 :
In Red color
![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/image10.png)

#### Cluster 2 :
In Purple color
![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/image11.png)

#### Cluster 3 :
In Light-Blue color
![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/image12.png)

#### Cluster 4 :
In Light-Green color
![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/image13.png)

#### Cluster 5 :
In Orange color
![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/image14.png)


Now lets say, The business types criteria we desire to have insights about are **French Restaurants**, **Coffee Shop** and **Wine Bars**. These are the venues categories types that we wants to have an **abundant density** of in the ideal high traffic or hot spots locations in Paris.

For this we can use our one-hot-encoding dataframe used for the above clustering results.

Our next step is now to look at **the frequency distribution of occurance** of the specified criteria **categories** for all the Paris neighborhoods, isolating the categorical venues.

In this context, we will use a categorical representation. Thus i've used **Violin Plots** from the **seaborn library** - it is a great way to *visualise frequency distributions* for each category. **Violin plots display a density estimation of the underlying distribution**.

![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/Distribution_Frequency_Venues_categories_1.png)


### *1st Observations* :

So as we can see from the analysis there are **9 neighborhoods to seek** - according to the criteria that they have the 3 specified venues in a great frequency (French Restaurants, Coffee Shops and Wine Bars).

They are as follows :
- 1 Arrondissement - Louvre
- 2 Arrondissement - Bourse
- 3 Arrondissement - Temple
- 4 Arrondissement - Hotel de Ville
- 5 Arrondissement - Pantheon
- 9 Arrondissement - Opera
- 10 Arrondissement - Entrepot
- 11 Arrondissement - Popincourt
- 18 Arrondissement - Buttes Montmartre


Let's take this further with some exploration and Inferential Analysis.

We have the **9 neighborhoods** that all include the venue category criteria specified for abundant activities we are seeking.

But if we included the **Clothing Store** venue category into the analysis, then we might be able to make some inferences based on the data, and domain knowledge or other informations, to **focus the list for our reseach**.

Adding the category  **Clothing Store** to the first specified criteria and rechecking our Violin plots :

![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/Distribution_Frequency_Venues_categories_2.png)


### *1st Inferences and Discussion : Chosen Neighborhoods - Results*

Inferential analysis using the data allow the list to be focussed to just **3 neighbourhoods** from the previous 9.

The reasoning being that if the **3 criteria** have been met - identifying neighbourhoods that are lively with **Restaurants, Coffee Shop and Wine Bars** - if seeking Clothing stores for example, adding **Clothing Stores** into the mix in the area is a **significant bonus**. Lets say having some of the same category of activities in the same area is a good thing,.

We increase **the criteria to include Restaurants, Coffee Shop, Wine Bars and Clothing Stores** - which narrows down and focuses the suggested districts for **the most suitable places** for such activities or for high traffic to be located.

So the final 3 prospective neighborhoods for most suitable locations are where 4 criteria are met:

- **Arrondissement 2, Bourse**
- **Arrondissement 3, Temple**
- **Arrondissement 4, Hotel de Ville**.

Now , let's take this to a next level in the next section.


## 2.3. Paris Hidden Activities Clustering :

At this level, we'll be clustering Paris Neighborhoods with respect to their hidden categories. As we saw above there are some activities that are very frequent and can prevent us to have better vision of some **less frequent** activities.

We can try to **Exclude** the **French Restaurants, Bars, Hotels** and other whole Paris omnipresent/most frequent activities or categories and recheck the clusters. This in order to have better insight about other hidden categories  selection of clusters based on other more significant category classes than the specified categories which seem evident to have all over Paris City Neighbours.

Note that we might have to **re-scale** our data for better clustering **after excluding these categories.**
    
Afterwords we would re-check our clusters and explore our cibling neighborhoods for trending spots if possible, and their density within their corresponding neighbourhoods. 

Otherwise, we can restrict to neighborhoods geographic **Density** as new criteria to have insights. We can define **Density** as the quotient of **neighborhoods Surface** to **the Number of corresponding venues**. 

We can try to make use of this to get insights about density of Neighborhoods in order to classify Neighbors/Clusters with respect to their **levels of density**.
    
To conclude one can choose, depending on his strategy, the most suitable locations in Paris for activities of his intrest.
    
For this, we'll have to proceed same as we did above. After the **one-hot-encoding, data wrangling and cleaning**, we end up with a dataframe to display **the top 20 venues hidden categories** :

![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/image15.png)


### Clustering Paris Hidden Categories :

Now we can Cluster another time Paris neighborhoods this time based on their **top 20 venues hidden categories**.
Same as before, we choose to cluster Paris city neighborhoods to **5 clusters** out of 20 district which can be plausible.

Examine result neighborhood **clusters** for **Hidden Categories** :

![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/image16.png)

Comparing the resuted clusters to the first clustering of Paris Neighborhoods **not much changed**, **3 clusters** have staid **the same**, while the left **2 clusters** - covering the whole **centre of Paris city** - have **crossed each other** this time with some small changes in their corresponding neighborhoods.

Recall the first Paris clusters map before :
![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/image9.png)


We can also examine our **new result neighborhood clusters** in Paris city. 

For example, **the first cluster** in Red color on the new Paris clusters map:

![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/image17.png)

Looking for more insights about Paris neighborhoods, we check for **Artistic and Tourism activities** in order to seek **higher level of traffic**, as these areas are usually **full of Tourists** which can give good insight about where to look for higher traffic levels.

At this level we'll be looking at a set of categories such : **Art Museum, Art Gallery, Theater**.

Same as before i will use a categorical representation, Violin Plots to display these categories frequency distributions and see where to seek for these activities :

![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/Distribution_Frequency_Venues_categories_3.png)


### *Observations*

So as we can see from the analysis there are many neighborhoods where to seek **Artistic Activities** mainly **Art Museum, Art Gallery and Theater** - according to the criteria that they have these 3 specified venues category in a great frequency.

The **first neighborhood** to seek these categories is the **8em Arrondissement** - that is not surprising as it corresponds to the **Elysee.**

Moreover, one can seek artistic activities in other Nieghborhoods corresponding to the centre of Paris City.
They are as follows:

- Arrondissement 1, Louvre
- Arrondissement 3, Temple
- Arrondissement 4, Hotel de Ville
- Arrondissement 6, Luxembourg
- Arrondissement 11, Popincourt

All these are distributed over two clusters concentrated  in the center of Paris City, especially arroud the river 'La seine' of Paris. Those are the Neighborhoods where one can seek Artistic/Touristic activity in Paris and can be considered where to seek higher levels of traffic areas.

lets recall what we found before for the criteria to include **Restaurants, Coffee Shop, Wine Bars and Clothing Stores** for where to seek Clothing stores as an example. The final 3 prospective neighborhoods for high traffic were:

- Arrondissement 2, Bourse
- Arrondissement 3, Temple
- Arrondissement 4, Hotel de Ville

Thus our choice can focus on **2 neighborhoods** as they correspond also for **Artistic/Touristic** criteria :

- **Arrondissement 3, Temple**
- **Arrondissement 4, Hotel de Ville**


We can try to order/choose between the two locations by looking at the distributions represented on their corresponding Violin Plots to compare their densities. 

Moreover, we will check their geographical densities. As i couldn't get data for trending spots, we can try to use the Density we defined at the start of this section and try to make use of the **surface of neighborhoods** as it can give us more insights for our objective study.

We can define **Geografic Density** as *the quotient of **Neighborhoods Surface to the Number of corresponding Venues**.*

Check the levels of **Density** within each neighborhoods are as following : 

![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/image18.png)
 
 we can say that **the Arrondissement 3 - Temple, has less available surface** per venue than **the Arrondissement 4 - Hotel de Ville**. 

This can be seen differently, we can look for more possibility of available locations in the Arrondissement 4 as it might deliver more liberty as we expect **the Arrondissement 3 - Temple** to be very **dense geographicaly** with **tiny spaces and very small stores** and given the distribution desity of target activities (**Violin Plots**), our choice favorise the **Arrondissement 4 - Hotel de Ville** as there is also **more geographic space available and higher frequencies**. 

### *2nd Inferences and Discussion : Chosen Neighborhoods - Results*

Finally, **my final order** would be to look as following :

- **First choice :  Arrondissement 4 - Hotel de Ville**, Blue color
- **Second choice : Arrondissement 3 - Temple.**, Red color

A **third alternative** is to look for the most suitable locations in **the area alining these two locations( Temple, Hotel-de-Ville) and in the direction of Arrondissement 8 - Elysee** as the Highest location for Artistic & Tourists.

By this, we are ready to interpret observations and make inferences in order to conclude, but before that let's check the Two **chosen Paris neighborhoods** a well as the **3rd alternative Arrondissement 8 - Les Champs Elysee** colored in Magenta.

![title](https://github.com/Bufucci/Coursera_Capstone/blob/master/Contibution/image19.png)


## Observations :

No surprise these Neighborhoods or the most suitable areas we selected - between the 3 of the Arrondissements represented above - of most  are centrally located  in the circular arrangement of Paris arrondissements in the direction of the alternative selected solution Arrondissement 8 - Champs Elysee. Locations fitting the criteria for popular venues for our selected activities would normally be in central locations in many cities of the world.

From this visualisation it is clear that on a practical level, with no data to base decisions on, the circle of the 20 districs is very large, and researching and then visiting them all would be a daunting and time consuming task. We have narrowed the search area down significantly from 20 potential districts to 3 that are most suitabe with respect to our certeria.



## Inferences :

We have made inferences from the data in making the location recommendations, but that is exactly the point. There is no right or wrong answer or conclusion for the task at hand. The job of data analysis here is to steer a course for the most suitable locations selection for certain activities. 

In our case study that is first to meet the criteria of being in neighbourhoods that are lively with abundant leisure venues, and second to narrow the search down to just a few of the main areas that are best suited to match the specified criteria.



## Conclusions :

There are many ways this analysis could have been performed based on different methodolgy and perhaps different data sources. 

I proceeded based on Data-Science process and chose a method straight forward way to narrow down the options, not complicating what is actually simple in many ways – meeting the the critera for the surrounding venues, and in our case study we checked for certain specified activities. First we clustred Neighborhoods for most apparent criteria and second we re-clustered for better vision of some hidden criterias - Artistic/Touristic category in order to target as we said higher traffic areas where reasonable Tourists spend their most time when in Paris.

The analysis and results are not an end point, but rather a starting point to guide the process in finding the most suitable locations for specified activities. To push this study further one can involve domain knowledge of the activities of intrest and even the city caracteristics. 

I originally intended to use trending venues data from the Foursquare API in order to formulate a notion of desity as the number of trending spots distributed on the corresponding neighborhood surface, and use it to get insights about geographical density of high traffic areas to take our choice precision level further, but we couldn't get the data unfortunately. This didn't prevent us from checking - with less precision - for a similar formulation for density levels based on the number of venues within each neighborhood.

Moreover, our data analysis and resulting recommendations have greatly narrowed down the most suitable location options based on data we could get hands on and what we could infer from it.

Without leveraging data to make focussed decisions, the process of finding the most suitable location could have been drawn out. Scrapping data from Foursquare API has helped to provide at least a narrow set of solutions for any specified category of activities. Data-driven decisions lead to a better solutions in the end.

Thanks for taking part in my Data-Science journey!

*With Regard to Micho & Micha*
