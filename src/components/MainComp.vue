<template>
   <main> 
     <h1 class="text-center">Film</h1>
     <FilmComp :propsArrayFilm2="propsArrayFilm"
      v-for="( element, index ) in propsArrayFilm"
      :key="index"
      :poster="element.poster_path"
      :title="element.title"
      :ogtitle="element.original_title"
      :language="element.original_language"
      :vote="element.vote_average"/>

      <h1 class="text-center">Serie</h1>
     <SerieComp :propsArraySerie2="propsArraySerie"
      v-for="( subelement, subindex ) in propsArraySerie"
      :key="`A${subindex}`"
      :poster="subelement.poster_path"
      :name="subelement.name"
      :ogname="subelement.original_name"
      :language="subelement.original_language"
      :vote="subelement.vote_average"/>

     
   </main>
</template>

<script>
import "bootstrap"
import FilmComp from './partials/FilmComp.vue'
import SerieComp from './partials/SerieComp.vue'


export default {
  //Cambiare il nome con quello del componente creato
  name: 'MainComp',
  components: {
    FilmComp,
    SerieComp
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
