<template >
<div class="flip-card">
  <div class="width-img flip-card-inner">
    <div class="flip-card-front">
      <img :src="`https://image.tmdb.org/t/p/w342/${poster}`" alt="" class="dimensioni poster">
    </div>

    <div class="flip-card-back pt-2 p-2 overflow font-size">
      <div class="">Titolo: {{title}}</div>
      <div class="pt-2">Titolo originale: {{ogtitle}}</div>
      <div class="d-flex align-item-center justify-content-center mt-2">
        <span class="mt-1">Lingua: </span>
        <span class="flag ms-2" :class="(language == 'en') ? 'flag-en' : (propsArrayFilm2.language == 'it') ? 'flag-it' : 'flag-unknown' "></span>
      </div>

      <p class="card-text pt-2" id="star">
        {{propsArrayFilm2.vote}}
        <i
          v-for="i in 5"
          :key="i"
          class="fa-star"
          :class="(i <= stelline()) ? 'fa-solid' : 'fa-regular'"
        ></i>
      </p> 
      <div>Trama:</div>
      <span class="">{{overview}}</span>
    </div>  
  </div>
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
    overview: String
  },
  methods: {
    stelline(){
      const votoStelline = Math.ceil(this.vote) / 2
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
    width: 100%;
  }

  .width-img{
    max-width: 80% !important;
  }

  .font-size{
    font-size: 10px;
  }

  
  //flip card
  /* The flip card container - set the width and height to whatever you want. We have added the border property to demonstrate that the flip itself goes out of the box on hover (remove perspective if you don't want the 3D effect */
.flip-card {
  background-color: transparent;
  width: 220px;
  height: 320px;
  perspective: 1000px;
}

.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.6s;
  transform-style: preserve-3d;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
}

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
  margin-left: 45px;
}

.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}

.flip-card-front {
  background-color: #bbb;
  color: black;
}

.flip-card-back {
  background-color: rgba(0, 0, 0, 0.564);
  color: white;
  transform: rotateY(180deg);
  width: 205px;
}


.overflow{
  overflow-y: scroll;
  ::-webkit-scrollbar {
    display: none;
  }
}

.dimensioni{
  width: 220px;
  height: 320px;
}

</style>