<template>
  <div id="app">
   <main> 
     <FilmComp/>
     <SerieComp/>
     <CardComp/>
   </main>
    
  </div>
</template>

<script>
import "bootstrap"
import FilmComp from './partials/FilmComp.vue'
import SerieComp from './partials/SerieComp.vue'
import CardComp from './partials/CardComp.vue'


export default {
  //Cambiare il nome con quello del componente creato
  name: 'App',
  components: {
    FilmComp,
    SerieComp,
    CardComp
  }
}
</script>

<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";
</style>
