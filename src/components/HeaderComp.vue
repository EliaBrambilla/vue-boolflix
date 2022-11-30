<template>
    <header class=" py-3 d-flex justify-content-around align-items-center">
      <div>
        <h2>BOOLFLIX</h2>
      </div>
  
      <div>
        <input type="text" v-model="textInput" @keyup.enter="$emit('search', textInput)" placeholder="Inserisci un titolo">
      </div>
    </header>
  </template>
  
  <script>
  export default {
      name: 'HeaderComp',
      data(){
        return{
          textInput: '',
        }
      }
  }
  </script>
  
  <style lang="scss" scoped>
    header{
      background-color: black;
      color: red;
      h2{
        margin: 1rem 0;
      }
    }
  </style>