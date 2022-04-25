<template>
  <header class="row">
    <div class="container">
      <div class="row row-cols-5">
        <div class="" v-for="(element, index) in film" :key="index">
          <div class="">
            <img  class="img-fluid" :src="element.poster_path" alt="">
            <h3 class="">{{element.title}}</h3>
            <h4 class="">{{element.original_title}}</h4>
            <h4 class="">{{element.overview}}</h4>
            <h4 class="">{{element.language}}</h4>
            <h4 class="">{{element.vote_average}}</h4>
          </div>                
        </div>
      </div> 
    </div> 
  </header>
</template>

<script>

import axios from 'axios';

export default {
  name: 'FilmComp',
  data(){
    return{
      film: []
    }
  },
  created(){
    axios.get( 'https://api.themoviedb.org/3/search/movie?api_key=12a60b0a52be8853f488359f4a303575&language=it-IT&page=1&include_adult=false&query=l' )
          .then( ( res )=>{
            this.film = res.data
            console.log(res.data)
         } )
  }
}
</script>

<style scoped lang="scss">
 /*Inserire style componente*/
</style>