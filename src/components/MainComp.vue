<template>
   <main> 
     <FilmComp :propsArrayFilm2="propsArrayFilm"/>
     <SerieComp :propsArraySerie2="propsArraySerie"/>
     <CardComp/>
   </main>
</template>

<script>
import "bootstrap"
import FilmComp from './partials/FilmComp.vue'
import SerieComp from './partials/SerieComp.vue'
import CardComp from './partials/CardComp.vue'


export default {
  //Cambiare il nome con quello del componente creato
  name: 'MainComp',
  components: {
    FilmComp,
    SerieComp,
    CardComp
  },
  props: {
    //ricevere dati tramite props
    propsArrayFilm: Array,
    propsArraySerie: Array
  }
}
</script>

<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";
</style>
