# LA Metro Rail Station Explorer

## What this map shows
This project presents an interactive web map showing LA Metro rail stations and rail and bus rapid transit (BRT) lines in Los Angeles, California. It mainly focuses on LA Metro rail stations. The purpose of this project is to help users easily explore the geographic distribution of transit stations in LA and be more familiar with how the stations are connected by different routes. Users are able to zoom in and out, navigate around the map, and click on individual stations to check their names and associated transit lines.

## Starting sample
This LA Metro Rail Station application is based on Esri's official [Intro to FeatureLayer](https://developers.arcgis.com/javascript/latest/sample-code/intro-layers/) sample from the ArcGIS Maps SDK for JavaScript 5.1. The original sample displays tree carbon storage data and I adapted its structure to create an interactive public transportation map.

## What I changed
I made some changes to the original sample. Firstly, I changed the center and the zoom level of the map to focus on Los Angeles. Then, I replaced the hybrid basemap with a grey vector basemap. After that, I customized the station symbols to blue circles with white outlines and added gray lines to represent transit routes. In addition, I changed the page title, background colors, and text colors. Finally, I replaced the original tree dataset with two LA Metro FeatureLayers and configured a new popup to display basic station information.

## Data source (name, URL, which layer type you used, and why you picked it)
The map uses the public LA Metro RAIL_BRT dataset, accessed through ArcGIS REST feature services. The [Rail Stations layer (FeatureServer/0)](https://services5.arcgis.com/7nsPwEMP38bSkCjy/arcgis/rest/services/RAIL_BRT/FeatureServer/0) uses point geometry to show station locations, while the [Rail and BRT layer (FeatureServer/1)](https://services5.arcgis.com/7nsPwEMP38bSkCjy/arcgis/rest/services/RAIL_BRT/FeatureServer/1) uses polyline geometry to display rail and bus rapid transit routes. The two layers are loaded using the FeatureLayer class in the ArcGIS Maps SDK for JavaScript, allowing the map to retrieve geographic data directly from online services rather than storing it locally. I selected this dataset because I usually drive a car, but public transportation is also an important part of urban mobility in Los Angeles, so I wanted to know more about it. More importantly, displaying stations together with transit routes helps users understand the city's transportation network.

## Component I added
In the lower-left corner of the map, I used the ArcGIS Legend component. The Legend displays the symbols for both transit lines and stations, which is helps users distinguish the two layers. In addition, I retained the Zoom component for map navigation.

## Problems and what I'd improve next
At the beginning, I only added the stations. After I edited the code to add the transit lines, the map failed to display the stations and lines because I forgot to add the FeatureLayers to the map. I fixed the problem by adding both layers using `viewElement.map.add()`. Another issue I noticed was that some transit lines did not have corresponding station markers, which may reflect differences in the datasets. I would add a search function and improve the display of different transit routes in the future.

## Credits
The application uses Esri's ArcGIS Maps SDK for JavaScript and the public LA Metro RAIL_BRT dataset. The starting code was adapted from Esri's Intro to FeatureLayer sample. ChatGPT was mainly used to help improve and debug the code, as well as to check and correct grammatical errors in the written content. Finally, the application was reviewed and tested.