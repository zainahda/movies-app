<template>
  <div class="movieApp">
    <List />
  </div>
</template>

<script>
    import List from './List.vue';
    export default {
        name: 'Movie',
        components: {
            List
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.movieApp {
  margin-top: 10px;
}
</style>
