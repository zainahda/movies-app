<template>
    <div class="search">
        <nav class="navbar navbar-dark bg-dark">
        <a class="navbar-brand">Movies App</a>
        <form class="form-inline justify-content-center">
        <input class="form-control mr-sm-2" type="search" v-model="search" placeholder="Search Movie" aria-label="Search"/>
        <button class="btn btn-outline-success my-2 my-sm-0" v-on:click="searchMovies">Search</button>
        </form>
        </nav>
    </div>
</template>

<script>
export default {
    name: 'Search',
    data(){
        return{
            search:''
        }
    },
    created(){
        this.$store.dispacth('searchMovie')
    },
    computed:{
        movie(){
            return this.$store.state.movies
        }
    },
    methods:{
        searchBtn: function(){
            this.$store.dispacth('searchMovie', this.search)
        }
    }
}
</script>

<style>

</style>