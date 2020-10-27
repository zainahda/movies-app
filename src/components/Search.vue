<template>
    <div class="search">
        <nav class="navbar navbar-dark bg-dark">
        <a class="navbar-brand">Zain Movies App</a>
        <form class="form-inline justify-content-center">
        <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search"/>
        <button class="btn btn-outline-success my-2 my-sm-0" @click="searchMovies">Search</button>
        </form>
        </nav>
    </div>
</template>

<script>
export default {
    name: 'Search',
    methods:{
        searchMovies(){
            
        }
    }
}
</script>

<style>

</style>