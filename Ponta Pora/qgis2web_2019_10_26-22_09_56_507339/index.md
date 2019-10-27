<!doctype html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="initial-scale=1,user-scalable=no,maximum-scale=1,width=device-width">
        <meta name="mobile-web-app-capable" content="yes">
        <meta name="apple-mobile-web-app-capable" content="yes">
        <link rel="stylesheet" href="css/leaflet.css">
        <link rel="stylesheet" href="css/qgis2web.css">
        <style>
        html, body, #map {
            width: 100%;
            height: 100%;
            padding: 0;
            margin: 0;
        }
        </style>
        <title></title>
    </head>
    <body>
        <div id="map">
        </div>
        <script src="js/qgis2web_expressions.js"></script>
        <script src="js/leaflet.js"></script>
        <script src="js/leaflet.rotatedMarker.js"></script>
        <script src="js/leaflet.pattern.js"></script>
        <script src="js/leaflet-hash.js"></script>
        <script src="js/Autolinker.min.js"></script>
        <script src="js/rbush.min.js"></script>
        <script src="js/labelgun.min.js"></script>
        <script src="js/labels.js"></script>
        <script src="data/background_0.js"></script>
        <script src="data/best_place_2.js"></script>
        <script src="data/danger_3.js"></script>
        <script>
        var map = L.map('map', {
            zoomControl:true, maxZoom:28, minZoom:1
        }).fitBounds([[-0.00419979335757,0.00343696246142],[-0.00210110427525,0.00623967039105]]);
        var hash = new L.Hash(map);
        map.attributionControl.addAttribution('<a href="https://github.com/tomchadwin/qgis2web" target="_blank">qgis2web</a>');
        var bounds_group = new L.featureGroup([]);
        function setBounds() {
        }
        function pop_background_0(feature, layer) {
            var popupContent = '<table>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['id'] !== null ? Autolinker.link(String(feature.properties['id'])) : '') + '</td>\
                    </tr>\
                </table>';
            layer.bindPopup(popupContent, {maxHeight: 400});
        }

        function style_background_0_0() {
            return {
                pane: 'pane_background_0',
                opacity: 1,
                color: 'rgba(254,0,254,1.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fillOpacity: 0,
            }
        }
        map.createPane('pane_background_0');
        map.getPane('pane_background_0').style.zIndex = 400;
        map.getPane('pane_background_0').style['mix-blend-mode'] = 'normal';
        var layer_background_0 = new L.geoJson(json_background_0, {
            attribution: '<a href=""></a>',
            pane: 'pane_background_0',
            onEachFeature: pop_background_0,
            style: style_background_0_0,
        });
        bounds_group.addLayer(layer_background_0);
        map.addLayer(layer_background_0);
        var img_pontapora_modified_1 = 'data/pontapora_modified_1.png';
        var img_bounds_pontapora_modified_1 = [[-0.00803857372021,-1.70720907813e-05],[1.33686308172e-05,0.00962359434315]];
        var overlay_pontapora_modified_1 = new L.imageOverlay(img_pontapora_modified_1, img_bounds_pontapora_modified_1);
        bounds_group.addLayer(overlay_pontapora_modified_1);
        map.addLayer(overlay_pontapora_modified_1);
        function pop_best_place_2(feature, layer) {
            var popupContent = '<table>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['id'] !== null ? Autolinker.link(String(feature.properties['id'])) : '') + '</td>\
                    </tr>\
                </table>';
            layer.bindPopup(popupContent, {maxHeight: 400});
        }

        function style_best_place_2_0() {
            return {
                pane: 'pane_best_place_2',
                opacity: 1,
                color: 'rgba(255,239,7,0.45)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(255,209,1,0.45)',
            }
        }
        map.createPane('pane_best_place_2');
        map.getPane('pane_best_place_2').style.zIndex = 402;
        map.getPane('pane_best_place_2').style['mix-blend-mode'] = 'normal';
        var layer_best_place_2 = new L.geoJson(json_best_place_2, {
            attribution: '<a href=""></a>',
            pane: 'pane_best_place_2',
            onEachFeature: pop_best_place_2,
            style: style_best_place_2_0,
        });
        bounds_group.addLayer(layer_best_place_2);
        map.addLayer(layer_best_place_2);
        function pop_danger_3(feature, layer) {
            var popupContent = '<table>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['id'] !== null ? Autolinker.link(String(feature.properties['id'])) : '') + '</td>\
                    </tr>\
                </table>';
            layer.bindPopup(popupContent, {maxHeight: 400});
        }

        function style_danger_3_0() {
            return {
                pane: 'pane_danger_3',
                opacity: 1,
                color: 'rgba(255,1,221,0.48)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(255,13,1,0.48)',
            }
        }
        map.createPane('pane_danger_3');
        map.getPane('pane_danger_3').style.zIndex = 403;
        map.getPane('pane_danger_3').style['mix-blend-mode'] = 'normal';
        var layer_danger_3 = new L.geoJson(json_danger_3, {
            attribution: '<a href=""></a>',
            pane: 'pane_danger_3',
            onEachFeature: pop_danger_3,
            style: style_danger_3_0,
        });
        bounds_group.addLayer(layer_danger_3);
        map.addLayer(layer_danger_3);
        setBounds();
        L.ImageOverlay.include({
            getBounds: function () {
                return this._bounds;
            }
        });

    function onMapClick(e) {
     console.log("You clicked the map at " + e.latlng);
    }

    map.on('click', onMapClick);

        </script>
    </body>
</html>
