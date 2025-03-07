<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calfreen Map</title>
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
    <style>
        body { margin: 0; }
        #map { height: 100vh; width: 100vw; }
    </style>
</head>
<body>
    <div id="map"></div>

    <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
    <script>
        var map = L.map('map', {
            minZoom: -1.5,
            maxZoom: 1,
            zoomSnap: 0.5,
            crs: L.CRS.Simple
        });

        var imageUrl = 'Calfreen.jpg'; // Make sure this image is in /static/
        var imageBounds = [[0, 0], [1536, 2048]];

        L.imageOverlay(imageUrl, imageBounds).addTo(map);
        map.setView([1024, 821], -1);
        map.fitBounds(imageBounds);
    </script>
</body>
</html>
