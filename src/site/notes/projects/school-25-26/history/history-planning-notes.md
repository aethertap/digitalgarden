---
{"dg-publish":true,"permalink":"/projects/school-25-26/history/history-planning-notes/"}
---


# History teaching 2025-2026

- Study time from 1770 to present
- emphasis on modern, with mapping
    - american revolution
    - slavery
    - civil war
    - wwi
    - wwii
    - holocaust
    - communism

I want them to create a map and timeline using QGIS that has digitized data to show what we studied and when it happened. I need to have the power to limit queries to only data within certain date ranges, but otherwise this will be a great way to keep track of the world's history as we learn it.

- [x] Figure out how to use QGIS or other mapping tool to do a time-dependent map for history #todo/school

## Using QGIS for history

[Temporal Controller](https://www.qgistutorials.com/en/docs/3/animating_time_series.html) allows you to view data within a certain time window.

The different shapefile types correspond to most of what we will want to know about history:
- Territory is polygon data
- Routes are lines
- Battlefronts are lines
- Events happen at points, or polygons if they have large extent
- heatmap/raster data can be used for things like death tolls from plague and war
- Text data can hold links that point to documents, either stuff they write or resources they reference.

## Lesson Builder

[Students of History curriculum](https://www.studentsofhistory.com/products/world-history-complete-curriculum)

- Identify where on the map and when in time we're working
- Mark the lesson region on the map and timeline as a polygon or point, depending on what it is
- Add the lesson link and assignment to the text data for that feature
- 