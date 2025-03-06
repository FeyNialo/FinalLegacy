<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calfreen Map</title>
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
    <style>
        #map { width: 100vw; height: 100vh; }
    </style>
</head>
<body>
    <div id="map"></div>

    <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
    <script>
        // Initialize the map
        var map = L.map('map', {
            minZoom: -1.5,
            maxZoom: 1,
            zoomSnap: 0.5
        }).setView([1024, 821], -1); // Center based on lat/long

        // Define image bounds
        var imageBounds = [[0, 0], [1536, 2048]];

        // Add custom map image overlay
        L.imageOverlay('Calfreen.jpg', imageBounds).addTo(map);

        // Fit the map to the image bounds
        map.fitBounds(imageBounds);

        // Add scale bar
        L.control.scale({
            metric: false,
            imperial: true,
            maxWidth: 200
        }).addTo(map);
    </script>
</body>
</html>
