<template>
  <header>
    <h2>{{ title }}</h2>
  </header>
</template>

<script>
export default {
  props: ["title"],
};
</script>

<style scoped>
header {
  width: 100%;
  height: 4rem;
  background-color: #34495e;
  display: flex;
  justify-content: center;
  align-items: center;
}

header h2 {
  color: white;
  margin: 0;
  font-family: "Dosis";
}
</style>
