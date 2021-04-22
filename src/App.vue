<template>
  <div id="app">
    <login-component/>
  </div>
</template>

<script>
import LoginComponent from './components/LoginComponent.vue';
export default {
  components: { LoginComponent },
 
  name: "app",
  data() {
    return {
      msg: "Welcome to Your Vue.js App",
    };
  },
};
</script>
