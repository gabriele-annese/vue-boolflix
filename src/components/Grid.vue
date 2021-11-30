<template>
    <section>
        <div class="box-movies"  v-if = "moviesArray !== null">
            <div v-for="(elMovies, index) in moviesArray" :key="`elMovies-${index}`" >
                <div class="imgMovie" >
                     <img :src="`https://image.tmdb.org/t/p/${Imgsize}${elMovies.poster_path} `" :alt="elMovies.title">
                </div>
                <Card 
                :title="elMovies.title"
                :originalTitle="elMovies.original_title"
                :language="elMovies.original_language"
                :text="elMovies.vote_average"
                />
            </div>
        </div>
         <div class="box-tv"  v-if = "tvArray !== null">
            <div v-for="(elTv, index) in tvArray" :key="`elTv-${index}`" >
             <div class="imgMovie" >
                     <img :src="`https://image.tmdb.org/t/p/${Imgsize}${elTv.poster_path} `" :alt="elTv.name">
                </div>
                <CardTv class="card"
                :title="elTv.name"
                :originalTitle="elTv.original_name"
                :language="elTv.original_language"
                :text="elTv.vote_average"
                />
            </div>
        </div>
        <Loader v-else/>
    </section>
</template>

<script>
import Card from './Card.vue'
import Loader from './Loader.vue'
import CardTv from './CardTv.vue'
export default {
  components: { Card, Loader, CardTv },
name: 'Grid',
props:{
    moviesArray: Array,
    tvArray: Array,
},
data(){
    return{
        Imgsize:'w185'
    }
},
}
</script>

<style lang="scss" scoped>

.imgMovie{
    margin-top: 20px;
}
</style>