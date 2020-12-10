<!doctype html>

<head>
    <title>OpenLayers</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/openlayers/openlayers.github.io@master/en/v6.4.3/css/ol.css" type="text/css">
    <style>
        body {
            margin: 0;
            padding: 0;
        }

        .map {
            position: absolute;
            height: 100%;
            width: 100%;
        }
    </style>
    <script src="https://cdn.jsdelivr.net/gh/openlayers/openlayers.github.io@master/en/v6.4.3/build/ol.js"></script>
</head>

<body>
    <div id="map" class="map"></div>
    <script type="text/javascript">
        var map = new ol.Map({
            target: 'map',
            layers: [
                new ol.layer.Tile({
                    source: new ol.source.OSM()
                })
            ],
            view: new ol.View({
                center: ol.proj.fromLonLat([8, 47]),
                zoom: 10
            })
        });
        //change map color
        map.on('postcompose', function(e) {
            document.querySelector('canvas').style.filter = "grayscale(90%)";
        });
    </script>
</body>

</html>