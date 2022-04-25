<template>
  <header>
   
  </header>
</template>

<script>

import axios from 'axios';

export default {
  //Cambiare il nome con quello del componente creato
  name: 'SerieComp',
  data(){
    return{
      //Creare un array dove salvare i data della chiamata axios
      //Modificare il nome a piacere
      avatarsArray: []
    }
  },
  created(){
    //Qui utiliziamo axios
    //Modificare il link con l'api che si vuole usare
    axios.get( 'https://api.themoviedb.org/3/movie/550?api_key=12a60b0a52be8853f488359f4a303575' )
         .then( ( res )=>{
           //Controllo delle informazioni che otteniamo alla chiamata
           console.log( res.data );
           //Modifica dell'array dove salveremo i dati
           this.avatarsArray = res.data
         } )
         //Salvataggio in console di possibili errori
         .catch( (error) => {
           console.log( error )
         } )
  }
}
</script>

<style scoped lang="scss">
 /*Inserire style componente*/
</style>