<template>
  <div class="row row-column text-center d-flex justify-content-center">
    <img :src="`https://image.tmdb.org/t/p/w342/${poster}`" alt="" class="poster">
    <span class="">{{title}}</span>
    <span class="">{{ogtitle}}</span>
    <div class="d-flex align-items-center justify-content-center">
      <span>Lingua: </span>
      <span class="flag ms-2" :class="(propsArrayFilm2.language == 'en') ? 'flag-en' : (propsArrayFilm2.language == 'it') ? 'flag-it' : 'flag-unknown' "></span>
    </div>
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
  },
  methods: {
    
  }
}
</script>

<style scoped lang="scss">
  .flag {
    height: 24px;
    width: 24px;
    background-size: contain;
    background-repeat: no-repeat;
    display: inline-block;
  }

  .flag-en {
    background-image: url(../../assets/GB-United-Kingdom-Flag-icon.png);
  }

  .flag-it {
    background-image: url(../../assets/italian_flag.png);
  }

  .flag-unknown {
    background-image: url(../../assets/globe.png);
  }

  .poster{
    width: 10%;
  }
</style>