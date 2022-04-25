<template>
  <header class="row">
    <div class="container">
      <div class="row row-cols-5">
        <div class="" v-for="(element, index) in serie" :key="index">
          <div class="">
            <img  class="img-fluid" :src="element.backdrop_path" alt="">
            <h3 class="">{{element.name}}</h3>
            <h4 class="">{{element.original_name}}</h4>
            <h4 class="">{{element.overview}}</h4>
            <h4 class="">{{element.original_language}}</h4>
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
  name: 'SerieComp',
  data(){
    return{
      serie: []
    }
  },
  created(){
    axios.get( 'https://api.themoviedb.org/3/search/tv?api_key=12a60b0a52be8853f488359f4a303575&language=it-IT&page=1&include_adult=false&query=s' )
         .then( ( res )=>{
            this.serie = res.data
            console.log(res.data)
         } )
  }
}
</script>

<style scoped lang="scss">
 /*Inserire style componente*/

</style>