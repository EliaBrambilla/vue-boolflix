<template>
    <div>
      <div class="card">
        <img :src="`http://image.tmdb.org/t/p/w342/${singleSerie.poster_path}`" alt="">
        <div class="titles">
          <p>Titolo: {{singleSerie.name}}</p>
          <p>Titolo Originale: {{singleSerie.original_name}}</p>
          <img v-if="flags.includes(singleSerie.original_language)" :src="require(`../assets/${singleSerie.original_language}.svg`)" class="flag">
          <p v-else>Lingua Originale: {{singleSerie.original_language.toUpperCase()}}</p>
          <div class="d-flex">
              <p class="me-2">Voto: {{ singleSerie.vote_average }}/10</p>
              
              <div v-for="x in stellaPiena" :key="'b' + x">
                <font-awesome-icon icon="fa-solid fa-star" class="gold" />
              </div>
              <div v-if="mezzaStella == true">
                <font-awesome-icon
                  icon="fa-solid fa-star-half-stroke"
                  class="gold"
                />
              </div>
              <div v-for="x in stellaVuota" :key="'a' + x">
                <font-awesome-icon icon="fa-regular fa-star" class="gold" />
              </div>
            </div>
          <p>Overview: {{singleSerie.overview}}</p>
        </div>
  
      </div>
    </div>
  </template>
  
  <script>
    export default {
      name: 'CardSerie',
      props: {
        singleSerie: Object,
      },
      data(){
        return {
          flags: ["it", "en", "fr", "de", "es", "ja", "pt"],
          mezzoVoto: "0",
          stellaPiena: "0",
          stellaVuota: "0",
          mezzaStella: false,
        };
      },
      methods: {
        starsRating() {
          this.mezzoVoto = this.singleSerie.vote_average / "2";
          if (this.mezzoVoto != Math.floor(this.mezzoVoto)) {
            this.mezzaStella = true;
            this.stellaPiena = Math.floor(this.mezzoVoto);
            this.stellaVuota = "5" - this.stellaPiena - "1";
          } else {
            this.stellaPiena = this.mezzoVoto;
            this.stellaVuota = "5" - this.stellaPiena;
          }
        },
      },
      mounted() {
        this.starsRating();
      }
    }
  </script>
  
  <style lang="scss" scoped>
  .card{
    position: relative;
  }
  .titles{
    display: none;
    h4{
      display: inline;
    }
    .flag{
      width: 3rem;
      margin: 1rem 0;
    }
  }
  .card:hover .titles{
    padding: 2rem 1rem 0;
    width: 100%;
    height: 100%;
    background-color: black;
    color: white;
    opacity: 0.9;
    position: absolute;
    display: inline;
    overflow: auto;
    cursor: pointer;
  }
  .gold {
    color: gold;
  }
  </style>