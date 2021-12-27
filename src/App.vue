<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <ul>
    <learning-resource></learning-resource>

  </ul>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import LearningResource from './components/Learning-Resources/LearningResource.vue'

export default {
  name: "App",
  data() {
    return {
      storedResources: [
        {
          id: "official-guide",
          title: "Official Guide",
          description: "The official VUe Js documentation",
          link: "https://vuejs.org",
        },
        {
          id: 'search-engine',
          title: 'Google',
          description: 'Learn how to search solution productively',
          link:'https://google.com'
        },
      ],
    };
  },
  components: {
    LearningResource
    // HelloWorld
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
