# Indoor Positioning Systems
Prediction of Location with IPS with R

### Introduction
Indoor positioning system (IPS) analysis is a growing field for analysts and data scientist to take time and understand. Gartner, Inc., a research and industry advisory firm predicts by 2020 that the market for indoor location platforms and services could grow to $12.5B by 2020 [1]. Statistical methods are deployed to track people and objects inside retail stores, healthcare facilties and warehouses with the use of IPS to understand a variety of behaviors and offer insights to the users of IPS data.

Global Positioning Systems (GPS) do not realiably work inside buildings, but with the growth of Wireless Fidelity (Wi-Fi), signals from Wi-Fi can be used to build indoor positioning systems that offer almost real-time answers to where objects, or people are. One method to used to predict where an item of interst is located is K-Nearest Neighbors (K-NN).

The motivation behind this analysis is supplied by a case study in the book "Data Science in R: A Case Study Approach to Computational Reasoning and Problem Solving by Deborah Nolan and Duncan Temple Long. The data is presented to us in raw form where we will have to understand how the data was obtained and formatted so we can create a structure to the data to make in platable for analysis through a statistical analysis language called R to predict location with K-NN.

### Background
The data for this analysis is from a the Community Resource for Archiving Wireless Data At Dartmouth (CRAWDAD). The "offline" is a referenced data set that houses signal strengths measured with a hand-held device on a grid of 166 points spaced 1 meter apart located in the hallways of a building at the University of Mannheim in Germany. The floor plan measures 15 by 36 meters. A floor plan is given in Figure 1:

![](README_files/floorPlan.png)
