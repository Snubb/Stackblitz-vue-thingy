<script setup>
import 'leaflet/dist/leaflet.css';
import L from 'leaflet';
import { ref } from 'vue';

defineProps({
  msg: String,
});

const count = ref(0);
</script>
<template>
  <p>TEST DASHBOARD</p>
  <h1>{{ msg }}</h1>
  <div id="map"></div>
  <input type="button" value="TEST" onclick="test()" style="width: 200px" />
</template>

<style scoped>
#map {
  position: fixed;
  width: 100%;
  height: 100%;
  top: 0px;
  left: 0px;
  z-index: -1;
}
</style>
<script>
console.log('soontm');
/*setTimeout(test, 1);*/

function test2() {
  console.log(':DDD');
}

function test() {
  console.log('Attempting to set map');
  var map = L.map('map').setView([63.820926, 20.303753], 18);
  L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
    maxZoom: 19,
    attribution:
      '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>',
  }).addTo(map);
}

setTimeout(test, 1);
</script>
