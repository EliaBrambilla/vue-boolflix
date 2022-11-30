<template>
    <div>
      <h1>Lista di Film:</h1>
      <div class="d-flex overflow-auto">
        <CardFilm
          v-for="(elem, index) in arrayFilm2"
          :key="index"
          :singleFilm="elem"
        />
      </div>
    </div>
  </template>
  
  <script>
  import CardFilm from "./CardFilm.vue";
  export default {
    name: "FilmsList",
    components: {
      CardFilm,
    },
    props: {
      arrayFilm2: Array,
    },
  };
  </script>
  
  <style lang="scss" scoped>
  h1 {
    padding: 1.5rem 1rem;
    color: #E7EEF1;
  }
  .overf-x{
    overflow-x: scroll;
  }
  </style>