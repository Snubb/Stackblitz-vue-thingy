<script setup>
import { ref } from 'vue';
import StaticMap from './StaticMap.vue';
</script>

<template>
  <StaticMap/>
  <div id="login">
    <h1 id="title">Login</h1>
   
    <div id="form">
        <va-form
    tag="form"
    @submit.prevent="handleSubmit"
  >
    <va-input
      style="margin-bottom: 20px;"
      color="#394053"
      v-model="username"
      label="Username"
    />

    <va-input
      style="margin-bottom: 40px;"
      color="#394053"
      v-model="password"
      class="mt-3"
      type="password"
      label="Password"
    />


    <va-button id="loginButton"
      color="#394053"
      type="submit"
      class="mt-3"
      href="/dashboard"
    >
      Login
    </va-button>
  </va-form>
  </div>

  
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: "",
      password: "",
      value: "",
      options: ["admin", "user"],
    };
  },
  methods: {
    handleSubmit() {
      alert("-- form submit --");
    },
  },
};
</script>

<style scoped>
#login {
  position: relative;
  background-color: white;
  width: 500px;
  height: 580px;
  z-index: 1;
  border-radius: 12px;

}

#title {
    font-size: 22px;

    position: relative;
    top: 8%; /* Adjust the value to position the element from the top */
    right: -10%; /* Adjust the value to position the element from the left */
}

#form {
    position: relative;
    max-width: 250px;
    margin-top: 25%;
    margin-left: 25%;
}

#form va-input {
  margin-bottom: 20px; /* Adjust the value to control the vertical spacing between the elements */
}

#loginButton {
    margin-left: 50%;
    
}


</style>
