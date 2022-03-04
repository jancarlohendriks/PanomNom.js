# PanomNom.js

Panorama fetching tools for JavaScript

Current supported sources

- Google Street View panoramas
- Google PhotoSpheres

### How to use

Include the google maps API for the services to resolve metadata.

```javascript
<script src="https://maps.google.com/maps/api/js"></script>
```

Include the library or the module. You can import the functions separatedly from the /src folder, or from the PanomNom.module file.

```javascript
import { GoogleStreetViewLoader } from "./PanomNom.module.js";
```

Create a loader. There's two loaders, one for Street View panoramas and the other for PhotoSpheres:

```javascript
const loader = new GoogleStreetViewLoader();
const loader = new GooglePhotoSphereLoader();
```

```javascript
/* Load from ID: pano id, zoom 3 */
await loader.load(panoId, 3);

/* Load from location: google.maps.LatLng, zoom default 1 */
import { getIdByLocation } from "./PanonomNom.module.js";
const data = await getIdByLocation(pos.lat, pos.lng);
await loader.load(data.data.location.pano, 3);

/* Load from URL: URL from maps.google.com, zoom 2 */
import { getIdFromURL } from "./PanonomNom.module.js";
const id = getIdFromURL(url);
await loader.load(id, 2);
```

Once the panorama is loaded, `loader.canvas` has the resulting stitched image.

**Note: getIdByLocation will only return ids valid for Street View panoramas**

Please see the examples folder for proper implementations of each case.

[Street View panorama from id](https://spite.github.io/PanomNom.js/examples/basic/sv-panoid.html)
[Street View panorama from lat,lng](https://spite.github.io/PanomNom.js/examples/basic/sv-location.html)
[Street View panorama from URL](https://spite.github.io/PanomNom.js/examples/basic/sv-url.html)

# License

MIT licensed

Copyright (C) 2022 Jaume Sanchez Elias http://twitter.com/thespite

http://www.clicktorelease.com
