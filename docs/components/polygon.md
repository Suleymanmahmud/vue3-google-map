<script setup>
import { GoogleMap, Polygon } from '@lib'
import { apiPromise } from '@docs/shared'

const center = { lat: 24.886, lng: -70.268 }
const triangleCoords = [
  { lat: 25.774, lng: -80.19 },
  { lat: 18.466, lng: -66.118 },
  { lat: 32.321, lng: -64.757 },
  { lat: 25.774, lng: -80.19 },
]
const bermudaTriangle = {
  paths: triangleCoords,
  strokeColor: '#FF0000',
  strokeOpacity: 0.8,
  strokeWeight: 2,
  fillColor: '#FF0000',
  fillOpacity: 0.35,
}
</script>

# Polygon

Use the `Polygon` component to draw polgons (arbitrary number of sides) on a map.

## Options

You can pass a [PolylgonOptions](https://developers.google.com/maps/documentation/javascript/reference/polygon#PolygonOptions) object to the `options` prop to configure your polyline.

```vue
<script setup>
import { GoogleMap, Polygon } from 'vue3-google-map'

const center = { lat: 24.886, lng: -70.268 }
const triangleCoords = [
  { lat: 25.774, lng: -80.19 },
  { lat: 18.466, lng: -66.118 },
  { lat: 32.321, lng: -64.757 },
  { lat: 25.774, lng: -80.19 },
]
const bermudaTriangle = {
  paths: triangleCoords,
  strokeColor: '#FF0000',
  strokeOpacity: 0.8,
  strokeWeight: 2,
  fillColor: '#FF0000',
  fillOpacity: 0.35,
}
</script>

<template>
  <GoogleMap
    api-key="YOUR_GOOGLE_MAPS_API_KEY"
    style="width: 100%; height: 500px"
    :center="center"
    :zoom="5"
  >
    <Polygon :options="bermudaTriangle" />
  </GoogleMap>
</template>
```

<ClientOnly>
  <GoogleMap
    :api-promise="apiPromise"
    style="width: 100%; height: 500px"
    :center="center"
    :zoom="5"
  >
    <Polygon :options="bermudaTriangle" />
  </GoogleMap>
</ClientOnly>

## Events

You can listen for [the following events](https://developers.google.com/maps/documentation/javascript/reference/polygon#Polygon-Events) on the `Polygon` component.
