# Clustering Countries by Covid-19 Community Mobility Reports and Visualization on World Map

## Introduction

This study aims to cluster countries and find a possible relationship by examining the mobility data of countries during the covid period. This relationship may be geographical, cultural, religious or so.
Plotting these clusters on the world map will help us find out whether there is a relationship, and if so, what kind of relationship it is.

## Google Mobility Data

These Community Mobility Reports aim to provide insights into what has changed in response to policies aimed at combating COVID-19. The reports chart movement trends over time by geography, across different categories of places such as retail and recreation, groceries and pharmacies, parks, transit stations, workplaces, and residential.

More details on the data can be found on the Google's Mobility Reports website

https://www.google.com/covid19/mobility/data_documentation.html?hl=en

Accessing to dataset through local csv file,

The dataset can be downloaded from https://www.google.com/covid19/mobility/

## Inspecting the data

Plotting of graphs for observing the mobility data of several countries during the covid period in order to
check how different the mobility reports can be in different countries

![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/6f44fd98-9803-482c-ac97-0d48a331c84b)
![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/c4e87a89-de63-4fc0-b58c-44dab7159837)
![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/f91b027c-da11-480f-972e-76a16f28c386)
![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/4fd0906b-222f-4434-8518-57fa0c3a8a66)
![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/0acaea6d-3567-497c-8d7d-cb26c2772e70)
![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/d6c4858c-e336-44df-83de-b7d31a3a0962)

As can be seen above, the mobility data of different countries can be similar to each other or very different.

For example, if we look at the change in the data going to the parks, while the rate of going to the parks increases in Turkey, United States and Greece in the summer months, we can observe that there is a zig-zag graph in Japan, the downward trend continues in Argentina, and it gradually increases after the initial decline in Nigeria.

## The relationship between the mobility categories

Plotting the relationship between mobility categories against each other for turkey.

Although this chart may vary from country to country, it is intended to give a preliminary idea of the relationship between the categories.

![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/7f28c19f-288a-4aca-b837-2e9bb37e1fb9)

## High Dimensional Clustering

In this section we will cluster countries using all categories of mobility data.

We will use the DBSCAN algorithm for clustering. So why did we choose to use DBSCAN? Because we did not have much value to determine the input parameters (for example, the k value in the k-means algorithm), its good efficiency in large databases and clusters with random shapes was effective in choosing the DBSCAN algorithm.

Detailed information about the DBSCAN algorithm https://towardsdatascience.com/machine-learning-clustering-dbscan-determine-the-optimal-value-for-epsilon-eps-python-example-3100091cfbc

Detailed information on using the DBSCAN algorithm in high-dimensional datasets https://towardsdatascience.com/how-to-cluster-in-high-dimensions-4ef693bacc6

## DBSCAN visualization on world map

![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/b173185a-9674-400e-9a62-b7dcc6ebaf02)

On the map, we can see that cluster 0 countries cover almost the entire map. We see that the countries that are not in the core countries cluster are some African and Asian countries.

So what does this map tell us?

When we build our model using all mobility categories, we see that countries are mostly in the same cluster. Although we can see countries that have experienced the Covid period very differently from other countries, it would not be right to comment that the central cluster is too large and the attitudes of the clustered countries are the same during the covid period.

So how do we find more specific sets?

If we create a model by choosing two clusters that can be related to each other, without collecting all the mobility categories in a single model, we can reach more distinctive and meaningful clusters.

## 2 Dimensional Clustering for parks and residental change from baseline

In this section, we will cluster the countries by choosing 2 categories from their mobility data. We will use the K-Means algorithm for clustering.

Why did we use the K-Means algorithm?

The K-Means algorithm is one of the most popular clustering algorithms. Due to the performance advantage it provides, it enables us to cluster large data more easily and in a short time. We thought it would be useful to use the K-Means algorithm since the data we have is large.

One of the disadvantages is; Since the K-Means algorithm is a partitioning algorithm, it does not find the clusters, it divides the dataset into as many pieces as we want by trying to minimize the distances in the dataset. For this, we need to specify exactly how many clusters we want to the K-Means algorithm. To do this, we looked at the 'silhouette score' values ​​of the clusters and the 'dendogram' graph. As a result, we decided how many clusters we would divide and ran the K-Means algorithm.

