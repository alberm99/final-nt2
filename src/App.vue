<template>
  <div id="app" class="container-fluid mt-3">
    <div>
      
      <h1>Final NT2</h1>
      <hr>

      <Texto />
      
    </div>
  </div>
</template>

<script>
import Texto from './components/Texto.vue'







export default {
  name: 'App',
  components: {
    Texto
  }
}
</script>

<style>
#app {
 
}

h1{
  color: blue
}
</style>
