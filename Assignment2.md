---
title: "Developing Data Products - Week 2 Assignment"
author: "Lina"
date: "08/04/2021"
output: 
  html_document: 
    keep_md: yes
---

## Data
The data for this map is tourist attractions in London. The data is taken from [here](https://www.latlong.net/place/the-london-eye-uk-2843.html)


```r
objects <- read.csv(textConnection("
Object,latitude,longitude
Clarence House, 51.504002, -0.138500
Prime Meridian (Greenwich) , 51.477928, -0.001545
Sky Garden, 51.511177, -0.083094
County Hall, 51.501945, -0.118889
Lloyds Building, 51.513058, -0.082361
The Shard, 51.504501, -0.086500
The Royal Albert Hall, 51.500942, -0.177498
St Paul's Cathedral, 51.513611,	-0.098056
Westminster Cathedral, 51.496284,	-0.139888
Abbey Road, 51.532005,	-0.177331
Oxford Street, 51.515419,	-0.141099
Big Ben, 51.510357,	-0.116773
The Tower of London, 51.508530,	-0.076132
St. James’s Park, 51.502464,	-0.137000
Greenwich Park, 51.476688,	0.000130
Hyde Park, 51.508610,	-0.163611
British Museum, 51.518757, -0.126168
Victoria and Albert Museum, 51.496639,	-0.172180
Tower Bridge, 51.505554,	-0.075278
Buckingham Palace, 51.501476,	-0.140634
Royal Botanic Gardens (Kew),	51.478298,	-0.297954
"))
```
 
## Plotting Map

The map below shows some of the most popular tourist attractions in London.


```r
library(leaflet)
objects %>%
  leaflet() %>%
  addTiles() %>%
  addMarkers(clusterOptions = markerClusterOptions())
```

```{=html}
<div id="htmlwidget-5b63264b4d7a36edbaf3" style="width:672px;height:480px;" class="leaflet html-widget"></div>
<script type="application/json" data-for="htmlwidget-5b63264b4d7a36edbaf3">{"x":{"options":{"crs":{"crsClass":"L.CRS.EPSG3857","code":null,"proj4def":null,"projectedBounds":null,"options":{}}},"calls":[{"method":"addTiles","args":["//{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",null,null,{"minZoom":0,"maxZoom":18,"tileSize":256,"subdomains":"abc","errorTileUrl":"","tms":false,"noWrap":false,"zoomOffset":0,"zoomReverse":false,"opacity":1,"zIndex":1,"detectRetina":false,"attribution":"&copy; <a href=\"http://openstreetmap.org\">OpenStreetMap<\/a> contributors, <a href=\"http://creativecommons.org/licenses/by-sa/2.0/\">CC-BY-SA<\/a>"}]},{"method":"addMarkers","args":[[51.504002,51.477928,51.511177,51.501945,51.513058,51.504501,51.500942,51.513611,51.496284,51.532005,51.515419,51.510357,51.50853,51.502464,51.476688,51.50861,51.518757,51.496639,51.505554,51.501476,51.478298],[-0.1385,-0.001545,-0.083094,-0.118889,-0.082361,-0.0865,-0.177498,-0.098056,-0.139888,-0.177331,-0.141099,-0.116773,-0.076132,-0.137,0.00013,-0.163611,-0.126168,-0.17218,-0.075278,-0.140634,-0.297954],null,null,null,{"interactive":true,"draggable":false,"keyboard":true,"title":"","alt":"","zIndexOffset":0,"opacity":1,"riseOnHover":false,"riseOffset":250},null,null,{"showCoverageOnHover":true,"zoomToBoundsOnClick":true,"spiderfyOnMaxZoom":true,"removeOutsideVisibleBounds":true,"spiderLegPolylineOptions":{"weight":1.5,"color":"#222","opacity":0.5},"freezeAtZoom":false},null,null,{"interactive":false,"permanent":false,"direction":"auto","opacity":1,"offset":[0,0],"textsize":"10px","textOnly":false,"className":"","sticky":true},null]}],"limits":{"lat":[51.476688,51.532005],"lng":[-0.297954,0.00013]}},"evals":[],"jsHooks":[]}</script>
```
