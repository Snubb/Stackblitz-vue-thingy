<script setup>
import { ref } from 'vue';
import Map from './Map.vue';

var successpopup = false;
</script>

<template>
  <Map />
  <div id="dashboard">
    <div class="button-div">
      <va-button class="extra-button" round color="#394053"><span class="material-symbols-outlined button-icon">
          question_mark
        </span></va-button>
      <va-button class="extra-button material" round color="#394053"><span class="material-symbols-outlined button-icon">
          filter_list
        </span></va-button>
      <va-button class="extra-button" round color="#394053"><span class="material-symbols-outlined button-icon">
          format_list_bulleted
        </span></va-button>
      <va-button class="extra-button" round color="#394053"><span class="material-symbols-outlined button-icon">
          playlist_add
        </span></va-button>
      <va-button id="add-button" round color="#394053" @click="showCustomContent = !showCustomContent">
        <span style="font-size: 64px" class="material-symbols-outlined">
          add
        </span></va-button>
      <va-modal class="mission-modal" v-model="showCustomContent" no-padding :overlay="false">
        <template #content="{ ok }">
          <va-card-title> Select mission type </va-card-title>
          <va-card-content>
            <va-button class="mission-button" color="#FFF2D1" href="/booking">
              <p>Food</p>
            </va-button>
            <va-button class="mission-button" color="#FFE4D6">
              <p>Transport</p>
            </va-button>
            <va-button class="mission-button" color="#D7E4FF">
              <p>Taxi</p>
            </va-button>
          </va-card-content>
        </template>
      </va-modal>
    </div>
    <va-alert v-model="isCloseableAlertVisible" closeable class="mb-6" color="success" style="position: fixed; top: 0px;">
      Successfully booked mission
    </va-alert>
  </div>
</template>

<style scoped>
.mission-vodal {
  left: 6rem;
  bottom: 5rem;
}

.mission-button {
  display: block;
  width: 200px;
  margin-bottom: 0.5rem;
  text-align: center;
  align-items: center;
}

.button-div {
  position: fixed;
  left: 5rem;
  bottom: 5rem;
}

#add-button {
  font-size: large;
  display: block;
}

.extra-button {
  display: block;
  margin: 0 auto;
  margin-bottom: 1rem;
  text-align: center;
}

.button-icon {
  margin: 0 auto;
}
</style>
<script>
export default {
  data() {
    return {
      showCustomContent: false,
      isCloseableAlertVisible: true
    };
  },
};
</script>