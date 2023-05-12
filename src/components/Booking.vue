<script setup>
import { ref } from 'vue';
</script>

<template>
  <div id="Booking">
    <div class="background-div"></div>
    <h1 class="va-h1">Enter your order:</h1>
    <div class="button-div">
      <va-button href="/dashboard" color="#394053" round><va-icon name="continue" /></va-button>
    </div>
    <div class="write-div">
      <div style="max-width: 300px">
        <va-input v-model="order" class="mb-6" placeholder="Enter food order" />
        <va-input
          v-model="pickup"
          class="mb-6"
          placeholder="Enter pickup location"
        />
        <va-input
          v-model="destination"
          class="mb-6"
          placeholder="Enter destination"
        />
      </div>
    </div>
    <div class="checkbox-div">
      <va-checkbox v-model="checked" :label="leftLabel" left-label />
    </div>
  </div>
</template>

<style scoped>
#id {
  z-index: 1;
}

.background-div {
  position: fixed;
  height: 70rem;
  width: 30rem;
  background-color: white;
  border-radius: 1rem;
  right: 3rem;
  top: 3rem;
}

.va-h1 {
  position: fixed;
  right: 6rem;
  top: 6rem;
}

.button-div {
  position: fixed;
  right: 5rem;
  bottom: 7rem;
}

.write-div {
  position: fixed;
  right: 9rem;
  top: 10rem;
}

.mb-6 {
  margin-top: 6rem;
  width: 100rem;
}
.checkbox-div {
  position: fixed;
  right: 17rem;
  top: 40rem;
}
</style>
<script>
export default {
  data() {
    return {
      value: '',
      order: '',
      pickup: '',
      destination: '',
      checked: false,
      leftLabel: 'Is this an emergency?',
    };
  },
};
</script>