For detailed information about silhouette analysis https://scikit-learn.org/stable/auto_examples/cluster/plot_kmeans_silhouette_analysis.html

## Selecting the number of clusters with silhouette analysis

![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/cf829492-b7d2-4ed6-b616-0eede9a71040)
![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/939f3ac1-5fdb-4bba-a14a-8e68ce6deb01)
![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/e2966994-e8f1-4f8d-a477-5ce6dd769000)
![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/fea91943-5e44-4f5f-8b08-d504638cf435)
![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/441ab6d7-129c-4238-9af0-e2f475a5713a)

You can see the silhouette scores of the clusters above. Having a high Silhouette score is our first priority. But we also don't want to keep the number of clusters low. Therefore, it is up to us to choose the most optimal number of clusters and specify it in the K-Means algorithm.

## Determining number of clusters from Dendrogram

We also used the dendogram to determine the number of clusters. We determined the number of clusters as a result of Dendogram and Silhouette scores.

To learn in detail how to find the optimal number of clusters using a dendogram, https://hlab.stanford.edu/brian/number_of_clusters_.html

![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/bd3e1c4d-712c-4d3d-a109-b7e041ebe307)

When we analyzed the silhouette scores of the clusters and the dendogram, we chose 5 for the number of clusters.

## Kmeans Clustering

Let's run the K-Means algorithm

## Kmeans Visualization on world map

![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/82d5d070-e305-46f0-9324-50cbaf60c5a9)

Interestingly, we observe that neighboring countries are the same color on the map this time. This shows us that 2-dimensional clustering gives better results. Looking at the map, we can assume that there is a relation between the rate of change in parks and settlements and geography. Although we can observe the distribution of clusters on the map, we also need other datasets to more accurately determine the relations between countries belonging to the same cluster.

However, we can say that the movements of the countries of the same color in the parks and settlements during the covid pandemic process are similar.

## 2 Dimensional Clustering for workplace and retail&recreation change from baseline

This time we will examine two different categories (workplaces and retail recreation). We thought that workplaces and places of entertainment were among 

the mobility categories with the highest risk of disease transmission, and we examined the differences in behavior between countries in these places during covid-19.

## Silhuette Analysis

![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/41a95cd8-78b7-4216-bf49-1b6876c52fb3)
![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/be9bcfaf-3d5e-4868-974d-5687d683e5fc)
![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/bcaf335d-7bde-4d11-bd4a-fb8472e8d304)
![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/3eeaee01-c9cb-4757-bebc-fea011ead7cd)
![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/b6fec8ae-d8f8-4f99-ac56-8ba0f43f54b2)

## Dendogram

![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/38a2cade-931d-4037-9401-5c40111b8455)

## Kmeans clustering

![image](https://github.com/Agalip/Clustering-Countries-by-Covid-19-Community-Mobility-Reports-and-Visualization-on-World-Map/assets/61115719/02520d6e-9126-40be-ae3f-38f10283d116)

A little different from the previous map, we see that North America and almost all of Europe are the same color. On the other hand, South American countries are gathered in a separate cluster.

Although we see once again the effect of geography on the mobility of countries, it does not seem possible with the data we have to say the reason or type of the relationship with certainty. A more meaningful model can be put forward if situations such as the effect of a possible temperature or climate, the existence of a cultural effect are also included. However, it would not be a lie to say that the current model gives results beyond my expectations.

## Other References

Comparison of clusterin algorithms
https://medium.com/analytics-vidhya/comparative-study-of-the-clustering-algorithms-54d1ed9ea732

Impression on world map with folium
https://geopandas.org/en/stable/gallery/plotting_with_folium.html

Receiving and examining the mobility reports of the countries
https://www.kaggle.com/jkalamar/exploring-the-google-and-apple-mobility-data

XINGYU BIAN - Coronavirus (COVID-19) Visualization & Prediction

GEORGII VYSHNIA - CoronaVirus Pandemic and Google Mobility Trend EDA (2020)

A simple example of using geopandas and folium together
https://www.learnpythonwithrune.org/plot-world-data-to-map-using-python-in-3-easy-steps/
