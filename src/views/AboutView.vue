<script>
/* global mapboxgl*/

export default {
  // data: function () {
  //   return {
  //     places: [
  //       { lat: -25.363, lng: 131.044, description: "A place in Australia" },
  //       { lat: -33.8675, lng: 151.207, description: "The main city!" },
  //     ],
  //   };
  // },
  mounted: function () {
    mapboxgl.accessToken = process.env.VUE_APP_MAPBOX_API_KEY;
    const map = new mapboxgl.Map({
      container: "map", // container ID
      style: "mapbox://styles/mapbox/streets-v11", // style URL
      center: [-69.0648, 44.2098], // starting position [lng, lat]
      zoom: 9, // starting zoom
    });
    // Create a default Marker and add it to the map.
    const marker1 = new mapboxgl.Marker().setLngLat([-69.0648, 44.2098]).addTo(map);
    // create the popup
    const popup = new mapboxgl.Popup({ offset: 25 }).setText("Welcome to Camden, Maine!");
    console.log(map, marker1, popup);
  },
};
</script>
<template>
  <div class="about">
    <h1>This is an about page</h1>
    <p>MAP</p>
    <div id="map"></div>
  </div>
</template>
<style>
body {
  margin: 0;
  padding: 0;
}
#map {
  /* position: absolute; */
  /* top: 0; */
  /* bottom: 0; */
  height: 300px;
  width: 100%;
}
#marker {
  background-image: url("https://media.istockphoto.com/photos/view-from-mount-battie-overlooking-camden-harbor-maine-picture-id1176662480?k=20&m=1176662480&s=612x612&w=0&h=mJRo1s7-WO3LSFLc6oa0qRkiavW3TAAPi2k-afbpvyU=");
  background-size: cover;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  cursor: pointer;
}

.mapboxgl-popup {
  max-width: 200px;
}
</style>
