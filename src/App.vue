<template>
  <div id="app">
    <header>
      <HeaderComp/>
    </header>
   <main>
     <MainComp/>
     <FilmComp/>
     <SerieComp/>
     <CardComp/>
   </main>
    
  </div>
</template>

<script>
import "bootstrap"
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'
import FilmComp from './components/FilmComp.vue'
import SerieComp from './components/SerieComp.vue'
import CardComp from './components/CardComp.vue'


export default {
  //Cambiare il nome con quello del componente creato
  name: 'AvatarsComp',
  components: {
    HeaderComp,
    FilmComp,
    SerieComp,
    MainComp,
    CardComp
  }
}
</script>

<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";
</style>
