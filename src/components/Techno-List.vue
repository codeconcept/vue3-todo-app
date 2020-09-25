<template>
  <h3>Toutes les technos à veiller</h3>
  {{technos.length}} techno{{technos.length > 1 ? 's' : ''}}
  <ul>
    <li v-for="tech in technos" :key="tech.id">
      <button @click="deleteTechno(tech)">x</button>
      {{tech.techno}}
    </li>
  </ul>
</template>

<script>
export default {
  emits: ["delete-techno"],
  setup(props, { emit }) {
    let deleteTechno = function (tech) {
      emit("delete-techno", tech);
    };

    return {
      deleteTechno,
    };
  },
  props: {
    technos: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style>
ul {
  text-align: left;
  width: 50%;
  margin-left: 100px;
}

</style>