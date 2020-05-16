---
title: Map of States with Face Mask Laws During the COVID-19 Pandemic
tags: [JavaScript, Mapbox, Spatial Analysis]
image: /assets/images/projects/project-inhabited-01.png
style: border
color: primary
description: Using the Mapbox Albers projection to display states that require face masks.
---

First edited data using [Mapshaper](https://mapshaper.org/)








Mapshaper

// within Mapshaper console, clean up Natural Earth Populated Places data
// https://www.naturalearthdata.com/http//www.naturalearthdata.com/download/10m/cultural/ne_10m_populated_places_simple.zip

$ filter 'iso_a2 == "US"'

$ filter-fields featurecla,name,adm1name,longitude,latitude,pop_max,geonameid,min_zoom

// in terminal, reproject in Albers
cat placesusa.json | dirty-reproject --forward albersUsa > placesusa.geojson


Thanks to... for this post...
Read his tutorial here:
https://blog.mapbox.com/mapping-the-us-elections-guide-to-albers-usa-projection-in-studio-45be6bafbd7e
