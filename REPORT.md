# Project Report

## Story of visualization

Since the ages of the hunting and gathering, people are constantly moving their living places all over the world. In the modern
world, most people's intention is not looking for new food or wildlife: people migrate because of their work, they
flee from war, social captivity, or other reasons. Two variables that may summarize these reasons, are Gross Domestic
Product (GDP) and happiness. This web-application shows the average GDP per capita and happiness rates of
countries in the world. Select a country and see what the origins of immigrants and destinations of emigrants
are. Did those migrants seek for money or happiness?

## Description application

The data visualtization exists of four views: a woldmap, a linechart with a horizontal time axis and two y-axi: a GDP and a happiness axis. The worldmap has a buttontool, which let the user choose to display happiness or GDP values on the map. Furthermore, the user can slide a slider to choose the year, between 2008 and 2016. If the user clicks on a country in the worldmap, the linecharts change to the selected country, and two pie charts appear of the selected country. One pie chart displays the immigration with countries of origin. The other pie chart displayes the emigration, with countries of destiny. Which year the pie charts show, can be chosen by the user with a drop-down menu (options: 2010 and 2015).

![](/doc/final-snap1.png)
![](/doc/final-snap2.png)
![](/doc/final-snap3.png)


## Technical design

This projects contains three different interactive visualizations: a worldmap, a multiple-line chart with two different y-axi, and two pie charts. The visualizations provide two different interactive components: toggle buttons and a slider.

#### Visualization 1 (Worldmap)
The worldmap shows the GPD or happiness-grade per country. If you hover over a specific country, the information will be displayed in a pop-up (country, GDP, happiness-grade and possibly population). A toggle button lets the user choose between GPD and happiness: this choice will color the map in GPD- or happiness-rates. A slider lets the user change the year, from 2008 up till 2016. When the users clicks on a specific country, the line chart and pie charts change to the selected country.

##### Functions
* A function that draws the entire map, and updates the piecharts and linecharts after country is clicked
* A function that draws the legend
* A function that converts data into useable format and assigns the fill keys
* A jQuery function that shifts the tooltip of the slider towards the selector

#### Visualization 2 (Multiple Line Chart)
The multiple line chart consists of a GPD-time line, and a happiness-time line. Because these lines do not have the same dimensions on the y-axis, two axi are drawn: a GPD-axis on the left of the chart and a happiness-axis on the right of the chart. When hovering with the mouse over the lines, a vertical line with a pop-up appears, showing the GPD and happiness values. The time-axis starts at 2008 and ends at 2016. The chart shows the country that is selected by clicking on a country in the worldmap.

##### Functions
* A function that adds all elements to draw the line chart svg, axis, add scales, initiates paths, title and the legend
* An update function that updates the data if a different country is clicked
* A function that converts the data into a specific form that is usable for the update function

#### Visualization 3 (Pie charts)
There are two pie charts: one showing the countries from which immigrants originate (including the amount of immigrants), and one showing the countries where emigrants migrated (including the amount of emigrants). In addition, the total number of immigrants and emigrants is displayed above or underneath the pie charts. A toggle button lets the user choose between the years 2010 and 2015. The charts show the country that is selected by clicking on a country in the worldmap.

##### Functions
* A function that adds all elements to draw the pie-charts, title, etc.
* A function that creates a string containing top 6 countries and their values of the countries in 'Others' for tooltip labeling
* A function that counts the total migration of a dataset

#### Interactive component 1 (Toggle buttons (2x))
Both the worldmap as the pie charts use toggle buttons. The worldmap lets the user choose between showing the GPD, or the happiness values. In order to implement these interactive components, ...

#### Interactive component 2 (Slider)
Beside the toggle button, the worldmap contains a slider which lets the user choose the year (2008-2016). In order to implement this interactive component, ...

### Supporting files and functions

#### index.js
In this file, all functions are called to draw, remove and update all visualizations on users actions.

#### helpers.js
This file contains all function used in one or multiple javascript files. Examples:
* Parse functions to parse numbers in specific formats
* A tooltip function
* Mouse-event functions


## Challenges during process
I encountered multiple challenges during the process:
* Finding a good color scale for the gdp and happiness worldmaps: This was hard, because due to extrema's in the data (a few countries with an extremely low GDP and a few countries with an extremely high GDP, for example), all 'average' countries would look the same with a continuous scale, and changing time was hard to see a change (see images). This was fixed by scaling the color in different intervals.
* During the process, I had to change the structure of the json files a lot of times in order to accomplish some decisions. This took some time, but were very hard needed.
![](/doc/map2010.png) + ![](/doc/map2014.png)

* I found it pretty hard to provide a good layout. All the time, div's, svg's, g's, etc. were overlapping each other, hiding other visualizations, falling off the page, etc. This took a lot of time. Next time, it will be smart to make a strict and well-organised planning for the page layout.


## Decisions
After twe weeks, I decided to switch the locations of the visualisations. Instead of the linechart bottom-left, with the two piecharts
right of it (see project-proposal sketch beneath), I decided to place the linechart at the right-top location. I left the piecharts at the bottom. This was a bit more symmetrical and gave the visualizations some more space. For the rest, I sticked to the initial plans.


![](/doc/project_sketch.png)
