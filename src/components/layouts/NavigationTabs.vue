<template>
  <base-card>
    <base-button
      @click="setSelectedTab('stored-resource')"
      :mode="storedResBtnMode"
      >Available Resources</base-button
    >
    <base-button @click="setSelectedTab('add-resource')" :mode="addResBtnMode"
      >Add Resource</base-button
    >
  </base-card>
  <component :is="selectedTab"></component>
</template>

<script>
import StoredResource from "../learning-resource/StoredResource.vue";
import AddResource from "../learning-resource/AddResource.vue";
export default {
  components: {
    StoredResource,
    AddResource,
  },
  data() {
    return {
      selectedTab: "stored-resource",
      storedResources: [
        {
          id: "vue-guide",
          title: "Vue 3 documentation",
          description: "The offical guide for vue.js",
          link: "https://vuejs.org",
        },
        {
          id: "google",
          title: "Google",
          description: "Learn how to google",
          link: "https://google.com",
        },
      ],
    };
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addResource(title, description, url) {
      const newResource = {
        id: new Date().toISOString(),
        title: title,
        description: description,
        link: url,
      };
      this.storedResources.unshift(newResource);
      this.selectedTab = "stored-resource";
    },
  },

  computed: {
    storedResBtnMode() {
      return this.selectedTab === "stored-resource" ? null : "flat";
    },
    addResBtnMode() {
      return this.selectedTab === "add-resource" ? null : "flat";
    },
  },
  provide() {
    return {
      resources: this.storedResources,
      addResource: this.addResource,
    };
  },
};
</script>

<style scoped></style>
