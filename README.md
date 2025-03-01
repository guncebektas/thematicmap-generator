# Heatmap Generator
Generate heatmaps from your CSV data with complete privacy. Your data stays in your browser -  no server upload.

## Live Demo

Try it live at [heatmap.guncebektas.com](https://heatmap.guncebektas.com)

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

### Required Columns

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

### Example CSV Format

```csv
Latitude,Longitude,Intensity,Description
40.7589,-73.9851,1.0,"Times Square"
40.7654,-73.9812,0.7,"250m from Times Square"
40.7712,-73.9754,0.4,"500m from Times Square"
```

## Privacy

This tool processes all data locally in your browser. No data is ever sent to any server, making it suitable for sensitive location data visualization.

## Credits

Created by [@guncebektas](https://github.com/guncebektas)

## Technologies Used

- Leaflet.js for mapping
- Leaflet.heat for heatmap visualization
- Bootstrap 5 for UI
- Pure JavaScript (No frameworks required)
