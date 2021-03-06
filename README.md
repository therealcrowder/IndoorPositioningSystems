# Indoor Positioning Systems
Prediction of Location with IPS with R

### Introduction
Indoor positioning system (IPS) analysis is a growing field for analysts and data scientist to take time and understand. Gartner, Inc., a research and industry advisory firm predicts by 2020 that the market for indoor location platforms and services could grow to $12.5B by 2020 [1]. Statistical methods are deployed to track people and objects inside retail stores, healthcare facilties and warehouses with the use of IPS to understand a variety of behaviors and offer insights to the users of IPS data.

Global Positioning Systems (GPS) do not realiably work inside buildings, but with the growth of Wireless Fidelity (Wi-Fi), signals from Wi-Fi can be used to build indoor positioning systems that offer almost real-time answers to where objects, or people are. One method to used to predict where an item of interst is located is K-Nearest Neighbors (K-NN).

The motivation behind this analysis is supplied by a case study in the book "Data Science in R: A Case Study Approach to Computational Reasoning and Problem Solving by Deborah Nolan and Duncan Temple Long. The data is presented to us in raw form where we will have to understand how the data was obtained and formatted so we can create a structure to the data to make in platable for analysis through a statistical analysis language called R to predict location with K-NN.

### Background
The data for this analysis is from a the Community Resource for Archiving Wireless Data At Dartmouth (CRAWDAD). The "offline" is a referenced data set that houses signal strengths measured with a hand-held device on a grid of 166 points spaced 1 meter apart located in the hallways of a building at the University of Mannheim in Germany. The floor plan measures 15 by 36 meters. A floor plan is given in Figure 1:

![](README_files/floorPlan.png)

###### Figure 1: Floor Plan of the Test Environment. There are 6 fixed access points which are denoted by black square markers. The "offline" training data were collected at the locations marked with the grey dots. We can see that the grey dots are spaced a meter apart.

The offline dataset onced cleaned contains around 915K observations with nine variables. The observations represent recordings of singal strength which were recorded at eight orientations in 45 degree incremenets (0, 45, 90, and so on). A full list of variables can be found in Table 1:

Variable  | Description
------------- | -------------
t | Time of Observation
id | MAC address of the scanning device
pos | Degree orientation of the user carrying the scanning device
MAC | MAC address of a responding peer (i.e. access point or a device in adhoc mode) with values for signal strength in dBm (Decibel-milliwatts)
orientation | Angle of observation
signal | Signal strength
rawTime | timestamp in milliseconds since midnight, January 1, 1970 UTC
angle | 45 degree cutoff of orientation

Exploratory data analysis (EDA) of this involved some spatial analysis to look at number of recordings at each position and exploring the signal strength within the building. In a perfect world there would be 110 signals measured with eight angles for each of the six access points for a total 5,280 recordings, we come up with about 5,500 recordings at each location in Figure 2.

![](README_files/Geo_XYByCount.png)

###### Figure 2: Counts of signals at each position. Plotted at each location in the building is the total number of signals detected from all access points for the offline data. In a perfect world there is 110 signals measured with 8 angles for each 6 access points for a total of 5,280 recordings. These data include a 7th MAC address and not all signals were detected, so there are about 5,500 recordings at each location

To visualize signal stregth we display the observed posX and posY values with a contour plot. This is similar to what is seen in a topographical map. The areas where we have a strong signal corresponds to the higher elevated areas of a contour map. Just like in the last visualization we want to control for the access point and the orientation. We will begin by selecting one MAC address and one orientation to examine.

![](README_files/Geo_HeatMap.png)

###### Figure 3: This figure is telling us that the location of the access point is the dark red region at the top of the "hill". We can also see the effect of the orientation on signal strength. In addition we can also detect a corridor effect. The signal is greater relative to the distance along the corridors where the signals are not blocked by walls.


