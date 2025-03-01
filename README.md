# Map Visualization Generator
Generate heatmaps and thematic maps from your CSV data with complete privacy. Your data stays in your browser - no server upload.

## Live Demo

Try heatmap live at [heatmap.guncebektas.com](https://heatmap.guncebektas.com)
Try thematic map live at [thematicmap.guncebektas.com](https://thematicmap.guncebektas.com)

## Visualization Types

### Heatmap
Heatmaps show concentration or intensity using a color gradient. They're ideal for:
- Showing density patterns
- Visualizing clusters
- Representing continuous data across geographic areas

### Thematic Map
Thematic maps use colors to represent specific data values in defined regions. They're perfect for:
- Comparing values between regions
- Showing categorical data
- Visualizing statistics by administrative boundaries (countries, states, etc.)

## Understanding Intensity

Intensity is a measure of "heat" or "concentration" at each point on your map. Think of it like this:

- `0.9 - 1.0` = Very Hot (Red) 
  - Example: The center of Times Square where it's most crowded
- `0.7 - 0.8` = Warm (Lime green)
  - Example: 250m from Times Square, still busy but less crowded
- `0.4 - 0.6` = Cool (Blue)
  - Example: 500m from Times Square, fewer people
- `Below 0.4` = Not visible on the map

Real-world examples of what intensity might represent:
- Crowd density at different locations
- Signal strength of WiFi hotspots
- Number of sales in different neighborhoods
- Temperature readings across a city
- Air pollution levels in different areas

## CSV File Requirements

### For Heatmaps

#### Required Columns

1. `Latitude`
   - Geographic latitude in decimal degrees
   - Example: 40.7589
   - Must be between -90 and 90

2. `Longitude`
   - Geographic longitude in decimal degrees
   - Example: -73.9851
   - Must be between -180 and 180

3. `Intensity`
   - Value between 0 and 1
   - Controls the heat level at this point
   - Examples:
     - 1.0 = Maximum intensity (red)
     - 0.7 = Medium intensity (lime)
     - 0.4 = Low intensity (blue)

4. `Description` (Optional)
   - Text description of the point
   - Used for documentation purposes
   - Not displayed on the map

#### Example CSV Format for Heatmaps

```csv
Latitude,Longitude,Intensity,Description
40.7589,-73.9851,1.0,"Times Square"
40.7654,-73.9812,0.7,"250m from Times Square"
40.7712,-73.9754,0.4,"500m from Times Square"
```

### For Thematic Maps

#### Required Columns

1. `Region`
   - Name or code of the region (country, state, etc.)
   - Must match the region identifiers in the map data

2. `Value`
   - Numeric value to be represented by color
   - Higher values will be shown with darker/more intense colors

3. `Description` (Optional)
   - Additional information about the region
   - Used for tooltips or documentation

#### Example CSV Format for Thematic Maps

```csv
Region,Value,Description
USA,0.8,"United States data point"
CAN,0.6,"Canada data point"
MEX,0.4,"Mexico data point"
```

## Privacy

This tool processes all data locally in your browser. No data is ever sent to any server, making it suitable for sensitive location data visualization.

## Credits

Created by [@guncebektas](https://github.com/guncebektas)

## Technologies Used

- Leaflet.js for mapping
- Leaflet.heat for heatmap visualization
- GeoJSON for thematic map visualization
- Bootstrap 5 for UI
- Pure JavaScript (No frameworks required)
