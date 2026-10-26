# LA Metro Rail Station Explorer

## What this map shows
This project presents an interactive web map showing LA Metro rail stations and rail and bus rapid transit (BRT) lines in Los Angeles, California. The purpose is to help users explore the geographic distribution of transit stations in LA and understand how they are connected by different routes. Users can zoom in and out, navigate around the map, and click on individual stations to check their names and associated transit lines.

## Starting sample
This application based on Esri's official [Intro to FeatureLayer](https://developers.arcgis.com/javascript/latest/sample-code/intro-layers/) sample from the ArcGIS Maps SDK for JavaScript 5.1. The original sample displays tree carbon storage data, and I adapted it to create an interactive public transportation map.

## What I changed
Firstly, I changed the map's center and zoom level to focus on Los Angeles. Then, I replaced the hybrid basemap with a grey vector basemap. I customized the station symbols to blue circles with white outlines and added gray lines for transit routes. In addition, I changed the page title, background colors, and text colors. Finally, I replaced the tree dataset with two LA Metro FeatureLayers and configured a popup for station information.

## Data source (name, URL, which layer type you used, and why you picked it)
The map uses the public LA Metro RAIL_BRT dataset from ArcGIS REST feature services. The [Rail Stations layer (FeatureServer/0)](https://services5.arcgis.com/7nsPwEMP38bSkCjy/arcgis/rest/services/RAIL_BRT/FeatureServer/0) uses point geometry to show station locations, while the [Rail and BRT layer (FeatureServer/1)](https://services5.arcgis.com/7nsPwEMP38bSkCjy/arcgis/rest/services/RAIL_BRT/FeatureServer/1) uses polyline geometry to display rail and bus rapid transit routes. Both layers use the FeatureLayer class, allowing the map to retrieve geographic data directly from online services rather than storing it locally. I selected this dataset because I usually drive a car but wanted to learn more about public transportation in Los Angeles. More importantly, displaying stations together with transit routes helps users understand the city's transportation network.

## Component I added
I added the ArcGIS Legend component in the map's lower-left corner. The legend displays symbols for transit lines and stations, helping users distinguish between the two layers. I also retained the Zoom component for navigation.

## Problems and what I'd improve next
After I added the transit lines, the map failed to display both layers because I forgot to add the FeatureLayers to the map. I fixed the problem using `viewElement.map.add()`. Another issue I noticed was that some transit lines did not have corresponding station markers, which may reflect differences in the datasets. I would add a search function and improve the display of transit routes in the future.

## Credits
The application uses Esri's ArcGIS Maps SDK for JavaScript and the public LA Metro RAIL_BRT dataset. The starting code was adapted from Esri's Intro to FeatureLayer sample. ChatGPT was used to improve and debug the code and check grammatical errors in the written content. Finally, I reviewed and tested the application.
