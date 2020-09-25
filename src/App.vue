<template>
  <h1>Veille techno</h1>
  <Form @add="saveTechno" />
  <br />
  <TechnoList :technos="technos" />
</template>

<script>
import { ref } from "vue";
import Form from "@/components/Form";
import TechnoList from "@/components/Techno-List";
export default {
  name: "App",
  components: {
    Form,
    TechnoList,
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
