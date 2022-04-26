<template>
  <div class="">
    <img :src="poster" alt="" class="">
    <span class="">{{name}}</span>
    <span class="">{{ogname}}</span>
    <span class="">{{language}}</span>
    <span class="">{{vote}}</span>
  </div>
</template>

<script>
export default {
  //Cambiare il nome con quello del componente creato
  name: 'SerieComp',
  props: {
    //ricevere dati tramite props
    propsArraySerie2: Array,
    poster: String,
    name: String,
    ogname: String,
    language: String,
    vote: Number,
  }
}
</script>

<style scoped lang="scss">
 /*Inserire style componente*/
</style>