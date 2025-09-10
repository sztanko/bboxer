# OSM Bounding Box Visualizer

An interactive web application for visualizing geographic precision cells on OpenStreetMap. Click anywhere on the map or use URL parameters to display nested bounding boxes at different decimal precision levels.

## Features

- 🗺️ Interactive OpenStreetMap interface
- 📍 Click-to-select coordinate visualization
- 🔲 Multi-precision bounding box display (2, 3, and 4 decimal places)
- 🔗 URL parameter support for sharing specific locations
- 📱 Responsive design for desktop and mobile
- 🎨 Color-coded precision levels with legend

## Demo

Simply open `index.html` in a web browser. No server or build process required.

## Usage

### Interactive Mode
1. Open the application in your browser
2. Click anywhere on the map to select a coordinate
3. The app will display three nested rectangles showing the precision cells at:
   - 2 decimal places (green)
   - 3 decimal places (blue)
   - 4 decimal places (amber)

### URL Parameters
Share specific locations by using URL parameters:
```
index.html?lat=40.7128&lng=-74.0060
```

The URL automatically updates when you click on the map, making it easy to share exact locations.

## Technical Details

### Precision Cells
The application visualizes how geographic coordinates are grouped at different decimal precisions:

- **2 decimals**: ~1.1 km resolution at the equator
- **3 decimals**: ~110 m resolution at the equator
- **4 decimals**: ~11 m resolution at the equator

Each rectangle represents the bounding box for all coordinates that round down to the same value at that precision level.

### Implementation
- Pure JavaScript with no build tools required
- Leaflet.js for map functionality
- OpenStreetMap tiles (no API key needed)
- Responsive CSS with modern styling

### Key Functions
- `floorTo(value, decimals)`: Rounds coordinates down to specified decimal precision
- `boundsForPrecision(lat, lng, decimals)`: Calculates bounding box for a precision cell
- `drawFromPoint(lat, lng)`: Renders marker and precision rectangles
- `setQueryLatLng(lat, lng)`: Updates URL parameters without page reload

## Browser Compatibility
Works in all modern browsers that support:
- ES6 JavaScript
- CSS Grid and Flexbox
- Leaflet.js 1.9.4

## License
Open source - feel free to use and modify as needed.

## Dependencies
- [Leaflet.js](https://leafletjs.com/) v1.9.4 (loaded from CDN)
- [OpenStreetMap](https://www.openstreetmap.org/) tiles