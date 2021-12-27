<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <the-header title='V-Learning Hub' />
  <TheResources />
</template>

<script>
import TheHeader from './components/layouts/TheHeader.vue';
import TheResources from './components/Learning-Resources/TheResources.vue';
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: "App",
  data() {
    return {
     
    };
  },
  components: {
    TheHeader,
    TheResources,
    // HelloWorld
  },
};
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */

@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>
