<template>
  <ul>
    <learning-resource
      v-for="res in allResources"
      :key="res.id"
      :idFor="res.id"
      :titleFor="res.title"
      :descriptionFor="res.description"
      :linkFor="res.link"
    />
  </ul>
</template>

<script>
import LearningResource from "./LearningResource.vue";
export default {
  inject: ["allResources"],
  components: {
    LearningResource,
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>