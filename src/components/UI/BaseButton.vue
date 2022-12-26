<template>
  <button :type="type" :class="mode">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: ["type", "mode"],
};
</script>

<style scoped>
button {
  padding: 0.75rem 1.5rem;
  background-color: #384f67;
  border-radius: 25px;
  border: none;
  color: white;
  font-family: "Dosis";
  font-weight: bold;
  cursor: pointer;
}

button:hover,
button:active {
  background-color: #34495e;
}

.flat {
  background-color: transparent;
  color: #e74c3c;
  border: none;
}

.flat:hover,
.flat:active {
  background-color: #bbd2ebb2;
  border-radius: 25px;
}
</style>
