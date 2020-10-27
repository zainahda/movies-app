<template>
  <div id="app">
    <Search />
    <Movie />
    
  </div>
</template>

<script>
import Search from './components/Search.vue'
import Movie from './components/Movie.vue'

export default {
  name: 'App',
  components: {
    Movie,
    Search,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
