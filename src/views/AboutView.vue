<script>
/* global mapboxgl*/

export default {
  mounted: function () {
    mapboxgl.accessToken = process.env.VUE_APP_MAPBOX_API_KEY;
    const map = new mapboxgl.Map({
      container: "map", // container ID
      style: "mapbox://styles/mapbox/streets-v11", // style URL
      center: [-69.0648, 44.2098], // starting position [lng, lat]
      zoom: 9, // starting zoom
    });
    console.log(map);
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
</style>
