---
layout: page
title: Data organizing
---

# Our Approach

We decided to design and create a relational database to contain the joined FDA recall and Amazon review data. This way, researchers can continue to work on this topic, beginning with the analytical tasks, rather than spending so much time joining the data on unique identifiers and organizing it into a concise, easy-to-use format. 

Some visualizations based on summary statistics queried from the database can be found [here](https://escience.shinyapps.io/unsafefoods).

## Understanding the Data

## Visualizing the damage data

<script src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY" async defer></script>
<link rel="stylesheet" href="https://unpkg.com/leaflet@1.0.3/dist/leaflet.css" />
<script src="https://unpkg.com/leaflet@1.0.3/dist/leaflet.js"></script>

<script src='https://unpkg.com/leaflet.gridlayer.googlemutant@latest/Leaflet.GoogleMutant.js'></script>

var roads = L.gridLayer.googleMutant({
    type: 'roadmap' // valid values are 'roadmap', 'satellite', 'terrain' and 'hybrid'
}).addTo(map);
