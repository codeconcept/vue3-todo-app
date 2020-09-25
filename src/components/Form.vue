<template>
  <form @submit.prevent="addTechno">
    <label for="techno">Techno</label>
    <br />
    <input type="text" name="techno" v-model="techToLearn" />
    <br />
    <button type="submit">ajouter</button>
  </form>
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    let techToLearn = ref("");
    const addTechno = function () {
      console.log("techToLearn", techToLearn.value);
      techToLearn.value = "";
    };

    return {
      techToLearn,
      addTechno,
    };
  },
};
</script>

<style>
</style>