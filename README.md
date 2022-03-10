<!DOCTYPE html>
<html>
    <body>
        <h1>51Degrees cloud example</h1>
        <button type="button" onclick="buttonClicked()">Use my location</button>
        <div id="htmlExampleOutput"></div>
    </body>
</html>
<script async src="https://cloud.51degrees.com/api/v4/AQTIHPLX-TmulbEC2kg.js"></script>
<script type="text/javascript">
    window.onload = function() {
        fod.complete(function (data) {
            // Fetch the properties from the JSON response and write to the page.
            addText("DeviceType: " + data.device["devicetype"]);
            addText("SetHeaderHardwareAccept-CH: " + data.device["setheaderhardwareaccept-ch"]);
            addText("SetHeaderBrowserAccept-CH: " + data.device["setheaderbrowseraccept-ch"]);
            addText("IsMobile: " + data.device["ismobile"]);
            addText("IsSmartPhone: " + data.device["issmartphone"]);
            addText("MaxNumberOfSIMCards: " + data.device["maxnumberofsimcards"]);
            addText("SupportedSIMCardTypes: " + data.device["supportedsimcardtypes"]);
            addText("SupportedBearers: " + data.device["supportedbearers"]);
            addText("Prompts: " + data.device["prompts"]);
            addText("PriceBand: " + data.device["priceband"]);
            addText("IsWebApp: " + data.device["iswebapp"]);
            addText("GeoLocation: " + data.device["geolocation"]);
            addText("JavascriptPreferredGeoLocApi: " + data.device["javascriptpreferredgeolocapi"]);
        });
    }

    buttonClicked = function() {
        fod.complete(function (data) {
            addText("Region (by lat/lon): " + data.location["region"]);
            addText("State (by lat/lon): " + data.location["state"]);
            addText("Country (by lat/lon): " + data.location["country"]);
            addText("CountryCode (by lat/lon): " + data.location["countrycode"]);
            addText("County (by lat/lon): " + data.location["county"]);
            addText("Town (by lat/lon): " + data.location["town"]);
        }, 'location');
    }

    addText = function(text) {
        document.getElementById("htmlExampleOutput").innerHTML+=text + "<br>";
    }
</script>
