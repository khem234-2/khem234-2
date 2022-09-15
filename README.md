<html>
    <head>
        <meta charset="UTF-8"/>
        <meta name="viewport" content="=width=device-width , initial-scale=1.0">
        <link rel="stylesheet" href="https://unpkg.com/leaflet@1.7.1/dist/leaflet.css" 
        integrity="sha512-xodZBNTC5n17Xt2atTPuE1HxjVMSvLVW9ocqUKLsCC5CXdbqCmblAshOMAS6/keqq/sMZMZ19scR4PsZChSR7A==" 
        crossorigin=""/>
        <script src="https://unpkg.com/leaflet@1.7.1/dist/leaflet.js" 
        integrity="sha512-XQoYMqMTK8LvdxXYG3nZ448hOEQiglfqkJs1NOQV44cWnUrBc8PkAOcXy20w0vlaXaVUearIOBhiXZ5V3ynxwA==" 
        crossorigin=""></script>
        <script src="https://code.jquery.com/jquery-3.6.1.min.js"></script>
    </head>
    <body>
        <div id="map" style=" width:100%; height:100%; "></div>
        <script>
            var map = L.map("map").setView([13.8, 100.9], 6);
            var sat =L.tileLayer("http://{s}.google.com/vt?lyrs=s&x={x}&y={y}&z={z}",{
                maxZoom: 9,
                subdomains:['mt0','mt1','mt2','mt3']
            }).addTo(map); 
            var openn =L.tileLayer("https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png", {
                attribution:'&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
            }).addTo(map);
const baseMap = {"Google Satleite":sat,"OpenStreetmap": openn};
const layerControl = L.control.layers(baseMap).addTo(map);
        </script>
    </body>
</html>
