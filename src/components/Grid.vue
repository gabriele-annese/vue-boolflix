<template>
    <section>
        <div class="list-movies"  v-if = "moviesArray !== null">
            <div v-for="(elMovies, index) in moviesArray" :key="`elMovies-${index}`" >
                <Card 
                :title="elMovies.title"
                :originalTitle="elMovies.original_title"
                :language="elMovies.original_language"
                :text="elMovies.vote_average"
                />
            </div>
        </div>
         <div class="list-tv"  v-if = "tvArray !== null">
            <div v-for="(elTv, index) in tvArray" :key="`elTv-${index}`" >
                <CardTv 
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
}
}
</script>

<style lang="scss" scoped>

</style>