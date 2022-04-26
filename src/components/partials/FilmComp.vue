<template>
  <div class="row row-column text-center">
    <img :src="poster" alt="" class="">
    <span class="">{{title}}</span>
    <span class="">{{ogtitle}}</span>
    <span class="">{{language}}</span>
    <span class="">{{vote}}</span>
  </div>
</template>

<script>
export default {
  //Cambiare il nome con quello del componente creato
  name: 'FilmComp',
  props: {
    //ricevere dati tramite props
    propsArrayFilm2: Array,
    poster: String,
    title: String,
    ogtitle: String,
    language: String,
    vote: Number,
  }
}
</script>

<style scoped lang="scss">
 /*Inserire style componente*/
</style>