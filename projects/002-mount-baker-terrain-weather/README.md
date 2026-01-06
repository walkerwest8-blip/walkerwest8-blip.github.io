# Terrain Controls on Potential Weather and Snow Behavior  
**Mount Baker, Washington**

## Overview

This project examines how mountain terrain influences potential weather and snow behavior on Mount Baker, Washington. Using elevation, aspect, and slope derived from a digital elevation model, the analysis focuses on how topography constrains temperature patterns, solar energy exposure, and the retention or shedding of snow and cold air. The goal is not to describe current weather conditions, but to demonstrate how terrain shapes the ways weather can express itself across a mountain landscape.

## Research Question

How do elevation, aspect, and slope influence potential differences in weather and snow behavior across Mount Baker?

## Data

The analysis uses a USGS 1/3 arc-second digital elevation model (approximately 10 m resolution), downloaded from the USGS Map Downloader on January 7, 2025.  
The DEM was reprojected to NAD83 / UTM Zone 10N (EPSG:26910) so that elevation, slope, and distance are measured in meters, allowing for physically meaningful terrain and weather interpretation.

From this DEM, the following terrain products were derived:
- Elevation bands
- Aspect
- Slope (degrees)

## Methods

Terrain analysis was conducted in QGIS. Elevation bands were used to examine vertical temperature gradients and precipitation phase potential. Aspect was analyzed to assess differences in solar energy input and melt timing between north- and south-facing slopes. Slope was calculated in degrees to evaluate how terrain geometry influences snow retention and cold-air pooling.

The analysis emphasizes controlled observation and interpretation rather than cartographic presentation. Screenshots included in the repository serve as evidence of terrain patterns rather than as polished maps.

## Key Observations

- A large portion of Mount Baker’s surface area lies at higher elevations, while lower elevations are confined mainly to valleys and drainage corridors.
- Aspect varies systematically across the mountain, producing distinct north- and south-facing slope patterns on opposing valley walls and mid-slopes.
- Gentler slopes are most common in valleys and broad mid-slope areas, while steeper slopes are concentrated along ridges and upper mountain flanks.

## Terrain–Weather Interpretation

Valleys tend to accumulate cold air and retain snow due to low elevation, gentle slopes, and limited solar exposure. Mid-slopes represent transitional zones where temperature and melt timing respond quickly to changes in sunlight. Ridges are higher, steeper, and more exposed, increasing wind influence and reducing the retention of snow and cold air.

Together, these patterns illustrate how terrain alone can explain why different parts of the same mountain experience contrasting surface conditions under identical atmospheric conditions.

## Limitations

This project is intentionally terrain-based and does not include observed meteorological data such as temperature, wind speed, or precipitation. Temporal variability, including seasonal and storm-to-storm differences, is not represented. The DEM resolution limits analysis to broad terrain features, and all interpretations describe potential rather than actual or current weather conditions.

## Future Work

Incorporating a temperature or freezing-level dataset would allow future analysis to test how often different elevation bands transition between rain, wet snow, and dry snow under varying atmospheric conditions.

## Repository Structure

- `qgis/` – QGIS project file  
- `data/raw/` – Original DEM (unmodified)  
- `data/derived/` – Reprojected DEM, slope, and aspect layers  
- `data/notes/` – Data sources and processing notes  
- `figures/` – Screenshots used as analytical evidence  
- `report/` – Questionnaire and written report  
