# Radius Map

Draw circles of a given radius around points on an OpenStreetMap map.

Live: https://muffix.github.io/radius-map/

## Usage

- Click the map to add a circle. It uses the radius and unit (m or km) in the box at the top right.
- Right-click a circle or its marker to remove it.
- Use the crosshair button at the bottom right to re-center the map on your location. The map also zooms to your location on load, if you allow it.

Each circle keeps the radius it was drawn with. Circles are not saved, so a reload clears them.

## Run locally

The site is static (`index.html` and `favicon.svg`), with no build step. Serve the folder over HTTP:

```
python3 -m http.server 8000
```

Then open http://localhost:8000.

Opening the file directly (`file://`) does not work. The browser sends no Referer header, and OpenStreetMap's tile server answers with 403. Geolocation also needs `localhost` or HTTPS.

## Notes

- Built with [Leaflet](https://leafletjs.com/), loaded from the unpkg CDN, so an internet connection is required.
- Map tiles come from OpenStreetMap's public tile server, which is meant for light use. See the [tile usage policy](https://operations.osmfoundation.org/policies/tiles/) before putting this under real traffic.
- Map data &copy; [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors.
