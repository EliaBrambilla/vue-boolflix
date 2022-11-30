<template>
    <main>
      <FilmsList :arrayFilm2="arrayFilm" />
      <SeriesList :arraySerie2="arraySerie" />
    </main>
  </template>
  
  <script>
  import FilmsList from './FilmsList.vue'
  import SeriesList from './SeriesList.vue'
  export default {
    name: 'MainComp',
    components: {
        FilmsList,
        SeriesList,
    },
    props: {
      arrayFilm: Array,
      arraySerie: Array,
    }
  }
  </script>
  
  <style lang="scss" scoped>
  * {
    background-color: #424242;
  }
  </style>
  Footer
  © 2022 GitHub, Inc.
  Footer navigation
  Terms
  Privacy
  Security
  Status
  Doc