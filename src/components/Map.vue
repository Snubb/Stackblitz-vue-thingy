<script setup>
import 'leaflet/dist/leaflet.css';
import L from 'leaflet';
import { ref } from 'vue';
</script>

<template>
  <div id="map"></div>
</template>

<style scoped>
#map {
  position: fixed;
  width: 100%;
  height: 100%;
  top: 0px;
  left: 0px;
  z-index: 0;
}
</style>
<script>
function loadMap() {
  var map = L.map('map', {
    center: [63.820926, 20.303753],
    zoom: 17,
    zoomControl: false,
  });
  L.control
    .zoom({
      position: 'bottomright',
    })
    .addTo(map);
  L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
    maxZoom: 19,
    attribution:
      '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>',
  }).addTo(map);

  var circle = L.circle([63.822353, 20.305281], {
    color: 'yellow',
    fillColor: '#fff64a',
    fillOpacity: 0.5,
    radius: 3
  }).addTo(map);
  circle.bindPopup("<div><span class='material-symbols-outlined'>local_pizza</span>Food mission<br></div>" +
                   "<div><span class='material-symbols-outlined'>not_listed_location</span>Nygatan 24<br></div>" +
                   "<div><span class='material-symbols-outlined'>person</span>0<br></div>" + 
                   "<div><span class='material-symbols-outlined'>directions_car</span>Name/ID of car<br></div>");
}

setTimeout(loadMap, 1);
</script>
