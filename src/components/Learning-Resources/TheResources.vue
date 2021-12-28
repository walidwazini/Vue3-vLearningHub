<template>
  <base-card>
    <base-button
      @click="setSelectedTab('stored-resources')"
      :mode="storedResButtonMode"
      >Stored Resources</base-button
    >
    <base-button
      @click="setSelectedTab('add-resource')"
      :mode="addResButtonMode"
      >Add Resource</base-button
    >
  </base-card>
  <keep-alive>
    <component :is="selectedTab"></component>
  </keep-alive>
</template>

<script>
import StoredResources from "./StoredResources.vue";
import AddResource from "./AddResource.vue";
// import BaseButton from '../UI/BaseButton.vue';

export default {
  components: {
    StoredResources,
    AddResource,
  },
  data() {
    return {
      selectedTab: "stored-resources",
      storedResources: [
        {
          id: "official-guide",
          title: "Official Guide",
          description: "The official VUe Js documentation",
          link: "https://vuejs.org",
        },
        {
          id: "search-engine",
          title: "Google",
          description: "Learn how to search solution productively",
          link: "https://google.com",
        },
      ],
    };
  },
  provide() {
    return {
      allResources: this.storedResources,
      // Provide key of the function to another component
      addResourceKey: this.addResource,
      deleteResourceKey: this.removeResource
    };
  },
  computed: {
    storedResButtonMode() {
      return this.selectedTab === "stored-resources" ? null : "flat";
    },
    addResButtonMode() {
      return this.selectedTab === "add-resource" ? null : "flat";
    },
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addResource(titleAdd, descriptionAdd, urlAdd) {
      const newResource = {
        id: new Date().toISOString(),
        title: titleAdd,
        description: descriptionAdd,
        link: urlAdd,
      };
      this.storedResources.unshift(newResource);
      this.selectedTab = "stored-resources";
      console.log("the resources ar");
    },
    removeResource(resId){
      const resIndex = this.storedResources.findIndex(res => res.id === resId)

      this.storedResources.splice(resIndex, 1)
    }
  },
};
</script>

<style>
</style>