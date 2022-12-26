<template>
  <the-header title="Learning  Resources"></the-header>
  <navigation-tabs></navigation-tabs>
</template>

<script>
import TheHeader from "./components/layouts/TheHeader.vue";
import NavigationTabs from "./components/layouts/NavigationTabs.vue";
export default {
  components: {
    TheHeader,
    NavigationTabs,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Abel&family=Dosis&display=swap");

* {
  box-sizing: border-box;
}

html {
  font-family: "Abel", sans-serif;
}

body {
  margin: 0;
}
</style>
