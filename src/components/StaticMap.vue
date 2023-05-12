<script setup>
import 'leaflet/dist/leaflet.css';
import L from 'leaflet';
import { ref } from 'vue';
</script>

<template>
  <div id="loginMap"></div>
 
</template>

<style scoped>
#loginMap {

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
  var loginMap = L.map('loginMap', {
    center: [63.820926, 20.303753],
    zoom: 17,
    zoomControl: false,
    dragging: false,
    minZoom: 17,
    maxZoom:17,
  });
  

 
  L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
    maxZoom: 19,
    attribution:
      '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>',
  }).addTo(loginMap);
}

setTimeout(loadMap, 1);
</script>