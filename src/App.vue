<template>
  <div id="app">
    <header>
      <HeaderComp/>
      <MainComp :propsArrayFilm="film" :propsArraySerie="serie"/>
    </header>
  </div>
</template>

<script>
import "bootstrap"
import axios from 'axios';
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'

export default {
  //Cambiare il nome con quello del componente creato
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  },
  data(){
    return{
      film: [],
      serie: [],
    }
  },
  created(){
    //Chiamata API film e serie tramite axios in App vue
    axios.get( 'https://api.themoviedb.org/3/search/movie?api_key=12a60b0a52be8853f488359f4a303575&language=it-IT&page=1&include_adult=false&query=star' )
         .then( ( res )=>{
           console.log( res.data.results );
           this.film = res.data.results
         } )
         .catch( (error) => {
           console.log( error )
         } )

    axios.get( 'https://api.themoviedb.org/3/search/tv?api_key=12a60b0a52be8853f488359f4a303575&language=it-IT&page=1&include_adult=false&query=love' )
         .then( ( res )=>{
           console.log( res.data.results );
           this.serie = res.data.results
         } )
         .catch( (error) => {
           console.log( error )
         } )
  }
}
</script>

<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";
</style>
