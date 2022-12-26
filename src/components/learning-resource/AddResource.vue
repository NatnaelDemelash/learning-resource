<template>
  <base-card>
    <h3>Add New Resource</h3>
    <form @submit.prevent="submitData">
      <div class="form-control">
        <label for="title">Title</label>
        <input id="title" name="title" type="text" ref="titleInput" />
      </div>
      <div class="form-control">
        <label for="description">Description</label>
        <textarea
          id="description"
          name="description"
          rows="3"
          ref="descInput"
        ></textarea>
      </div>
      <div class="form-control">
        <label for="link">Link</label>
        <input id="link" name="link" type="url" ref="linkInput" />
      </div>
    </form>
    <base-button type="submit" @click="addResource">Add Resource</base-button>
  </base-card>
</template>

<script>
import BaseButton from "../UI/BaseButton.vue";
export default {
  inject: ["addResource"],

  methods: {
    submitData() {
      const enteredTitle = this.$refs.titleInput.value;
      const enteredDesc = this.$refs.descInput.value;
      const enteredurl = this.$refs.linkInput.value;

      this.addResource(enteredTitle, enteredDesc, enteredurl);
    },
  },
};
</script>

<style scoped>
h3 {
  text-align: center;
  font-family: "Dosis";
}

label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}

.form-control {
  margin: 1rem 0;
}
</style>
