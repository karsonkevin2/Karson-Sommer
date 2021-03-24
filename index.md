# Overview

This page serves as an overview of selected projects I have contributed to.

1. [OpenStreetMap](#openstreetmap--fall-2019---present--overview)
2. [Iowa Tracks](#iowa-tracks--winter-20202021--website--github)
3. [Heatmap Skeletonizataion](#heatmap-skeletonization--summer-2020--github)
4. [Line Drawing to SVG](#line-drawing-to-svg--summer-2020--github)
5. [NCAA Colors](#ncaa-colors--summer-2020--github)
6. [Strogger](#strogger--spring-2020--github)
7. [AlertLife](#alertlife--spring-2019--github)
8. [Smart Fire Sprinkler](#smart-fire-sprinkler--spring-2018)

# Projects

## OpenStreetMap | Fall 2019 - Present | [Overview](https://hdyc.neis-one.org/?karsonkevin2)
OpenStreetMap is a map which can be edited and contributed to by anyone. OpenStreetMap is one of the most popular map services since it is free to use and is used by companies such as Amazon, Facebook, Snapchat, Lyft, ...

I am an avid contributor and like to map things which benefit the end user. Some important contributions I have made include:
- standardizing a tagging schema for running tracks and cross country courses
- mapping every athletic facility in the state of Iowa
- create named neighborhood polygons in the Quad Cities, Iowa City, Des Moines, ... in conjunction with county GIS departments
- add missing road suffixes to every road in Wayne County, Iowa
- convert many parks or wildlife management areas from nodes into areas in Iowa
- add road names and correct road classes to clean up low quality edits from Amazon's mapping team
- ... various other changes  

## Iowa Tracks | Winter 2020/2021 | [Website](https://karsonkevin2.github.io/Iowa-Tracks/) | [Github](https://github.com/karsonkevin2/Iowa-Tracks)
This project was spurred by [Russ Biggs Swimming Pools](https://github.com/russbiggs/swimming-pools). I though I could adapt the code to create an effective display of all running tracks in Iowa.

I had previously mapped every running track in Iowa. I utilized [Overpass Turbo](https://overpass-turbo.eu/) to get an extract of the information and [Mapshaper](https://mapshaper.org/) to reformat the information to TopoJSON. The actual code needed to be modified so that each polygon would render its own color. The code also needed to be modified to correctly display multipolygons.

## Heatmap Skeletonization | Summer 2020 | [Github](https://github.com/karsonkevin2/heatmap-skeletonization)
Traversal heatmaps are provided by many sources and can be converted to roads for OpenStreetmap more efficiently than using machine learning models on satellite imagery. An example heatmap can be found from the [Strava Heatmap](https://www.strava.com/heatmap). 

These functions provide a variety of parameters to skeletonize a heatmap. The data must first be obtained from a raster Slippy map, possibly using the created functions. Then using a serious of parameters, optimized by the user for the locale, the heatmap is reduced to a bitmap skeletonization. This skeletonization can then be processed using my Line Drawing to SVG library and imported into OpenStreetMap using the JOSM importVec plugin.

## Line Drawing to SVG | Summer 2020 | [Github](https://github.com/line-drawing-to-svg)
When trying to create my heatmap skeletonization project, I realized I had no way of losslessly converting bitmap line drawings to svg. MATLAB's built in method was not lossless and every implementation I found on the Internet attempted the conversion using ML techniques. I needed a way to convert the information 1:1.

This package for MATLAB allows lossless conversion of a bitmap line drawing to svg file format. This process is attempts to reduce the data as much as possible by representing the information as a set of straight lines. As far as I can tell, this is the only existing implementation in any language.


## NCAA Colors | Summer 2020 | [Github](https://github.com/karsonkevin2/NCAA-Colors)
This project was undertaken out of curiosity to see how similar NCAA DI team colors are. The B1G Conference team colors caused this project since Nebraska, UW-Madison, IU all have similar team colors.

Data was obtained from through website which had already compiled this information. This information was then explored in Excel. A Visual Basic macro was created to ensure that the colors were visually represented rather than just a unsigned short. Even segmentation proved ineffective, so a clustering based strategy was adopted. The data was moved to MATLAB where meaningful 3D charts could be created of the derived color space.

## Strogger | Spring 2020 | [Github](https://github.com/kmhall/Strogger)
This project was created for the Electrical Engineering Senior Design course. I worked with [Kyle Hall](https://github.com/kmhall) and [Jordan Mitchell](github.com/jmitchell37). We worked loosely with a design group from both the Biomedical Engineering department and the law college, but our projects diverged during the Spring semester.

We designed an Android application which provides real-time analytics on a runner's form. The phone is held in the runner's hand and will provide audio and vibrational feedback when bad form is detected. The application uses the phone sensors to quantify bad form using cadence, twisting, and exaggerated form. The app has a display which can be used to view various statistics and charts of the run. Authentication is required as the information could be personally identifying. Data is stored in the cloud using [Google Firebase](https://firebase.google.com/). Bluetooth connectivity was partially implemented with the goal of providing audio feeback direclty to headphones.

## Alertlife | Spring 2019 | [Github](https://github.com/karsonkevin2/AlertLife)
This project was created for the course, Embedded Systems. The project was designed with a partner. 

We envisioned an understaffed elderly home where people may have a medical emergency. In order for the staff to be appropriately informed, we designed a system which monitors for someone falling down and then sounds an audible alarm and sends a Bluetooth transmission to a central monitoring computer.

## Smart Fire Sprinkler | Spring 2018
Implements a overhead fire sprinkler system which can aim itself to only extinguish the fire and not cause collateral damage to the building. Most fire sprinkler systems, once activated, must be manually turned off by the fire department which can cause great monetary loss, especially in server rooms. This project was designed as a team of 4 for the classs, Internet of Things.

The system is controlled locally via an Raspberry Pi which is interfaced with 3 stepper motors, an infrared sensor, and a pump. This allows the system to aim the water, detect where the fire is, and switch the stream on and off. Information about the status of the system is transmitted via a WiFi connection to Google Firebase which can then be accessed via an Android application we designed. The app allows viewing the statuses of multiple sprinkler systems as well as viewing the temperature array and whether the pump has been toggled.
