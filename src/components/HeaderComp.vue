<template>
  <header class="d-flex p-4 bg-black flex-wrap justify-content-between">
    <div class="">
      <img class="pt-2 logonetflix" src="../assets/Netflix_2015_logo.svg" alt=""> 
    </div>
    <div class="d-flex">

      <input
      type="text" class="me-2 pt-2 form-control" placeholder="Cerca film e serie" aria-label="Username" aria-describedby="basic-addon1"
        v-model="testoCercato"
        @keydown.enter="$emit('search', testoCercato)">

      <button type="button" class="pt-2 btn btn-primary"
        @click="$emit('search', testoCercato)">Cerca</button>

    </div>
  </header>
</template>

<script>
export default {
  //Cambiare il nome con quello del componente creato
  name: 'HeaderComp',
  data() {
    return {
      testoCercato: ''
    };
  }
}
</script>

<style scoped lang="scss">
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  header {
    padding: 40px;
  }

  .logonetflix{
    width: 100px;
  }

  .bg-black{
    background-color: #1b1b1b;
  }

  .btn {
    background-color: rgb(209, 45, 45);
    border: rgb(209, 45, 45);
  }

</style>