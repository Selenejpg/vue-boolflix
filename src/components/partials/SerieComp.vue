<template>
  <div class="row row-column text-center">
    <div class=" d-flex justify-content-center">
      <img :src="`https://image.tmdb.org/t/p/w342/${poster}`" alt="" class="poster">
    </div>

    <div class="d-flex flex-column justify-content-center">
      <span class="">{{name}}</span>
      <span class="">{{ogname}}</span>
      <div class="d-flex align-items-center justify-content-center">
        <span>Lingua: </span>
        <span class="flag ms-2" :class="(language == 'en') ? 'flag-en' : (language == 'it') ? 'flag-it' : 'flag-unknown' "></span>
      </div>

      <p class="card-text" id="star">
        {{propsArraySerie2.vote}}
        <i
          v-for="i in 5"
          :key="i"
          class="fa-star"
          :class="(i = stelline()) ? 'fa-solid' : 'fa-regular'"
        ></i>
      </p> 
      
      <span class="">{{overview}}</span>
    </div>
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
    overview: String
   
  },
  methods: {
    stelline(){
      const votoStelline = Math.ceil(this.vote)
      return votoStelline
    }
    
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