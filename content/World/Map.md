
# Interactive Map of Calfreen

Here is the interactive map of **Calfreen**. You can click on locations to view details.

<div id="map" style="height: 600px;"></div>

<script>
    // Load Leaflet
    var script = document.createElement('script');
    script.src = "https://unpkg.com/leaflet@1.7.1/dist/leaflet.js";
    script.onload = function () {
        var map = L.map('map', {
            minZoom: -1.5,
            maxZoom: 1
        }).setView([0, 0], 1);

        // Load the map image
        var imageUrl = '../static/Calfreen.jpg'; // Make sure the image is accessible
        var imageBounds = [[0, 0], [1536, 2048]];
        L.imageOverlay(imageUrl, imageBounds).addTo(map);
        map.fitBounds(imageBounds);

        // Example marker linking to another .md file
        L.marker([1024, 821]).addTo(map)
            .bindPopup('<a href="/World/SomePage.md">Go to Some Page</a>');

    };
    document.head.appendChild(script);
</script>


[View Interactive Map](../static/Calfreen.jpg)

