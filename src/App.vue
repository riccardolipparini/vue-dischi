<template>
  <div id="app">
    <Selezione/>
    
  </div>
</template>

<script>
import Selezione from '@/components/Selezione.vue'


export default {
  name: 'App',
  components: {
    Selezione,
    
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
