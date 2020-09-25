<template>
  <h1>Veille techno</h1>
  <Form @add="saveTechno" />
  <br />
  <ul>
    <li v-for="tech in technos" :key="tech.id">{{tech.techno}}</li>
  </ul>
  {{technos.length}} techno{{technos.length > 1 ? 's' : ''}}
</template>

<script>
import { ref } from "vue";
import Form from "@/components/Form";
export default {
  name: "App",
  components: {
    Form,
  },
  setup() {
    let technos = ref([]);

    const saveTechno = function (data) {
      console.log("App / saveTechno()", data);
      // technos = [...technos, { techno: data, id: Date.now() }];
      technos.value.push({ techno: data, id: Date.now() });
      console.log("technos", technos);
    };

    return {
      saveTechno,
      technos,
    };
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

ul {
  list-style: none;
}
</style>
