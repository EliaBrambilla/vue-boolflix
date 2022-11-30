<template>
    <div>
      <h1>Lista di Serie:</h1>
      <div class="d-flex overflow-auto">
        <CardSerie
          v-for="(elem, index) in arraySerie2"
          :key="index"
          :singleSerie="elem"
        />
      </div>
    </div>
  </template>
  
  <script>
  import CardSerie from "./CardSerie.vue";
  export default {
    name: "SeriesList",
    components: {
      CardSerie,
    },
    props: {
      arraySerie2: Array,
    },
  };
  </script>
  
  <style lang="scss" scoped>
  h1 {
    padding: 1.5rem 1rem;
    color: #E7EEF1;
  }
  </style>