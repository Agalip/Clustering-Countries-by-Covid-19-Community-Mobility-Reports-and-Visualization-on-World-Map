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

