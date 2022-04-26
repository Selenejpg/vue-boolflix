<template>
  <div id="app">
    <header>
      <HeaderComp/>
      <MainComp/>
    </header>
  </div>
</template>

<script>
import "bootstrap"
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'

export default {
  //Cambiare il nome con quello del componente creato
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  }
}
</script>

<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";
</style>
