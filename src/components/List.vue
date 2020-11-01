<template>
<div class="container">
    <div class="movielist">
        <div class="movie-wrap" v-if="movie.results">
            <div class="row row-cols-lg-5 ml-auto">
            <div class="card-movie col" style= "width: 10rem;"  v-for="item in movie.results" :key="item.id">
                <img :src="`https://image.tmdb.org/t/p/w500${item.poster_path}`" :alt="movie.original_title" />
                <a href="#" class="btn btn-primary ">Play
                    <svg width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-play" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd" d="M10.804 8L5 4.633v6.734L10.804 8zm.792-.696a.802.802 0 0 1 0 1.392l-6.363 3.692C4.713 12.69 4 12.345 4 11.692V4.308c0-.653.713-.998 1.233-.696l6.363 3.692z"/>
                    </svg>
                </a>
                <div class="card-body">
                <h4 class="card-title text-info justify-content-center">{{ item.original_title }}</h4>
                <p class="rating justify-content-center">Rating 
                    <svg width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-star-fill" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
                    <path d="M3.612 15.443c-.386.198-.824-.149-.746-.592l.83-4.73L.173 6.765c-.329-.314-.158-.888.283-.95l4.898-.696L7.538.792c.197-.39.73-.39.927 0l2.184 4.327 4.898.696c.441.062.612.636.283.95l-3.523 3.356.83 4.73c.078.443-.36.79-.746.592L8 13.187l-4.389 2.256z"/>
                    </svg>
                    {{ item.vote_average }}</p>
                <!-- <p class="card-text">{{ item.overview }}</p> -->
                <!-- <div> -->
                    <!-- <span v-if="!readMoreActivated">{{item.overview.slice(0, 200)}}</span>
                        <a class="readmore" v-if="!readMoreActivated" @click="activateReadMore" href="#">
                        read more...
                    </a>
                    <span v-if="readMoreActivated" v-html="item.overview"></span> -->
                <!-- </div> -->
                </div>
                
            </div>
        </div>
        </div>
        <div v-else>Data Kosong</div>
    </div>
</div>
</template>

<script>
export default {
    name: 'List',
    computed: {
        movie() {
            return this.$store.state.movies
        }
    },
    created(){
        this.$store.dispatch('fetchMovie')
    },
}
</script>

<style>
.card-movie {
    width: 50px;
    box-shadow: 0 2px 5px 0 rgba(0, 0, 0, .16), 0 2px 10px 0 rgba(0, 0, 0, .12);
    margin: 5px 5px 5px 5px;
    
}
.card-text {
    text-align: justify;
}
.card-title {
    font-size: 20px;
}
.card-body {
    display: block;
}

img {
    margin-top: 10px;
    width: 150px;
    height: 250px;
    
}
.btn {
    padding: 10px;
    margin-top: 10px;
}
.btn:active {
    box-shadow: none;
    position: relative;
    top: 2px;
}
.rating {
    margin-top: 15px;
}
.rating svg {
    color: orange;
}
</style>