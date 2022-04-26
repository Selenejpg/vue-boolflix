<template>
  <header class="d-flex p-3 flex-wrap justify-content-between">
    <div class="">
      <img class="logonetflix" src="../assets/Netflix_2015_logo.svg" alt=""> 
    </div>
    <div class="d-flex">
      <input type="text" class="w-90 me-2 form-control" placeholder="Username" aria-label="Username" aria-describedby="basic-addon1">
      <button type="button" class="btn btn-primary">Primary</button>
    </div>
  </header>
</template>

<script>
export default {
  //Cambiare il nome con quello del componente creato
  name: 'HeaderComp',
}
</script>

<style scoped lang="scss">
  .logonetflix{
    width: 100px;
  }
</style>